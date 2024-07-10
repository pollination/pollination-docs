---
description: A summary of supported export formats in Model Editor.
---

# Export

One of the most loved aspects of the Model Editor is its ability to export the model to several building energy and daylight simulation formats. Our pact with our users is if you get your model to be valid, we will translate it to BEM software without errors. If you find any errors, we consider it a bug and fix it. If we cannot fix it, we will refund your money!

{% hint style="info" %}
The gbXML, IDM, and OSM formats are not currently available on the web-based version of the Model Editor. The support for IDF in the editor is limited. See the IDF export section below for more information.
{% endhint %}

## gbXML

You can export your model to gbXML if the native format of your target software is not yet supported, and gbXML is the only available option. Even though Pollination exports a clean gbXML with closed rooms, correct windows, doors, and shades, the quality of the import will rely on the import implementation of the target software. Consider the gbXML format as the last resort.

### All Interior Floors

Set to True to export all the interior floors.

### Full Geometry

You most likely want to leave it as False.

***

## IDF

Use the IDF file to export the model to EnergyPlus.

### Simplified IDF

A boolean to only export the geometry. It is faster but doesn't include all the information.

### Geometry Names

Use Geometry names as opposed to identifiers.

### Resource Names

User Resource names as opposed to identifiers.

***

## IDM

Use this format to export to IDA ICE. Currently, we only support version 4.8. We will add support for version 5.0 soon.

### Merge Distance

The distance in meters.

***

## OSM

OpenStudio file format. The version of the OSM file is aligned with the latest version of the OpenStudio SDK that is used in Pollination products (currently OpenStudio v3.7). We are working on a solution to provide support for older versions of OpenStudio using Pollination recipes.

### Geometry Names

Use Geometry names as opposed to identifiers.

### Resource Names

User Resource names as opposed to identifiers.

***

## DFJSON

Use DFJSON format to export the model as a Dragonfly file. This file format is compatible with the Pollination Rhino plugin and Ladybug Tools Dragonfly.

***

## GEM

Use the GEM file to export the model to IES VE. The GEM file format only supports exporting the geometry information for rooms and shades.

***

## HBJSON

Use the HBSJON format to export the model to the Pollination Rhino plugin or Ladybug Tools Honeybee.

***

## INP

Use the INP file to export the model to eQuest.

### **HVAC mapping**

Indicates how HVAC systems should be assigned to the exported model. "Story" will assign one HVAC system for each distinct DOE-2 level, "Model" will use only one HVAC system for the whole model, and "Assigned-HVAC" will follow how the HVAC systems have been assigned to the rooms. (Default: Story).

### **eQuest version**

The exporter supports versions 3.65 and 3.64.

### **Exclude Interior Walls**

Notes whether interior wall Faces should be excluded from the resulting file. (Default: False).

### **Exclude Interior Ceilings**

Notes whether interior ceiling Faces should be excluded from the resulting file. (Default: False).

***

## RAD

Use the RAD export to export the model to Radiance.

### M**inimal File**

Option for whether the file should have as few line breaks as possible or should use the longer format for Radiance objects. Minimal files are smaller but can be less readable. (Default: True).

