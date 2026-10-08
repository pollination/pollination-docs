# Export to Green Building XML (gbXML)

The Pollination plugins have the ability to export a generic gbXML file with many different export options, making these gbXMLs highly customizable in terms of their format. While it is often possible to configure gbXML export options for maximal compatibility with different target software packages,  issues may still sometimes arise when importing them into software not listed on the [interoperability page](README.md) due to varying gbXML import implementations. For this reason, exports of generic gbXMLs are not covered by the [Pollination Pact](https://www.pollination.solutions/pact) and there is no guarantee that certain types of data included within the gbXML can be imported to the destination software. The list below summarizes what is included in these generic gbXMLs.

| Model Element                  | gbXML (Generic)   |
| ------------------------------ | ----------------- |
| Geometry                       | ☑                |
| Zoning                         | ☑ <sup>1</sup>   |
| Face Types<br>(eg. AirBoundary)| ☑ <sup>1</sup>   |
| Boundary Conditions            | ☑ <sup>1</sup>   |
| Opaque Constructions           | ☑ <sup>1</sup>   |
| Window Constructions           | ☑ <sup>1</sup>   |
| Schedules                      | :x:               |
| Internal Loads                 | ☑ <sup>1</sup>   |
| Thermostats +<br>Outdoor Air   | ☑ <sup>1</sup>   |
| Program Types                  | N/A               |
| HVAC Systems                   | :x:               |
| SHW Systems                    | N/A               |

<sup>1</sup> Included in the exported data but there is no guarantee that destination software can import them.

## In the Pollination Revit Plugin (Model Editor)

Exporting a gbXML from the Pollination Model Editor just involves going to the "Export" tab on the left side of the window and selecting "Green Building XML (.xml)" as the file format. The exporter comes with a range of options to support the many different ways that gbXML files can be interpreted by destination simulation tools:

![Export gbXML in the Pollination Model Editor](../../.gitbook/assets/revit-plugin/export-gbxml.png)


## In the Pollination Rhino Plugin

Exporting a gbXML from the Pollination Rhino plugin just involves the "File > Save As" menu and then selecting "Green Building XML (*.xml)" as the file type as seen in this video:

{% embed url="https://youtu.be/U-Ms_bFJzJQ" %}
How to export a Pollination Rhino model to gbXML
{% endembed %}
