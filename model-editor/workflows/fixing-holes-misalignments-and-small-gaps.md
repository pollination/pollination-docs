# Fixing Holes, Misalignments, and Small Gaps

Most of the models that are exported from Revit have many holes in them. Some are holes that should not have been there, like the footprint of a column in the middle or at the edge of the rooms, and some are holes that need to be filled in a room. This is usually the case for electrical space, an elevator shaft, or an exhaust duct, where architects don't place a room. This section covers how to deal with all these cases.

In addition, gaps and misalignments between the rooms and spaces are common in models. Either it is because of the difference in the wall thickness, a slight move of the wall between the different levels, or careless use of Revit separation lines, you can see misalignments and gaps in every model. Model Editor provides you with functionalities to find the gaps and misalignments and fix them.

One of the most useful commands is the [Auto Align](../commands/me_auto_align.md) command which combines many of the steps that are documented as separate workflows below.

{% embed url="https://www.youtube.com/watch?v=07zAuIKOxYw" %}

You can read the full announcement here:

{% embed url="https://discourse.pollination.solutions/t/model-editor-update-automating-the-tedious-cleanup-process-with-auto-align/7046" %}

## Removing column holes from inside the rooms

Removing the column holes from inside the rooms is straightforward. Use the [remove holes](../commands/#remove-holes) command to remove the holes smaller than a certain area. Input the maximum area threshold as the input, and press run. You can apply the command to multiple rooms at once.

{% embed url="https://drive.google.com/file/d/1_kYb7HzS-V5kR__8yfFd2nDPi06tJ9rv/view?usp=sharing" %}

## Removing column holes on the facade

You can remove the columns from the sides of the building by either using the [Remove Short Segments](../commands/#remove-short-segments) or [Align](../commands/#align) commands. Depending on the regularity of the holes and setbacks, you may need to use the command more than once.

In most cases, you may want to run the [Join Coplanar Faces](../commands/#join-coplanar-faces) command after removing the segments to remove the unnecessary vertices from the wall.

{% embed url="https://drive.google.com/open?id=1XZt4b8qwogVWW-4qQ5bLBV1w9Saul_nw&usp=drive_fs" %}



## Finding the gaps

You can find the gaps in the model by selecting the rooms and running the [Find Adjacency Gaps](../commands/#find-adjacency-gaps) command. Set a reasonable value for finding the unwanted gaps between the rooms. The command generates red dots where there are issues.

To delete the points:

1. Right-click on the canvas, and click on `Select all points`.
2. Click on the `Delete` button to delete the points.

{% embed url="https://drive.google.com/open?id=1_rFeXKSS4PyATZb_D2PpRDnjsJzRs8zp&usp=drive_fs" %}

## Finding orthogonality issues

Find adjacency gaps should find all the unwanted gaps in your model, but that is not always enough. In some cases, the model has slightly non-orthogonal walls that are fully aligned with other walls. Use `Alt + O` to highlight those walls in your model.

{% embed url="https://drive.google.com/open?id=1_n7f7T5GkBpkykE_1dFY8HiRZPiR-Px7&usp=drive_fs" %}

## Fixing misalignments between the rooms

There are 3 different commands to help you with fixing the misalignments between the rooms:

* [Align to lines and points](../commands/#align)
* [Pull to room](../commands/#pull-to-room)
* [Subtract rooms](../commands/#subtract-rooms)

Depending on the case, you may need to use one or all of these commands.

{% embed url="https://drive.google.com/open?id=1_q_t68x1LYdvxO10bLLUU2gJWkGRUNqW&usp=drive_fs" %}

{% embed url="https://drive.google.com/open?id=1_qCkYqgEhJ3wtULccb1HKiuyE5xjl3TB&usp=drive_fs" %}

{% embed url="https://drive.google.com/open?id=1XXNms4EwkrQteXZpxaFP7laQxpouSK74&usp=drive_fs" %}
Pull to Room
{% endembed %}

{% embed url="https://drive.google.com/open?id=1_rSiuGc7GnIzVDB3OE9Y06SEYNiXMQpx&usp=drive_fs" %}
