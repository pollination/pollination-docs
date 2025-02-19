# Commands
Below is the list of commands available in the Pollination Model Editor.

# Room Commands

#### ![](../../.gitbook/assets/align.svg#thumbnail) **Align**

Align the selected rooms' vertices to the selected lines/polylines if the room vertices lie within the specified Alignment Distance. [Read more](./me_align.md).

#### ![](../../.gitbook/assets/auto-align.svg#thumbnail) **Auto align**

Automatically align selected rooms to common axes identified across them. The command is intended to automatically perform most of the alignments that would typically be done manually. Note that having a line selected while running this command will force the generated alignment axes to be generated only in the plane of that line. [Read more](./me_auto_align.md).

#### ![](../../.gitbook/assets/merge-coplanar.svg#thumbnail) **Join coplanar faces**

Join coplanar walls of the room, effectively removing colinear vertices from the room polygon. Use this command to simplify the geometry and clean up the model before running 'solve adjacency' or 'alignment' commands. [Read more](./me_join_coplanar_faces.md).

#### ![](../../.gitbook/assets/pull-to-room.svg#thumbnail) **Pull to room**

Pull the vertices of one or more rooms to the first 'target' room in the selection. The operation of pulling can be thought of as aligning the rooms to the target room's segments and then snapping to its vertices. [Read more](./me_pull_to_room.md).

#### ![](../../.gitbook/assets/remove-small-holes.svg#thumbnail) **Remove holes**

Remove the holes inside the room that are smaller than a certain specified Area Threshold. Use this command to remove column and duct holes from inside rooms. [Read more](./me_remove_holes.md).

#### ![](../../.gitbook/assets/remove-short-segments.svg#thumbnail) **Remove short segments**

Remove the segments of the room polygon that are smaller than a certain specified Segment Distance. Use this command to remove column holes and other unwanted small segments at the edges of the rooms. [Read more](./me_remove_short_segments.md).

#### ![](../../.gitbook/assets/simplify-curved-room.svg#thumbnail) **Simplify Curved Edges**

Simplify and reduce the number of vertices defining curved edges of rooms. [Read more](./me_simplify_curved_edges.md).

#### ![](../../.gitbook/assets/snap-to-grid.svg#thumbnail) **Snap to grid**

Snap the selected rooms to a cartesian grid defined by a Grid Increment distance, which sets the resolution of the grid. This command is useful for IES VE modelers who need geometry on a grid for ease of edit-ability. [Read more](./me_snap_to_grid.md).

#### ![](../../.gitbook/assets/subtract-rooms.svg#thumbnail) **Subtract rooms**

Subtract one room from another room. Useful for resolving colliding room geometries. [Read more](./me_subtract_rooms.md).

#### ![](../../.gitbook/assets/offset-windows.svg#thumbnail) **Offset windows**

Offset all windows and/or skylights by a certain distance. This is useful for translating between interfaces that expect the window frame to be included within or excluded from the geometry. [Read more](./me_offset_windows.md).

#### ![](../../.gitbook/assets/repair-windows.svg#thumbnail) **Repair windows**

Fix the windows of the rooms by merging the colliding windows and trimming those that extend past the parent Face. The Rectangle option can be used to further simplify non-rectangular windows into rectangular shapes. [Read more](./me_repair_windows.md).

#### ![](../../.gitbook/assets/simplify-windows.svg#thumbnail) **Simplify windows**

Simplify the windows and skylights of a room for either simulation speed or overall model cleanliness. [Read more](./me_simplify_windows.md).

#### ![](../../.gitbook/assets/fill-holes-with-rooms.svg#thumbnail) **Fill holes**

Fill holes and gaps across the selected rooms with new rooms (or existing rooms that are adjacent to each hole) [Read more](./me_fill_holes.md).

#### ![](../../.gitbook/assets/merge-with-filter.svg#thumbnail) **Merge Small Rooms**

Merge small rooms in the selection into the larger adjacent rooms. Small rooms are always merged into the adjacent large room with which they share the most perimeter. [Read more](./me_merge_small_rooms.md).

