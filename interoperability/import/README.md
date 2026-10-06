# Import

The Pollination plugins support importing geometry and (some) properties from a few different file file formats.

In both the Pollination Rhino Plugin and the Model Editor of the Revit Plugin, there are two modes to open the file formats.

* Open: Creates a new Pollination model and follows all conventions of the opened file (including units)
* Import: Adds the file to the current Pollination model and converts the imported file to the current units

## Supported Formats

Files in the following format can be opened or imported to the Pollination plugins:

* [Ladybug Tools \(HBJSON and DFJSON\)](https://www.ladybug.tools/)
* [OpenStudio \(OSM\)](https://openstudiocoalition.org/)
* [Green Building XML \(gbXML\)](https://www.gbxml.org/)
* [EnergyPlus \(IDF and epJSON\)](https://energyplus.net/)
* [eQuest \(INP\)](https://www.doe2.com/equest/)
* [IES-VE \(GEM\)](https://www.iesve.com/)

There is no loss of information when importing from HBJSON or DFJSON but only certain model elements\
can be imported from the other formats. These are summarized below.

| Model Element                  | HBJSON/<br>DFJSON | OSM            | gbXML             | IDF/<br>epJSON | INP            | GEM            |
| ------------------------------ | ----------------- | -------------- | ----------------- | -------------- | -------------- | -------------- |
| Geometry                       | ☑                | ☑              | ☑                | ☑ <sup>1</sup> | ☑             | ☑              |
| Zoning                         | ☑                | ☑              | ☑                | ☑              | :x:            | :x:            |
| Face Types<br>(eg. AirBoundary)| ☑                | ☑              | ☑                | ☑              | ☑             | ☑             |
| Boundary Conditions            | ☑                | ☑              | ☑                | ☑              | ☑             | :x:            |
| Opaque Constructions           | ☑                | ☑              | ☑                | ☑              | :x:            | :x:            |
| Window Constructions           | ☑                | ☑ <sup>2</sup> | ☑                | ☑ <sup>2</sup> | :x:            | :x:            |
| Schedules                      | ☑                | ☑              | :x: <sup>4</sup> | ☑               | ☑             | :x:            |
| Internal Loads                 | ☑                | ☑              | :x: <sup>4</sup> | ☑               | ☑             | :x:            |
| Thermostats + Outdoor Air Req. | ☑                | ☑ <sup>3</sup> | :x: <sup>4</sup> | ☑               | ☑             | :x:            |
| Program Types                  | ☑                | ☑              | :x:              | :x:             | ☑             | :x:            |
| HVAC Systems                   | ☑                | :x:            | :x:              | :x:              | :x:            | :x:            |
| SHW Systems                    | ☑                | :x:            | :x:              | :x:              | :x:            | :x:            |
| Everything Else                | ☑                | :x:            | :x:              | :x:              | :x:            | :x:            |

<sup>1</sup> IDF only supports Apertures/Doors with 3-4 vertices (more complex window geometries are usually triangulated).\
<sup>2</sup> No window frames of window constructions are imported.\
<sup>3</sup> These become divorced from Pollination ProgramTypes since they are not a part of SpaceTypes.\
<sup>4</sup> These may eventually be supported depending upon [this issue](https://github.com/NREL/OpenStudio/issues/4320).
