# Pollinate

![Pollinate](<../../../.gitbook/assets/Pollinate (1).png>)

Schedule a new Pollination job for runs.

## Inputs

*   **runs \[Required]**

    PollinationRun from SetupRuns
*   **name \[Default]**

    A text for human friendly name for a Pollination job.
*   **description \[Optional]**

    An optional input for a job's description
*   **sub\_folder \[Optional]**

    An optional input for relative folder path where you want to save all Pollination job's files, instead of project root folder. For example: "Phase 1/Team A"
*   **keywords \[Optional]**

    An optional input for a list of keywords that you want to label the jobs

## Outputs

*   **study**

    A Pollination study that is either running on the Pollination cloud or your local machine. You can use CheckJobStatus to monitor each study.
