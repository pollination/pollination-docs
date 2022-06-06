# Download an Output

In this section, we will see how we can download an output of a recipe that has successfully finished running on Pollination.

Install the following libraries first

```python
pip install streamlit pollination-streamlit
```

Importing necessary libraries

```python
import zipfile
import streamlit as st
from pollination_streamlit.interactors import Job
from pollination_streamlit.api.client import ApiClient
```

Helper function to download the output of a job

```python
def download_output(api_key: str, owner: str, project: str, job_id: str, run_index: int,
                    output_name: str, target_folder: str) -> None:
    """Download output from a job on Pollination.

    Args:
        api_key: The API key of the Pollination account.
        owner: The owner of the Pollination account.
        project: The name of the project inside which the job was created.
        job_id: The id of the job.
        run_index: The index of the run inside the job.
        output_name: The name of the output you wish to download. You can find the names
            of all the outputs either on the job page or on the recipe page.
        target_folder: The folder where the output will be downloaded.
    """
    job = Job(owner, project, job_id, ApiClient(api_token=api_key))
    run = job.runs[run_index]
    output = run.download_zipped_output(output_name)

    with zipfile.ZipFile(output) as zip_folder:
        zip_folder.extractall(target_folder)
```

Streamlit form to download the output of a job

```python
with st.form('download-result'):
    api_key = st.text_input('api_key', type='password')
    owner = st.text_input('owner')
    project = st.text_input('project')
    job_id = st.text_input('job_id')
    run_index = st.number_input('run_index', value=0)
    output_name = st.text_input('output_name')
    target_folder = st.text_input('target_folder', value='.')

    submit_button = st.form_submit_button(
        label='Submit')

    if submit_button:
        download_output(owner, project, job_id, api_key,
                        run_index, output_name, target_folder)
```

The streamlit form above will render the following interface;

![](../.gitbook/assets/pollination-apps/download\_job.png)

Providing the following inputs will download a file named "daylight\_factor.vtkjs" in your current working directory;

![](../.gitbook/assets/pollination-apps/download\_job\_query.png)
