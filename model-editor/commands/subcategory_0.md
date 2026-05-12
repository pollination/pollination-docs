# Room Edit Commands

Below are the commands that edit room floor geometry without creating new rooms.

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