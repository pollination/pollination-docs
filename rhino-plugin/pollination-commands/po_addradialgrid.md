# PO_AddRadialGrid

Adding radial sensor grids for running Radiance grid based simulations.
The input geometries can be Rhino surfaces, rooms or orphaned faces. 
For rooms, only sub-surfaces with floor type will be used for generating sensor grids.
This type of sensor grid is particularly helpful for studies of multiple view directions, such as imageless glare studies.

## Options

* **GridSize**

  space between any two sensor points. (in Rhino&apos;s unit)

* **Offset**

  offset distance from the input geometries. (in Rhino&apos;s unit)

* **Directions**

  A positive integer for the number of radial directions to be generated around each position. (Default: 8)

