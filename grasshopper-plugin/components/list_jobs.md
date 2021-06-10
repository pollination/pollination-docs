# List Jobs

![](../../.gitbook/assets/List_Jobs.png)

List all jobs from a Pollination project. You can either type in formatted text "project-owner/project-name" or right click or double click on the component and select a project.

## Inputs

* **project \[Required\]**

  A Pollination project from which to list jobs. You can type in formated text "ProjectOwner/ProjectName", or double/right click the component to get a project. 

* **status**

  An optional input to filter the jobs based on status. Valid inputs are:  -Created  -PreProcessing  -Running  -Failed  -Cancelled  -Completed  -Unknown 

## Outputs

* **names**

  Name of Pollination jobs from the selected project. 

* **descriptions**

  Description of Pollination jobs from the selected project. 

* **recipes**

  The recipe that Pollination run ran with. 

* **jobs**

  List of Pollination jobs from the selected project. 

