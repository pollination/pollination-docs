# Room Commands

Below are all commands that operate on rooms.

## <img src="images/align.svg" width="30" height="30"> Align

Align the selected rooms' vertices to the selected lines/polylines if the room vertices lie within the specified Alignment Distance.

---

## <img src="images/auto-align.svg" width="30" height="30"> Auto align

Automatically align selected rooms to common axes identified across them. The command is intended to automatically perform most of the alignments that would typically be done manually. Note that having a line selected while running this command will force the generated alignment axes to be generated only in the plane of that line.

---

## <img src="images/auto-zone.svg" width="30" height="30"> Auto zoning

Automatically assign zones to rooms with similar properties. Properties that are used to group rooms into zones include story, orientation, and (optionally) energy programs.

---

## <img src="images/merge-coplanar.svg" width="30" height="30"> Join coplanar faces

Join coplanar walls of the room, effectively removing colinear vertices from the room polygon. Use this command to simplify the geometry and clean up the model before running 'solve adjacency' or 'alignment' commands.

---

## <img src="images/match-and-replace.svg" width="30" height="30"> Match and replace rooms

Replace the room floor plate geometry of selected rooms using the rooms of a base story in the selection. This is useful for the case that several stories with repeated room geometry exist over the building all with unique room names and window geometry. However, only one story represents the clean room floor plates such that a desired result can be achieved by simply replacing the room geometry of the other stories with that of the base story.

---

## <img src="images/pull-to-room.svg" width="30" height="30"> Pull to room

Pull the vertices of one or more rooms to the first 'target' room in the selection. The operation of pulling can be thought of as aligning the rooms to the target room's segments and then snapping to its vertices.

---

## <img src="images/remove-small-holes.svg" width="30" height="30"> Remove holes

Remove the holes inside the room that are smaller than a certain specified Area Threshold. Use this command to remove column and duct holes from inside rooms.

---

## <img src="images/remove-short-segments.svg" width="30" height="30"> Remove short segments

Remove the segments of the room polygon that are smaller than a certain specified Segment Distance. Use this command to remove column holes and other unwanted small segments at the edges of the rooms.

---

## <img src="images/simplify-curved-room.svg" width="30" height="30"> Simplify Curved Edges

Simplify and reduce the number of vertices defining curved edges of rooms.

---

## <img src="images/snap-to-grid.svg" width="30" height="30"> Snap to grid

Snap the selected rooms to a cartesian grid defined by a Grid Increment distance, which sets the resolution of the grid. This command is useful for IES VE modelers who need geometry on a grid for ease of edit-ability.

---

## <img src="images/subtract-rooms.svg" width="30" height="30"> Subtract rooms

Subtract one room from another room. Useful for resolving colliding room geometries.

---

## <img src="images/export-windows.svg" width="30" height="30"> Export openings

Export windows and doors to HBJSON. Use this file to edit the geometry in Pollination Rhino plugin. You can then use the import windows button to import the edited windows back to Model Editor.

---

## <img src="images/import-windows.svg" width="30" height="30"> Import openings

Import windows and doors from a HBJSON file, replacing the currently-assigned windows. If rooms are selected while running this command, only the windows and doors of the selected rooms will be updated.

---

## <img src="images/make-windows-flush.svg" width="30" height="30"> Make openings flush

Make the edges of nearby windows flush with one another. Useful for cleaning up overlapping windows in a way that does not merge them together like 'Repair Windows' or removing gaps between windows without offsetting all edges like 'Offset windows for frame'.

---

## <img src="images/offset-windows.svg" width="30" height="30"> Offset openings for frame

Offset the edges of all windows and/or skylights by a certain distance. Useful for translating between interfaces that expect the window frame to be included within or excluded from the geometry.

---

## <img src="images/rectangularize-windows.svg" width="30" height="30"> Rectangularize openings

Convert windows and/or skylights to rectangles. Useful for cleaning Revit-exported window families that are supposed to be rectangular.

---

## <img src="images/remove-windows.svg" width="30" height="30"> Remove small openings

