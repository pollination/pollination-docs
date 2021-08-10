# Rooms and Room Separation Lines

Similar to the Rhino plugin, the Revit plugin also uses a room-by-room approach to generating an analytical model for building energy modeling. 

## Room & Area Settings

Avoid room export errors by selecting the "Areas and Volumes" room computation option. While this option might be slower than the areas only option, it generates rooms that are bounded more accurately in height. 

![](../../.gitbook/assets/image%20%28136%29.png)

{% hint style="info" %}
If you have a pitched roof, you must select the room and extend it beyond the highest point of the roof in section view. If the Areas and Volumes Computation option is selected, the room will automatically match the room pitch to the roof pitch.    
{% endhint %}

![](../../.gitbook/assets/room-extension.gif)

## Room Bounding Elements

Ensure all appropriate elements are room bounding, this includes: 

* Walls
* Curtain Walls
* Floors
* Ceilings
* Roofs

If room bounding is not selected in the properties tab, it will not export correctly. 

![](../../.gitbook/assets/image%20%28133%29.png)

## Room Separation Lines

### General

As an overall strategy, minimize the use of room separation lines and avoid overlapping room separation lines. Pollination uses room separation lines to export air boundaries, so if there are instances where the room separation line overlaps with an already room bounding wall, curtain wall, or storefront, it will cause errors in the translation to an analytical model. 

### Walk-Through Openings 

When you have a door-less opening in a wall that allows for passage, it is important to place the room separation line correctly. In the example below, a walk-through opening is shown in axonometric and in plan view. In this instance, the room separation line should be located at the centerline of the wall assembly to properly export the opening as part of that wall. 

{% hint style="info" %}
At this time, Revit creates a single surface from the room separation line to represent the room opening. It get's exported as a full-height surface that requires some manual post-processing to be an air boundary. We need **two** coplanar surfaces that are the same height .   
{% endhint %}

![At walk-through openings, located a room separation line at the center of the wall assembly.](../../.gitbook/assets/room-separation-lines.jpg)



