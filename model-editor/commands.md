---
description: >-
  This page includes the list of model editor commands. Feel free to reach out
  on Discourse with suggestions for additional commands.
---

# Commands

<figure><img src="../.gitbook/assets/image (3) (1).png" alt=""><figcaption><p>Model Editor Commands</p></figcaption></figure>

## Room Commands

### ![](../.gitbook/assets/align.svg) Align

<details>

<summary>Options</summary>

#### Align Distance

The maximum distance between a room vertex and the line/polyline at which point the vertex will be aligned to the line.

#### Snap Vertices

Select to snap the room vertices to the line/polyline vertices after the initial alignment operation is complete.

</details>

Align the selected rooms' vertices to the selected lines/polylines if the room vertices lie within the specified `Alignment Distance`. Using the `Snap Vertices` option will perform an additional operation that snaps the vertices to line/polyline vertices after the initial alignment operation is complete.

{% embed url="https://discourse.pollination.cloud/uploads/default/original/2X/8/8e6e3a3b509e68779943c53f7c161534f3b87806.png" %}

This command is primarily used for fixing misalignments between rooms, which are common in raw exports from Revit. It is also useful for adjusting the exterior boundary around entire stories, enabling you to align rooms to the inside or outside wall finish instead of using the wall centerline as is typical when exporting Revit rooms. See the Create Boundary command for more information.

{% embed url="https://drive.google.com/open?id=1JxeHaCoO7B52SQADS9FlJoE-4fQ7i9uJ&usp=drive_fs" %}

This command is only visible when at least one room and one alignment line/polyline are selected.

### ![](../.gitbook/assets/pull-to-room.svg) Pull to room

<details>

<summary>Options</summary>

#### Coordinate Vertices

Select to further coordinate the vertices after the initial pulling operation is complete. Coordination means that any vertices of the target room that lie within the specified distance to a pulled room but were NOT matched to a vertex on that room will be inserted into the pulled room.

#### Pull Distance

The maximum distance between a room vertex and the target room edges at which point the vertex will be pulled to the target room.

</details>

Pull the vertices of one or more rooms to the first "target" room in the selection. The operation of pulling can be thought of as aligning the rooms to the target room's segments and then snapping to its vertices. Using the `Coordinate Vertices` option will run an additional operation to adjust the number of vertices in the rooms that were pulled. This can result in better matching of segments between the rooms like so:

{% embed url="https://discourse.pollination.cloud/uploads/default/original/2X/2/203c04e13aa5d1bda5a9e0da5897ac86b340005e.png" fullWidth="false" %}

{% embed url="https://discourse.pollination.cloud/uploads/default/original/2X/6/6a6d98e42f285051859279a07c419502d653d24f.png" %}

{% embed url="https://drive.google.com/open?id=1XXNms4EwkrQteXZpxaFP7laQxpouSK74&usp=drive_fs" %}
pull to room multi segment lines
{% endembed %}

### ![](../.gitbook/assets/snap-to-grid.svg) Snap to grid

<details>

<summary>Options</summary>

#### Grid Increment

A positive number for dimension of each grid cell. This should be less than the smallest detail to resolve on the rooms. NOTE that this value can be different from the grid size in the preview.

</details>

Snap the selected rooms to a cartesian grid defined by a `Grid Increment` distance, which sets the resolution of the grid. This command is particularly useful for workflows involving IES-VE where the model must be snapped to a grid in order for it to be editable once it is inside in the virtual environment.

{% embed url="https://drive.google.com/open?id=1XiU0mR1sLE7yBO51psrl-vOsI9ne74fD&usp=drive_fs" %}
Snap to Grid
{% endembed %}

### ![](../.gitbook/assets/remove-short-segments.svg) Remove short segments

<details>

<summary>Options</summary>

#### Segment Distance

The maximum length of a segment below which it will be removed.

</details>

Remove the segments of the room polygon that are smaller than a specified `Segment Distance`. This can remove column holes and other unwanted small segments at the corners of rooms.

{% embed url="https://drive.google.com/open?id=1XZt4b8qwogVWW-4qQ5bLBV1w9Saul_nw&usp=drive_fs" %}
Remove Columns at the Edge
{% endembed %}

### ![](../.gitbook/assets/remove-small-holes.svg) Remove holes

<details>

<summary>Options</summary>

#### Area Threshold

The maximum area for a hole below which it will be removed.

</details>

Remove holes inside a room that are smaller than a specified `Area Threshold`. This can remove small column and duct holes from inside rooms.

{% embed url="https://drive.google.com/open?id=1Xnfv6pGbWf0-XdxtkmtCiZRpd79a3o0G&usp=drive_fs" %}
Remove holes
{% endembed %}

### Join coplanar faces

Join coplanar walls of the room, effectively removing colinear vertices from the room polygon. Use this command to create a clean starting point for running "Solve adjacency" or "Align" commands.

