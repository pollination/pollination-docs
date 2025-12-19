# Line

Below are the commands that generate lines/polylines from rooms.

## ![](<../../.gitbook/assets/unite-square-duotone (1).svg>) Create boundary

Create polyline boundaries around a selection of rooms. The command can return polylines for either the exterior border around the rooms or just the holes (or both).

<details>

<summary>Options</summary>

**Mode**

The calculation mode for creating boundaries. The options are Include Holes, Exclude Holes , and Holes Only

**Merge Distance**

The maximum distance between rooms below which the boundary will be drawn around the rooms together (instead of being separate for each room). Setting a non-zero value here will allow you to draw boundaries around rooms that have gaps in between them (crossing gaps up to the specified distance)

</details>

You can use the generated borders for aligning the existing rooms or creating new rooms. See the line commands for the full list of the available commands.

{% embed url="https://drive.google.com/open?id=1XXLZWxD-9Q2Dy1BSkQw8Iz9hK_gyKEMV&usp=drive_fs" %}
Create Boundary
{% endembed %}

***

## ![](<../../.gitbook/assets/gen-align-axes (1).svg>) Generate alignment axes

Generate suggested alignment axes for rooms using a selected line to specify the alignment direction. All generated axes will be parallel to the selected line and will fall along the common axes of the selected rooms.

<details>

<summary>Options</summary>

**Distance**

The distance with which room vertices will be aligned to common axes. This dictates the resolution with which common axes will be generated

**All Common Axes**

Select to have this command output all common axes of the rooms regardless of whether the rooms are already aligned to the axes. By default, only common axes to which the rooms are not already aligned are output

</details>

***
