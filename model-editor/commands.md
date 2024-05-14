---
description: >-
  This page includes the list of model editor commands. Feel free to reach out
  on Discourse with suggestions for additional commands.
---

# Commands

## Room Commands

### Align

Align the selected rooms' vertices to the selected lines/polylines if the room vertices lie within the specified `Alignment Distance`. Using the `Snap Vertices` option will perform an additional operation that tries to snap the vertices to line/polyline vertices after running the alignment.

{% embed url="https://discourse.pollination.cloud/uploads/default/original/2X/8/8e6e3a3b509e68779943c53f7c161534f3b87806.png" %}

This command is primarily useful for fixing the misalignments between rooms, which are common in the raw export of Revit rooms. It is also useful for adjusting the exterior boundary around entire stories, enabling you to align rooms to the inside or outside wall finish instead of using the wall centerline as is typical when exporting Revit rooms. See the Create Boundary command for more information.

{% embed url="https://discourse.pollination.cloud/uploads/default/original/2X/e/ebecb887d8515bc39dab8ab9b11e7f75b312cd7d.mp4" %}
Align rooms to lines
{% endembed %}

This command is only visible when at least one room and one alignment line/polyline are selected.

### Pull to room

Pull the vertices of one or more rooms to the first "target" room in the selection. The operation of pulling can be thought of as aligning the rooms to the target room's segments and then snapping to its vertices. Using the `Coordinate Vertices` option will run an additional operation to adjust the number of vertices in the rooms that were pulled. This results in better matching of segments between the rooms like so:

{% embed url="https://discourse.pollination.cloud/uploads/default/original/2X/2/203c04e13aa5d1bda5a9e0da5897ac86b340005e.png" fullWidth="false" %}

{% embed url="https://discourse.pollination.cloud/uploads/default/original/2X/6/6a6d98e42f285051859279a07c419502d653d24f.png" %}

![pull to room multi segment lines|video](upload://xEn681GxrTslgVKeyapF4tgQwgJ.mp4)

### Snap to grid

Snap the selected rooms to a cartesian grid defined by a `Grid Increment` distance, which sets the resolution of the grid. This command is particularly useful for IES VE users who often need the model to be snapped to a grid.

![Snap to grid|video](upload://gcGR4Y6MP4ESjaxZdpKRCdf2qej.mp4)

### Remove short segments

Remove the segments of the room polygon that are smaller than a certain specified `Segment Distance`. Use this command to remove column holes and other unwanted small segments at the edges of the rooms.

![Remove Columns at the Edge|video](upload://cqLXl5zlfNCIe8AaE8W15MzBBjb.mp4)

### Remove holes

Remove the holes inside the room that are smaller than a certain specified `Area Threshold`. Use this command to remove column and duct holes from inside rooms.

![remove holes|video](upload://aPZT78bxsPzsLWY8Wc0BSuZ1alC.mp4)

### Join coplanar faces

Join coplanar walls of the room, effectively removing colinear vertices from the room polygon. Use this command to simplify the geometry and clean up the model before running "solve adjacency" or "alignment" commands.

![Join coplanar faces|video](upload://xp5JOBaN8SqQPWVM1aUrZNenIRG.mp4)

### Rebuild apertures

Rebuild the apertures of the rooms by merging the colliding apertures and trimming those that extend past the parent Face. The `Rectangle` option can be used to further simplify non-rectangular apertures into rectangular shapes.

### Solve adjacency

Solve adjacency between selected rooms by assigning interior boundary conditions where rooms touch one another. You can optionally turn off the `Ceiling Adjacency` if you are primarily interested in simulating each Story as a distinct unit with adiabatic floors and ceilings. This command will only be visible when more than one room is selected.

### Reset adjacency

Reset all of the wall boundary conditions to outdoors. Use this command to create a clean starting point for running "solve adjacency" or "alignment" commands.

### Merge rooms

Merge several rooms into a single room. Setting a `Merge Distance` that is larger than 0 will allow you to merge rooms that have gaps in between them (crossing gaps up to the specified distance). This option is particularly useful for IDA ICE users who must work with rooms that are exported at the interior wall finish.

![merge-rooms|video](upload://wr5kAqJ787ExYcSGU9CYjUgDHx4.mp4)

### Create boundary

Create polyline boundaries around a selection of rooms. The command can return polylines for either the exterior border around the rooms or just the holes (or both). You can use the generated borders for aligning the existing rooms or creating new rooms. See line commands for the full list of the available commands.

![Create boundary|video](upload://8iveUCmkZVGFrPoIncKU7IjSm8V.mp4)

### Split core and perimeter

Create core and perimeter rooms for a selected room. This is particularly useful for creating models according to typical zoning practices, where each façade orientation is a separate zone. The perimeter rooms will have a depth equal to the specified `Perimeter Offset` and the `Air Boundary` option lets you optionally set the boundaries between the core and perimeter rooms to an air boundary if the room being split represents an open space. It is recommended to clean up small edges and join coplanar faces before running this command.

![split core and perimeter|video](upload://7JDNvVBjxQ21aKDmac850qPFf53.mp4)

### Validate model

Run the validation routine for the selected rooms. Valid models should export to any of the supported BEM engines without errors. Invalid models will have their errors presented in a table with the option to zoom in on the part of the model where the error originates so that it can be fixed.

### 3D preview

Show the selected rooms in 3D. The 3D preview shows up in a new floating window.

![3D preview|video](upload://uHpAdBbHeezCidDnQEVBv8OOWiW.mp4)

## Line Commands

### Offset

Offset the selected lines and/or polylines. The `Offset Distance` can be either positive or negative and positive values will be interpreted as offsetting outwards or "to the right" while negative numbers will be offset inwards to "to the left".

![Offset|video](upload://a4n2wu0Ll95jYDXSZVg1Cf4E8eD.mp4)

### Create room

Create room from selected closed polylines. Set the room display name, and adjust the `Floor Height` and `Floor to Ceiling Height` if needed. By default, the command uses the heights of the current active story.

![Create Room|video](upload://he02wmgVr51jRgs1gcGZb08fJYk.mp4)

### Remove colinear vertices

Remove colinear vertices from a polyline.

## Upcoming commands

### Subtract rooms

Subtract one room from another room. Use this command to clean up colliding rooms by subtracting one room from another.

### Split room

Split a room into smaller rooms by using a line or polyline.

### Generate alignment lines

Generate a collection of proposed alignment lines for selected rooms by evaluating the common axes across the room polygon segments.

