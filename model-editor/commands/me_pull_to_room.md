# Pull to room

![](<../../.gitbook/assets/pull-to-room (1).svg>)

Pull the vertices of one or more rooms to the first 'target' room in the selection. The operation of pulling can be thought of as aligning the rooms to the target room's segments and then snapping to its vertices.

## Options

*   **Pull Distance**

    The maximum distance between a room vertex and the target room edges at which point the vertex will be pulled to the target room
*   **Coordinate Vertices**

    Select to further coordinate the vertices after the initial pulling operation is complete. Coordination means that any vertices of the target room that lie within the specified distance to a pulled room but were NOT matched to a vertex on that room will be inserted into the pulled room
*   **Constrain Edges**

    Select to have all axes of the room edges that were not pulled to the adjacent room be preserved
*   **Invert Selection**

    Select to have the command pull the first room in the selection to all other rooms in the selection. This is the inverse of the default behavior, which uses the first room in the selection as a target and then pulls all following rooms to it

## Details

Using the `Coordinate Vertices` option will run an additional operation to adjust the number of vertices in the rooms that were pulled. This can result in better matching of segments between the rooms like so:

{% embed url="https://discourse.pollination.solutions/uploads/default/original/2X/2/203c04e13aa5d1bda5a9e0da5897ac86b340005e.png" fullWidth="false" %}

{% embed url="https://discourse.pollination.solutions/uploads/default/original/2X/6/6a6d98e42f285051859279a07c419502d653d24f.png" %}

{% embed url="https://drive.google.com/open?id=1XXNms4EwkrQteXZpxaFP7laQxpouSK74&usp=drive_fs" %}
pull to room multi segment lines
{% endembed %}
