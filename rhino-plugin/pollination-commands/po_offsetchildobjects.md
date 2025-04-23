# PO\_OffsetChildObjects

Offset all child objects (apertures and doors) of selected rooms to ensure they don't touch the edges of rooms. Only child object's edges that are within the `OffsetDistance` from their host room face's edge will be offsetted.

Notes:

* If the aperture has an edge coincident to an edge of the room it is not valid for energy simulation.

<figure><img src="https://user-images.githubusercontent.com/2915573/209991804-5ec0fb4a-512d-462c-9aec-ca76ef768726.gif" alt=""><figcaption><p>Offset child objects</p></figcaption></figure>

## Options

*   **IgnoreInsideEdges**

    Set to Yes to ignore those edges are already inside the host room face boundary. Set to No to check all edges and ensure all of them are at least from the `OffsetDistance` of the host face boundary.
*   **OffsetDistance**

    A value that defines how far from the host room face's boundary that limits child's object

## See Also

* [PO\_ProjectChildToHost](po_projectchildtohost.md)

## Video Tutorials

{% embed url="https://youtu.be/SCqkWwhoov4" %}
How to Fix Problematic Apertures
{% endembed %}