#### ![](../../.gitbook/assets/merge-rooms.svg#thumbnail) **Merge rooms**

Merge several rooms into a single room. Setting a Merge Distance that is larger than 0 will allow you to merge rooms that have gaps in between them - crossing gaps up to the specified distance. [Read more](./me_merge_rooms.md).

#### ![](../../.gitbook/assets/split-room.svg#thumbnail) **Split**

Split rooms or roofs by the selected lines/polylines. [Read more](./me_split.md).

#### ![](../../.gitbook/assets/core-pr.svg#thumbnail) **Split core and perimeter**

Create core and perimeter rooms for a selected room. This is particularly useful for creating models according to typical zoning practices, where each façade orientation is a separate zone [Read more](./me_split_core_and_perimeter.md).

#### ![](../../.gitbook/assets/separate-plenums.svg#thumbnail) **Vertically split**

Split the selected rooms vertically if they are tall enough to cross multiple stories in the model. [Read more](./me_vertically_split.md).

#### ![](../../.gitbook/assets/air-boundaries.svg#thumbnail) **Set air boundaries**

Set the adjacencies between the selected rooms to use air boundaries. Note that adjacencies should be solved between rooms before running this method in order for it to have any effect. If lines are selected while running this command, they will be used to set air boundaries for only the adjacencies that are coincident with those lines. [Read more](./me_set_air_boundaries.md).

#### ![](../../.gitbook/assets/solve-adjacency.svg#thumbnail) **Solve adjacency**

Solve adjacency between selected rooms by assigning interior boundary conditions where rooms touch one another [Read more](./me_solve_adjacency.md).

#### ![](../../.gitbook/assets/unite-square-duotone.svg#thumbnail) **Create boundary**

Create polyline boundaries around a selection of rooms. The command can return polylines for either the exterior border around the rooms or just the holes (or both). [Read more](./me_create_boundary.md).

#### ![](../../.gitbook/assets/gen-align-axes.svg#thumbnail) **Generate alignment axes**

Generate suggested alignment axes for rooms using a selected line to specify the alignment direction. All generated axes will be parallel to the selected line and will fall along the common axes of the selected rooms. [Read more](./me_generate_alignment_axes.md).

#### ![](../../.gitbook/assets/3d-preview.svg#thumbnail) **3D preview**

Show the selected rooms and shades in 3D. The preview shows up in a new floating window. [Read more](./me_3d_preview.md).

#### ![](../../.gitbook/assets/find-adjacency-gaps.svg#thumbnail) **Find adjacency gaps**

Identify gaps smaller than a specified gap distance. Such gaps typically do not make the model invalid or un-simulate-able but they can create cases where adjacency solving fails to set interior boundary conditions where they likely should be. Small gaps can also result in sliver geometries for floors/ceilings in the case the ceiling adjacencies are solved. [Read more](./me_find_adjacency_gaps.md).

#### **Floor area change**

Visualize the change in floor area that has happened as a result of editing operations. [Read more](./me_floor_area_change.md).

#### ![](../../.gitbook/assets/validate-model.svg#thumbnail) **Validate model**

Check whether the selected rooms are valid/simulate-able. Valid models should export to any of the supported BEM engines without errors. Invalid models will have their errors presented in a table with the option to select the part of the model where the error originates so that it can be fixed. [Read more](./me_validate_model.md).

# Line Commands

#### ![](../../.gitbook/assets/create-room.svg#thumbnail) **Create rooms**

Create a room from the selected closed polylines. Set the room name and adjust the `Floor Height` and `Floor to Ceiling Height` if needed. By default, the command uses the heights of the current active story. [Read more](./me_create_rooms.md).

#### ![](../../.gitbook/assets/explode-polyline.svg#thumbnail) **Explode polyline**

Explode a polyline into several line segments. [Read more](./me_explode_polyline.md).

#### ![](../../.gitbook/assets/join-segments.svg#thumbnail) **Join segments**

