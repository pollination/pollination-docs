---
description: Use modifiers for non-room geometries
---

# Assign Modifiers

{% embed url="https://youtu.be/lV9nJTqzjhg?t=130" %}

## Step 1

**First select a geometry such as aperture, door, room face, or shade.** For a child geometry, you can double click its parent geometry which enters the editing mode and then you can select any child geometry, or you can select the child geometry from the right side room manager and expand the room all the way down to where you could find the child geometry. As for room's face, Rhino has a shortcut key for selecting child faces: hold Shift + Ctrl and click one of room's faces.



![Select a child geometry from Rhino](../../.gitbook/assets/image%20%28109%29.png)

## Step 2

Use command [PO\_SetApertureProperties](../pollination-commands-for-rhino/po_setapertureproperties.md),  [PO\_SetDoorProperties](../pollination-commands-for-rhino/po_setdoorproperties.md),  [PO\_SetFaceProperties](../pollination-commands-for-rhino/po_setfaceproperties.md), or [PO\_SetShadeProperties](../pollination-commands-for-rhino/po_setshadeproperties.md)  or double click the item from "Room Manager" to bring up the object properties dialog, in which you can override geometry's modifier.

![Override face&apos;s modifier by selecting a new modifier from Modifier Manager](../../.gitbook/assets/image%20%28107%29.png)

## Step 2B

Users can add new modifiers from following templates: [plastic](https://www.ladybug.tools/honeybee-schema/model.html#tag/plastic_model), [glass](https://www.ladybug.tools/honeybee-schema/model.html#tag/glass_model), [trans](https://www.ladybug.tools/honeybee-schema/model.html#tag/trans_model), [metal](https://www.ladybug.tools/honeybee-schema/model.html#tag/metal_model), [mirror](https://www.ladybug.tools/honeybee-schema/model.html#tag/mirror_model), [glow](https://www.ladybug.tools/honeybee-schema/model.html#tag/glow_model), [light](https://www.ladybug.tools/honeybee-schema/model.html#tag/light_model), and [BSDF](https://www.ladybug.tools/honeybee-schema/model.html#tag/bsdf_model).

![](../../.gitbook/assets/image%20%28112%29.png)

