# Upload\_Assets

![Upload Assets](<../../../.gitbook/assets/Upload_Assets (1).png>)

Upload local files and folders to Pollination cloud server, and they will be used as cloud asset references.

## Inputs

*   **project \[Required]**

    Project that all artifacts will be uploaded to. Use GetProject component or a name for getting a project from the current user. To get a project under another account, you can specify the account name before the project name with the format: AccountName/ProjectName. For example: pollination/NewDemoProject
*   **artifacts \[Required]**

    File or folder paths to be uploaded to the Pollination cloud.
*   **sub\_folder \[Optional]**

    An optional input for relative folder path where you want to save all Pollination job's files, instead of project root folder. For example: "Phase 1/Team A"
*   **upload \[Required]**

    Set to true to upload the assets.

## Outputs

*   **status**

    status.
*   **artifacts**

    artifacts that have been uploaded to the Pollination cloud.