{% embed url="https://drive.google.com/open?id=1Xa9pMIRnK8V09I8LgFAQI7zbKuqrLmMb&usp=drive_fs" %}
Join Coplanar Faces
{% endembed %}

### Rebuild apertures

<details>

<summary>Options</summary>

#### Parent Edge Offset

A number for the distance from the parent face edges to which windows will be trimmed. Entering a non-zero number here can ensure that space is left on parent faces to account for window frames.

#### Rectangle

Select to have overlapping window geometries resolved by replacing them with a boundary rectangle around the overlapped group instead of boolean unioning the overlapped geometries. Useful in cases where a dozen or more geometries overlap with one another such that the unioned result is not as clean/desirable as a bounding rectangle.

</details>

Fix all issues that make the windows and skylights of a room invalid or un-simulate-able. This includes cases of overlapping window geometries and windows extending past the boundary of their parent faces. This command is intended to fix such issues while being faithful to the original window geometry. It trims windows that extend past their parent face and merges overlapping windows by either boolean-unioning them or replacing them with a rectangle around the group (if the `Rectangle` option is selected).

For intentionally simplifying the window geometry for either simulation speed or overall model cleanliness, see the "Simplify windows" command.

### ![](../.gitbook/assets/simplify-windows.svg) Simplify windows

<details>

<summary>Options</summary>

#### Single Window

Select to have the windows simplified to a single window within the center of each wall, which matches the overall area of the original windows.

#### Merge Distance

The maximum distance between window polygons at which point they will be merged into a single geometry. Typically, this value is slightly larger than the window frame and is used to merge neighboring windows together. Note that this input has no effect when the "Single Window" option is used.

#### Delete Interior

Select to have the interior windows removed from the rooms, which can increase simulation speed in several BEM platforms.

#### Ignore Skylights

Select to have the skylights left exactly as they are during the process of simplifying windows.

#### Ignore Windows

Select to have the windows left exactly as they are during the process of simplifying skylights.

</details>

Simplify the windows and skylights of a room for either simulation speed or overall model cleanliness.

Note that this command is not intended to fix invalid or un-simulate-able windows and the "Rebuild apertures" command should be used for these purposes.

### ![](../.gitbook/assets/solve-adjacency.svg) Solve adjacency

<details>

<summary>Options</summary>

#### Intersect

Select to have the walls of adjacent rooms intersected with one another before solving adjacency between them. This option should always be selected unless your input model already has the correct intersections.

#### Ceiling Adjacencies

Select to have the adjacency between the stories solved (in addition to matching walls together within each story). If this is unselected, the interior floors and ceilings of the model will be adiabatic instead of supporting heat flow from one story to another.


</details>

Solve adjacency between selected rooms by assigning interior boundary conditions where rooms touch one another. You can optionally turn off the `Ceiling Adjacency` if you are primarily interested in simulating each Story as a distinct unit with adiabatic floors and ceilings. This command will only be visible when more than one room is selected.

### ![](../.gitbook/assets/reset-adjacency.svg) Reset adjacency

Reset all of the wall boundary conditions to outdoors. Use this command to erase any existing ground or adiabatic boundary conditions assigned to walls.

### ![](../.gitbook/assets/merge-rooms.svg) Merge rooms

<details>

<summary>Options</summary>

#### Merge Distance

The maximum distance between rooms at which point they will be merged together. Setting a non-zero value here will allow you to merge rooms that have gaps in between them (crossing gaps up to the specified distance). This option is particularly useful for IDA-ICE users who must work with rooms that are exported at the interior wall finish.

#### Simplify Windows

Select to have the windows simplified when merging rooms.

#### Join Faces

Select to have the coplanar walls should joined together when merging rooms.

</details>

Merge one or more rooms into a single room. Useful for cases where multiple rooms in a Revit model should be represented as a single zone in the energy model.

{% embed url="https://drive.google.com/open?id=1XYSAAKmYcU_iv8MBsa7OAZytVL86evNB&usp=drive_fs" %}
Merge Rooms
{% endembed %}

### Create boundary

<details>

<summary>Options</summary>

#### Mode

The calculation mode for creating boundaries. The options are `Include Holes`, `Exclude Holes` , and `Holes Only`.

#### Merge Distance

The maximum distance between rooms below which the boundary will be drawn around the rooms together (instead of being separate for each room). Setting a non-zero value here will allow you to draw boundaries around rooms that have gaps in between them (crossing gaps up to the specified distance).

</details>

Create polyline boundaries around a selection of rooms. The command can return polylines for either the exterior border around the rooms or just the holes in the selection (or both). You can use the generated borders for aligning the existing rooms or creating new rooms. See the line commands for the full list of the available commands.

{% embed url="https://drive.google.com/open?id=1XXLZWxD-9Q2Dy1BSkQw8Iz9hK_gyKEMV&usp=drive_fs" %}
Create Boundary
{% endembed %}

### Split core and perimeter

<details>

<summary>Options</summary>

#### Offset Distance

The distance that the perimeter of the rooms will be offset.

#### Air Boundary

