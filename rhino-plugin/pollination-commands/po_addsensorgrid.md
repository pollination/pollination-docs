# PO_AddSensorGrid

Add sensor grids for running Radiance grid based simulations. Use &quot;Pollination&quot; command to open Radiance Object Manager to check and edit each sensor grid.

<div>
<figure>
  <img src="https://user-images.githubusercontent.com/2915573/209876729-cd50c983-a1d6-413e-a1ae-e8148705cecc.gif" alt="">
</figure>
</div>

## Options

* **GridSize**

  space between any two sensor points. (in Rhino&apos;s unit)

* **Offset**

  offset distance from the input geometries. (in Rhino&apos;s unit)

* **MergeCoplanar**

  set to true to merge all selected surfaces that are coplanar to create minimum amount of sensor grids as possible. (default: false)

Notes:

* The input geometries can be Rhino surfaces (aperture, door, shade), sub-surface, rooms, orphaned faces, or a mesh.

## Useful Links

{% embed url="https://docs.pollination.cloud/user-manual/rhino-plugin/daylight-modeling/add-sensor-grid" %}

## Video Tutorials

{% embed url="https://user-images.githubusercontent.com/9031066/273817127-250e60c3-75f3-45c1-b08a-d2b8a8962281.mp4" %}Add sensors to a Room and Room faces{% endembed %}

