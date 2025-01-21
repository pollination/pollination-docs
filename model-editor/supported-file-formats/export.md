---
description: A summary of supported export formats in Model Editor.
---

# Export

One of the most loved aspects of the Model Editor is its ability to export the model to several building energy and daylight simulation formats. Our pact with our users is if you get your model to be valid, we will translate it to BEM software without errors. If you find any errors, we consider it a bug and fix it. If we cannot fix it, we will refund your money!

{% hint style="info" %}
The gbXML, TRACEXML, IDM, and OSM formats are not currently available on the web-based version of the Model Editor. The support for IDF in the editor is limited. See the IDF export section below for more information.
{% endhint %}

## gbXML

You can export your model to gbXML if the native format of your target software is not yet supported, and gbXML is the only available option. Even though Pollination exports a clean gbXML with closed rooms, correct windows, doors, and shades, the quality of the import will rely on the import implementation of the target software. Consider the gbXML format as the last resort.

### All Interior Floors

Notes whether all interior horizontal faces should be written with the InteriorFloor type instead of the combination of InteriorFloor and Ceiling that happens by default with OpenStudio gbXML serialization. By default, this option is set to False. Set this option to True if you are exporting your model to [Lesosai](https://lesosai.com/logiciel/bim-bem/). See [this topic](https://discourse.pollination.solutions/t/gbxml-export-surface-type-issues/3677/15) for the background behind adding this option.

### Full Geometry

Notes whether space boundaries and shell geometry should be included in the exported gbXML as opposed to just the minimal required non-manifold geometry. Setting to True to include the full geometry will increase file size without adding much new information. However, some gbXML interfaces need this geometry in order to properly represent and display room volumes. In most case, you should leave this option as False.

***

## IDF

Use the IDF file to export the model to EnergyPlus.

### Simplified IDF

A boolean to export a simplified version of the IDF file. This method is faster than exporting the full IDF but the exported IDF will not include the HVAC systems if any of them are present in your model.

### Use Geometry Names

Notes whether a cleaned version of all geometry display names should be used instead of identifiers when translating the Model to IDF. Using this flag will affect all Rooms, Faces, Apertures, Doors, and Shades. It will generally result in more readable names in the IDF but this means that it will not be easy to map the EnergyPlus results back to the original Model. Cases of duplicate IDs resulting from non-unique names will be resolved by adding integers to the ends of the new IDs that are derived from the name.

### Use Resource Names

Notes whether a cleaned version of all resource display names should be used instead of identifiers when translating the Model to IDF. Using this flag will affect all Materials, Constructions, ConstructionSets, Schedules, Loads, and ProgramTypes. It will generally result in more readable names for the resources in the IDF. Cases of duplicate IDs resulting from non-unique names will be resolved by adding integers to the ends of the new IDs that are derived from the name.

***

## IDM

Use this format to export to IDA ICE. Currently, we only support version 4.8. We will add support for version 5.0 soon.

### **Interior Wall Thickness**

Maximum thickness of the interior walls. This can include the units of the distance (eg. 1.5ft) or, if no units are provided, the value will be assumed to be in meters (the native units of IDA-ICE). This value will be used to generate the IDA-ICE building body that dictates which Room Faces are exterior vs. interior. This is necessary because IDA-ICE expects the input model to have gaps between the rooms that represent the wall thickness. This value input here must be smaller than the smallest Room that is expected in the resulting IDA-ICE model and it should never be greater than 0.5m in order to avoid creating invalid building bodies for IDA-ICE. For models where the walls are touching each other, use a value of 0. The default is set to 0.4m.

***

## OSM

OpenStudio file format. The version of the OSM file is aligned with the latest version of the OpenStudio SDK that is used in Pollination products (currently OpenStudio v3.7). We are working on a solution to provide support for older versions of OpenStudio using Pollination recipes.

### Use Geometry Names

Notes whether a cleaned version of all geometry display names should be used instead of identifiers when translating the Model to OSM. Using this flag will affect all Rooms, Faces, Apertures, Doors, and Shades. It will generally result in more readable names in the OSM and IDF but this means that it may not be easy to map the EnergyPlus results back to the original Model. Cases of duplicate IDs resulting from non-unique names will be resolved by adding integers to the ends of the new IDs that are derived from the name.

### Use Resource Names

Notes whether a cleaned version of all resource display names should be used instead of identifiers when translating the Model to OSM. Using this flag will affect all Materials, Constructions, ConstructionSets, Schedules, Loads, and ProgramTypes. It will generally result in more readable names for the resources in the OSM. Cases of duplicate IDs resulting from non-unique names will be resolved by adding integers to the ends of the new IDs that are derived from the name.

***

## DFJSON

Use DFJSON format to export the model as a Dragonfly file. This file format is compatible with the Pollination Rhino plugin and Ladybug Tools Dragonfly.

***

## GEM

Use the GEM file to export the model to IES VE. The GEM file format only supports exporting the geometry information for rooms and shades.

We are currently in the process of developing an alternative workflow to export constructions and program types in addition to the geometry.

{% embed url="https://discourse.pollination.solutions/uploads/default/original/2X/2/2ed18f1737d4d5d49b62f4a3402128a375acf028.mp4" %}

***

## HBJSON

Use the HBSJON format to export the model to the Pollination Rhino plugin or Ladybug Tools Honeybee.

***

## INP

Use the INP file to export the model to eQuest.

### **HVAC mapping**

Indicates how HVAC systems should be assigned to the exported model. "Story" will assign one HVAC system for each distinct DOE-2 level, "Model" will use only one HVAC system for the whole model, and "Assigned-HVAC" will follow how the HVAC systems have been assigned to the rooms. (Default: Story).

### **eQuest version**

Indicates the desired version of eQuest. The exporter supports versions 3.64 and 3.65.

### **Exclude Interior Walls**

Notes whether interior wall Faces should be excluded from the resulting file. (Default: False).

### **Exclude Interior Ceilings**

Notes whether interior ceiling Faces should be excluded from the resulting file. (Default: False).

***

## RAD

Use the RAD export to export the model to Radiance.

### M**inimal File**

Option for whether the file should have as few line breaks as possible or should use the longer format for Radiance objects. Minimal files are smaller but can be less readable. (Default: True).

***

## SDDXML

Use the SDDXML export to export the model to [California Building Energy Code Compliance (CBECC)](https://www.energy.ca.gov/programs-and-topics/programs/building-energy-efficiency-standards/2022-building-energy-efficiency-1) software.

### Use Geometry Names

Flag to note whether a cleaned version of all geometry display names should be used instead of identifiers when translating the Model to SDD. Using this flag will affect all Rooms, Faces, Apertures, Doors, and Shades. It will generally result in more readable names in the SDD but this means that it will not be easy to map the EnergyPlus results back to the original Honeybee Model. Cases of duplicate IDs resulting from non-unique names will be resolved by adding integers to the ends of the new IDs that are derived from the name.

### Use Resource Names

Flag to note whether a cleaned version of all resource display names should be used instead of identifiers when translating the Model to SDD. Using this flag will affect all Materials, Constructions, ConstructionSets, Schedules, Loads, and ProgramTypes. It will generally result in more readable names for the resources in the SDD. Cases of duplicate IDs resulting from non-unique names will be resolved by adding integers to the ends of the new IDs that are derived from the name.

***

## TRACEXML

Use the TRACEXML export to export the model to TRACE 3D Plus and TRACE 700.

### Rectangular Subdivision Distance

A number for the resolution at which non-rectangular Apertures will be subdivided into smaller rectangular units. This is required as TRACE 3D Plus cannot model non-rectangular geometries.

### Frame Merge Distance

A number for the maximum distance between non-rectangular Apertures at which point the Apertures will be merged into a single rectangular geometry. This is often helpful when several triangular Apertures together make a rectangle when they are merged across their frames.

### Single Window Merge

Flag to note whether all windows within walls should be converted to a single window with an area that matches the original geometry. (Default: True).

***

## HTML

Export your Pollination model as a standalone HTML file.

### Color By

An option to indicate what should be used for coloring the geometry in 3D preview. The default is Face type. Other options are Boundary condition, Program type, Construction, and HVAC.

