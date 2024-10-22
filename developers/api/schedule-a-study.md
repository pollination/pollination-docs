# Schedule a Study on Pollination

This page shows an example code for creating a single study with multiple runs on Pollination using the Pollination API. It also includes a function that waits for the study to finish and downloads the results.

This code was originally posted on Discourse in response to this topic. You can download the sample files from Discourse.

{% embed url="https://discourse.pollination.solutions/t/how-to-submit-an-energy-simulation-to-pollination-using-the-api/2753/9" %}

Here is the study that is submitted to Pollination using the sample code:

{% embed url="https://app.pollination.solutions/mostapha/projects/agent-based-energy-simulation/studies/bd4a3192-50a8-43ad-a09d-b02cf9f0b172?tab=details&perPage=5&status=null&page=1" %}

```python
"""
Sample code for using the API to submit several HBJSON files from a folder to
Pollination, and download the results when ready.
"""
import pathlib
import time
import requests
from requests.exceptions import HTTPError
import zipfile
import tempfile
import shutil

from typing import List

from pollination_io.api.client import ApiClient
from pollination_io.interactors import NewJob, Recipe, Job
from queenbee.job.job import JobStatusEnum


def submit_study(
    study_name: str, api_client: ApiClient, owner: str, project: str, epw: pathlib.Path,
        ddy: pathlib.Path, models_folder: pathlib.Path) -> Job:

    print(f'Creating a new study: {study_name}')
    # Assumption: the recipe has been already added to the project manually
    recipe = Recipe('ladybug-tools', 'annual-energy-use', '0.5.7', client=api_client)

    input_folder = pathlib.Path(models_folder)

    # create a new study
    new_study = NewJob(owner, project, recipe, client=api_client)
    new_study.name = study_name
    new_study.description = f'Annual Energy Simulation {input_folder.name}'

    # upload the weather files - you only need to upload them once, and you can use
    # the path to them directly
    assert epw.is_file(), f'{epw} is not a valid file path.'
    assert ddy.is_file(), f'{ddy} is not a valid file path.'

    epw_path = new_study.upload_artifact(epw, target_folder='weather-data')
    ddy_path = new_study.upload_artifact(ddy, target_folder='weather-data')

    recipe_inputs = {
        'epw': epw_path,
        'ddy': ddy_path
    }

    study_inputs = []
    for model in input_folder.glob('*.hbjson'):
        inputs = dict(recipe_inputs)  # create a copy of the recipe
        # upload this model to the project
        print(f'Uploading model: {model.name}')
        uploaded_path = new_study.upload_artifact(model, target_folder=input_folder.name)
        inputs['model'] = uploaded_path
        inputs['model_id'] = model.stem  # use model name as the ID.
        study_inputs.append(inputs)

    # add the inputs to the study
    # each set of inputs creates a new run
    new_study.arguments = study_inputs

    # # create the study
    running_study = new_study.create()

    job_url = f'https://app.pollination.solutions/{running_study.owner}/projects/{running_study.project}/jobs/{running_study.id}'
    print(job_url)
    time.sleep(5)
    return running_study


def check_study_status(study: Job):
    """"""
    status = study.status.status
    http_errors = 0
    while True:
        status_info = study.status
        print('\t# ------------------ #')
        print(f'\t# pending runs: {status_info.runs_pending}')
        print(f'\t# running runs: {status_info.runs_running}')
        print(f'\t# failed runs: {status_info.runs_failed}')
        print(f'\t# completed runs: {status_info.runs_completed}')
        if status in [
            JobStatusEnum.pre_processing, JobStatusEnum.running, JobStatusEnum.created,
            JobStatusEnum.unknown
        ]:
            time.sleep(15)
            try:
                study.refresh()
            except HTTPError as e:
                status_code = e.response.status_code
                print(str(e))
                if status_code == 500:
                    http_errors += 1
                    if http_errors > 3:
                        # failed for than 3 times with no success
                        raise HTTPError(e)
                    # wait for additional 15 seconds
                    time.sleep(10)
            else:
                http_errors = 0
                status = status_info.status
        else:
            # study is finished
            time.sleep(2)
            break


def _download_results(
    owner: str, project: str, study_id: int, download_folder: pathlib.Path,
    api_client: ApiClient, page: int = 1
        ):
    print(f'Downloading page {page}')
    per_page = 25
    url = f'https://api.pollination.solutions/projects/{owner}/{project}/runs'
    params = {
        'job_id': study_id,
        'status': 'Succeeded',
        'page': page,
        'per-page': per_page
    }
    response = requests.get(url, params=params, headers=api_client.headers)
    response_dict = response.json()
    runs = response_dict['resources']
    temp_dir = tempfile.TemporaryDirectory()
    # with tempfile.TemporaryDirectory() as temp_dir:
    if temp_dir:
        temp_folder = pathlib.Path(temp_dir.name)
        for run in runs:
            run_id = run['id']
            # the model-id is hardcoded in submit_study. This is not necessarily good
            # practice and makes the code to only be useful for this example.
            input_id = [
                inp['value']
                for inp in run['status']['inputs'] if inp['name'] == 'model_id'
            ][0]
            run_folder = temp_folder.joinpath(input_id)
            eui_file = run_folder.joinpath('eui.json')
            out_file = download_folder.joinpath(f'{input_id}.json')
            print(f'downloading {input_id}.json to {out_file.as_posix()}')
            run_folder.mkdir(parents=True, exist_ok=True)
            download_folder.mkdir(parents=True, exist_ok=True)
            url = f'https://api.pollination.solutions/projects/{owner}/{project}/runs/{run_id}/outputs/eui'
            signed_url = requests.get(url, headers=api_client.headers)
            output = api_client.download_artifact(signed_url=signed_url.json())
            with zipfile.ZipFile(output) as zip_folder:
                zip_folder.extractall(run_folder.as_posix())
            # move the json file to study folder
            shutil.copy(eui_file.as_posix(), out_file.as_posix())

    next_page = response_dict.get('next_page')
    if next_page is not None:
        time.sleep(1)
        _download_results(
            owner, project, study_id, download_folder, api_client, page=next_page
        )


def download_study_results(
        api_client: ApiClient, study: Job, output_folder: pathlib.Path):
    owner = study.owner
    project = study.project
    study_id = study.id

    _download_results(
        owner=owner, project=project, study_id=study_id, download_folder=output_folder,
        api_client=api_client
    )


if __name__ == '__main__':
    api_key = 'YOUR-API-KEY'
    assert api_key is not None, 'You must provide valid Pollination API key.'

    # project owner and project name - Change these!
    owner = 'mostapha'
    project = 'agent-based-energy-simulation'

    # change this to where the study folder is
    study_folder = pathlib.Path(__file__).parent
    input_folder = study_folder.joinpath('dataset_1')
    epw = study_folder.joinpath('PER_Arequipa.847520_IWEC.epw')
    ddy = study_folder.joinpath('PER_Arequipa.847520_IWEC.ddy')
    results_folder = study_folder.joinpath('results/dataset_1')
    name = 'YOUR-STUDY-NAME'
    api_client = ApiClient(api_token=api_key)

    study = submit_study(name, api_client, owner, project, epw, ddy, input_folder)
    # wait until the study is finished
    check_study_status(study=study)
    download_study_results(
        api_client=api_client, study=study, output_folder=results_folder
    )
```
