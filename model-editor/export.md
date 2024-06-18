---
description: A summary of supported export formats in Model Editor.
---

# Export

One of the most loved aspects of the Model Editor is its ability to export the model to several Building energy and daylight simulation formats.

## HBJSON

Use the HBSJON format to export the model to the Pollination Rhino plugin or Ladybug Tools Honeybee.

## GEM

Use the GEM file to export the model to IES VE. The GEM file format only supports exporting the geometry information for rooms and shades.

## INP

Use the INP file to export the model to eQuest.

### Options

**hvac\_mapping**

Indicates how HVAC systems should be assigned to the exported model. "Story" will assign one HVAC system for each distinct DOE-2 level, "Model" will use only one HVAC system for the whole model, and "Assigned-HVAC" will follow how the HVAC systems have been assigned to the rooms. (Default: Story).

**exclude\_interior\_walls**

Notes whether interior wall Faces should be excluded from the resulting file. (Default: False).

**exclude\_interior\_ceilings**

Notes whether interior ceiling Faces should be excluded from the resulting file. (Default: False).

## IDF

Use the IDF file to export the model to EnergyPlus.

### Options

**include\_sim\_par**

Notes whether default simulation parameters should be included in the exported IDF. Set to True if you want the exported IDF to be immediately simulate-able. Set to False if you intend to customize how the IDF is run or you plan to combine it with other IDFs, which already have simulation parameters. (Default: True).

**patch\_adjacencies**

Notes whether missing adjacencies in the exported file should be replaced with Adiabatic boundary conditions. Set to True if you would like the IDF to be simulateable on its own regardless of whether it is a whole or part of the model. Set to False if you intend to combine this IDF with other IDF files before simulation. (Default: True).

## RAD

Use the RAD export to export the model to Radiance.

### Options

**minimal\_file**

Option for whether the file should have as few line breaks as possible or should use the longer format for Radiance objects. Minimal files are smaller but can be less readable. (Default: True).

