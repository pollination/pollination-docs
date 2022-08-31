# PO_RebuildRooms

Rebuild selected rooms with following options: 1) merge all coplanar faces; 2) rebuild all room faces; 3) reset all boundary conditions; In this command, it also checks all child objects (apertures and doors)&apos;s normal to be matched with their host surfaces.

## Options

* **MergeCoplanar**

  set to true to merge all coplanar faces. This is similar to the Rhino&apos;s command MergeAllCoplanarFaces. (default:true)

* **RebuildFaces**

  set to true to recreate each planar faces from the duplicated-naked edge curves of the original geometry. This is also useful for rebuilding an invalid room. (default:false)

* **ResetBoundaryConditon**

  when this option is set to true, it resets all faces&apos;s boundary condition to Outdoor. Unless a face is below the Z 0, then its boundary condition will be set to the Ground. (default:true)

