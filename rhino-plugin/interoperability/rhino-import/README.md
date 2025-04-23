# Import

Pollination Rhino allows for the import/export of geometry and properties in the gbXML, OSM, IDF, hbjson file format.

There are two modes to open the file formats above.

* Open: Creates a new Pollination Rhino Model using the generic template
* Import: It add the model to the current Pollination Rhino model

## Import:

* [Import Honeybee JSON (HBJSON)](hbjson.md)
* [Import Green Building XML (gbXML)](gbxml.md)
* [Import OpenStudio Model (OSM)](osm.md)
* [Import Input Data File (IDF)](idf.md)

There is no loss of information when importing HBJSON but only certain model elements can be imported from OSM, gbXML and IDF. These are summarized below.

| Model Element                  | HBJSON | OSM | gbXML | IDF   |
| ------------------------------ | ------ | --- | ----- | ----- |
| Geometry                       | ☑      | ☑ 1 | ☑ 1   | ☑ 1 2 |
| Spaces / Zoning                | ☑      | ☑   | ☑     | ☑     |
| Boundary Conditions            | ☑      | ☑   | ☑     | ☑     |
| Face Types (eg. AirBoundary)   | ☑      | ☑   | ☑     | ☑     |
| Opaque Constructions           | ☑      | ☑   | ☑     | ☑     |
| Window Constructions           | ☑      | ☑ 3 | ☑ 3   | ☑ 3   |
| Schedules                      | ☑      | ☑   | :x: 5 | ☑     |
| Loads                          | ☑      | ☑   | :x: 5 | ☑     |
| Thermostats + Outdoor Air Req. | ☑      | ☑ 4 | :x: 5 | ☑     |
| Program Types                  | ☑      | ☑   | :x:   | :x:   |
| HVAC Systems                   | ☑      | :x: | :x:   | :x:   |
| SHW Systems                    | ☑      | :x: | :x:   | :x:   |
| Natural Ventilation            | ☑      | :x: | :x:   | :x:   |
| Everything Else                | ☑      | :x: | :x:   | :x:   |

1 Formats do not natively support geometries with holes (they are collapsed to a single list of inward-turning vertices on export).\
2 IDF only supports Apertures/Doors with 3-4 vertices (more complex window geometries are usually triangulated).\
3 No dynamic behavior of window constructions is imported.\
4 These always become divorced from ProgramTypes since they are not a part of OpenStudio SpaceTypes.\
5 These may eventually be supported depending upon [this issue](https://github.com/NREL/OpenStudio/issues/4320).
