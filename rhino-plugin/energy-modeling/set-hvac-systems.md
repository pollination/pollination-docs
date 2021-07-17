---
description: Assign 100+ HVACs from OpenStudio Standards
---

# Set HVAC Systems

{% embed url="https://www.youtube.com/watch?v=rHVnZt3euoA&list=PLHnzKQMrclYmtPc\_ISoD6vdjtPG3786S0&index=10" %}

## **Step 1**

Use command [PO\_SetRoomProperties](../pollination-commands-for-rhino/po_setroomproperties.md) or double click the room from "Room Manager" to bring up the "Room Properties" dialog, in which you can override the room's HVAC system.

![Override room&apos;s HVAC from Room Properties dialog](../../.gitbook/assets/image%20%28101%29.png)

## Step 2

Import ASHRAE 90.1 Baseline and other HVAC systems from [OpenStudio Standards](https://github.com/NREL/openstudio-standards/), developed by the US. [National Renewable Energy Laboratory](https://www.nrel.gov/) \(NREL\)'s OpenStudio Team. 

There are over 100+ HVAC systems are available in this library, and we categorize them into three groups: **All Air \(non DOAS\)**,  **Cooling Heating with DOAS**, and **Cooling Heating only**.

* **All Air \(non DOAS\):** a system that integrates ventilation component with cooling and heating, and using air as the only media to transfer energy. In a humid climate, this system tend to use more energy as cooling + reheat are needed for dehumidification for all supply air.
* **Cooling Heating with DOAS:** a system has a Dedicated Outdoor Air Systems \(DOAS\) for ventilation loads, separated from cooling and heating loads. The ventilation supply air tend to be at neutral temperature 20°C - 22°C \(68 °F - 72 °F\) and uses minimum cooling and re-heating energy for ventilation, which helps saving more energy compared to the first all air system. Its cooling and heating components are usually using water or refrigerant which is a more efficient mean to transfer energy while compared to air as a media.  
* **Cooling Heating only:** a system does not have any component that takes care of ventilation loads. This is typically used for residential or unoccupied spaces in commercial buildings such as: storage, restroom, mechanical room, etc. Note, there are building codes still require adding ventilation loads per area for unoccupied spaces. Typically in this case, air changes via room's infiltration is enough to meet the minimum ventilation requirement if any. 

_Currently ASHRAE  90.1 standards are available for versions of pre-1980, 1980-2004, 2004, 2007, 2013. We are currently working on 2016 version, and it will be added soon._

![Import HVAC systems from OpenStudio Standards library](../../.gitbook/assets/image%20%2892%29.png)

![Configurate a custom HVAC system from a template  ](../../.gitbook/assets/image%20%2879%29.png)