Select to have the new separation walls between the core and perimeter rooms set to `Air Boundary`.

</details>

Split a room into core and perimeter rooms. This is particularly useful for creating models according to typical zoning practices, where each façade orientation is a separate zone. The perimeter rooms will have a depth equal to the specified `Offset Distance` and the `Air Boundary` option lets you optionally set the boundaries between the core and perimeter rooms to an air boundary if the room being split represents an open space. It is recommended that the "Join coplanar faces" command be run before using this command.

{% embed url="https://drive.google.com/open?id=1XlQxN6N1M2LqzQdGNJ4h_Wuw39b3NXc5&usp=drive_fs" %}
Split core and perimeter
{% endembed %}

### ![](../.gitbook/assets/split-room.svg) Split rooms

Split the rooms using the selected lines/polylines.

### ![](../.gitbook/assets/subtract-rooms.svg) Subtract rooms

Subtract one room from another room. Useful for resolving colliding room geometries.

The first room of the selection is the room to be subtracted from and all following rooms in the selection will be used for subtraction.

### ![](../.gitbook/assets/fill-holes.svg) Fill holes

<details>

<summary>Options</summary>

#### Name

Text to set the name of the generated rooms. In the case of multiple holes being filled, this input will be a base name and an integer will be automatically added to the end of each new room name.

#### Area Threshold

The minimum area for a hole above which it will be filled with a new room. This can be used to make sure that very small holes like columns are not unintentionally filled with rooms.

</details>

Fill any holes across a selection of rooms with new rooms.


### ![](../.gitbook/assets/validate-model.svg) Validate model

Check whether the selected rooms are valid/simulate-able. Valid models will export to any of the supported BEM engines without errors. Invalid models will have their errors presented in a table with the option to zoom into each section of the model where the error originates so that it can be fixed.

{% embed url="https://drive.google.com/open?id=1K4iUHPC9lKHDfJenTkUSycjKys9rvw_j&usp=drive_fs" %}
Validate Model
{% endembed %}

### ![](../.gitbook/assets/3d-preview.svg) 3D preview

<details>

<summary>Options</summary>

#### Color by\*

A dropdown to indicate what should be used for coloring the geometry in 3D preview. The default is `Face type`. Other options are `Boundary condition`, `Program type`, `Construction` , and `HVAC`.&#x20;

\*This option is currently not available in the web-based version.

</details>

Visualize the selected rooms in 3D. The 3D preview shows up in a new floating window.

{% embed url="https://drive.google.com/open?id=1XXyLpIH1oNf8FZ4CV9fvfH15tyQ8E5Ty&usp=drive_fs" %}
3D Preview
{% endembed %}

## Line Commands

### ![](../.gitbook/assets/offset.svg) Offset

<details>

<summary>Options</summary>

#### Offset Distance

The distance that the selected line/polyline will be offset. This can be either positive or negative and positive values will be interpreted as offsetting outwards or "to the right" while negative numbers will be offset inwards or to "to the left".

#### Perimeter Polygons

Select to have the output be a series of closed perimeter polygons instead of a single offset line/polyline. Perimeter polygons can be used to split rooms into core/perimeter.

</details>

Offset the selected lines and/or polylines. The `Offset Distance` can be either positive or negative and positive values will be interpreted as offsetting outwards or "to the right" while negative numbers will be offset inwards or to "to the left". The `Perimeter Polygons` option can be used to generate polygons from the offset, which can split rooms into core/perimeter.

{% embed url="https://drive.google.com/open?id=1XnHe7jOAKEczKa-G_h015L-AFxmyh8A1&usp=drive_fs" %}
Offset
{% endembed %}

### ![](../.gitbook/assets/create-room.svg) Create rooms

<details>

<summary>Options</summary>

#### Name

Base name for the room(s). This name can be modified later in the rooms' table.

#### Use Current Story Height

Select to use the current story height for the newly created room. Unselect this option to be able to have specify the room height and floor elevation explicitly.

</details>

Create a room from the selected closed polylines. Set the room name and adjust the `Floor Height` and `Floor to Ceiling Height` if needed. By default, the command uses the heights of the current active story.

{% embed url="https://drive.google.com/open?id=1XeG30cXVSHu2TiNZN3ZKgAH351YQvlFe&usp=drive_fs" %}
Create Room
{% endembed %}

### ![](../.gitbook/assets/remove-colinear-vertices.svg) Remove colinear vertices

<details>

<summary>Options</summary>

#### Tolerance

The maximum distance between a polyline vertex and the line drawn between neighboring vertices below which it is considered colinear.

</details>

Remove colinear vertices from a polyline.

### ![](../.gitbook/assets/explode-polyline.svg) Explode polyline

Explode a polyline into several line segments.

### ![](../.gitbook/assets/join-segments.svg) Join segments

Join several segments into one or more polylines.

## Upcoming commands

### Generate alignment lines

Generate a collection of proposed alignment lines for selected rooms by evaluating the common axes across the rooms' polygon segments.

