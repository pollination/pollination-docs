# Room Edit Commands

## ![](../../.gitbook/assets/align.svg#thumbnail) Align

Align the selected rooms' vertices to the selected lines/polylines if the room vertices lie within the specified Alignment Distance.

<details>

<summary>Options</summary>

**Distance**

  The maximum distance between a room vertex and the line or polyline at which point the vertex will be aligned to the line

**Snap Vertices**

  Select to snap the room vertices to the line/polyline vertices after the initial alignment operation is complete

**Constrain Edges**

  Select to have all axes of the room edges that were not pulled to the line geometry be preserved

</details>

Using the `Snap Vertices` option will perform an additional operation that snaps the vertices to line/polyline vertices after the initial alignment operation is complete.

{% embed url="https://discourse.pollination.solutions/uploads/default/original/2X/8/8e6e3a3b509e68779943c53f7c161534f3b87806.png" %}

This command is primarily used for fixing misalignments between rooms, which are common in raw exports from Revit. It is also useful for adjusting the exterior boundary around entire stories, enabling you to align rooms to the inside or outside wall finish instead of using the wall centerline as is typical when exporting Revit rooms. See the Create Boundary command for more information.

{% embed url="https://drive.google.com/open?id=1JxeHaCoO7B52SQADS9FlJoE-4fQ7i9uJ&usp=drive_fs" %}

This command is only visible when at least one room and one alignment line/polyline are selected.

---

## ![](../../.gitbook/assets/auto-align.svg#thumbnail) Auto align

Automatically align selected rooms to common axes identified across them. The command is intended to automatically perform most of the alignments that would typically be done manually. Note that having a line selected while running this command will force the generated alignment axes to be generated only in the plane of that line.

<details>

<summary>Options</summary>

**Distance**

  The distance with which room vertices will be aligned to common axes. No vertex in the input rooms will be moved more than this distance

**Exclude Angle**

  A positive number in degrees for the maximum difference that a geometry segment can differ from the alignment axes for it to be ignored/excluded from alignment

**Axes Only**

  Select to have this command only output the common axes of the selected rooms into the scene and not perform any auto-alignment of rooms with these axes. This can give more control over which axes are or are not used by allowing manual selection and aligning with desired axes

</details>

---

## ![](../../.gitbook/assets/merge-coplanar.svg#thumbnail) Join coplanar faces

Join coplanar walls of the room, effectively removing colinear vertices from the room polygon. Use this command to simplify the geometry and clean up the model before running 'solve adjacency' or 'alignment' commands.

{% embed url="https://drive.google.com/open?id=1Xa9pMIRnK8V09I8LgFAQI7zbKuqrLmMb&usp=drive_fs" %}
Join Coplanar Faces
{% endembed %}

---

## ![](../../.gitbook/assets/pull-to-room.svg#thumbnail) Pull to room

Pull the vertices of one or more rooms to the first 'target' room in the selection. The operation of pulling can be thought of as aligning the rooms to the target room's segments and then snapping to its vertices.

<details>

<summary>Options</summary>

**Pull Distance**

  The maximum distance between a room vertex and the target room edges at which point the vertex will be pulled to the target room

**Coordinate Vertices**

  Select to further coordinate the vertices after the initial pulling operation is complete. Coordination means that any vertices of the target room that lie within the specified distance to a pulled room but were NOT matched to a vertex on that room will be inserted into the pulled room

**Constrain Edges**

  Select to have all axes of the room edges that were not pulled to the adjacent room be preserved

**Invert Selection**

  Select to have the command pull the first room in the selection to all other rooms in the selection. This is the inverse of the default behavior, which uses the first room in the selection as a target and then pulls all following rooms to it

</details>

Using the `Coordinate Vertices` option will run an additional operation to adjust the number of vertices in the rooms that were pulled. This can result in better matching of segments between the rooms like so:

{% embed url="https://discourse.pollination.solutions/uploads/default/original/2X/2/203c04e13aa5d1bda5a9e0da5897ac86b340005e.png" fullWidth="false" %}

{% embed url="https://discourse.pollination.solutions/uploads/default/original/2X/6/6a6d98e42f285051859279a07c419502d653d24f.png" %}

{% embed url="https://drive.google.com/open?id=1XXNms4EwkrQteXZpxaFP7laQxpouSK74&usp=drive_fs" %}
pull to room multi segment lines
{% endembed %}

---

## ![](../../.gitbook/assets/remove-small-holes.svg#thumbnail) Remove holes

Remove the holes inside the room that are smaller than a certain specified Area Threshold. Use this command to remove column and duct holes from inside rooms.

<details>

<summary>Options</summary>

**Area Threshold**

  The maximum area for a hole below which it will be removed

</details>

{% embed url="https://drive.google.com/open?id=1Xnfv6pGbWf0-XdxtkmtCiZRpd79a3o0G&usp=drive_fs" %}
Remove holes
{% endembed %}

---

## ![](../../.gitbook/assets/remove-short-segments.svg#thumbnail) Remove short segments

Remove the segments of the room polygon that are smaller than a certain specified Segment Distance. Use this command to remove column holes and other unwanted small segments at the edges of the rooms.

<details>

<summary>Options</summary>

**Segment Distance**

  The maximum length of a segment below which it will be removed

</details>

{% embed url="https://drive.google.com/open?id=1XZt4b8qwogVWW-4qQ5bLBV1w9Saul_nw&usp=drive_fs" %}
Remove Columns at the Edge
{% endembed %}

---

## ![](../../.gitbook/assets/simplify-curved-room.svg#thumbnail) Simplify Curved Edges

Simplify and reduce the number of vertices defining curved edges of rooms.

<details>

<summary>Options</summary>

**Deviation Distance**

  The distance that a curved part of the room is allowed to differ from a straight line. Lower tolerance values correspond to a higher resolution of curvature with more vertices

</details>

---

## ![](../../.gitbook/assets/snap-to-grid.svg#thumbnail) Snap to grid

Snap the selected rooms to a cartesian grid defined by a Grid Increment distance, which sets the resolution of the grid. This command is useful for IES VE modelers who need geometry on a grid for ease of edit-ability.

<details>

<summary>Options</summary>

**Grid Increment**

  A positive number for dimension of each grid cell. This should be less than the smallest detail to resolve on the rooms. NOTE that this value can be different from the grid size in the preview

**Exclude Angle**

  A positive number in degrees for the maximum difference that a geometry segment can differ from the grid for it to be ignored/excluded from snapping. Setting the exclude angle to zero will guarantee that all geometry is snapped to the grid. However, this may produce jagged geometries, particularly when there are parts of a geometry that are not intended to be aligned with a grid

</details>

{% embed url="https://drive.google.com/open?id=1XiU0mR1sLE7yBO51psrl-vOsI9ne74fD&usp=drive_fs" %}
Snap to Grid
{% endembed %}

---

## ![](../../.gitbook/assets/subtract-rooms.svg#thumbnail) Subtract rooms

Subtract one room from another room. Useful for resolving colliding room geometries.

The first room of the selection is the room to be subtracted from and all following rooms in the selection will be used for subtraction.

---

<style>
img[src*="#thumbnail"] {
   width:30px;
   height:30px;
}
</style>