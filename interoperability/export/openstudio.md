# Export to OpenStudio (OSM)

All energy simulation features of Pollination models are transferred to both the OpenStudio (OSM) as well as EnergyPlus (IDF + epJSON) formats.

| Model Element                   | OpenStudio      | EnergyPlus      |
| ------------------------------- | --------------- | --------------- |
| Geometry                        | ✅              | ✅              |
| Zoning                          | ✅              | ✅              |
| Face Types<br>(eg. AirBoundary) | ✅              | ✅              |
| Boundary Conditions             | ✅              | ✅              |
| Opaque Constructions            | ✅              | ✅              |
| Window Constructions            | ✅              | ✅              |
| Schedules                       | ✅              | ✅              |
| Internal Loads                  | ✅              | ✅              |
| Thermostats +<br>Outdoor Air    | ✅              | ✅              |
| Program Types                   | ✅ <sup>1</sup> | ✅ <sup>2</sup> |
| HVAC Systems                    | ✅              | ✅              |
| SHW Systems                     | ✅              | ✅              |

<sup>1</sup> Translated to SpaceType objects for easy editing of all spaces with the same program.\
<sup>2</sup> Translated to SpaceList objects for easy editing of all spaces with the same program.

## In the Pollination Revit Plugin (Model Editor)

Exporting an OSM from the Pollination Model Editor just involves going to the "Export" tab on the left side of the window and selecting "OpenStudio Model (.osm)" as the file format.

![Export OSM in the Pollination Model Editor](../../.gitbook/assets/revit-plugin/export-osm.png)


## In the Pollination Rhino Plugin

Exporting an OSM from the Pollination Rhino plugin just involves the "File > Save As" menu and then selecting "OpenStudio Model (*.osm)" as the file type as seen in this video:

{% embed url="https://youtu.be/rzdKy5xH330?list=PLHnzKQMrclYniHlazOZBDxxhrcsXNm5oC&t=398" %}
How to export a Pollination Rhino model to OpenStudio
{% endembed %}
