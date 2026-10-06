# Ladybug Tools Interoperability

## Export/Import DFJSON and HBJSON

Both the Pollination Model Editor 


## Pollination Rhino Grasshopper Components

In addition to interoperability offered by importing and exporting DFJSON and HBJSON, the Pollination Rhino Plugin includes several Grasshopper components to ensure these models can be used seamlessly with the Ladybug Tools Grasshopper plugin.

![Pollination Tab in Grasshopper](../../../.gitbook/assets/rhino-plugin/rhino-grasshopper-components.png)

Of the available components, three types are particularly relevant to the interoperability between Pollination Rhino and Ladybug Tools:

* _Primitives entity components_ to translate Pollination Rhino entities (eg. Room) into Honeybee entities
* _Primitives library components_ to use Pollination UI from inside Grasshopper
* _Serializer components_ to serialize a Honeybee model in Grasshopper to other file formats.


## Primitives entity components

Primitive components are is similar to native Grasshopper params except they bring fully-detailed objects (eg. Room or Model) instead of .

Right click on it to access to menu of actions. Generally the available features are:

* **Synchronize**: It refreshes the data which the component is reading.&#x20;
* **Select**: It selects the objects from Rhino canvas&#x20;
* **Bake**: It bakes Honeybee objects or Pollination Rhino objects&#x20;
* **Internalise**: It saves in persistent memory the data&#x20;
* **Clear**: It clear the persistent memory


### Sample of Pollination Rhino to Honeybee Grasshopper objects

Use one of the entity components, for example _Pollination Room _and right click on it.

![Menu of the actions](<../../../.gitbook/assets/image (117).png>)

Click on _Select Pollination Rooms _to select the rooms you want from Rhino canvas. It convert every Pollination Rhino room to a Honeybee room.

![Selection of the Pollination rooms](<../../../.gitbook/assets/image (118).png>)

Continue the workflow with Honeybee. For example, I can add border shades to all apertures. Use one of the preview components of Honeybee to check the geometries.

![Continue the workflow with Honeybee](<../../../.gitbook/assets/image (119).png>)

At this point you can decide to continue with Honeybee or going back to Rhino using the Bake feature.

