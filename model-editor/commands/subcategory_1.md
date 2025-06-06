# Room Windows Commands

Below are the commands that edit the room window geometry without changing floor geometry.

## <img src="images/export-windows.svg" width="30" height="30"> Export windows

Export windows and doors to HBJSON. Use this file to edit the geometry in Pollination Rhino plugin. You can then use the import windows button to import the edited windows back to Model Editor.

---

## <img src="images/import-windows.svg" width="30" height="30"> Import windows

Import windows from a HBJSON file.

<details>

<summary>Options</summary>

**Projection Distance**

  The distance used to project the window/door geometry onto parent rooms. Set to zero to have windows/doors only be added if they are coplanar with a room wall or roof.

**Is Revit Sourced**

  Select if the HBJSON file with windows has been exported directly from the Revit model. If so, the window geometry will be synchronized with the model's units and coordinate system if they have changed from the original Revit model.

</details>

---

## <img src="images/offset-windows.svg" width="30" height="30"> Offset windows

Offset all windows and/or skylights by a certain distance. This is useful for translating between interfaces that expect the window frame to be included within or excluded from the geometry.

<details>

<summary>Options</summary>

**Offset Distance**

  Offset all windows and/or skylights by a certain distance. This is useful for translating between interfaces that expect the window frame to be included within or excluded from the geometry

**Ignore Windows**

  Select to have the windows left as they are during the offset operation

**Ignore Skylights**

  Select to have the skylights left as they are during the offset operation

</details>

---

## <img src="images/repair-windows.svg" width="30" height="30"> Repair windows

Fix the windows of the rooms by merging the colliding windows and trimming those that extend past the parent Face. The Rectangle option can be used to further simplify non-rectangular windows into rectangular shapes

<details>

<summary>Options</summary>

**Parent Edge Offset**

  A number for the distance from the parent face edges to which windows will be trimmed. Entering a non-zero number here can ensure that space is left on parent faces to account for window frames

**Small Area Threshold**

  The maximum area of a window below which it will be removed. Set to zero to keep all windows no matter their size or their validity.

**Rectangle**

  Select to have overlapping window geometries resolved by replacing them with a boundary rectangle around the overlapped group instead of boolean unioning the overlapped geometries. Useful in cases where a dozen or more geometries overlap with one another such that the unioned result is not as clean or desirable as a bounding rectangle

</details>

This command is intended to fix such issues while being faithful to the original window geometry. It trims windows that extend past their parent face and merges overlapping windows by either boolean-unioning them or replacing them with a rectangle around the group (if the `Rectangle` option is selected).

For intentionally simplifying the window geometry for either simulation speed or overall model cleanliness, see the "Simplify windows" command.

---

## <img src="images/simplify-windows.svg" width="30" height="30"> Simplify windows

Simplify the windows and skylights of a room for either simulation speed or overall model cleanliness.

<details>

<summary>Options</summary>

**Merge Distance**

  The maximum distance between rooms at which point they will be merged together. Setting a non-zero value here will allow you to merge rooms that have gaps in between them (crossing gaps up to the specified distance). This option is particularly useful for IDA-ICE users who must work with rooms that are exported at the interior wall finish

**Single Window**

  Select to have the windows simplified to a single window within the center of each wall, which matches the overall area of the original windows

**Delete Interior**

  Select to have the interior windows removed from the rooms, which can increase simulation speed in several BEM platforms

**Ignore Skylights**

  Select to have the windows left exactly as they are during the process of simplifying skylights

**Ignore Windows**

  A boolean to note if the windows should be ignored during the process of simplifying the windows

</details>

Note that this command is not intended to fix invalid or un-simulate-able windows and the "Repair windows" command should be used for these purposes.

---