# Roof Commands

Below are all commands that operate on roofs.

## ![](<../../.gitbook/assets/export-roofs (1).svg>) Export roofs

Export roofs to HBJSON. Use this file to edit the roofs in Pollination Rhino plugin. You can then use the import roofs button to import the edited roofs back to Model Editor.

***

## ![](../../.gitbook/assets/find-adjacency-gaps.svg) Find roof gaps

Identify gaps smaller than a specified gap distance.

<details>

<summary>Options</summary>

**Gap Distance**

The maximum distance between two roofs that is considered an unwanted adjacency gap. Differences between roofs that are higher than this distance are considered meaningful separations between roofs that should be preserved. Typical recommended values might be around 15 cm or 6''.

</details>

***

## ![](<../../.gitbook/assets/int-roof (1).svg>) Find roof intersection

Find the intersection between two or more roof geometries in 3D space and draw a line (or polyline) in the scene where this intersection exists. Intersection lines will only be drawn on the first roof geometry of the selection and no result will be returned when the intersection of roof planes lies outside the boundary of the first face of the selection. So it may be necessary to adjust the order of the selection if the desired result is not obtained.

***

## ![](<../../.gitbook/assets/import-roofs (1).svg>) Import roofs

Import roofs from a HBJSON file. All orphaned shades in the HBJSON file are translated to roof elements.

<details>

<summary>Options</summary>

**Replace Current Roofs**

Select to have all of the roofs currently within the model replaced by the new roof geometries in the imported HBJSON file. If deselected, the roofs will simply be added to the current roof geometries in the model.

**Is Revit Sourced**

Select if the HBJSON file with roofs has been exported directly from the Revit model. If so, the roof geometry will be synchronized with the model's units and coordinate system if they have changed from the original Revit model.

</details>

***

## ![](../../.gitbook/assets/merge-roofs.svg) Merge roofs

Merge coplanar roofs together that are on the same story and touching edges.

***

## ![](<../../.gitbook/assets/prev-roof (1).svg>) Preview roofs

Show the selected roofs in 3D. The 3D preview shows up in a new floating window.

***

## ![](../../.gitbook/assets/reassign-roofs.svg) Reassign roofs

Reassign the model's roof geometries to the stories to which they are most applicable. This is useful after splitting roof geometries with story boundaries such that different roof elements are now applicable to different stories.

***

## ![](<../../.gitbook/assets/resolve-roof-overlaps (1).svg>) Resolve roof overlaps

Clean up roof geometries across the model.

***

## ![](<../../.gitbook/assets/shade-roof (1).svg>) Roof to shade

Convert roofs to shade objects.

***

## ![](<../../.gitbook/assets/show-tilt (1).svg>) Show tilt

Show tilt of the roof temporarily.

***

## ![](<../../.gitbook/assets/diff-roof (1).svg>) Subtract roofs

Subtract one roof part from another one.

***
