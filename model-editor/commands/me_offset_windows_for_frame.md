# Offset windows for frame
<img src="images/offset-windows.svg" width="50" height="50"> 

Offset the edges of all windows and/or skylights by a certain distance. Useful for translating between interfaces that expect the window frame to be included within or excluded from the geometry.

## Options

* **Offset Distance**

  The distance to offset the edges all windows and/or skylights. Positive values will offset the windows outwards (adding frame). Negative will offset the windows inwards (removing frame)

* **Overlap Resolve Method**

  The method that should be used for resolving overlaps between windows if offsetting causes them to collide. 'Offset To Flush' will make window edges flush at the centerline between windows that are closer than 2 times the offset distance. 'Offset And Merge' will join windows together that overlap after offsetting. 'Make Flush Only' will only make close windows flush without performing any additional offset of the boundary around each flush group.

* **Ignore Windows**

  Select to have the windows left as they are during the offset operation

* **Ignore Skylights**

  Select to have the skylights left as they are during the offset operation