Remove windows of the room that are smaller than a certain specified Area Threshold.

---

## <img src="images/repair-windows.svg" width="30" height="30"> Repair invalid openings

Fix invalid windows by merging overlapping windows together, trimming windows that extend past the parent face, and deleting self-intersecting windows

---

## <img src="images/simplify-windows.svg" width="30" height="30"> Simplify openings

Simplify and reduce the number of windows and/or skylights while maintaining the overall exterior window/skylight area. Useful for improving simulation speed without significantly changing energy use results.

---

## <img src="images/fill-holes-with-rooms.svg" width="30" height="30"> Fill holes

Fill holes and gaps across the selected rooms with new rooms (or existing rooms that are adjacent to each hole).

---

## <img src="images/merge-with-filter.svg" width="30" height="30"> Merge Small Rooms

Merge small rooms in the selection into the larger adjacent rooms. Small rooms are always merged into the adjacent large room with which they share the most perimeter.

---

## <img src="images/merge-rooms.svg" width="30" height="30"> Merge rooms

Merge several rooms into a single room. Setting a Merge Distance that is larger than 0 will allow you to merge rooms that have gaps in between them - crossing gaps up to the specified distance.

---

## <img src="images/split-room.svg" width="30" height="30"> Split

Split rooms or roofs by the selected lines/polylines.

---

## <img src="images/core-pr.svg" width="30" height="30"> Split core and perimeter

Create core and perimeter rooms for a selected room. This is particularly useful for creating models according to typical zoning practices, where each façade orientation is a separate zone.

---

## <img src="images/separate-plenums.svg" width="30" height="30"> Vertically split

Split the selected rooms vertically if they are tall enough to cross multiple stories in the model.

---

## <img src="images/air-boundaries.svg" width="30" height="30"> Set air boundaries

Set the adjacencies between the selected rooms to use air boundaries. Note that adjacencies should be solved between rooms before running this method in order for it to have any effect. If lines are selected while running this command, they will be used to set air boundaries for only the adjacencies that are coincident with those lines.

---

## <img src="images/solve-adjacency.svg" width="30" height="30"> Solve adjacency

Solve adjacency between selected rooms by assigning interior boundary conditions where rooms touch one another.

---

## <img src="images/unite-square-duotone.svg" width="30" height="30"> Create boundary

Create polyline boundaries around a selection of rooms. The command can return polylines for either the exterior border around the rooms or just the holes (or both).

---

## <img src="images/gen-align-axes.svg" width="30" height="30"> Generate alignment axes

Generate suggested alignment axes for rooms using a selected line to specify the alignment direction. All generated axes will be parallel to the selected line and will fall along the common axes of the selected rooms.

---

## <img src="images/3d-preview.svg" width="30" height="30"> 3D preview

Show the selected rooms and shades in 3D. The preview shows up in a new floating window.

---

## <img src="images/find-adjacency-gaps.svg" width="30" height="30"> Find adjacency gaps

Identify gaps smaller than a specified gap distance. Such gaps typically do not make the model invalid or un-simulate-able but they can create cases where adjacency solving fails to set interior boundary conditions where they likely should be. Small gaps can also result in sliver geometries for floors/ceilings in the case the inter-story adjacencies are solved.

---

## <img src="images/validate-model.svg" width="30" height="30"> Validate

Check whether the selected rooms are valid/simulate-able. Valid models should export to any of the supported BEM engines without errors. Invalid models will have their errors presented in a table with the option to select the part of the model where the error originates so that it can be fixed.

---

## <img src="images/validate-model.svg" width="30" height="30"> Validate model

Check whether the selected rooms are valid/simulate-able. Valid models should export to any of the supported BEM engines without errors. Invalid models will have their errors presented in a table with the option to select the part of the model where the error originates so that it can be fixed.

---

## <img src="images/reload-room.svg" width="30" height="30"> Reload Rooms from Revit

Replace rooms with updated version of the room from Revit. Existing openings will be projected onto the updated rooms based on the specified projection distance and angle tolerance.

---