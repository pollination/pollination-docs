# Fill holes
<img src="images/fill-holes-with-rooms.svg" width="50" height="50"> 

Fill holes and gaps across the selected rooms with new rooms (or existing rooms that are adjacent to each hole).

## Options

* **Area Threshold**

  The area below which a hole gets merged into adjacent rooms and above which it will be filled with a new room. To fill all holes with new rooms, set the area threshold to zero. To have all holes merged into neighboring rooms, set the area threshold to a high number

* **Courtyard Threshold**

  The area above which a hole is considered a courtyard and therefore should not be filled at all. To have all holes in the selection filled regardless of how large they are, set this value to a negative number (or any number smaller than the Area Threshold).

* **New Room Name**

  Text to set the name of newly-generated rooms. In the case of multiple holes being filled, this input will be a base name and an integer will be automatically added to the end of each new room name