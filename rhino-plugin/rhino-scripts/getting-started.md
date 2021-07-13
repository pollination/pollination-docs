# Getting Started

One of the easiest ways to create a Pollination Rhino script is ironpython of Rhino.

Rhino has an internal IDE to write ironpython. Type the command **EditPythonScript** on the command bar of Rhino to open it.

![Rhino Python Editor](../../.gitbook/assets/image%20%2859%29.png)

Or it is possible to use external IDE to create it.

## Importing the libraries

The first step is import modules and sub-modules that contain the useful classes

```text
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
  * **Objects**: Pollination Rhino Runtime Objects \(RoomObject, OrphanedFaceObject, ApertureObject, DoorObject, ShadeObject, SensorGridObject, ViewObject\)
  * **Entity**: It contains ModelEntity which collects on runtime all Pollination Object which the model is made
  * **Data**: Honeybee Schema data that every Pollination Object contains. E.g. RoomObject is composed by RoomData through Data Property



