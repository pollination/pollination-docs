# Import windows
<img src="images/import-windows.svg" width="50" height="50"> 

Import windows and doors from a HBJSON file, replacing the currently-assigned windows. If rooms are selected while running this command, only the windows and doors of the selected rooms will be updated.

## Options

* **Projection Distance**

  The distance used to project the window/door geometry onto parent rooms. Set to zero to have windows/doors only be added if they are coplanar with a room wall or roof.

* **Angle Tolerance**

  Angle tolerance in degrees, which sets the maximum angle difference between the normal vectors of the window and wall at which point the window will be projected onto the wall and assigned to it.

* **Is Revit Sourced**

  Select if the HBJSON file with windows has been exported directly from the Revit model. If so, the window geometry will be synchronized with the model's units and coordinate system if they have changed from the original Revit model.