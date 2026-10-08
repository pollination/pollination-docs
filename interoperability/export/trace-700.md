# Export to TRACE 700 (gbXML, XLSX, and EXP)

While the native TRACE 700 .TRC file type is proprietary and not a format that the Pollination plugins can author, TRACE 700 has a fairly robust importer for gbXML and also supports an importer for its own .EXP file type, which Pollination can author to transfer programs to TRACE 700 as room templates. Combined with an XLSX that Pollination exports, which includes values to paste into the TRACE 700 component tables, virtually all attributes of even the largest Pollination models can be transferred to TRACE 700 in a matter of minutes.

| Model Element                  | TRACE 700         |
| ------------------------------ | ----------------- |
| Geometry                       | ☑                |
| Zoning                         | ☑                |
| Face Types<br>(eg. AirBoundary)| ☑                |
| Boundary Conditions            | ☑                |
| Opaque Constructions           | ☑                |
| Window Constructions           | ☑                |
| Schedules                      | ☑                |
| Internal Loads                 | ☑                |
| Thermostats +<br>Outdoor Air   | ☑                |
| Program Types                  | ☑ <sup>1</sup>   |
| HVAC Systems                   | :x:               |
| SHW Systems                    | N/A               |

<sup>1</sup> Exported as Room templates through the TRACE 700 EXP file format.

## In the Pollination Revit Plugin (Model Editor)

Exporting an Pollination Model to TRACE 700 technically only requires the export of a gbXML, which is formatted for compatibility with TRACE 700. This can be done by going to the "Export" tab on the left side of the window and selecting "TRACE 700 Files (.zip)" as the file format with "Green Building XML (.xml)" as the "File Type." Importing the resulting gbXML into TRACE 700 will transfer all geometry, zoning, and boundary conditions to TRACE 700.

![Export to TRACE 700 in the Pollination Model Editor](../../.gitbook/assets/revit-plugin/export-trace-700.png)

To export the other energy properties from Pollination to TRACE 700, the EXP and XLSX files can be used. A full overview of how to use these different file types is summarized in the following videos.

#### Intro to Pollination TRACE 700 Workflows

{% embed url="https://youtu.be/81oH34GfKpg?list=PLMQg5Y_0aIyc" %}
Intro to Pollination TRACE 700 Workflows
{% endembed %}

#### Workflows 1 & 2 - Importing Geometry and Zoning with gbXML

{% embed url="https://youtu.be/UMBwacUuQuM?list=PLMQg5Y_0aIyc" %}
Workflows 1 & 2 - Importing Geometry and Zoning with gbXML
{% endembed %}

#### Workflow 3 - Importing Loads and Construction Templates with EXP

{% embed url="https://youtu.be/eEnf49O1Q74?list=PLMQg5Y_0aIyc" %}
Workflow 3 - Importing Loads and Construction Templates with EXP
{% endembed %}

#### Workflow 4 - Overriding Template Properties with XLSX

{% embed url="https://youtu.be/1q4tjW07kXI?list=PLMQg5Y_0aIyc" %}
Workflow 4 - Overriding Template Properties with XLSX
{% endembed %}


#### Finale - Detailed Airflow Calculations and Simulate!

{% embed url="https://youtu.be/fLP-lMFczrI?list=PLMQg5Y_0aIyc" %}
Finale - Detailed Airflow Calculations and Simulate!
{% endembed %}

## In the Pollination Rhino Plugin

Trace 700 export will be coming soon to the Pollination Rhino plugin.
