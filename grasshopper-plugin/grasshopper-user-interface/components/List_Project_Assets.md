## ![List Project Assets](../../images/icons/List_Project_Assets.png) List Project Assets

![List Project Assets](../../images/components/List_Project_Assets.png)

List all available cloud assets from a project folder

### Inputs

* #### project [Required]

  Project from which artifacts will be listing. Use GetProject component or a name for getting a project from the current user. To get a project under another account, you can specify the account name before the project name with the format: AccountName/ProjectName. For example: pollination/NewDemoProject

* #### sub_folder [Optional]

  An optional input for relative folder path where you want to list all Pollination job's files, instead of project root folder.  For example: "Phase 1/Team A"

* #### keyword [Optional]

  A keyword to filter the files.

### Outputs

* #### artifacts

  Project artifacts that can be used in the cloud-based jobs.
