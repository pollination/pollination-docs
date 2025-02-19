# ![](../../.gitbook/assets/fill-holes-with-rooms.svg#thumbnail) Fill holes

Fill holes and gaps across the selected rooms with new rooms (or existing rooms that are adjacent to each hole)

## Options

* **Area Threshold**

  The area below which a hole gets merged into adjacent rooms and above which it will be filled with a new room. To fill all holes with new rooms, set the area threshold to zero. To have all holes merged into neighboring rooms, set the area threshold to a high number

* **New Room Name**

  Text to set the name of newly-generated rooms. In the case of multiple holes being filled, this input will be a base name and an integer will be automatically added to the end of each new room name

<style>
img[src*="#thumbnail"] {
   width:50px;
   height:50px;
}
</style>