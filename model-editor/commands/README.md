---
description: >-
  Below is the list of commands available in the Pollination Model Editor.
---



# Room Commands

#### ![](../../.gitbook/assets/align.svg) <mark style="background-color:yellow;">Align</mark>

Align the selected rooms' vertices to the selected lines/polylines if the room vertices lie within the specified Alignment Distance. [Read more](./me_align.md).

#### ![](../../.gitbook/assets/pull-to-room.svg) <mark style="background-color:yellow;">Pull to room</mark>

Pull the vertices of one or more rooms to the first 'target' room in the selection. The operation of pulling can be thought of as aligning the rooms to the target room's segments and then snapping to its vertices. [Read more](./me_pull_to_room.md).

#### ![](../../.gitbook/assets/snap-to-grid.svg) <mark style="background-color:yellow;">Snap to grid</mark>

Snap the selected rooms to a cartesian grid defined by a Grid Increment distance, which sets the resolution of the grid. This command is useful for IES VE modelers who need geometry on a grid for ease of edit-ability. [Read more](./me_snap_to_grid.md).

#### ![](../../.gitbook/assets/remove-short-segments.svg) <mark style="background-color:yellow;">Remove short segments</mark>

Remove the segments of the room polygon that are smaller than a certain specified Segment Distance. Use this command to remove column holes and other unwanted small segments at the edges of the rooms. [Read more](./me_remove_short_segments.md).

#### ![](../../.gitbook/assets/remove-small-holes.svg) <mark style="background-color:yellow;">Remove holes</mark>

Remove the holes inside the room that are smaller than a certain specified Area Threshold. Use this command to remove column and duct holes from inside rooms. [Read more](./me_remove_holes.md).

#### ![](../../.gitbook/assets/join-coplanar-faces.svg) <mark style="background-color:yellow;">Join coplanar faces</mark>

Join coplanar walls of the room, effectively removing colinear vertices from the room polygon. Use this command to simplify the geometry and clean up the model before running 'solve adjacency' or 'alignment' commands. [Read more](./me_join_coplanar_faces.md).

#### ![](../../.gitbook/assets/repair-windows.svg) <mark style="background-color:yellow;">Repair windows</mark>

Fix the windows of the rooms by merging the colliding windows and trimming those that extend past the parent Face. The Rectangle option can be used to further simplify non-rectangular windows into rectangular shapes. [Read more](./me_repair_windows.md).

#### ![](../../.gitbook/assets/simplify-windows.svg) <mark style="background-color:yellow;">Simplify windows</mark>

Simplify the windows and skylights of a room for either simulation speed or overall model cleanliness. [Read more](./me_simplify_windows.md).

#### ![](../../.gitbook/assets/solve-adjacency.svg) <mark style="background-color:yellow;">Solve adjacency</mark>

Solve adjacency between selected rooms by assigning interior boundary conditions where rooms touch one another [Read more](./me_solve_adjacency.md).

#### ![](../../.gitbook/assets/merge-rooms.svg) <mark style="background-color:yellow;">Merge rooms</mark>

Merge several rooms into a single room. Setting a Merge Distance that is larger than 0 will allow you to merge rooms that have gaps in between them - crossing gaps up to the specified distance. [Read more](./me_merge_rooms.md).

#### ![](../../.gitbook/assets/unite-square-duotone.svg) <mark style="background-color:yellow;">Create boundary</mark>

Create polyline boundaries around a selection of rooms. The command can return polylines for either the exterior border around the rooms or just the holes (or both). [Read more](./me_create_boundary.md).

#### ![](../../.gitbook/assets/core-pr.svg) <mark style="background-color:yellow;">Split core and perimeter</mark>

Create core and perimeter rooms for a selected room. This is particularly useful for creating models according to typical zoning practices, where each façade orientation is a separate zone [Read more](./me_split_core_and_perimeter.md).

#### ![](../../.gitbook/assets/subtract-rooms.svg) <mark style="background-color:yellow;">Subtract rooms</mark>

Subtract one room from another room. Useful for resolving colliding room geometries. [Read more](./me_subtract_rooms.md).

#### ![](../../.gitbook/assets/fill-holes-with-rooms.svg) <mark style="background-color:yellow;">Fill holes</mark>

Fill holes and gaps across the selected rooms with new rooms (or existing rooms that are adjacent to each hole) [Read more](./me_fill_holes.md).

#### ![](../../.gitbook/assets/validate-model.svg) <mark style="background-color:yellow;">Validate model</mark>

Check whether the selected rooms are valid/simulate-able. Valid models should export to any of the supported BEM engines without errors. Invalid models will have their errors presented in a table with the option to select the part of the model where the error originates so that it can be fixed. [Read more](./me_validate_model.md).

#### ![](../../.gitbook/assets/3d-preview.svg) <mark style="background-color:yellow;">3D preview</mark>

Show the selected rooms and shades in 3D. The preview shows up in a new floating window. [Read more](./me_3d_preview.md).

#### <mark style="background-color:yellow;">Auto align</mark>

Automatically align selected rooms to common axes identified across them. The command is intended to automatically perform most of the alignments that would typically be done manually. Note that having a line selected while running this command will force the generated alignment axes to be generated only in the plane of that line. [Read more](./me_auto_align.md).

#### <mark style="background-color:yellow;">Find adjacency gaps</mark>

Identify gaps smaller than a specified gap distance. Such gaps typically do not make the model invalid or un-simulate-able but they can create cases where adjacency solving fails to set interior boundary conditions where they likely should be. Small gaps can also result in sliver geometries for floors/ceilings in the case the ceiling adjacencies are solved. [Read more](./me_find_adjacency_gaps.md).

