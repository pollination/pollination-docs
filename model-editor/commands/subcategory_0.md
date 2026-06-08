# Room Edit Commands

Below are the commands that edit room floor geometry without creating new rooms.

## <img src="images/align.svg" width="30" height="30"> Align

Align the selected rooms' vertices to the selected lines/polylines if the room vertices lie within the specified Alignment Distance.

<details>

<summary>Options</summary>

**Distance**

  The maximum distance between a room vertex and the line or polyline at which point the vertex will be aligned to the line

**Snap Method**

  The method to be used for snapping room vertices to the lines. 'Snap Vertices' will snap the room vertices to the line/polyline vertices if they lie within the distance. 'Coordinate Vertices' will perform an additional step of inserting new room vertices when line/polyline vertices lie within the distance

**Constrain Edges**

  Select to have all axes of the room edges that were not pulled to the line geometry be preserved

</details>

---

## <img src="images/auto-align.svg" width="30" height="30"> Auto align

Automatically align selected rooms to common axes identified across them. The command is intended to automatically perform most of the alignments that would typically be done manually. Note that having a line selected while running this command will force the generated alignment axes to be generated only in the plane of that line.

<details>

<summary>Options</summary>

**Distance**

  The distance with which room vertices will be aligned to common axes. No vertex in the input rooms will be moved more than this distance

**Exclude Angle**

  A positive number in degrees for the maximum difference that a geometry segment can differ from the alignment axes for it to be ignored/excluded from alignment

**Base Story Name**

  Optional text for the name of the level among the selected rooms to be used as a base for auto-aligning the other rooms in the selection. Rooms on this base story will not be edited during the alignment operation.

**Axes Only**

  Select to have this command only output the common axes of the selected rooms into the scene and not perform any auto-alignment of rooms with these axes. This can give more control over which axes are or are not used by allowing manual selection and aligning with desired axes

**Use Anchor Lines**

  Select to have the currently selected line geometry override any suggested alignment axes. This can be used to ensure that auto-aligning does not move parts of the model that are already correct.

**Constrain Edges**

  Select to have all axes of the room edges that were not pulled to the line geometry be preserved

**Group by Base Plane**

  Select to have the command group the selected rooms by the underlying base plane that best fits the room geometry before auto-aligning them. This is useful in cases where the selected rooms contain different structural grids that are at angles to one another.

</details>

---

## <img src="images/auto-zone.svg" width="30" height="30"> Auto zoning

Automatically assign zones to rooms with similar properties. Properties that are used to group rooms into zones include story, orientation, and (optionally) energy programs.

<details>

<summary>Options</summary>

**Orientation Count**

  A positive integer to set the number of orientation groups to use for zoning. Setting this to 4, for example, will result in zones being established based on the four orientations (North, East, South, West).

**North Angle**

  A number between 0 and 360 to set the clockwise north direction in degrees. (0=North, 90=East, 180=South, 270=West). Default is 0 for the world Y-axis. (North, East, South, West).

**Ignore Programs**

  Select to have any room programs ignored during the automatic zoning process in which case rooms with different programs may appear in the same zone.

</details>

---

## <img src="images/merge-coplanar.svg" width="30" height="30"> Join coplanar faces

Join coplanar walls of the room, effectively removing colinear vertices from the room polygon. Use this command to simplify the geometry and clean up the model before running 'solve adjacency' or 'alignment' commands.

---

## <img src="images/match-and-replace.svg" width="30" height="30"> Match and replace rooms

Replace the room floor plate geometry of selected rooms using the rooms of a base story in the selection. This is useful for the case that several stories with repeated room geometry exist over the building all with unique room names and window geometry. However, only one story represents the clean room floor plates such that a desired result can be achieved by simply replacing the room geometry of the other stories with that of the base story.

<details>

<summary>Options</summary>

**Base Story Name**

  Text for the name of the level in the building that represents the clean room geometry to be used as a base for all of the stories to be replaced

**Overlap Percent**

  A number between that represents the percentage of total floor area overlap between a given base room and a room in the replaced stories at which point the room will be replaced with the geometry from the base story. It is recommended that 50% be used as the lowest and most lenient overlap here given that lower numbers have the potential to match a room to two or more rooms in the base story

**Projection Distance**

  A number to be used to project the original window and door geometry back onto the wall segments of each room after the floor geometry has been replaced. If the windows/doors on the original geometry do not differ by more than this distance between the base room and the replaced room, these original windows will be preserved

**Angle Tolerance**

  Angle tolerance in degrees, which sets the maximum angle difference between the normal vectors of a  window and wall at which point the window will be projected onto the wall and assigned to it

**Remove Unmatched**

  Select to have the rooms in the selection the that are not matched to any room on the base story removed from the model. This is useful when the clean up of the base story included deletion of several small rooms, which you want to be removed from the other stories during replacement

</details>

---

## <img src="images/pull-to-room.svg" width="30" height="30"> Pull to room

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

---

## <img src="images/remove-small-holes.svg" width="30" height="30"> Remove holes

Remove the holes inside the room that are smaller than a certain specified Area Threshold. Use this command to remove column and duct holes from inside rooms.

<details>

<summary>Options</summary>

**Area Threshold**

  The maximum area for a hole below which it will be removed

</details>

---

## <img src="images/remove-short-segments.svg" width="30" height="30"> Remove short segments

Remove the segments of the room polygon that are smaller than a certain specified Segment Distance. Use this command to remove column holes and other unwanted small segments at the edges of the rooms.

<details>

<summary>Options</summary>

**Segment Distance**

  The maximum length of a segment below which it will be removed

</details>

---

## <img src="images/simplify-curved-room.svg" width="30" height="30"> Simplify Curved Edges

Simplify and reduce the number of vertices defining curved edges of rooms.

<details>

<summary>Options</summary>

**Deviation Distance**

  The distance that a curved part of the room is allowed to differ from a straight line. Lower tolerance values correspond to a higher resolution of curvature with more vertices

</details>

---

## <img src="images/snap-to-grid.svg" width="30" height="30"> Snap to grid

Snap the selected rooms to a cartesian grid defined by a Grid Increment distance, which sets the resolution of the grid. This command is useful for IES VE modelers who need geometry on a grid for ease of edit-ability.

<details>

<summary>Options</summary>

**Grid Increment**

  A positive number for dimension of each grid cell. This should be less than the smallest detail to resolve on the rooms. NOTE that this value can be different from the grid size in the preview

**Exclude Angle**

  A positive number in degrees for the maximum difference that a geometry segment can differ from the grid for it to be ignored/excluded from snapping. Setting the exclude angle to zero will guarantee that all geometry is snapped to the grid. However, this may produce jagged geometries, particularly when there are parts of a geometry that are not intended to be aligned with a grid

</details>

---

## <img src="images/subtract-rooms.svg" width="30" height="30"> Subtract rooms

Subtract one room from another room. Useful for resolving colliding room geometries.

---