# Automate App Deployment

In this section, we will see how we can automate the deployment of an app to Pollination using Github. Since this section builds on the section on [deploying a Pollination app](deploy-app.md), it is necessary that you work through that first.

### Prerequisite

In order to follow this section, you will need to be comfortable using Github and Github desktop. Use [this](https://www.youtube.com/watch?v=iv8rSLsi1xo) video to walk yourself through the process of creating a Github repository, cloning it locally, and pushing your changes to it.

### Step-1 Download Gitub Desktop

Go to [this](https://desktop.github.com/) page, download, and install Github desktop on your system.

### Step-2: Create a Repository on Github

Once you have created a Github account, click on the "+" button in the top right corner of the screen. Click on "New Repository".

![](../.gitbook/assets/pollination-apps/github_new_repo.png)

**Note**: Make sure to use the you want your app on Pollination to have as the Github repository name. We used **wind-rose** as the project name in the previous section and we will use that same name here for our Github repository.

Add a description to your repository and click on "Create Repository".

![](../.gitbook/assets/pollination-apps/github_create_repo.png)

Click on "creating a new file"

![](../.gitbook/assets/pollination-apps/github_create_new_file.png)

Give any name to your file, here, we will use "sample.txt".

![](../.gitbook/assets/pollination-apps/github_sample.png)

Use "chore(sample.txt): add a sample file" as the commit message and click on "Commit a new file".

![](../.gitbook/assets/pollination-apps/github_commit_sample.png)

A repository named "wind-rose" is successfully created under your Github account.

![](../.gitbook/assets/pollination-apps/github_repo_created.png)

### Step-3: Rename default branch

Click on the "Settings"

![](../.gitbook/assets/pollination-apps/github_rename_settings.png)

Click on the "branches"

![](../.gitbook/assets/pollination-apps/github_rename_branches.png)

Click on the edit button and rename the default branch to "master".

![](../.gitbook/assets/pollination-apps/github_rename_edit.png)

Click on the "Change default branch" button.

![](../.gitbook/assets/pollination-apps/github_rename_change_default.png)

The name of the default branch should be "master" now.

![](../.gitbook/assets/pollination-apps/github_rename_complete.png)

Click on wind-rose and you should see the following dialog box. Click on "Ok, got it" to close the dialog box.

![](../.gitbook/assets/pollination-apps/github_rename_ok.png)

Your repository's default branch in successfully renamed to "master".

![](../.gitbook/assets/pollination-apps/github_rename_success.png)

### Step-3: Add a Secret

In manual deployment, we entered the Pollination API key in the deploy command. In automated deployment, we need to add that key as a secret to the Github repository.

Click on "Settings" and then click on "Secrets".

![](../.gitbook/assets/pollination-apps/github_secret_click.png)

Click on "New repository secret"

![](../.gitbook/assets/pollination-apps/github_secret_new.png)

Use "POLLINATION_TOKEN" as the secret name, enter the Pollination API key as the secret value, and click on "Add secret". Look at **Generating API token** step in the [previous](deploy-app.md) section to see how to get the API key.

![](../.gitbook/assets/pollination-apps/github_secret_api.png)

The secret is successfully added to the Github repository.

### Step-4: Create a Release

We need to trigger the first release ourselves. To do that, click on the "Create a new release" link.

![](../.gitbook/assets/pollination-apps/github_release_click.png)

Click on "Choose a tag". That will open up a dropdown menu.

![](../.gitbook/assets/pollination-apps/github_release_choose.png)

![](../.gitbook/assets/pollination-apps/github_release_dropdown.png)

Enter "v0.0.0" as the tag name, click on "Create new tag: v0.0.0 on publish", and then "Publish release".

![](../.gitbook/assets/pollination-apps/github_release_publish.png)

You should a new release on your repository and a new release tag.

![](../.gitbook/assets/pollination-apps/github_release_success.png)

### Step-5: Clone the Repository

We will now clone the repository locally and copy all the files necessary to run the wind-rose app.

Open Github desktop on your system and click on "Clone a repository from the internet...".

![](../.gitbook/assets/pollination-apps/github_clone_desktop.png)

In the search box, enter "wind-rose" and wind-rose repository under your github account should appear. Next, enter the path to the folder on your system where you would like to clone this repository. Click on "Clone".

![](../.gitbook/assets/pollination-apps/github_clone_local.png)

You should see your repository cloned locally with the "master" branch active.

![](../.gitbook/assets/pollination-apps/github_clone_done.png)

### Step-6 Copy App

Open the folder where you cloned the repository and delete the sample.txt file.

![](../.gitbook/assets/pollination-apps/github_copy_delete.png)

Open the wind-rose folder created in the previous section. We have both the wind-rose folder created in the previous section and the locally cloned wind-rose repository side by side here.

![](../.gitbook/assets/pollination-apps/github_copy_side_by_side.png)

Copy the files from the wind-rose folder to the cloned wind-rose repository.

![](../.gitbook/assets/pollination-apps/github_copy_files.png)

Now, we have all the files necessary to run the wind-rose app in the locally cloned wind-rose repository.

### Step-7: Commit message format

In the next step, we will commit the local changes to the Github repository. However, before that, we need to learn the format of the commit message.

In automated deployment, the format of the commit message will determine whether the changes will be deployed to Pollination or not. Therefore, it is important to write commit messages in the formal recommended below.

Commit Message Format Each commit message consists of a **header**, a **body** and a **footer**. The header has a special format that includes a **type**, a **scope** and a **subject**:

```
<type>(<scope>): <subject>
<BLANK LINE>
<body>
<BLANK LINE>
<footer>
```

The **header** is mandatory and the **scope** of the header is optional.

Any line of the commit message cannot be longer than 100 characters! This allows the message to be easier to read on GitHub as well as in various git tools.

### Revert

If the commit reverts a previous commit, it should begin with `revert: `, followed by the header of the reverted commit. In the body it should say: `This reverts commit <hash>.`, where the hash is the SHA of the commit being reverted.

### Type

Must be one of the following:

- **feat**: A new feature
- **fix**: A bug fix
- **docs**: Documentation only changes
- **style**: Changes that do not affect the meaning of the code (white-space, formatting, missing semi-colons, etc)
- **refactor**: A code change that neither fixes a bug nor adds a feature
- **perf**: A code change that improves performance
- **test**: Adding missing or correcting existing tests
- **chore**: Changes to the build process or auxiliary tools and libraries such as documentation generation

### Scope

The scope could be anything specifying place of the commit change. For example `$location`, `$browser`, `$compile`, `$rootScope`, `ngHref`, `ngClick`, `ngView`, etc...

You can use `*` when the change affects more than a single scope.

### Subject

The subject contains succinct description of the change:

- use the imperative, present tense: "change" not "changed" nor "changes"
- don't capitalize first letter
- no dot (.) at the end

### Body

Just as in the **subject**, use the imperative, present tense: "change" not "changed" nor "changes". The body should include the motivation for the change and contrast this with previous behavior.

### Footer

The footer should contain any information about **Breaking Changes** and is also the place to [reference GitHub issues that this commit closes][closing-issues].

**Breaking Changes** should start with the word `BREAKING CHANGE:` with a space or two newlines. The rest of the commit message is then used for this.

**Note**: Only the the `fix` and the `feat` type will trigger a release and deployment to Pollination. Also using the fix tag will bump the version number by 0.0.1 whereas using the feat tag will bump the version number by 0.1.0.

### Step-8: Commit Local Changes to Github

Open Github desktop and use an appropriate commit message to commit the local changes to the Github repository. Our repository on Github has only the 'sample.txt' file. We want to fix it to have all the files necessary to run the wind-rose app. Therefore, we will commit the local changes to the Github repository using the `fix` type. Also, since we are committing more than one files, we will use `*` as the scope of the commit message.

![](../.gitbook/assets/pollination-apps/github_commit_message.png)

Click on "Push origin" to push the changes to the Github repository.

![](../.gitbook/assets/pollination-apps/github_commit_push.png)

### Step-9: Check deployment on Github

This steps is optional.

Now, Github will deploy the app to the Pollination for us and we can see the status of this deployment on Github.

After pushing to origin in the last step, go to the Github repository and you should see the last commit message and a yellow dot indicating that the deployment is in progress.

To see the deployment, click on "Actions".

![](../.gitbook/assets/pollination-apps/github_deploy_commit.png)

Click on "fix(\*): setup repository"

![](../.gitbook/assets/pollination-apps/github_deploy_setup.png)

You will see the steps of deployment

![](../.gitbook/assets/pollination-apps/github_deploy_steps.png)

In 3-4 miniutes, you should see the deployment finish.

![](../.gitbook/assets/pollination-apps/github_deploy_finish.png)

Lastly, come back to the home page of the Github repository and you should see the last commit message and a green check mark indicating that the deployment is complete.

![](../.gitbook/assets/pollination-apps/github_deploy_complete.png)

### Step-10: Check deployment on Pollination

Go to your Pollination, click on your avatar to see the dropdown menu. In the dropdown menu, click on "Your apps".

![](../.gitbook/assets/pollination-apps/github_pollination_avatar.png)

Click on the wind-rose app card.

![](../.gitbook/assets/pollination-apps/github_pollination_app_card.png)

Click on "versions"

![](../.gitbook/assets/pollination-apps/github_pollination_versions_click.png)

You will see the last commit message and version tag on the ongoing deployment.

![](../.gitbook/assets/pollination-apps/github_pollination_deploy_awaited.png)

In 5-10 minutes, you should see the deployment finish. This means your app is deployed to Pollination and is ready for use.

![](../.gitbook/assets/pollination-apps/github_pollination_deploy_finish.png)

Lastly, click on the wind-rose app to see the app in action. You might have to refresh the webpage for the app to appear after the deployment. To refresh use `shift + F5` on Chrome or equivalent on your browser.

![](../.gitbook/assets/pollination-apps/github_final.png)

In the [next](update-app.md) section, we will make a change to our app and we will see how a new version of the app can be deployed to Pollination with the new changes.
