---
description: Add a camera view for Radiance's view based simulation
---

# Add View

{% embed url="https://youtu.be/XG0s2WNHAmU?t=136" %}

Command [PO\_AddView](../pollination-commands-for-rhino/po_addview.md) provides two options to create camera views: from points and from the current view.

**From points:** users can create camera views directly from points in Rhino, and default view orientation is facing along with Rhino's X axis. However, it can always be relocated and rotated afterwards.

![](../../.gitbook/assets/image%20%28114%29.png)

**From current view**: users will need to adjust current active Rhino view to a location and orientation before running the command PO\_AddView. This command will translate current Rhino view to a view point object.

![Adjust the current Rhino view](../../.gitbook/assets/image%20%28113%29.png)

