# Repair windows
<img src="images/repair-windows.svg" width="50" height="50"> 

Fix the windows of the rooms by merging the colliding windows and trimming those that extend past the parent Face. The Rectangle option can be used to further simplify non-rectangular windows into rectangular shapes

## Options

* **Parent Edge Offset**

  A number for the distance from the parent face edges to which windows will be trimmed. Entering a non-zero number here can ensure that space is left on parent faces to account for window frames

* **Small Area Threshold**

  The maximum area of a window below which it will be removed

* **Rectangle**

  Select to have overlapping window geometries resolved by replacing them with a boundary rectangle around the overlapped group instead of boolean unioning the overlapped geometries. Useful in cases where a dozen or more geometries overlap with one another such that the unioned result is not as clean or desirable as a bounding rectangle

## Details

This command is intended to fix such issues while being faithful to the original window geometry. It trims windows that extend past their parent face and merges overlapping windows by either boolean-unioning them or replacing them with a rectangle around the group (if the `Rectangle` option is selected).

For intentionally simplifying the window geometry for either simulation speed or overall model cleanliness, see the "Simplify windows" command.