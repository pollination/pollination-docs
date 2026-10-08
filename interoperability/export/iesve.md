# Export to IES-VE (GEM)

Given the limitations of the GEM format, exporting Pollination models to IES-VE only transfers geometry and a few general properties. Transfer of other energy simulation properties (eg. Program Types) from Pollination to IES-VE is currently a work in progress (WIP).

| Model Element                   | IES-VE          |
| ------------------------------- | --------------- |
| Geometry                        | ☑              |
| Zoning                          | ☑ <sup>1</sup> |
| Face Types<br>(eg. AirBoundary) | ☑              |
| Boundary Conditions             | :x:             |
| Opaque Constructions            | :x:             |
| Window Constructions            | :x:             |
| Schedules                       | :x:             |
| Internal Loads                  | :x:             |
| Thermostats +<br>Outdoor Air    | :x:             |
| Program Types                   | ☑ <sup>2</sup> |
| HVAC Systems                    | :x:             |
| SHW Systems                     | :x:             |

<sup>1</sup> Supported via an export option that merges rooms of the same zone (or shared plenums) into a single volume.\
<sup>2</sup> Map-able to IES-VE Templates through the Pollination Bridge navigator (WIP).


## In the Pollination Revit Plugin (Model Editor)

Exporting an IES-VE GEM file from the Pollination Model Editor just involves going to the "Export" tab on the left side of the window and selecting "IE-SVE Geometry (.gem)" as the file format.

![Export GEM in the Pollination Model Editor](../../.gitbook/assets/revit-plugin/export-gem.png)


# In the Pollination Rhino Plugin

Exporting a GEM from the Pollination Rhino plugin just involves the "File > Save As" menu and then selecting "IES-VE Geometry (*.gem)" as the file type as seen in this video:

{% embed url="https://youtu.be/_q07tzElNmU" %}
How to export a Pollination model to IES-VE
{% endembed %}
