---
description: >-
  Construction is a terminology that is used in energy simulations for
  assembling material layers ordered from the outside to interior.
---

# Add Constructions

## **Step 1**

Use command [PO\_SetRoomProperties](../pollination-commands-for-rhino/po_setroomproperties.md) or double click the room from "Room Manager" to bring up the "Room Properties" dialog, in which you can override room's construction set\*.

Note: **construction set** is a new concept that we added to our energy modeling process. You would be familiar with the construction set if you are an OpenStudio user. Construction set helps with grouping constructions and assign them to geometries based on face types \(wall, floor, roof/ceiling\), which prevents wasting time and efforts to assign constructions to each face, and helps managing and reporting projects' constructions at global level.

![Assign construction set in Room Properties dialog](../../.gitbook/assets/image%20%2896%29.png)

## Step 2A

From construction set manager, select a construction set that you want to apply to the room. You can also double click the selected item or click Edit button to review the details of this construction set.

![Select a construction set from construction set manager](../../.gitbook/assets/image%20%2888%29.png)

![Review and edit the construction set](../../.gitbook/assets/image%20%28100%29.png)

## Step 2B

Import ASHRAE 90.1 Baseline constructions from [OpenStudio Standards](https://github.com/NREL/openstudio-standards/), developed by the US. [National Renewable Energy Laboratory](https://www.nrel.gov/) \(NREL\)'s OpenStudio Team. 

_Currently ASHRAE  90.1 standards are available for versions of pre-1980, 1980-2004, 2004, 2007, 2013. We are currently working on 2016 version, and it will be added soon._

![](../../.gitbook/assets/image%20%2897%29.png)

