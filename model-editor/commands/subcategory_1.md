# Room Windows Commands

Below are the commands that edit the room window geometry without changing floor geometry.

## <img src="images/export-windows.svg" width="30" height="30"> Export openings

Export windows and doors to HBJSON. Use this file to edit the geometry in Pollination Rhino plugin. You can then use the import windows button to import the edited windows back to Model Editor.

---

## <img src="images/import-windows.svg" width="30" height="30"> Import openings

Import windows and doors from a HBJSON file, replacing the currently-assigned windows. If rooms are selected while running this command, only the windows and doors of the selected rooms will be updated.

---

## <img src="images/make-windows-flush.svg" width="30" height="30"> Make openings flush

Make the edges of nearby windows flush with one another. Useful for cleaning up overlapping windows in a way that does not merge them together like 'Repair Windows' or removing gaps between windows without offsetting all edges like 'Offset windows for frame'.

---

## <img src="images/offset-windows.svg" width="30" height="30"> Offset openings for frame

Offset the edges of all windows and/or skylights by a certain distance. Useful for translating between interfaces that expect the window frame to be included within or excluded from the geometry.

---

## <img src="images/rectangularize-windows.svg" width="30" height="30"> Rectangularize openings

Convert windows and/or skylights to rectangles. Useful for cleaning Revit-exported window families that are supposed to be rectangular.

---

## <img src="images/remove-windows.svg" width="30" height="30"> Remove small openings

Remove windows of the room that are smaller than a certain specified Area Threshold.

---

## <img src="images/repair-windows.svg" width="30" height="30"> Repair invalid openings

Fix invalid windows by merging overlapping windows together, trimming windows that extend past the parent face, and deleting self-intersecting windows

---

## <img src="images/simplify-windows.svg" width="30" height="30"> Simplify openings

Simplify and reduce the number of windows and/or skylights while maintaining the overall exterior window/skylight area. Useful for improving simulation speed without significantly changing energy use results.

---