# Room New Commands

Below are the commands that create new rooms (typically by splitting, joining or filling gaps in existing rooms).

## <img src="images/fill-holes-with-rooms.svg" width="30" height="30"> Fill holes

Fill holes and gaps across the selected rooms with new rooms (or existing rooms that are adjacent to each hole).

<details>

<summary>Options</summary>

**Area Threshold**

  The area below which a hole gets merged into adjacent rooms and above which it will be filled with a new room. To fill all holes with new rooms, set the area threshold to zero. To have all holes merged into neighboring rooms, set the area threshold to a high number

**New Room Name**

  Text to set the name of newly-generated rooms. In the case of multiple holes being filled, this input will be a base name and an integer will be automatically added to the end of each new room name

</details>

---

## <img src="images/merge-with-filter.svg" width="30" height="30"> Merge Small Rooms

Merge small rooms in the selection into the larger adjacent rooms. Small rooms are always merged into the adjacent large room with which they share the most perimeter.

<details>

<summary>Options</summary>

**Area Threshold**

  The floor area below which rooms are considered small and should be merged into larger rooms of the selection.

</details>

---

## <img src="images/merge-rooms.svg" width="30" height="30"> Merge rooms

Merge several rooms into a single room. Setting a Merge Distance that is larger than 0 will allow you to merge rooms that have gaps in between them - crossing gaps up to the specified distance.

<details>

<summary>Options</summary>

**Merge Distance**

  The maximum distance between the rooms in which the rooms should be merged.

**Simplify Windows**

  Select to have the windows simplified when merging rooms.

**Join Faces**

  Select to have the coplanar walls should joined together when merging rooms.

</details>

Useful for cases where multiple rooms in a Revit model should be represented as a single zone in the energy model.

{% embed url="https://drive.google.com/open?id=1XYSAAKmYcU_iv8MBsa7OAZytVL86evNB&usp=drive_fs" %}

---

## <img src="images/split-room.svg" width="30" height="30"> Split

Split rooms or roofs by the selected lines/polylines.

<details>

<summary>Options</summary>

**Gap Distance**

  An optional distance value to introduce a gap along the line/polyline that is splitting. This should almost always be zero except when using this command to work around eQuest's lack of support for courtyard buildings. In this case, the gap distance can be used to create a gap that connects the building exterior to the courtyard.

</details>

---

## <img src="images/core-pr.svg" width="30" height="30"> Split core and perimeter

Create core and perimeter rooms for a selected room. This is particularly useful for creating models according to typical zoning practices, where each façade orientation is a separate zone.

<details>

<summary>Options</summary>

**Offset Distance**

  The distance that the perimeter of the rooms will be offset

**Air Boundary**

  Select to have the new separation walls between the core and perimeter rooms set to Air Boundary

</details>

The perimeter rooms will have a depth equal to the specified `Offset Distance` and the `Air Boundary` option lets you optionally set the boundaries between the core and perimeter rooms to an air boundary if the room being split represents an open space. It is recommended that the "Join coplanar faces" command be run before using this command.

{% embed url="https://drive.google.com/open?id=1XlQxN6N1M2LqzQdGNJ4h_Wuw39b3NXc5&usp=drive_fs" %}
Split core and perimeter
{% endembed %}

---

## <img src="images/separate-plenums.svg" width="30" height="30"> Vertically split

Split the selected rooms vertically if they are tall enough to cross multiple stories in the model.

---