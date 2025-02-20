# ![](../../.gitbook/assets/align.svg) Align

Align the selected rooms' vertices to the selected lines/polylines if the room vertices lie within the specified Alignment Distance.

## Options

* **Distance**

  The maximum distance between a room vertex and the line or polyline at which point the vertex will be aligned to the line

* **Snap Vertices**

  Select to snap the room vertices to the line/polyline vertices after the initial alignment operation is complete

* **Constrain Edges**

  Select to have all axes of the room edges that were not pulled to the line geometry be preserved

## Details

Using the `Snap Vertices` option will perform an additional operation that snaps the vertices to line/polyline vertices after the initial alignment operation is complete.

{% embed url="https://discourse.pollination.solutions/uploads/default/original/2X/8/8e6e3a3b509e68779943c53f7c161534f3b87806.png" %}

This command is primarily used for fixing misalignments between rooms, which are common in raw exports from Revit. It is also useful for adjusting the exterior boundary around entire stories, enabling you to align rooms to the inside or outside wall finish instead of using the wall centerline as is typical when exporting Revit rooms. See the Create Boundary command for more information.

{% embed url="https://drive.google.com/open?id=1JxeHaCoO7B52SQADS9FlJoE-4fQ7i9uJ&usp=drive_fs" %}

This command is only visible when at least one room and one alignment line/polyline are selected.