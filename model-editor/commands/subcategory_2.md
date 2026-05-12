# Room New Commands

Below are the commands that create new rooms (typically by splitting, joining or filling gaps in existing rooms).

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