Join several segments into one or more polylines. [Read more](./me_join_segments.md).

#### ![](../../.gitbook/assets/offset.svg#thumbnail) **Offset**

Offset the selected lines and/or polylines by a specified distance. [Read more](./me_offset.md).

#### ![](../../.gitbook/assets/remove-colinear-vertices.svg#thumbnail) **Remove colinear vertices**

Remove colinear vertices from a polyline. [Read more](./me_remove_colinear_vertices.md).

# Roof Commands

#### ![](../../.gitbook/assets/export-roofs.svg#thumbnail) **Export roofs**

Export roofs to HBJSON. Use this file to edit the roofs in Pollination Rhino plugin. You can then use the import roofs to import the edited roofs back to Model Editor. [Read more](./me_export_roofs.md).

#### ![](../../.gitbook/assets/find-adjacency-gaps.svg#thumbnail) **Find roof gaps**

Identify gaps smaller than a specified gap distance. [Read more](./me_find_roof_gaps.md).

#### ![](../../.gitbook/assets/int-roof.svg#thumbnail) **Find roof intersection**

Find the intersection between two or more roof geometries in 3D space and draw a line (or polyline) in the scene where this intersection exists. Intersection lines will only be drawn on the first roof geometry of the selection and no result will be returned when the intersection of roof planes lies outside the boundary of the first face of the selection. So it may be necessary to adjust the order of the selection if the desired result is not obtained. [Read more](./me_find_roof_intersection.md).

#### ![](../../.gitbook/assets/import-roofs.svg#thumbnail) **Import roofs**

Import roofs from a HBJSON file. Import roofs translates all the orphaned shades in the HBJSON file to roof elements. [Read more](./me_import_roofs.md).

#### ![](../../.gitbook/assets/prev-roof.svg#thumbnail) **Preview roofs**

Show the selected roofs in 3D. The 3D preview shows up in a new floating window. [Read more](./me_preview_roofs.md).

#### ![](../../.gitbook/assets/resolve-roof-overlaps.svg#thumbnail) **Resolve roof overlaps**

Clean up roof geometries across the model. [Read more](./me_resolve_roof_overlaps.md).

#### ![](../../.gitbook/assets/shade-roof.svg#thumbnail) **Roof to shade**

Convert roofs to shade objects. [Read more](./me_roof_to_shade.md).

#### ![](../../.gitbook/assets/show-tilt.svg#thumbnail) **Show tilt**

Show tilt of the roof temporarily. [Read more](./me_show_tilt.md).

#### ![](../../.gitbook/assets/diff-roof.svg#thumbnail) **Subtract roofs**

Subtract one roof part from another one. Use this command to clean up colliding roofs where faces overlap in plan and the user wants the taller of the two roof geometries in the overlap to be used. [Read more](./me_subtract_roofs.md).

# Model Commands

#### ![](../../.gitbook/assets/auto-top-ground.svg#thumbnail) **Auto top ground**

Automatically assign top exposed properties to any rooms with no room above them and assign ground contact to all rooms of the bottom story. [Read more](./me_auto_top_ground.md).

#### **Change units**

Change units and/or tolerance. [Read more](./me_change_units.md).

#### ![](../../.gitbook/assets/convert-to-room2d.svg#thumbnail) **Convert to room2D**

Convert a room3D to a room2D. Room3D are not editable. [Read more](./me_convert_to_room2d.md).

#### ![](../../.gitbook/assets/multipliers-to-geo.svg#thumbnail) **Multipliers to geometry**

Click to convert multipliers assigned to stories into explicit room geometry. [Read more](./me_multipliers_to_geometry.md).

#### ![](../../.gitbook/assets/separate-plenums.svg#thumbnail) **Separate plenums**

Click to convert ceiling and floor plenum depths assigned to rooms into explicit plenum room geometry. [Read more](./me_separate_plenums.md).

<style>
img[src*="#thumbnail"] {
   width:20px;
   height:20px;
}
</style>