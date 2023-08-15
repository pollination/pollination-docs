# PO_OffsetChildObjects

Offset all child objects (apertures and doors) of selected rooms to ensure they don&apos;t touch the edges of rooms.
Only child object&apos;s edges that are within the `OffsetDistance` from their host room face&apos;s edge will be offsetted.

Notes:
- If the aperture has an edge coincident to an edge of the room it is not valid for energy simulation.

<div>
<figure>
  <img src="https://user-images.githubusercontent.com/2915573/209991804-5ec0fb4a-512d-462c-9aec-ca76ef768726.gif" alt="">
  <figcaption>
    <p>Offset child objects</p>
  </figcaption>
</figure>
</div>

## Options

* **IgnoreInsideEdges**

  Set to Yes to ignore those edges are already inside the host room face boundary. Set to No to check all edges and ensure all of them are at least from the `OffsetDistance` of the host face boundary.

* **OffsetDistance**

  A value that defines how far from the host room face&apos;s boundary that limits child&apos;s object


## See Also

* [PO_ProjectChildToHost](./po_projectchildtohost.md)

## Video Tutorials

{% embed url="https://youtu.be/SCqkWwhoov4" %}How to Fix Problematic Apertures{% endembed %}

