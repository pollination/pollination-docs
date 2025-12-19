# Split core and perimeter

![](<../../.gitbook/assets/core-pr (1).svg>)

Create core and perimeter rooms for a selected room. This is particularly useful for creating models according to typical zoning practices, where each façade orientation is a separate zone.

## Options

*   **Offset Distance**

    The distance that the perimeter of the rooms will be offset
*   **Air Boundary**

    Select to have the new separation walls between the core and perimeter rooms set to Air Boundary

## Details

The perimeter rooms will have a depth equal to the specified `Offset Distance` and the `Air Boundary` option lets you optionally set the boundaries between the core and perimeter rooms to an air boundary if the room being split represents an open space. It is recommended that the "Join coplanar faces" command be run before using this command.

{% embed url="https://drive.google.com/open?id=1XlQxN6N1M2LqzQdGNJ4h_Wuw39b3NXc5&usp=drive_fs" %}
Split core and perimeter
{% endembed %}
