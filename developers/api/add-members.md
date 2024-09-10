# Add Members to an Organization

This page shows how to use the Pollination API to add members to an organization from a list. There is an additional check not to overwite the existing member. This check is useful to ensure the existing organization owners are not being changed to members.

```python
import requests
import pathlib
import time

from typing import List


def get_current_users(api_key: str, org_name: str) -> List[str]:
    """This functions returns an empty list if the api_key doesn't belong to an organization owner."""
    url = f'https://api.pollination.cloud/orgs/{org_name}/members'
    response = requests.get(
            url=url,
            headers={'x-pollination-token': api_key}
        )
    response.raise_for_status()
    members_info = response.json()['resources']
    current_users = [
        user_info['user']['username'] for user_info in members_info
    ]
    return current_users


def add_users_to_org(
    api_key: str,
    user_handles: List[str],
    org_name: str,
    role: str = 'member',
    overwrite: bool = False
        ):

    # get current users
    current_users = get_current_users(api_key=api_key, org_name=org_name) \
        if not overwrite else []

    for handle in user_handles:
        if handle in current_users:
            print(f'{handle} is already a member of {org_name}')
            continue
        print(f'Adding {handle} to {org_name} as a {role}')
        url = f'https://api.pollination.cloud/orgs/{org_name}/members/{handle}/{role}'
        response = requests.patch(
            url=url,
            headers={'x-pollination-token': api_key}
        )
        response.raise_for_status()
        time.sleep(0.5)
        
```
