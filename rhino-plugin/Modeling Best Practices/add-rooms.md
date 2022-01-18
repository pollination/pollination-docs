# Create Rooms

## What are Rooms and Why Do You Need Them?

Pollination uses a room-based modeling hierarchy which allows for surface-based modifications. The room-by-room approach is efficient for creating a quick analytical model to simulate energy, daylight, or comfort performance without spending time with a surface-by-surface.

There are three methods for creating rooms using Pollination:&#x20;

1. Select Geometries
2. Select by Layers
3. Draw New Room

{% hint style="info" %}
A room-based model is not required for daylight simulations, users can still use surface-by-surface method to build a daylight model. It is worth noting that a non-room-based model is not simulate-able for EnergyPlus simulations.
{% endhint %}

## Select Geometries or Select by Layer

{% embed url="https://youtu.be/MQmKfh3TboU" %}

## Draw New Rooms



##

{% hint style="info" %}
All rooms should be modeled as a closed planar polysurface. If they are not, then you will see an error indicating that your polysurface is open.
{% endhint %}

