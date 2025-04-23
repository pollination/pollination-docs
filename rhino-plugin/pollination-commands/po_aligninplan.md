# PO\_AlignInPlan

Align geometries (generic geometries or Pollination geometries) to a grid system. Non-planar faces will be triangulated.

<figure><img src="https://user-images.githubusercontent.com/9031066/211238032-5833de73-ac07-48e7-8bb7-d3289a81649a.gif" alt=""><figcaption><p>This command automatically triangulates non-planar surfaces.</p></figcaption></figure>

{% embed url="https://drive.google.com/file/d/1GQwN4L0hVmVsVX0nDVwAIOQPWdJrlVCw/view" %}

## Options

*   **Threshold**

    A distance tolerance for how far away from each grid line that a vertex should be affected and snapped to. Default 10x of document tolerance.
*   **Angle Tolerance**

    A degree number from 0 to 360 to filter each input geometry edges that have a angle difference from the grids. Input -1 to disable checking the angle tolerance. Default to the current document angle tolerance.
*   **Snap Corners**

    snap all vertices within the range of threshold to a closest corner (end point), instead of perpendicular to the grid lines.

## See Also

* [PO\_AlignToRoom](po_aligntoroom.md)
* [PO\_RemoveShortSegments](po_removeshortsegments.md)
* [PO\_AlignInElevation](po_aligninelevation.md)

## Video Tutorials

{% embed url="https://youtu.be/GrH6br4DQrg" %}
Fix Models with Alignment Errors
{% endembed %}
