---
description: >-
  This page covers the most common workflows that are used in the process of
  cleaning a model. Let us know if you need any additional workflows that are
  missing from this page.
---

# Workflows

## Dealing with holes

Most of the models that are exported from Revit have many holes in them. Some are holes that should not have been there like the footprint of a column in the middle or at the edge of the rooms, and some are the ones that need to be filled with a room. This is usually the case for electrical space, an elevator shaft, or an exhaust duct where architects don't place a room. This section covers how to deal with all these cases.

### Removing column holes from inside the rooms

Removing the column holes from inside the rooms is straightforward. Use the [remove holes](commands.md#remove-holes) command to remove the holes smaller than a certain area. Input the maximum area threshold as the input, and press run. You can apply the command to multiple rooms at once.

{% embed url="https://drive.google.com/file/d/1_kYb7HzS-V5kR__8yfFd2nDPi06tJ9rv/view?usp=sharing" %}

### Removing column holes on the facade

You can remove the columns from the sides of the building by either using the [Remove Short Segments](commands.md#remove-short-segments) or [Align](commands.md#align) commands. Depending on the regularity of the holes and setbacks, you may need to use the command more than once.

In most cases, you may want to run the [Join Coplanar Faces](commands.md#join-coplanar-faces) command after removing the segments to remove the unnecessary vertices from the wall.

{% embed url="https://drive.google.com/open?id=1XZt4b8qwogVWW-4qQ5bLBV1w9Saul_nw&usp=drive_fs" %}

### Adding missing rooms

You can add the missing rooms in two steps:

1. Select the rooms around the missing rooms.
2. Use the [Fill Holes](commands.md#fill-holes) command to place a room in the missing areas. The command allows you to set the basename for the newly created rooms.

Keep in mind that the hole area should be fully bounded. You might need to use the [Pull to Room](commands.md#pull-to-room) or [Align](commands.md#align) command to clean the rooms around the hole ensuring the hole is fully bound before adding a new room.

In case of a missing room on the edge of the building, we suggest inserting the rooms in Revit. You can also use alignment commands and the [Split Rooms](commands.md#split-rooms) command to fill the missing area and then split it into a new room.

{% embed url="https://drive.google.com/open?id=1_kr2VCgtq-n0W1u-7Fif6y7C-MNbLIao&usp=drive_fs" %}

## Dealing with gaps and misalignments

Gaps and misalignments between the rooms and spaces are common in models. Either it is because of the difference in the wall thickness, a slight move of the wall between the different levels, or careless use of Revit separation lines, you can see misalignments and gaps in every model. Model Editor provides you with functionalities to find the gaps and misalignments and fix them.

### Finding the gaps

You can find the gaps in the model by selecting the rooms and running the [Find Adjacency Gaps](commands.md#find-adjacency-gaps) command. Set a reasonable value for finding the unwanted gaps between the rooms. The command generates red dots where there are issues.

To delete the points:

1. Right-click on the canvas, and click on `Select all points`.
2. Click on the `Delete` button to delete the points.

{% embed url="https://drive.google.com/open?id=1_rFeXKSS4PyATZb_D2PpRDnjsJzRs8zp&usp=drive_fs" %}

### Finding orthogonality issues

Find adjacency gaps should find all the unwanted gaps in your model but that is not always enough. In some cases, the model has slightly non-orthogonal walls that are fully aligned with other walls. Use `Alt + O` to highlight those walls in your model.

{% embed url="https://drive.google.com/open?id=1_n7f7T5GkBpkykE_1dFY8HiRZPiR-Px7&usp=drive_fs" %}

### Fixing misalignments between the rooms

There are 3 different commands to help you with fixing the misalignments between the rooms:

* [Align to lines and points](commands.md#align)
* [Pull to room](commands.md#pull-to-room)
* [Subtract rooms](commands.md#subtract-rooms)

Depending on the case you may need to use one or all of these commands.

{% embed url="https://drive.google.com/open?id=1_q_t68x1LYdvxO10bLLUU2gJWkGRUNqW&usp=drive_fs" %}

{% embed url="https://drive.google.com/open?id=1_qCkYqgEhJ3wtULccb1HKiuyE5xjl3TB&usp=drive_fs" %}

{% embed url="https://drive.google.com/open?id=1XXNms4EwkrQteXZpxaFP7laQxpouSK74&usp=drive_fs" %}
Pull to Room
{% endembed %}

{% embed url="https://drive.google.com/open?id=1_rSiuGc7GnIzVDB3OE9Y06SEYNiXMQpx&usp=drive_fs" %}

## Snapping model to grid

Certain platforms including IES VE are optimized to work when every corner of every room is on a grid. If that's a requirement for your model, use the [Snap to Grid](commands.md#snap-to-grid) command. The command works for both rooms and shades.&#x20;

{% embed url="https://drive.google.com/open?id=1XiU0mR1sLE7yBO51psrl-vOsI9ne74fD&usp=drive_fs" %}

## Simplifying models

It is common for energy modelers to simplify the architectural models before exporting them as an energy model. We currently support merging several rooms together into a single room or simplifying several windows into one or multiple windows.

### Merge rooms

You can merge several rooms into a single room by selecting the rooms and using the [Merge Rooms](commands.md#merge-rooms) command. The command also provides options for simplifying the walls or the windows as part of the merge process.

{% embed url="https://drive.google.com/open?id=1_mlbM3efgGvLu_FsPAo8CcKB3rsShO99&usp=drive_fs" %}

### Simplify windows

You can simplify windows and skylights in your model using the [Simplify Windows](commands.md#simplify-windows) command.

{% embed url="https://drive.google.com/open?id=1_jHDm-RsARELTTLdQ_ZcB1TY1ZMUZ1XL&usp=drive_fs" %}

## Modifying model geometry

You can modify the model geometry in several ways. The most common workflows are creating core and perimeter models and offsetting the building boundary.

### Creating core and perimeter models

{% embed url="https://drive.google.com/open?id=1XlQxN6N1M2LqzQdGNJ4h_Wuw39b3NXc5&usp=drive_fs" %}

### Adjust floor boundary

Some modeling codes are very specific about how the boundary of the room should be located for external versus internal walls. By default, Revit locates the boundary lines in the middle of the walls for both interior and exterior walls. You can use a combination of [Create Boundary](commands.md#create-boundary), [Offset](commands.md#offset), and [Align](commands.md#align) commands to adjust the floor boundary to match the outside of the exterior walls.

{% embed url="https://drive.google.com/file/d/1_iouFk4yIS3Xu3J2WYSKvq1Gl2j34yqe/view" %}

## Modifying model metadata

### Renaming rooms

Editing the names of the rooms based on different room properties has been one of the most common requests for the Model Editor. Use the Python script editor to rename all the rooms or a selection of the rooms based on the different room properties. See [this example](python-script-editor/your-first-python-script.md#rename-the-rooms) for getting started.&#x20;

## Validating models

You can use the [Validate Model](commands.md#validate-model) command to ensure your model meets all the validation requirements. In case the model is invalid, you can use several Model Editor commands including the alignment commands, and the [Repair Windows](commands.md#repair-windows) command to validate the model.

{% embed url="https://drive.google.com/open?id=1K4iUHPC9lKHDfJenTkUSycjKys9rvw_j&usp=drive_fs" %}

