# Repair invalid windows
<img src="images/repair-windows.svg" width="50" height="50"> 

Fix invalid windows by merging overlapping windows together, trimming windows that extend past the parent face, and deleting self-intersecting windows

## Options

* **Parent Edge Offset**

  A number for the distance from the parent face edges to which windows will be trimmed. Entering a non-zero number here can ensure that space is left on parent faces to account for window frames

* **Rectangle**

  Select to have overlapping window geometries resolved by replacing them with a boundary rectangle around the overlapped group instead of boolean unioning the overlapped geometries. Useful in cases where a dozen or more geometries overlap with one another such that the unioned result is not as clean or desirable as a bounding rectangle