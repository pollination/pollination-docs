# PO\_AddSensorGrid

Add sensor grids for running Radiance grid based simulations. Use "Pollination" command to open Radiance Object Manager to check and edit each sensor grid.\
The input geometries can be generic Rhino Brep/Mesh geometries, or Pollination geometries such as rooms, room's child surfaces (aperture, door, shade), sub-surface (room's wall, or other type of faces selected by Shift+Ctrl+Click), and orphaned faces.

<figure><img src="https://user-images.githubusercontent.com/2915573/209876729-cd50c983-a1d6-413e-a1ae-e8148705cecc.gif" alt=""><figcaption></figcaption></figure>

## Options

*   **GridSize**

    space between any two sensor points. (in Rhino's unit)
*   **Offset**

    offset distance from the input geometries. (in Rhino's unit)
*   **MergeCoplanar**

    set to true to merge all selected surfaces that are coplanar to create minimum amount of sensor grids as possible. (default: false)
*   **Filter**

    filter currently selected geometries based on types (Floor, Wall, Roof, Window, Skylight, Door) if possible. (default: bySelected)
*   **ShrinkDist**

    shrink distance from the input geometries' edges. (in Rhino's unit)
*   **QuadOnly**

    set to true to only generate quad faces. (default: false)

## Useful Links

{% embed url="https://docs.pollination.solutions/user-manual/rhino-plugin/daylight-modeling/add-sensor-grid" %}

## Video Tutorials

{% embed url="https://user-images.githubusercontent.com/9031066/273817127-250e60c3-75f3-45c1-b08a-d2b8a8962281.mp4" %}
Add sensors to a Room and Room faces
{% endembed %}
