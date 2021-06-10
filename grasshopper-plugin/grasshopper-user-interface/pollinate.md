# Pollinate

![](../../.gitbook/assets/Pollinate.png)

Schedule a new Pollination job for runs.

## Inputs

* **runs \[Required\]**

  PollinationRun from SetupRuns 

* **name**

  A text for human friendly name for a Pollination job. 

* **description**

  An optional input for a job's description 

* **sub\_folder**

  An optional input for relative folder path where you want to save all Pollination job's files, instead of project root folder.  For example: "Phase 1/Team A" 

* **keywords**

  An optional input for a list of keywords that you want to label the jobs 

## Outputs

* **job**

  A Pollination job that is either running on the Pollination cloud or your local machine. You can use CheckJobStatus to monitor each job. 

