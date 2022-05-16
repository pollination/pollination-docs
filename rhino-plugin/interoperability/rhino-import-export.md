# Rhino Import/Export

Pollination Rhino allows for the import/export of geometry and properties in the gbXML, OSM, IDF, hbjson file format.

There are two modes to open the file formats above.

* Open: Creates a new Pollination Rhino Model using the generic template
* Import: It add the model to the current Pollination Rhino model

## Import:

* [Import Honeybee JSON \(HBJSON\)](import/hbjson.md)
* [Import Green Building XML \(gbXML\)](import/gbxml.md)
* [Import OpenStudio Model \(OSM\)](import/osm.md)
* [Import Input Data File \(IDF\)](import/idf.md)

There is no loss of information when importing HBJSON but only certain model elements
can be imported from OSM, gbXML and IDF. These are summarized below.

| Model Element                  | HBJSON     | OSM                    | gbXML                  | IDF                      |
| ------------------------------ | ---------- | ---------------------- | ---------------------- | ------------------------ |
| Geometry                       |  &#x2611;  |  &#x2611; <sup>1</sup> |  &#x2611; <sup>1</sup> |  &#x2611; <sup>1 2</sup> |
| Spaces / Zoning                |  &#x2611;  |  &#x2611;              |  &#x2611;              |  &#x2611;                |
| Boundary Conditions            |  &#x2611;  |  &#x2611;              |  &#x2611;              |  &#x2611;                |
| Face Types (eg. AirBoundary)   |  &#x2611;  |  &#x2611;              |  &#x2611;              |  &#x2611;                |
| Opaque Constructions           |  &#x2611;  |  &#x2611;              |  &#x2611;              |  &#x2611;                |
| Window Constructions           |  &#x2611;  |  &#x2611; <sup>3</sup> |  &#x2611; <sup>3</sup> |  &#x2611; <sup>3</sup>   |
| Schedules                      |  &#x2611;  |  &#x2611;              |  :x: <sup>5</sup>      |  &#x2611;                |
| Loads                          |  &#x2611;  |  &#x2611;              |  :x: <sup>5</sup>      |  &#x2611;                |
| Thermostats + Outdoor Air Req. |  &#x2611;  |  &#x2611; <sup>4</sup> |  :x: <sup>5</sup>      |  &#x2611;                |
| Program Types                  |  &#x2611;  |  &#x2611;              |  :x:                   |  :x:                     |
| HVAC Systems                   |  &#x2611;  |  :x:                   |  :x:                   |  :x:                     |
| SHW Systems                    |  &#x2611;  |  :x:                   |  :x:                   |  :x:                     |
| Natural Ventilation            |  &#x2611;  |  :x:                   |  :x:                   |  :x:                     |
| Everything Else                |  &#x2611;  |  :x:                   |  :x:                   |  :x:                     |

<sup>1</sup> Formats do not natively support geometries with holes (they are collapsed to a single list of inward-turning vertices on export).<br>
<sup>2</sup> IDF only supports Apertures/Doors with 3-4 vertices (more complex window geometries are usually triangulated).<br>
<sup>3</sup> No dynamic behavior of window constructions is imported.<br>
<sup>4</sup> These always become divorced from ProgramTypes since they are not a part of OpenStudio SpaceTypes.<br>
<sup>5</sup> These may eventually be supported depending upon [this issue](https://github.com/NREL/OpenStudio/issues/4320).

## Export:

There is no loss of information when exporting to HBJSON and all energy properties are
included upon export to OSM and IDF. For gbXML, the properties that are exported
are the same as those which are imported.

* [Export Honeybee JSON \(HBJSON\)](export/hbjson.md)
* [Export Green Building XML \(gbXML\)](export/gbxml.md)
* [Export OpenStudio Model \(OSM\) + Input Data File \(IDF\)](export/osm.md)
