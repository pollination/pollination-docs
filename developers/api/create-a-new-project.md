# Create a New Project

This sample code shows how to use the API to create a new project under your project and add the recipes to the project.&#x20;

```python
import requests
from typing import List


def create_project(
    api_key: str, owner: str, name: str, is_public: bool = False,
    description: str = None, recipes: List[dict] = None
        ):
    headers = {'x-pollination-token': api_key}
    # create the project
    url = f'https://api.pollination.cloud/projects/{owner}'
    data = {
        'name': name,
        'description': description if description else '',
        'public': is_public
    }
    print(f'Creating project {owner}/{name} ...')
    response = requests.post(url=url, headers=headers, json=data)
    response.raise_for_status()
    print(f'Project {owner}/{name} is created!')

    # add the recipes if any
    recipes = recipes or []
    recipe_url = f'https://api.pollination.cloud/projects/{owner}/{name}/recipes/filters'
    for recipe in recipes:
        # each recipe should be formatted as
        # {'owner': 'owner', 'name':'name, 'tag': 'tag'}
        print(f'Adding recipe {recipe} to the project.')
        recipe_response = requests.post(
            url=recipe_url, headers=headers, json=recipe
        )
        recipe_response.raise_for_status()
        
```

Here is an example of using the function to create a project under the Pollination organization.

```python
if __name__ == '__main__':
    api_key = ''  # provide a valid API key
    assert api_key, 'Provide a valid API Key.'
    owner = 'pollination'  # change the owner to your organization
    name = 'Sample Project'
    description = 'This project is created automatically using the API.'
    # see this link for the list of available recipes
    # https://app.pollination.cloud/recipes
    recipes = [
        {'owner': 'ladybug-tools', 'name': 'annual-daylight', 'tag': 'latest'},
        {'owner': 'ladybug-tools', 'name': 'annual-energy-use', 'tag': 'latest'}
    ]
    create_project(
        api_key=api_key, owner=owner, name=name, description=description,
        recipes=recipes
    )
```

Here are the screenshots of the project created using the sample code.

<figure><img src="../../.gitbook/assets/image (167).png" alt=""><figcaption><p>Project landing page</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (168).png" alt=""><figcaption><p>Project settings</p></figcaption></figure>
