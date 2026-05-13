# Auto zoning
<img src="images/auto-zone.svg" width="50" height="50"> 

Automatically assign zones to rooms with similar properties. Properties that are used to group rooms into zones include story, orientation, and (optionally) energy programs.

## Options

* **Orientation Count**

  A positive integer to set the number of orientation groups to use for zoning. Setting this to 4, for example, will result in zones being established based on the four orientations (North, East, South, West).

* **North Angle**

  A number between 0 and 360 to set the clockwise north direction in degrees. (0=North, 90=East, 180=South, 270=West). Default is 0 for the world Y-axis. (North, East, South, West).

* **Ignore Programs**

  Select to have any room programs ignored during the automatic zoning process in which case rooms with different programs may appear in the same zone.