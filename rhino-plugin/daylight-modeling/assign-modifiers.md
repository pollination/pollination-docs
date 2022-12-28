---
description: Use modifiers for non-room geometries
---

# Assign Modifiers

{% embed url="https://youtu.be/lV9nJTqzjhg?t=130" %}

## Step 1

**First select a geometry such as aperture, door, room face, or shade.** For a child geometry, you can double click its parent geometry which enters the editing mode and then you can select any child geometry, or you can select the child geometry from the right side room manager and expand the room all the way down to where you could find the child geometry. As for room's face, Rhino has a shortcut key for selecting child faces: hold Shift + Ctrl and click one of room's faces.

![Select a child geometry from Rhino](<../../.gitbook/assets/image (109).png>)

## Step 2

Use command [PO\_EditApertureProperties](../pollination-commands/po\_editapertureproperties.md), [PO\_EditDoorProperties](../pollination-commands/po\_editdoorproperties.md), [PO\_EditFaceProperties](../pollination-commands/po\_editfaceproperties.md), or [PO\_EditShadeProperties](../pollination-commands/po\_editshadeproperties.md) or double click the item from "Room Manager" to bring up the object properties dialog, in which you can override geometry's modifier.

![Override face's modifier by selecting a new modifier from Modifier Manager](<../../.gitbook/assets/image (107).png>)

## Step 2B

Users can add new modifiers from following templates: [plastic](https://www.ladybug.tools/honeybee-schema/model.html#tag/plastic\_model), [glass](https://www.ladybug.tools/honeybee-schema/model.html#tag/glass\_model), [trans](https://www.ladybug.tools/honeybee-schema/model.html#tag/trans\_model), [metal](https://www.ladybug.tools/honeybee-schema/model.html#tag/metal\_model), [mirror](https://www.ladybug.tools/honeybee-schema/model.html#tag/mirror\_model), [glow](https://www.ladybug.tools/honeybee-schema/model.html#tag/glow\_model), [light](https://www.ladybug.tools/honeybee-schema/model.html#tag/light\_model), and [BSDF](https://www.ladybug.tools/honeybee-schema/model.html#tag/bsdf\_model).

![](<../../.gitbook/assets/image (112).png>)
