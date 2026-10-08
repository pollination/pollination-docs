# Export

The Pollination plugins support exporting all geometry as faithfully as possible to a few different file formats. Usually, some properties assigned to the geometry area also exported.

## In the Pollination Revit Plugin (Model Editor)

In the Pollination Model Editor, the entire model can always be exported to any of the formats below by going to the "Export" menu while the whole model displaying in the Model Editor workspace.

A portion of the model can be exported by using the the "Export" menu with only part of the model displaying in the workspace.

## In the Pollination Rhino Plugin

In the Pollination Rhino plugin, using the native Rhino "File > Save As" dialog will bring up the option to save the entire Pollination model to any of the destination file formats below.

Using the native Rhino "File > Export Selected" dialog will bring up the option to save the currently selected portion of the model to any of the destination file formats below.

## Supported Formats

Files in the following format can be exported from the Pollination plugins:

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

All file formats export geometry as faithfully as possible into the destination engines. Some file formats support the translation of effectively all pollination model properties but, others will only translate some of the properties assigned to the model geometry. These are summarized below.

### Commercial Simulation Platforms

By exporting to the native file formats used by commercial simulation platforms, the Pollination plugins not only faithfully translate geometry but some properties assigned to this geometry (eg. zoning) can also be exported.

| Model Element                  | TRACE 700         | IES-VE         | DesignBuilder     | IDA ICE        | TRACE 3D Plus  |
| ------------------------------ | ----------------- | -------------- | ----------------- | -------------- | -------------- |
| Geometry                       | ✅                | ✅              | ✅                | ✅ <sup>4</sup> | ✅             |
| Zoning                         | ✅                | ✅ <sup>1</sup> | ✅ <sup>1</sup>   | ✅ <sup>5</sup> | ✅ <sup>1</sup> |
| Face Types<br>(eg. AirBoundary)| ✅                | ✅              | ✅                | :x:             | :x:            |
| Boundary Conditions            | ✅                | :x:             | ✅                | :x:            | :x:            |
| Opaque Constructions           | ✅                | :x:             | :x:              | :x:             | :x:            |
| Window Constructions           | ✅                | :x:             | :x:              | :x:             | :x:            |
| Schedules                      | ✅                | :x:             | :x:              | :x:             | :x:            |
| Internal Loads                 | ✅                | :x:             | :x:              | :x:             | :x:            |
| Thermostats +<br>Outdoor Air   | ✅                | :x:             | :x:              | :x:             | :x:            |
| Program Types                  | ✅ <sup>2</sup>   | ✅ <sup>3</sup> | :x:               | :x:             | :x:            |
| HVAC Systems                   | :x:               | :x:            | :x:               | :x:             | :x:            |
| SHW Systems                    | N/A               | :x:            | :x:               | :x:             | N/A            |

<sup>1</sup> Supported via an export option that merges rooms of the same zone (or shared plenums) into a single volume.\
<sup>2</sup> Exported as Room templates through the TRACE 700 EXP file format.\
<sup>3</sup> Map-able to IES-VE Templates through the Pollination Bridge navigator (WIP).\
<sup>4</sup> Includes an auto-generated building body to set interior vs. exterior boundary conditions.\
<sup>5</sup> Zones are exported as Groups in the IDM.

### Free Simulation Platforms

The Pollination plugins also export to a wide variety of free and open source engines. Due to the well-documented, text-readable file formats of these engines, nearly all attributes can be transferred through the export.

| Model Element                  | Ladybug Tools     | OpenStudio     | EnergyPlus        | eQuest         | Radiance        |
| ------------------------------ | ----------------- | -------------- | ----------------- | -------------- | --------------  |
| Geometry                       | ✅                | ✅              | ✅                | ✅              | ✅              |
| Zoning                         | ✅                | ✅              | ✅                | ✅ <sup>1</sup> | ✅ <sup>1</sup> |
| Face Types<br>(eg. AirBoundary)| ✅                | ✅              | ✅                | ✅              | ✅ <sup>5</sup> |
| Boundary Conditions            | ✅                | ✅              | ✅                | ✅              | ✅ <sup>5</sup> |
| Opaque Constructions           | ✅                | ✅              | ✅                | ✅              | ✅ <sup>5</sup> |
| Window Constructions           | ✅                | ✅              | ✅                | ✅              | ✅ <sup>5</sup> |
| Schedules                      | ✅                | ✅              | ✅                | ✅              | N/A            |
| Internal Loads                 | ✅                | ✅              | ✅                | ✅              | N/A            |
| Thermostats +<br>Outdoor Air   | ✅                | ✅              | ✅                | ✅              | N/A            |
| Program Types                  | ✅                | ✅              | ✅ <sup>2</sup>   | ✅ <sup>3</sup> | N/A            |
| HVAC Systems                   | ✅                | ✅              | ✅                | ✅ <sup>4</sup> | N/A            |
| SHW Systems                    | ✅                | ✅              | ✅                | :x:             | N/A            |

<sup>1</sup> Supported via an export option that merges rooms of the same zone into a single volume.\
<sup>2</sup> Translated to SpaceList objects for easy editing of all spaces with the same program.\
<sup>3</sup> Translated to switch statements for easy editing of all zones with the same program.\
<sup>4</sup> Only HVAC grouping is translated and not any HVAC attributes.\
<sup>5</sup> Exported insofar as the geometry properties can influence the assigned Radiance modifiers.

### Dedicated Standards Compliance Platforms

The Pollination plugins are also often usable with location-specific energy code compliance software. Pollination offers dedicated exporters to assist with California Title 24 compliance through the native XML format of CBECC and a specially-formatted gbXML for EnergyPro 9, which are fully covered by the [Pollination Pact](https://www.pollination.solutions/pact). Other compliance software packages that can import gbXML (eg. Lesosai and SIMIEN) usually accept the generic gbXML files that the Pollination plugins export, particularly if the gbXML export options are configured for maximal compatibility with them. However, while the generic gbXML files exported by Pollination are accurate and highly customizable in terms of their format, compatibility issues may still sometimes arise when importing them due to varying import implementations. For this reason, exports of generic gbXMLs to platforms not listed on this page are not covered by the Pollination Pact.

| Model Element                  | gbXML (Generic)   | CBECC          | EnergyPro         |
| ------------------------------ | ----------------- | -------------- | ----------------- |
| Geometry                       | ✅                | ✅              | ✅                |
| Zoning                         | ✅ <sup>1</sup>   | ✅              | ✅                |
| Face Types<br>(eg. AirBoundary)| ✅ <sup>1</sup>   | ✅              | ✅                |
| Boundary Conditions            | ✅ <sup>1</sup>   | ✅              | ✅                |
| Opaque Constructions           | ✅ <sup>1</sup>   | ✅              | :x:               |
| Window Constructions           | ✅ <sup>1</sup>   | ✅              | :x:               |
| Schedules                      | :x:               | :x:            | :x:               |
| Internal Loads                 | ✅ <sup>1</sup>   | :x:             | :x:              |
| Thermostats +<br>Outdoor Air   | ✅ <sup>1</sup>   | :x:             | :x:              |
| Program Types                  | N/A               | :x:            | :x:               |
| HVAC Systems                   | :x:               | :x:            | :x:               |
| SHW Systems                    | N/A               | :x:            | :x:               |

<sup>1</sup> Included in the exported data but there is no guarantee that destination software can import it if not listed on this page.
