# Use Rhino Scripts to Automate Processes

Pollination Rhino plugin is based on a series of custom libraries that it is possible to use to create scripts. E.g. I would like to override all current glass material of the apertures with a custom one with just one click. A script could do that fast.

Example files that used in the video are available from: [https://github.com/pollination/pollination-rhino-scripts](https://github.com/pollination/pollination-rhino-scripts)

{% embed url="https://youtu.be/I1boPxLh0u4" %}

{% embed url="https://youtu.be/r52gfpPwyW4" %}

One of the easiest ways to create a Pollination Rhino script is ironpython of Rhino.

Rhino has an internal IDE to write ironpython. Type the command **EditPythonScript **on the command bar of Rhino to open it.

![Rhino Python Editor](<../.gitbook/assets/image (60).png>)

Or it is possible to use external IDE to create it.

## Importing the libraries

The first step is import modules and sub-modules that contain the useful classes

```
# import rhinocommon
import Rhino
import System

# import pollination part
import clr
clr.AddReference('Pollination.Core.dll')
clr.AddReference('HoneybeeSchema.dll')
import HoneybeeSchema as hb # Honeybee Schema
import Core as po # Pollination classes
```

* **HoneybeeSchema.dll** contains the schema that Pollination rhino uses
* **Pollination.Core.dll** contains following sub-modules:
* **Objects**: Pollination Rhino Runtime Objects (RoomObject, OrphanedFaceObject, ApertureObject, DoorObject, ShadeObject, SensorGridObject, ViewObject)
* **Entity**: It contains ModelEntity which collects on runtime all Pollination Object which the model is made
* **Data**: Honeybee Schema data that every Pollination Object contains. E.g. RoomObject is composed by RoomData through Data Property

See links below for more information:

* Honeybee Schema: [_https://www.ladybug.tools/honeybee-schema/model.html_](https://www.ladybug.tools/honeybee-schema/model.html)
* Pollination.Core: [_https://pollination.github.io/rhino-plugin/api/Core.Objects.html_](https://pollination.github.io/rhino-plugin/api/Core.Objects.html)
