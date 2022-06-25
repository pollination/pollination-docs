# Prepare App folder

In this section, we are going to learn how to prepare a folder before you start writing your app. Pollination offers resources to prepare this folder in such a way that you can automate app deployment to Pollination. We will use these resources to prepare a folder for an app that plots the wind rose from the EPW data.

### Prerequisite

To follow this section, you will need to be comfortable doing actions using the command line. Check the following tutorials to learn about the command prompt on Windows and the terminal on Mac.

* [windows](https://youtu.be/A3nwRCV-bTU)
* [Mac](https://youtu.be/aKRYQsKR46I)

### Creating App Folder

We will use the [pollination-apps](https://pollination.github.io/pollination-apps/cli.html) library to create this folder for us.

Install the `pollination-apps` library by using the following command on your command prompt / terminal.

```python
pip install -U pollination-apps
```

Go to the location on your system where you'd like to create the app folder and run the following command. [This](https://www.lifewire.com/change-directories-in-command-prompt-5185508) article shows how to change directory on windows command prompt to go to a location on your system.

```python
pollination-apps new
```

This will ask for the project name. The project name here will become the name of your app. Also, make sure to not have any blank spaces in your project name. In our case, we will choose the project name to be **wind-rose**.

```
project_name [Pollination-app]: wind-rose
```

Next, it will ask for the project\_slug. Enter the same name you entered above or keep it blank which will use the same name you entered above for the project\_name. We are keeping it blank.

```
project_slug [wind-rose]:
```

Next, we will enter project\_short\_description. This is a short description of your app.

```
project_short_description [Your Pollination app!]: Generate a wind rose from EPW.
```

Next, comes pollination\_owner. This is your username in Pollination. We looked at how to find this owner name in [this](create-job.md) section.

```
pollination_owner []: YOUR_USERNAME
```

Next, pollination-apps will ask you whether you'll need the [Pollination-viewer](integrating-the-pollination-viewer.md) in your app. You'll most likely need the Pollination viewer in your app if you are dealing with any 3D geometry. In this case, we're simply creating a 2D interactive chart so we will choose not to have the Pollination viewer.

```
Select pollination_viewer:
1 - no
2 - yes
Choose from 1, 2 [1]:1
```

Next, pollination-apps will give you an option to choose the visibility setting of the app you are deploying. We will choose the `public` option. We will choose our app to be public.

```
Select app_visibility:
1 - public
2 - private
Choose from 1, 2 [1]: 1
```

Lastly, pollination-apps will give you three options to choose from for [continuous integration](https://docs.github.com/en/actions/automating-builds-and-tests/about-continuous-integration#about-continuous-integration) (CI).

```
Select ci:
1 - none
2 - github-manual
3 - github-automated
Choose from 1, 2, 3 [1]:
```

The first option creates the following app folder structure without any CI. In this option, deploying an app on Pollination relies on using the command line. Go to [this](deploy-app.md) section to learn how to deploy an app when you have chosen this option.

```
wind-rose
│   README.md
│
└───app
        app.py
        Dockerfile
        requirements.txt
```

The second option creates the following app folder structure with basic CI. In this option, deploying an app on Pollination relies on triggering a release on Github. Go to [this](github-manual.md) section to learn how to deploy an app when you have chosen this option.

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

The third option creates the following app folder structure with advanced CI.In this option, deploying an app on Pollination relies on the commit messages. Go to [this](github-automated.md) section to learn how to deploy an app when you have chosen this option.

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
