---
description: Schedule a new energy simulation and check html report
---

# Run Simulation and Load Results

In the current beta version, we only support running simulation on Pollination cloud (it is free!), but we will enable local simulation execution in the next release.

{% embed url="https://youtu.be/es8uieh3vVI?t=41" %}

## Step 1

Use command [PO\_RunSimulation](../pollination-commands/po\_runsimulation.md) or click "Run Simulation" button on [Pollination panel](../getting-started.md#pollination-panel). This brings up the Run Simulation dialog where you can select recipes and schedule a new simulation job.

![](<../../.gitbook/assets/image (98) (1).png>)

## Step 2

Select "annual-energy-use" recipe from the recipe list, and fill in all required parameters that starts with "\_" in its name. In this case, inputs "ddy" and "epw" are required before starting the simulation. You can select these two files from your local drive, and click "Pollinate" button to schedule a new job on Pollination cloud.

Note: please wait until the job is successfully created on the Pollination cloud before closing the dialog.

![Select a recipe from the recipe list](<../../.gitbook/assets/image (82).png>)

![Fill in required parameters](<../../.gitbook/assets/image (99).png>)

## Step 3

Depends on the size of projects, the simulation might take a few minutes to hours. You can only load results for those has completed. Once a job is finished, you can choice one of available results from dropdown list to load.

Note: some results are not visualize-able, and they will only be downloaded from the Pollination cloud. Users can review all downloaded files by clicking "ResultFolder" button.

![](<../../.gitbook/assets/image (89).png>)
