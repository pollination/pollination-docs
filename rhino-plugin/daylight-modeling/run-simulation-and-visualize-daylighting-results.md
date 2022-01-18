# Run Simulation and Visualize Daylighting Results

{% embed url="https://www.youtube.com/watch?v=FkZxOIpONLI&list=PLHnzKQMrclYmtPc_ISoD6vdjtPG3786S0" %}

## Step 1

Use command [PO\_RunSimulation](../pollination-commands/po\_runsimulation.md) or click "Run Simulation" button on [Pollination panel](../getting-started.md#pollination-panel). This brings up the Run Simulation dialog where you can select recipes and schedule a new simulation job.

![Run simulation dialog](<../../.gitbook/assets/image (110).png>)

## Step 2

Select "annual-daylight" recipe from the recipe list, and fill in all required parameters that starts with "\_" in its name. In this case, inputs "\_model" and "\_wea" are required before starting the simulation. You can select the wea file from your local drive, and click "Pollinate" button to schedule a new job on Pollination cloud.

_Note: please wait until the job is successfully created on the Pollination cloud before closing the dialog._

![Select the annual daylight recipe](<../../.gitbook/assets/image (108).png>)

![Select a wea file from local drive](<../../.gitbook/assets/image (102).png>)

## Step 3

Depending on the number of sensor points and input radiance parameters, the simulation might take a few minutes to hours. You can only load results for those has completed. Once a job is finished, you can choice one of available results from dropdown list to load.

Note: some results are not visualize-able, and they will only be downloaded from the Pollination cloud. Users can review all downloaded files by clicking "ResultFolder" button.

![Select one of results to load](<../../.gitbook/assets/image (105).png>)

![Load daylight results to Rhino](<../../.gitbook/assets/image (106).png>)

Note: users can double click the result mesh to adjust the legend parameter.

![Adjust the minimum and maximum value for the legend](<../../.gitbook/assets/image (111).png>)
