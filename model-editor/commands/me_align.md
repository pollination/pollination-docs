# Align
<img src="images/align.svg" width="50" height="50"> 

Align the selected rooms' vertices to the selected lines/polylines if the room vertices lie within the specified Alignment Distance.

## Options

* **Distance**

  The maximum distance between a room vertex and the line or polyline at which point the vertex will be aligned to the line

* **Snap Method**

  The method to be used for snapping room vertices to the lines. 'Snap Vertices' will snap the room vertices to the line/polyline vertices if they lie within the distance. 'Coordinate Vertices' will perform an additional step of inserting new room vertices when line/polyline vertices lie within the distance

* **Constrain Edges**

  Select to have all axes of the room edges that were not pulled to the line geometry be preserved