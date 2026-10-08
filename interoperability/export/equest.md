# Export to eQuest (INP)

Due to the well-documented, text-readable INP file format used by eQuest, nearly all attributes can be transferred through the export.

| Model Element                   | eQuest          |
| ------------------------------- | --------------- |
| Geometry                        | ✅              |
| Zoning                          | ✅ <sup>1</sup> |
| Face Types<br>(eg. AirBoundary) | ✅              |
| Boundary Conditions             | ✅              |
| Opaque Constructions            | ✅              |
| Window Constructions            | ✅              |
| Schedules                       | ✅              |
| Internal Loads                  | ✅              |
| Thermostats +<br>Outdoor Air    | ✅              |
| Program Types                   | ✅ <sup>2</sup> |
| HVAC Systems                    | ✅ <sup>3</sup> |
| SHW Systems                     | :x:             |

<sup>1</sup> Supported via an export option that merges rooms of the same zone into a single volume.\
<sup>2</sup> Translated to switch statements for easy editing of all zones with the same program.\
<sup>3</sup> Only HVAC grouping is translated and not any HVAC attributes.


## In the Pollination Revit Plugin (Model Editor)

Exporting an eQuest INP file from the Pollination Model Editor just involves going to the "Export" tab on the left side of the window and selecting "eQuest Model (.inp)" as the file format.

![Export INP in the Pollination Model Editor](../../.gitbook/assets/revit-plugin/export-inp.png)


# In the Pollination Rhino Plugin

Exporting an INP from the Pollination Rhino plugin just involves the "File > Save As" menu and then selecting "eQuest Geometry (*.inp)" as the file type as seen in this video:

{% embed url="https://youtu.be/mLyUsiDWfRg?list=PLHnzKQMrclYmtPc_ISoD6vdjtPG3786S0" %}
How to export a Pollination model to eQuest INP
{% endembed %}
