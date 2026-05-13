# Reload Rooms from Revit
<img src="images/reload-room.svg" width="50" height="50"> 

Replace rooms with updated version of the room from Revit. Existing openings will be projected onto the updated rooms based on the specified projection distance and angle tolerance.

## Options

* **Projection Distance**

  The distance used to project the window/door geometry onto parent rooms. Set to zero to have windows/doors only be added if they are coplanar with a room wall or roof.

* **Angle Tolerance**

  Angle tolerance in degrees, which sets the maximum angle difference between the normal vectors of the window and wall at which point the window will be projected onto the wall and assigned to it.