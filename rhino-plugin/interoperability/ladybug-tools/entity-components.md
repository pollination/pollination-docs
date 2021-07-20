# Entity components

An entity component it is similar to a Rhino param. Right click on it to access to menù of actions. Generally the available features are:

* **Synchronize**: It refreshes the data which the component is reading. 
* **Select**: It selects the objects from Rhino canvas 
* **Bake**: It bakes Honeybee objects or Pollination Rhino objects 
* **Internalise**: It saves in persistent memory the data 
* **Clear**: It clear the persistent memory

### Current Limits

* They do not internalise Honeybee object in the persistent memory
* They do not support automatic synchronization for now

## From Pollination Rhino to Honeybee

Use one of the entity components, for example _Pollination Room_ and right click on it.

![Menu of the actions](../../../.gitbook/assets/image%20%28117%29.png)

Click on _Select Pollination Rooms_ to select the rooms you want from Rhino canvas. It convert every Pollination Rhino room to a Honeybee room.

![Selection of the Pollination rooms](../../../.gitbook/assets/image%20%28118%29.png)

Continue the workflow with Honeybee. For example, I can add border shades to all apertures. Use one of the preview components of Honeybee to check the geometries.

![Continue the workflow with Honeybee](../../../.gitbook/assets/image%20%28119%29.png)

At this point you can decide to continue with Honeybee or going back to Rhino using the Bake feature.







