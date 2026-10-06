# Export

The Pollination plugins support exporting all geometry as faithfully as possible to a few different file formats. Usually, some properties assigned to the geometry area also exported.

## In the Pollination Model Editor (Revit Plugin)

In the Pollination Model Editor, the entire model can always be exported to any of the formats below by going to the "Export" menu while the whole model displaying in the Model Editor workspace.

A portion of the model can be exported by using the the "Export" menu with only part of the model displaying in the workspace.

## In the Pollination Rhino Plugin

In the Pollination Rhino plugin, using the native Rhino "File > Save As" dialog will bring up the option to save the entire Pollination model to any of the destination file formats below.

Using the native Rhino "File > Export Selected" dialog will bring up the option to save the currently selected portion of the model to any of the destination file formats below.

## Supported Formats

Files in the following format can be saved or exported from the Pollination plugins:

* [Ladybug Tools \(HBJSON and DFJSON\)](https://www.ladybug.tools/)
* [IES-VE \(GEM\)](https://www.iesve.com/)
* [TRACE 700 \(gbXML, XLSX, and EXP\)](https://www.trane.com/commercial/latin-america/pr/en/products-systems/design-and-analysis-tools/trane-design-tools/trace-700.html)
* [eQuest \(INP\)](https://www.doe2.com/equest/)
* [DesignBuilder \(dsbXML\)](https://designbuilder.co.uk/)
* [OpenStudio \(OSM\)](https://openstudiocoalition.org/)
* [EnergyPlus \(IDF and epJSON\)](https://energyplus.net/)
* [IDA ICE \(IDM\)](https://www.equa.se/en/ida-ice)
* [Radiance \(RAD\)](https://www.radiance-online.org/)
* [TRACE 3D Plus \(gbXML\)](https://www.trane.com/commercial/latin-america/gy/en/products-systems/design-and-analysis-tools/trane-design-tools/trace-3d-plus-load-design.html)
* [EnergyPro \(gbXML\)](https://www.energysoft.com/)
* [CBECC \(SDD XML\)](https://www.energy.ca.gov/programs-and-topics/programs/building-energy-efficiency-standards/2025-energy-code-compliance-software)
* [Green Building XML \(gbXML\)](https://www.gbxml.org/)

All file formats export geometry as faithfully as possible into the destination engines. Some file formats support the translation of effectively all pollination model properties into the during but, others will only translate some of the properties assigned to the model geometry. These are summarized below.

### Commercial Simulation Platforms

The Pollination plugins can export to the native file formats of a variety of commercial simulation platforms.

| Model Element                  | TRACE 700         | IES-VE         | DesignBuilder     | IDA ICE        | TRACE 3D Plus  |
| ------------------------------ | ----------------- | -------------- | ----------------- | -------------- | -------------- |
| Geometry                       | ☑                | ☑              | ☑                | ☑ <sup>4</sup> | ☑             |
| Zoning                         | ☑                | ☑ <sup>1</sup> | ☑ <sup>1</sup>   | :x:             | :x:            |
| Face Types<br>(eg. AirBoundary)| ☑                | ☑              | ☑                | :x:             | :x:            |
| Boundary Conditions            | ☑                | :x:             | ☑                | :x:            | :x:            |
| Opaque Constructions           | ☑                | :x:             | :x:              | :x:             | :x:            |
| Window Constructions           | ☑                | :x:             | :x:              | :x:             | :x:            |
| Schedules                      | ☑                | :x:             | :x:              | :x:             | :x:            |
| Internal Loads                 | ☑                | :x:             | :x:              | :x:             | :x:            |
| Thermostats + Outdoor Air Req. | ☑                | :x:             | :x:              | :x:             | :x:            |
| Program Types                  | ☑ <sup>2</sup>   | ☑ <sup>3</sup> | :x:               | :x:             | :x:            |
| HVAC Systems                   | :x:               | :x:            | :x:               | :x:             | :x:            |
| SHW Systems                    | :x:               | :x:            | :x:               | :x:             | :x:            |
| Everything Else                | :x:               | :x:            | :x:               | :x:             | :x:            |

<sup>1</sup> Supported via an export option that merges rooms of the same zone (or shared plenums) into a single volume.\
<sup>2</sup> Exported as Room templates through the TRACE 700 EXP file format.\
<sup>3</sup> Map-able to IES-VE Templates through the Pollination Bridge navigator (WIP).\
<sup>4</sup> Includes an auto-generated building body to set interior vs. exterior boundary conditions.

### Free Simulation Platforms

The Pollination plugins also export to a wide variety of free and open source engines.

| Model Element                  | Ladybug Tools     | eQuest         | OpenStudio        | EnergyPlus     | Radiance        |
| ------------------------------ | ----------------- | -------------- | ----------------- | -------------- | --------------  |
| Geometry                       | ☑                | ☑              | ☑                | ☑              | ☑              |
| Zoning                         | ☑                | ☑ <sup>1</sup> | ☑                | ☑              | ☑ <sup>1</sup> |
| Face Types<br>(eg. AirBoundary)| ☑                | ☑              | ☑                | ☑              | ☑              |
| Boundary Conditions            | ☑                | ☑              | ☑                | ☑              | ☑              |
| Opaque Constructions           | ☑                | ☑              | ☑                | ☑              | ☑              |
| Window Constructions           | ☑                | ☑              | ☑                | ☑              | ☑              |
| Schedules                      | ☑                | ☑              | ☑                | ☑              | :x:            |
| Internal Loads                 | ☑                | ☑              | ☑                | ☑              | :x:            |
| Thermostats + Outdoor Air Req. | ☑                | ☑              | ☑                | ☑              | :x:            |
| Program Types                  | ☑                | ☑ <sup>2</sup> | ☑                | ☑ <sup>3</sup> | :x:            |
| HVAC Systems                   | ☑                | ☑ <sup>4</sup> | ☑                | ☑              | :x:            |
| SHW Systems                    | ☑                | :x:            | ☑                 | ☑              | :x:            |
| Everything Else                | ☑                | :x:            | ☑                 | ☑              | :x:            |

<sup>1</sup> Supported via an export option that merges rooms of the same zone into a single volume.\
<sup>2</sup> Supported via switch statements for easy editing of all zones with the same program.\
<sup>3</sup> Supported via ZoneList objects for easy editing of all zones with the same program.\
<sup>4</sup> Only HVAC grouping is translated and not any HVAC attributes.

### Dedicated Code Compliance Platforms

The Pollination plugins are also often usable with location-specific energy code compliance software when these software platforms include an option to import a gbXML. There are dedicated options offered for California Title 24 compliance through EnergyPro and CBECC native XML formats. Other compliance software like Lesosai and SIMIEN can also often accept the generic gbXML file format that the Pollination plugins export.

| Model Element                  | gbXML (Generic)   | EnergyPro      | CBECC             |
| ------------------------------ | ----------------- | -------------- | ----------------- |
| Geometry                       | ☑                | ☑              | ☑                |
| Zoning                         | ☑                | ☑              | ☑                |
| Face Types<br>(eg. AirBoundary)| ☑                | ☑              | ☑                |
| Boundary Conditions            | ☑                | ☑              | ☑                |
| Opaque Constructions           | ☑                | :x:             | ☑                |
| Window Constructions           | ☑                | :x:             | ☑                |
| Schedules                      | :x:               | :x:            | :x:               |
| Internal Loads                 | ☑                | :x:             | :x:              |
| Thermostats + Outdoor Air Req. | ☑                | :x:             | :x:              |
| Program Types                  | :x:               | :x:            | :x:              |
| HVAC Systems                   | :x:               | :x:            | :x:              |
| SHW Systems                    | :x:               | :x:            | :x:              |
| Everything Else                | :x:               | :x:            | :x:              |
