---
description: >-
  This page includes the list of model editor commands. Feel free to reach out
  on Discourse with suggestions for additional commands.
---

# Commands

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption><p>Model Editor Commands</p></figcaption></figure>

## Room Commands

### Align

Align the selected rooms' vertices to the selected lines/polylines if the room vertices lie within the specified `Alignment Distance`. Using the `Snap Vertices` option will perform an additional operation that tries to snap the vertices to line/polyline vertices after running the alignment.

{% embed url="https://discourse.pollination.cloud/uploads/default/original/2X/8/8e6e3a3b509e68779943c53f7c161534f3b87806.png" %}

This command is primarily useful for fixing the misalignments between rooms, which are common in the raw export of Revit rooms. It is also useful for adjusting the exterior boundary around entire stories, enabling you to align rooms to the inside or outside wall finish instead of using the wall centerline as is typical when exporting Revit rooms. See the Create Boundary command for more information.

{% embed url="https://drive.google.com/open?id=1XSuB7fxBHFProkxYEnD0t5r0vHvfw-yC&usp=drive_fs" %}

This command is only visible when at least one room and one alignment line/polyline are selected.

### Pull to room

Pull the vertices of one or more rooms to the first "target" room in the selection. The operation of pulling can be thought of as aligning the rooms to the target room's segments and then snapping to its vertices. Using the `Coordinate Vertices` option will run an additional operation to adjust the number of vertices in the rooms that were pulled. This results in better matching of segments between the rooms like so:

{% embed url="https://discourse.pollination.cloud/uploads/default/original/2X/2/203c04e13aa5d1bda5a9e0da5897ac86b340005e.png" fullWidth="false" %}

{% embed url="https://discourse.pollination.cloud/uploads/default/original/2X/6/6a6d98e42f285051859279a07c419502d653d24f.png" %}

{% embed url="https://drive.google.com/open?id=1XXNms4EwkrQteXZpxaFP7laQxpouSK74&usp=drive_fs" %}
pull to room multi segment lines
{% endembed %}

### Snap to grid

Snap the selected rooms to a cartesian grid defined by a `Grid Increment` distance, which sets the resolution of the grid. This command is particularly useful for IES VE users who often need the model to be snapped to a grid.

{% embed url="https://drive.google.com/open?id=1XiU0mR1sLE7yBO51psrl-vOsI9ne74fD&usp=drive_fs" %}
Snap to Grid
{% endembed %}

### Remove short segments

Remove the segments of the room polygon that are smaller than a certain specified `Segment Distance`. Use this command to remove column holes and other unwanted small segments at the edges of the rooms.

{% embed url="https://drive.google.com/open?id=1XZt4b8qwogVWW-4qQ5bLBV1w9Saul_nw&usp=drive_fs" %}
Remove Columns at the Edge
{% endembed %}

### Remove holes

Remove the holes inside the room that are smaller than a certain specified `Area Threshold`. Use this command to remove column and duct holes from inside rooms.

{% embed url="https://drive.google.com/open?id=1Xnfv6pGbWf0-XdxtkmtCiZRpd79a3o0G&usp=drive_fs" %}
Remove holes
{% endembed %}

### Join coplanar faces

Join coplanar walls of the room, effectively removing colinear vertices from the room polygon. Use this command to simplify the geometry and clean up the model before running "solve adjacency" or "alignment" commands.

{% embed url="https://drive.google.com/open?id=1Xa9pMIRnK8V09I8LgFAQI7zbKuqrLmMb&usp=drive_fs" %}
Join Coplanar Faces
{% endembed %}

### Rebuild apertures

Rebuild the apertures of the rooms by merging the colliding apertures and trimming those that extend past the parent Face. The `Rectangle` option can be used to further simplify non-rectangular apertures into rectangular shapes.

### Solve adjacency

Solve adjacency between selected rooms by assigning interior boundary conditions where rooms touch one another. You can optionally turn off the `Ceiling Adjacency` if you are primarily interested in simulating each Story as a distinct unit with adiabatic floors and ceilings. This command will only be visible when more than one room is selected.

### Reset adjacency

Reset all of the wall boundary conditions to outdoors. Use this command to create a clean starting point for running "solve adjacency" or "alignment" commands.

### Merge rooms

Merge several rooms into a single room. Setting a `Merge Distance` that is larger than 0 will allow you to merge rooms that have gaps in between them (crossing gaps up to the specified distance). This option is particularly useful for IDA ICE users who must work with rooms that are exported at the interior wall finish.

{% embed url="https://drive.google.com/open?id=1XYSAAKmYcU_iv8MBsa7OAZytVL86evNB&usp=drive_fs" %}
Merge Rooms
{% endembed %}

### Create boundary

Create polyline boundaries around a selection of rooms. The command can return polylines for either the exterior border around the rooms or just the holes (or both). You can use the generated borders for aligning the existing rooms or creating new rooms. See line commands for the full list of the available commands.

{% embed url="https://drive.google.com/open?id=1XXLZWxD-9Q2Dy1BSkQw8Iz9hK_gyKEMV&usp=drive_fs" %}
Create Boundary
{% endembed %}

### Split core and perimeter

Create core and perimeter rooms for a selected room. This is particularly useful for creating models according to typical zoning practices, where each façade orientation is a separate zone. The perimeter rooms will have a depth equal to the specified `Perimeter Offset` and the `Air Boundary` option lets you optionally set the boundaries between the core and perimeter rooms to an air boundary if the room being split represents an open space. It is recommended to clean up small edges and join coplanar faces before running this command.

{% embed url="https://drive.google.com/open?id=1XlQxN6N1M2LqzQdGNJ4h_Wuw39b3NXc5&usp=drive_fs" %}
Split core and perimeter
{% endembed %}

### Validate model

Run the validation routine for the selected rooms. Valid models should export to any of the supported BEM engines without errors. Invalid models will have their errors presented in a table with the option to zoom in on the part of the model where the error originates so that it can be fixed.

### 3D preview

Show the selected rooms in 3D. The 3D preview shows up in a new floating window.

{% embed url="https://drive.google.com/open?id=1XXyLpIH1oNf8FZ4CV9fvfH15tyQ8E5Ty&usp=drive_fs" %}
3D Preview
{% endembed %}

## Line Commands

### Offset

Offset the selected lines and/or polylines. The `Offset Distance` can be either positive or negative and positive values will be interpreted as offsetting outwards or "to the right" while negative numbers will be offset inwards to "to the left".

{% embed url="https://drive.google.com/open?id=1XnHe7jOAKEczKa-G_h015L-AFxmyh8A1&usp=drive_fs" %}
Offset
{% endembed %}

### Create room

Create room from selected closed polylines. Set the room display name, and adjust the `Floor Height` and `Floor to Ceiling Height` if needed. By default, the command uses the heights of the current active story.

{% embed url="https://drive.google.com/open?id=1XeG30cXVSHu2TiNZN3ZKgAH351YQvlFe&usp=drive_fs" %}
Create Room
{% endembed %}

### Remove colinear vertices

Remove colinear vertices from a polyline.

## Upcoming commands

### Subtract rooms

Subtract one room from another room. Use this command to clean up colliding rooms by subtracting one room from another.

### Split room

Split a room into smaller rooms by using a line or polyline.

### Generate alignment lines

Generate a collection of proposed alignment lines for selected rooms by evaluating the common axes across the room polygon segments.

