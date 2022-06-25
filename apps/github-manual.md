# Deploy using Github releases

In this section, we will see how we can deploy an app on Pollination by triggering a release on Github.

### Prerequisite

Since this section builds on it, it is necessary that you go through [this](app-folder.md) section first. Make sure that before you start going through this section, you have an app folder named "wind-rose" with the following structure.

```
wind-rose
│   README.md
│
├───.github
│   └───workflows
│           ci.yaml
│
└───app
        app.py
        Dockerfile
        requirements.txt
```

You will also need to be comfortable using Github and Github desktop. Use [this](https://www.youtube.com/watch?v=iv8rSLsi1xo) video to walk yourself through the process of creating a Github repository, cloning it locally, and pushing your changes to it.

### Step-1: Write the App

Follow the steps described [here](deploy-app.md#step-3-writing-the-app) to write the app. Once you do that, the structure of your app folder should look like the following;

```
wind-rose
│   README.md
│
├───.github
│   └───workflows
│           ci.yaml
│
└───app
    │   app.py
    │   Dockerfile
    │   requirements.txt
    │
    └───assets
            sample.epw
```

### Step-2: Download Github Desktop

Go to [this](https://desktop.github.com/) page, download, and install Github desktop on your system.

### Step-3: Create a Github Repository

Once you have created a Github account, click on the "+" button in the top right corner of the screen and click on "New Repository".

![](../.gitbook/assets/pollination-apps/github-manual/github_new_repo.png)

**Note**: Make sure to use the name you want your app on Pollination to have as the Github repository name. We used **wind-rose** as the project name in the previous section and therefore, we will use that same name here for our Github repository.

Add a description to your repository and create repository.

![](../.gitbook/assets/pollination-apps/github-manual/github_repo_description.png)

Click on "Creating a new file"

![](../.gitbook/assets/pollination-apps/github-manual/github_create_new_file.png)

Name that new file anything you like. We're naming it "sample.txt" here.

![](../.gitbook/assets/pollination-apps/github-manual/github_sample_txt.png)

Create the new file.

![](../.gitbook/assets/pollination-apps/github-manual/github_sample_added.png)

### Step-4: Add a Secret

In manual deployment, we entered the Pollination API key in the deploy command. In this deployment, we need to add that key as a secret to the Github repository.

Click on "Settings".

![](../.gitbook/assets/pollination-apps/github-manual/github_settings.png)

Click on "Secrets" and then "Actions"

![](../.gitbook/assets/pollination-apps/github-manual/github_actions.png)

Click on "New repository secret".

![](../.gitbook/assets/pollination-apps/github-manual/github_new_repo_secret.png)

Use "POLLINATION_TOKEN" as the name, paste your Pollination API Key in the box, and click on the "Add secret". Go to [this](create-job.md) section to learn how to get this POllination API key.

**Note**: Make sure to use "POLLINATION_TOKEN" as the name.

![](../.gitbook/assets/pollination-apps/github-manual/github_add_secret.png)

You should the pollination token added as a secret to your repository like so;

![](../.gitbook/assets/pollination-apps/github-manual/github_add_secret_success.png)

### Step-5: Clone the Repository Locally

Open Github Desktop and click on "Clone a repository from the internet..."

![](../.gitbook/assets/pollination-apps/github-manual/github_open_github_desktop.png)

Search for "Wind-rose" and the repository should come up under your account name. Next, choose any local path. This is the path to a folder on your system where you'd like to clone this repository. Lastly, click on "Clone".

![](../.gitbook/assets/pollination-apps/github-manual/github_clone.png)

Once you clone the repository, the Github Desktop interface should look like so;

![](../.gitbook/assets/pollination-apps/github-manual/github_clone_success.png)

### Step-6: Push Local Changes

Now we have the App folder create in [earlier](app-folder.md) section and the local repository folder created in the step above open side by side.

Delete the "sample.txt" from the local repository folder.

![](../.gitbook/assets/pollination-apps/github-manual/github_delete_sample.png)

Copy and paste all the items from the App folder to the local repository folder.

![](../.gitbook/assets/pollination-apps/github-manual/github_copy_paste.png)

Go to Github Desktop now. You should see all the changes you made in the local repository folder. Choose a short message to describe this change and click on "Commit to main".

![](../.gitbook/assets/pollination-apps/github-manual/github_desktop_again.png)

Click on "Push origin".

![](../.gitbook/assets/pollination-apps/github-manual/github_push_origin.png)

### Step-7: Create a Release

Go to your repository on Github and the app folder should show up. That means, all the files necessary to deploy the app are there on Github repository now.

Click on the "Create a new release" link

![](../.gitbook/assets/pollination-apps/github-manual/github_create_new_release.png)

Click on "Choose a tag"

![](../.gitbook/assets/pollination-apps/github-manual/github_choose_tag.png)

Write any tag name. We are choosing to write "v0.0.0" here. You can read more here if you are interested [versioning](https://en.wikipedia.org/wiki/Software_versioning#Semantic_versioning).

![](../.gitbook/assets/pollination-apps/github-manual/github_version.png)

Write any message to describe the release

![](../.gitbook/assets/pollination-apps/github-manual/github_release_name.png)

You should have successfully created a release on Github

![](../.gitbook/assets/pollination-apps/github-manual/github_release_success.png)

### Step-8: Check deployment on Github

This step is optional.

Go you the repository on Github and click on "actions"

![](../.gitbook/assets/pollination-apps/github-manual/github_click_actions.png)

You should see the release message with a yellow dot in front of it. This means the deployment from Github has started.

![](../.gitbook/assets/pollination-apps/github-manual/github_deployment_started.png)

After a few minutes, you will see a green check mark. That will indicate that the deployment from Github was a success.

![](../.gitbook/assets/pollination-apps/github-manual/github_deployment_ongoing.png)

![](../.gitbook/assets/pollination-apps/github-manual/github_deployment_complete.png)

### Step-9: Check deployment on Pollination

Click on your avatar and then click on "Your Apps" on Pollination.

![](../.gitbook/assets/pollination-apps/github-manual/github_avatar.png)

Click on the "wind-rose" app card

![](../.gitbook/assets/pollination-apps/github-manual/github_app_card.png)

Click on "Versions"

![](../.gitbook/assets/pollination-apps/github-manual/github_app_versions.png)

At the top of the version history, you should see the app being deployed with the version tag you chose in step-7 above.

![](../.gitbook/assets/pollination-apps/github-manual/github_pollination_app_deploying.png)

After about 5-10 minutes the deployment will finish

![](../.gitbook/assets/pollination-apps/github-manual/github_pollination_app_pending.png)

![](../.gitbook/assets/pollination-apps/github-manual/github_pollination_app_complete.png)

Lastly, click on the wind-rose app to see the app in action. You might have to refresh the webpage for the app to appear after the deployment. To refresh use `shift + F5` on Chrome or equivalent on your browser.

![](../.gitbook/assets/pollination-apps/github-manual/github_final.png)

In the [next](github-automated.md) section, we will see how we can use commit messages to automate App deployment to Pollination.
