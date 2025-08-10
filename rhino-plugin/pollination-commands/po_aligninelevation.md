# PO\_AlignInElevation

Align geometries (generic geometries or Pollination geometries) to elevation reference lines.\
Non-planar faces will be triangulated.

## Options

*   **Threshold**

    A distance tolerance for how far away from each grid line that a vertex should be affected and snapped to. Default 10x of document tolerance.
*   **Angle Tolerance**

    A degree number from 0 to 360 to filter each input geometry edges that have a angle difference from the grids. Input -1 to disable checking the angle tolerance. Default to the current document angle tolerance.

## See Also

* [PO\_AlignInPlan](po_aligninplan.md)
* [PO\_RemoveShortSegments](po_removeshortsegments.md)
