---
description: >-
  Use this command to add windows by window-to-wall ratio for each outdoor wall
  of selected rooms.
---

# PO\_AddAperturesByWWR

<div>

<figure><img src="../pollination-commands-for-rhino/img/PO_AddAperturesByWWR.gif" alt=""><figcaption><p>Add apertures to room by window to wall ratio</p></figcaption></figure>

 

<figure><img src="https://discourse.pollination.cloud/uploads/default/original/2X/4/418a84b441faa7d475f0d3fa3adbb8d27032c365.png" alt=""><figcaption><p>Right aligned image</p></figcaption></figure>

 

<figure><img src="../../.gitbook/assets/RoomSelectionOFF.gif" alt=""><figcaption><p>Room selection mode</p></figcaption></figure>

</div>

### Options

*   **WindowWallRatio\_North**

    set a number between 0 to 1 for WWR. (default:0.4)
*   **WindowWallRatio\_East**

    set a number between 0 to 1 for WWR. (default:0.4)
*   **WindowWallRatio\_South**

    set a number between 0 to 1 for WWR. (default:0.4)
*   **WindowWallRatio\_West**

    set a number between 0 to 1 for WWR. (default:0.4)
*   **Subdivide**

    Boolean to note whether to generate a single window in the center of each Face(False) or to generate a series of rectangular windows using the other inputs below(True). (default: No)
*   **Window\_Height**

    A number for the target height of the output apertures.
*   **Sill\_Height**

    A number for the target height above the bottom edge of the face to start the apertures.
*   **Horizontal\_Separation**

    A number for the horizontal separation between individual aperture centerlines.
*   **Vertical\_Separation**

    An optional number to create a single vertical separation between the top and bottom apertures. (default:0.0)

### See Also

* [PO\_AddApertures](po\_addaperturesbywwr.md)
* [PO\_DrawApertures](po\_drawapertures.md)

### Discourse Topics

{% embed url="https://discourse.pollination.cloud/t/splitting-an-aperture-between-two-rooms/2270" %}

### Video Tutorials

{% embed url="https://www.youtube.com/watch?v=_q07tzElNmU" %}
How to export the Pollination Rhino Model to IES
{% endembed %}

Enjoy!
