# Automate App Deployment

In this section, we will see how we can automate the deployment of an app to Pollination using the commit messages on Github.&#x20;

### Prerequisite

Since this section builds on it, it is necessary that you go through [this](app-folder.md) section first. Make sure that before you start going through this section, you have an app folder named "wind-rose" with the following structure.

```
wind-rose
│   .gitignore
│   .releaserc.json
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

You will need to be comfortable using Github and Github desktop. Use [this](https://www.youtube.com/watch?v=iv8rSLsi1xo) video to walk yourself through the process of creating a Github repository, cloning it locally, and pushing your changes to it.

### Step-1: Write the App

Follow the steps described [here](deploy-app.md#step-3-writing-the-app) to write the app. Once you do that, the structure of your app folder should look like the following;

```
wind-rose
│   .gitignore
│   .releaserc.json
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

### Step-3: Create a Repository on Github

Once you have created a Github account, click on the "+" button in the top right corner of the screen and click on "New Repository".

![](../.gitbook/assets/pollination-apps/github-automated/github\_new\_repo.png)

**Note**: Make sure to use the name you want your app on Pollination to have as the Github repository name. We used **wind-rose** as the project name in the previous section and therefore, we will use that same name here for our Github repository.

Add a description to your repository and click on "Create Repository".

![](../.gitbook/assets/pollination-apps/github-automated/github\_create\_repo.png)

Click on "creating a new file"

![](../.gitbook/assets/pollination-apps/github-automated/github\_create\_new\_file.png)

Give any name to your file. Here, we will use "sample.txt".

![](../.gitbook/assets/pollination-apps/github-automated/github\_sample.png)

Use "chore(sample.txt): add a sample file" as the commit message and click on "Commit a new file".

![](../.gitbook/assets/pollination-apps/github-automated/github\_commit\_sample.png)

A repository named "wind-rose" is successfully created under your Github account.

![](../.gitbook/assets/pollination-apps/github-automated/github\_repo\_created.png)

### Step-4: Rename the Default Branch

Click on the "Settings"

![](../.gitbook/assets/pollination-apps/github-automated/github\_rename\_settings.png)

Click on the "branches"

![](../.gitbook/assets/pollination-apps/github-automated/github\_rename\_branches.png)

Click on the edit button and rename the default branch to "master".

![](../.gitbook/assets/pollination-apps/github-automated/github\_rename\_edit.png)

Click on the "Change default branch" button.

![](../.gitbook/assets/pollination-apps/github-automated/github\_rename\_change\_default.png)

The name of the default branch should be "master" now.

![](../.gitbook/assets/pollination-apps/github-automated/github\_rename\_complete.png)

Click on wind-rose and you should see the following dialog box. Click on "Ok, got it" to close the dialog box.

![](../.gitbook/assets/pollination-apps/github-automated/github\_rename\_ok.png)

Your repository's default branch in successfully renamed to "master".

![](../.gitbook/assets/pollination-apps/github-automated/github\_rename\_success.png)

### Step-5: Add a Secret

In the deployment using the command line, we entered the Pollination API key in the deploy command. In automated deployment, we need to add that key as a secret to the Github repository.

Click on "Settings" and then click on "Secrets".

![](../.gitbook/assets/pollination-apps/github-automated/github\_secret\_click.png)

Click on "New repository secret"

![](../.gitbook/assets/pollination-apps/github-automated/github\_secret\_new.png)

