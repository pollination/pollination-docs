# PO_AddRooms

Convert closed geometries to rooms. New created rooms contains default energy and radiance properties. Use &quot;Pollination&quot; command to open Room Manager to check and edit each room.

## Options

* **Property**

  override the default room properties, such as construction set, program type, hvac, and internal loads. (default: Default)

* **SkipExistingRoom**

  set to Yes to only convert non-room geometries (default: Yes)

* **MaxRoofAngle**

  change the max angle for how much a surface is tilted will be set to roof type. Any surface tilted between 0 and max angle will be set to roof (default: 30)


<div>
<figure>
  <img src="https://user-images.githubusercontent.com/2915573/209876724-d3fcefd3-abb9-4c25-8bd6-e8b5a8170c53.gif" alt="">
</figure>
</div>

## See Also

* [PO_AddRoomsByLayer](./po_addroomsbylayer.md)
* [PO_DrawRoom](./po_drawroom.md)

