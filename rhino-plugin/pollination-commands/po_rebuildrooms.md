# PO_RebuildRooms

Rebuild selected rooms with following options: 1) merge all coplanar faces; 2) rebuild all room faces; 3) reset all boundary conditions; In this command, it also checks all child objects (apertures and doors)&apos;s normal to be matched with their host surfaces.

## Options

* **MergeCoplanar**

  set to true to merge all coplanar faces. This is similar to the Rhino&apos;s command MergeAllCoplanarFaces. (default:true)

* **RebuildFaces**

  when set to true, this option recreates each planar face from the duplicated naked edge curves of the original geometry. It is also useful for removing tiny &quot;invalid&quot; face with an area smaller than tolerance squared. Additionally, setting this to true will reset the face type based on its normal. Face type with AirBoundary will be kept even RebuildFaces is set to True. You can use PO_ResetFaceType command to reset all room faces including air boundaries. (default:false)

* **ResetBoundaryConditon**

  when this option is set to true, it resets all faces&apos;s boundary condition to Outdoor. Unless a face is below the Z 0, then its boundary condition will be set to the Ground. (default:true)

* **FixApertureDoors**

  set to true to check all child objects (apertures and doors) to ensure they are coplanar with their host faces.