Use "POLLINATION\_TOKEN" as the secret name, enter the Pollination API key as the secret value, and click on "Add secret". Look at [this](create-job.md#step-1-pollination-credentials) step to see how to get the API key if you need guidance.

![](../.gitbook/assets/pollination-apps/github-automated/github\_secret\_api.png)

The secret is successfully added to the Github repository.

### Step-6: Create a Release

We need to trigger the first release ourselves. To do that, click on the "Create a new release" link.

![](../.gitbook/assets/pollination-apps/github-automated/github\_release\_click.png)

Click on "Choose a tag". That will open up a dropdown menu.

![](../.gitbook/assets/pollination-apps/github-automated/github\_release\_choose.png)

![](../.gitbook/assets/pollination-apps/github-automated/github\_release\_dropdown.png)

Enter "v0.0.0" as the tag name, click on "Create new tag: v0.0.0 on publish", and then "Publish release".

![](../.gitbook/assets/pollination-apps/github-automated/github\_release\_publish.png)

You should a new release on your repository and a new release tag.

![](../.gitbook/assets/pollination-apps/github-automated/github\_release\_success.png)

### Step-7: Clone the Repository Locally

We will now clone the repository locally and copy all the files necessary to run the wind-rose app.

Open Github desktop on your system and click on "Clone a repository from the internet...".

![](../.gitbook/assets/pollination-apps/github-automated/github\_clone\_desktop.png)

In the search box, enter "wind-rose" and wind-rose repository under your Github account should appear. Next, enter the path to the folder on your system where you would like to clone this repository. Click on "Clone".

![](../.gitbook/assets/pollination-apps/github-automated/github\_clone\_local.png)

You should see your repository cloned locally with the "master" branch active.

![](../.gitbook/assets/pollination-apps/github-automated/github\_clone\_done.png)

### Step-8 Copy App

Open the folder where you cloned the repository and delete the sample.txt file.

![](../.gitbook/assets/pollination-apps/github-automated/github\_copy\_delete.png)

Have both the wind-rose folder prepared in step-1(left) and the locally cloned wind-rose repository(right) side by side here.

![](../.gitbook/assets/pollination-apps/github-automated/github\_copy\_side\_by\_side.png)

Copy the files from the wind-rose folder to the cloned wind-rose repository.

![](../.gitbook/assets/pollination-apps/github-automated/github\_copy\_files.png)

Now, we have all the files necessary to run the wind-rose app in the locally cloned wind-rose repository.

### Step-9: Commit Message Format

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

#### Revert

If the commit reverts a previous commit, it should begin with `revert:` , followed by the header of the reverted commit. In the body it should say: `This reverts commit <hash>.`, where the hash is the SHA of the commit being reverted.

#### Type

Must be one of the following:

* **feat**: A new feature
* **fix**: A bug fix
* **docs**: Documentation only changes
* **style**: Changes that do not affect the meaning of the code (white-space, formatting, missing semi-colons, etc)
* **refactor**: A code change that neither fixes a bug nor adds a feature
* **perf**: A code change that improves performance
* **test**: Adding missing or correcting existing tests
* **chore**: Changes to the build process or auxiliary tools and libraries such as documentation generation

#### Scope

The scope could be anything specifying place of the commit change. For example `$location`, `$browser`, `$compile`, `$rootScope`, `ngHref`, `ngClick`, `ngView`, etc...

You can use `*` when the change affects more than a single scope.

#### Subject

The subject contains succinct description of the change:

* use the imperative, present tense: "change" not "changed" nor "changes"
* don't capitalize first letter
* no dot (.) at the end

#### Body

Just as in the **subject**, use the imperative, present tense: "change" not "changed" nor "changes". The body should include the motivation for the change and contrast this with previous behavior.

#### Footer

The footer should contain any information about **Breaking Changes** and is also the place to \[reference GitHub issues that this commit closes]\[closing-issues].

**Breaking Changes** should start with the word `BREAKING CHANGE:` with a space or two newlines. The rest of the commit message is then used for this.

**Note**: Only the the `fix` and the `feat` type will trigger a release and deployment to Pollination. Also using the fix tag will bump the version number by 0.0.1 whereas using the feat tag will bump the version number by 0.1.0.

### Step-10: Commit Local Changes to Github

Open Github desktop and use an appropriate commit message to commit the local changes to the Github repository. Our repository on Github has only the 'sample.txt' file. We want to fix it to have all the files necessary to run the wind-rose app. Therefore, we will commit the local changes to the Github repository using the `fix` type. Also, since we are committing more than one files, we will use `*` as the scope of the commit message.

![](../.gitbook/assets/pollination-apps/github-automated/github\_commit\_message.png)

Click on "Commit to master" and then on "Push origin" to push the changes to the Github repository.

![](../.gitbook/assets/pollination-apps/github-automated/github\_commit\_push.png)

### Step-11: Check Deployment on Github

This steps is optional.

Now, Github will deploy the app to the Pollination for us and we can see the status of this deployment on Github.

After pushing to origin in the last step, go to the Github repository and you should see the last commit message and a yellow dot indicating that the deployment is in progress.

To see the deployment, click on "Actions".

![](../.gitbook/assets/pollination-apps/github-automated/github\_deploy\_commit.png)

Click on "fix(\*): setup repository"

![](../.gitbook/assets/pollination-apps/github-automated/github\_deploy\_setup.png)

You will see the steps of deployment

![](../.gitbook/assets/pollination-apps/github-automated/github\_deploy\_steps.png)

In 3-4 miniutes, you should see the deployment finish.

![](../.gitbook/assets/pollination-apps/github-automated/github\_deploy\_finish.png)

Lastly, come back to the home page of the Github repository and you should see the last commit message and a green check mark indicating that the deployment is complete.

![](../.gitbook/assets/pollination-apps/github-automated/github\_deploy\_complete.png)

### Step-12: Check Deployment on Pollination

Go to Pollination, click on your avatar to see the dropdown menu. In the dropdown menu, click on "Your apps".

![](../.gitbook/assets/pollination-apps/github-automated/github\_pollination\_avatar.png)

Click on the wind-rose app card.

![](../.gitbook/assets/pollination-apps/github-automated/github\_pollination\_app\_card.png)

Click on "versions"

![](../.gitbook/assets/pollination-apps/github-automated/github\_pollination\_versions\_click.png)

You will see the last commit message and version tag on the ongoing deployment.

![](../.gitbook/assets/pollination-apps/github-automated/github\_pollination\_deploy\_awaited.png)

In 5-10 minutes, you should see the deployment finish. This means your app is deployed to Pollination and is ready for use.

![](../.gitbook/assets/pollination-apps/github-automated/github\_pollination\_deploy\_finish.png)

Lastly, click on the wind-rose app to see the app in action. You might have to refresh the webpage a few times for the app to appear after the deployment. To refresh use `shift + F5` on Chrome or equivalent on your browser.

![](../.gitbook/assets/pollination-apps/github-automated/github\_final.png)

In the [next](update-app.md) section, we will make a change to our app and we will see how a new version of the app can be deployed to Pollination with the new changes.
