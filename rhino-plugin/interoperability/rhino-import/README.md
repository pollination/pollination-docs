# Rhino Import

Pollination Rhino allows for the import/export of geometry and properties in the gbXML, OSM, IDF, hbjson file format.

There are two modes to open the file formats above.

* Open: Creates a new Pollination Rhino Model using the generic template
* Import: It add the model to the current Pollination Rhino model

## Import:

* [Import Honeybee JSON \(HBJSON\)](hbjson.md)
* [Import Green Building XML \(gbXML\)](gbxml.md)
* [Import OpenStudio Model \(OSM\)](osm.md)
* [Import Input Data File \(IDF\)](idf.md)

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
| Schedules                      |  &#x2611;  |  &#x2611; <sup>4</sup> |  WIP <sup>5</sup>      |  WIP <sup>5</sup>        |
| Loads                          |  &#x2611;  |  &#x2611; <sup>4</sup> |  WIP <sup>5</sup>      |  WIP <sup>5</sup>        |
| Thermostats + Outdoor Air Req. |  &#x2611;  |  &#x2611; <sup>6</sup> |  WIP <sup>5</sup>      |  WIP <sup>5</sup>        |
| Program Types                  |  &#x2611;  |  &#x2611;              |  :x:                   |  :x:                     |
| HVAC Systems                   |  &#x2611;  |  :x:                   |  :x:                   |  :x:                     |
| SHW Systems                    |  &#x2611;  |  :x:                   |  :x:                   |  :x:                     |
| Natural Ventilation            |  &#x2611;  |  :x:                   |  :x:                   |  :x:                     |
| Everything Else                |  &#x2611;  |  :x:                   |  :x:                   |  :x:                     |

<sup>1</sup> Formats do not natively support geometries with holes (they are collapsed to a single list of inward-turning vertices on export).<br>
<sup>2</sup> IDF only supports Apertures/Doors with 3-4 vertices (more complex window geometries are triangulated upon export).<br>
<sup>3</sup> No dynamic behavior of window constructions is imported.<br>
<sup>4</sup> Only Ruleset and FixedInterval schedules are imported.<br>
<sup>5</sup> Will be supported once [this update](https://github.com/NREL/OpenStudio/issues/4469) is in an OpenStudio release.<br>
<sup>6</sup> These become divorced from the ProgramType since they are not a part of OpenStudio SpaceTypes.
