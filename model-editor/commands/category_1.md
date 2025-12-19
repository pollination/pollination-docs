# Line Commands

Below are all commands that operate on lines/polylines.

## ![](<../../.gitbook/assets/create-room (1).svg>) Create rooms

Create room from selected closed polylines. Set the room display name, and adjust the Floor Height and Floor to Ceiling Height if needed. By default, the command uses the heights of the current active story.

<details>

<summary>Options</summary>

**Room Name**

Text to set the name of the generated room.

**Use Current Story Height**

Select to use the current story height for the newly created room. Unselect this option to be able to have specify the room height and floor elevation explicitly

**Room Height**

Height of the room.

**Room Elevation**

Elevation of the room.

</details>

{% embed url="https://drive.google.com/open?id=1XeG30cXVSHu2TiNZN3ZKgAH351YQvlFe&usp=drive_fs" %}
Create Room
{% endembed %}

***

## ![](<../../.gitbook/assets/explode-polyline (1).svg>) Explode polyline

Explode a polyline into several line segments.

***

## ![](<../../.gitbook/assets/join-segments (1).svg>) Join segments

Join several segments into one or more polylines.

***

## ![](<../../.gitbook/assets/offset (1).svg>) Offset

Offset the selected lines and/or polylines by a specified distance.

<details>

<summary>Options</summary>

**Offset Distance**

The distance that the selected line/polyline will be offset. This can be either positive or negative and positive values will be interpreted as offsetting outwards or 'to the right' while negative numbers will be offset inwards or to 'to the left'

**Perimeter Polygons**

Select to have the output be a series of closed perimeter polygons instead of a single offset line or polyline. Perimeter polygons can be used to split rooms into core and perimeter

</details>

The `Offset Distance` can be either positive or negative and positive values will be interpreted as offsetting outwards or "to the right" while negative numbers will be offset inwards or "to the left". The `Perimeter Polygons` option can be used to generate polygons from the offset, which can split rooms into core/perimeter.

{% embed url="https://drive.google.com/open?id=1XnHe7jOAKEczKa-G_h015L-AFxmyh8A1&usp=drive_fs" %}
Offset
{% endembed %}

***

## ![](<../../.gitbook/assets/remove-colinear-vertices (1).svg>) Remove colinear vertices

Remove colinear vertices from a polyline.

<details>

<summary>Options</summary>

**Tolerance**

The maximum distance between a polyline vertex and the line drawn between neighboring vertices below which it is considered colinear

</details>

***
