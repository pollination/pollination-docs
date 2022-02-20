# Add Shade or Context

## From Rhino Geometry

We are supporting different type of shades: aperture/door shades, room shades, building shades, and site context/shades. 

In general, there is no difference among above types. However, they are useful to be organized when you want to convert your model to ASHRAE 90.1 baseline model with our Pollination recipe or you want to study an annual daylight simulation for LM-83 standard \(LEED daylight credit\). All shades, except the site context/shades, have to be removed or controlled dynamically for above standards. Assigning shade geometries to a correct type will make your future work easier. 

{% embed url="https://youtu.be/6uMqPPP4I-0" %}

## Add shades parametrically from Grasshopper 

Typically creating shade geometries for all windows may take some time if you are not familiar with Rhino, but it becomes very simple if you want to generate shades for all windows parametrically in Grasshopper. Once you created all shades in Grasshopper, you are able to bake them back to Rhino so they can be part of your existing model.

_Note: be aware of duplicated geometries in Rhino when you bake multiple times._

{% embed url="https://youtu.be/OALOnKM9lKQ" %}



