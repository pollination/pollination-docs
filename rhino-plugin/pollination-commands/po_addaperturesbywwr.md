# PO_AddAperturesByWWR

Add windows by window to wall ratio for each outdoor walls of selected rooms. Use &quot;Pollination&quot; command to open Room Manager or Orphaned Object Manager to check and edit each hosted window object.

<div>
<figure>
  <img src="https://user-images.githubusercontent.com/2915573/209876723-e427d0f9-38e6-40e8-93ca-e732d2c61afb.gif" alt="">
</figure>
</div>

## Options

* **WindowWallRatio_North**

  Set a number between 0 to 1 for WWR. Default: 0.4 (40%).

* **WindowWallRatio_East**

  Set a number between 0 to 1 for WWR. Default: 0.4 (40%).

* **WindowWallRatio_South**

  Set a number between 0 to 1 for WWR. Default: 0.4 (40%).

* **WindowWallRatio_West**

  Set a number between 0 to 1 for WWR. Default: 0.4 (40%).

* **Subdivide**

  Boolean to note whether to generate a single window in the center of each Face(False) or to generate a series of rectangular windows using the other inputs below (True). Default: No.

* **Window_Height**

  A number for the target height of the output apertures.

* **Sill_Height**

  A number for the target height above the bottom edge of the face to start the apertures.

* **Horizontal_Separation**

  A number for the horizontal separation between individual aperture centerlines.

* **Vertical_Separation**

  An optional number to create a single vertical separation between top and bottom apertures. Default: 0.0.

Notes:

* Set the ratio to 0 to skip the aperture creation in the specific direction.

## See Also

* [PO_AddSkylightsByRatio](./po_addskylightsbyratio.md)

## Video Tutorials

{% embed url="https://youtu.be/3u_xXu4F1L0" %}Add Apertures{% endembed %}