#### <mark style="background-color:yellow;">Generate alignment axes</mark>

Generate suggested alignment axes for rooms using a selected line to specify the alignment direction. All generated axes will be parallel to the selected line and will fall along the common axes of the selected rooms. [Read more](./me_generate_alignment_axes.md).

#### <mark style="background-color:yellow;">Merge Small Rooms</mark>

Merge small rooms in the selection into the larger adjacent rooms. Small rooms are always merged into the adjacent large room with which they share the most perimeter. [Read more](./me_merge_small_rooms.md).

#### <mark style="background-color:yellow;">Offset windows</mark>

Offset all windows and/or skylights by a certain distance. This is useful for translating between interfaces that expect the window frame to be included within or excluded from the geometry. [Read more](./me_offset_windows.md).

#### <mark style="background-color:yellow;">Set air boundaries</mark>

Set the adjacencies between the selected rooms to use air boundaries. Note that adjacencies should be solved between rooms before running this method in order for it to have any effect. If lines are selected while running this command, they will be used to set air boundaries for only the adjacencies that are coincident with those lines. [Read more](./me_set_air_boundaries.md).

#### <mark style="background-color:yellow;">Simplify Curved Edges</mark>

Simplify and reduce the number of vertices defining curved edges of rooms. [Read more](./me_simplify_curved_edges.md).

#### <mark style="background-color:yellow;">Split</mark>

Split rooms or roofs by the selected lines/polylines. [Read more](./me_split.md).

#### <mark style="background-color:yellow;">Vertically split</mark>

Split the selected rooms vertically if they are tall enough to cross multiple stories in the model. [Read more](./me_vertically_split.md).

# Line Commands

#### ![](../../.gitbook/assets/offset.svg) <mark style="background-color:yellow;">Offset</mark>

Offset the selected lines and/or polylines by a specified distance. [Read more](./me_offset.md).

#### ![](../../.gitbook/assets/create-room.svg) <mark style="background-color:yellow;">Create rooms</mark>

Create a room from the selected closed polylines. Set the room name and adjust the `Floor Height` and `Floor to Ceiling Height` if needed. By default, the command uses the heights of the current active story. [Read more](./me_create_rooms.md).

#### ![](../../.gitbook/assets/remove-colinear-vertices.svg) <mark style="background-color:yellow;">Remove colinear vertices</mark>

Remove colinear vertices from a polyline. [Read more](./me_remove_colinear_vertices.md).

#### ![](../../.gitbook/assets/explode-polyline.svg) <mark style="background-color:yellow;">Explode polyline</mark>

Explode a polyline into several line segments. [Read more](./me_explode_polyline.md).

#### ![](../../.gitbook/assets/join-segments.svg) <mark style="background-color:yellow;">Join segments</mark>

Join several segments into one or more polylines. [Read more](./me_join_segments.md).

# Roof Commands

#### ![](../../.gitbook/assets/prev-roof.svg) <mark style="background-color:yellow;">Preview roofs</mark>

Show the selected roofs in 3D. The 3D preview shows up in a new floating window. [Read more](./me_preview_roofs.md).

#### <mark style="background-color:yellow;">Export roofs</mark>

Export roofs to HBJSON. Use this file to edit the roofs in Pollination Rhino plugin. You can then use the import roofs to import the edited roofs back to Model Editor. [Read more](./me_export_roofs.md).

#### <mark style="background-color:yellow;">Find roof gaps</mark>

Identify gaps smaller than a specified gap distance. [Read more](./me_find_roof_gaps.md).

#### <mark style="background-color:yellow;">Find roof intersection</mark>

Find the intersection between two or more roof geometries in 3D space and draw a line (or polyline) in the scene where this intersection exists. Intersection lines will only be drawn on the first roof geometry of the selection and no result will be returned when the intersection of roof planes lies outside the boundary of the first face of the selection. So it may be necessary to adjust the order of the selection if the desired result is not obtained. [Read more](./me_find_roof_intersection.md).

#### <mark style="background-color:yellow;">Import roofs</mark>

Import roofs from a HBJSON file. Import roofs translates all the orphaned shades in the HBJSON file to roof elements. [Read more](./me_import_roofs.md).

#### <mark style="background-color:yellow;">Show tilt</mark>

Show tilt of the roof temporarily. [Read more](./me_show_tilt.md).

#### <mark style="background-color:yellow;">Roof to shade</mark>

Convert roofs to shade objects. [Read more](./me_roof_to_shade.md).

#### <mark style="background-color:yellow;">Subtract roofs</mark>

Subtract one roof part from another one. Use this command to clean up colliding roofs where faces overlap in plan and the user wants the taller of the two roof geometries in the overlap to be used. [Read more](./me_subtract_roofs.md).

# Model Commands

#### <mark style="background-color:yellow;">Multipliers to geometry</mark>

Click to convert multipliers assigned to stories into explicit room geometry. [Read more](./me_multipliers_to_geometry.md).

#### <mark style="background-color:yellow;">Auto top ground</mark>

Automatically assign top exposed properties to any rooms with no room above them and assign ground contact to all rooms of the bottom story. [Read more](./me_auto_top_ground.md).

#### <mark style="background-color:yellow;">Separate plenums</mark>

Click to convert ceiling and floor plenum depths assigned to rooms into explicit plenum room geometry. [Read more](./me_separate_plenums.md).