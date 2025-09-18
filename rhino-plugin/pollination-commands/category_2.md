# Model Alignment & Updates

## PO_AlignInElevation

Align geometries (generic geometries or Pollination geometries) to elevation reference lines.
Non-planar faces will be triangulated.

### Options

* **Threshold**

  A distance tolerance for how far away from each grid line that a vertex should be affected and snapped to. Default 10x of document tolerance.

* **Angle Tolerance**

  A degree number from 0 to 360 to filter each input geometry edges that have a angle difference from the grids. Input -1 to disable checking the angle tolerance. Default to the current document angle tolerance.


### See Also

* [PO_AlignInPlan](./po_aligninplan.md)
* [PO_RemoveShortSegments](./po_removeshortsegments.md)

---

## PO_AlignInPlan

Align geometries (generic geometries or Pollination geometries) to a grid system.
Non-planar faces will be triangulated.

<div>
<figure>
  <img src="https://user-images.githubusercontent.com/9031066/211238032-5833de73-ac07-48e7-8bb7-d3289a81649a.gif" alt="">
  <figcaption>
    <p>This command automatically triangulates non-planar surfaces.</p>
  </figcaption>
</figure>
</div>

{% embed url="https://drive.google.com/file/d/1GQwN4L0hVmVsVX0nDVwAIOQPWdJrlVCw/view" %}

### Options

* **Threshold**

  A distance tolerance for how far away from each grid line that a vertex should be affected and snapped to. Default 10x of document tolerance.

* **Angle Tolerance**

  A degree number from 0 to 360 to filter each input geometry edges that have a angle difference from the grids. Input -1 to disable checking the angle tolerance. Default to the current document angle tolerance.

* **Snap Corners**

  snap all vertices within the range of threshold to a closest corner (end point), instead of perpendicular to the grid lines.


### See Also

* [PO_AlignToRoom](./po_aligntoroom.md)
* [PO_RemoveShortSegments](./po_removeshortsegments.md)
* [PO_AlignInElevation](./po_aligninelevation.md)

### Video Tutorials

{% embed url="https://youtu.be/GrH6br4DQrg" %}Fix Models with Alignment Errors{% endembed %}

---

## PO_AlignInPlan2D

Rebuild all 2D plan curves by aligning them to Rhino grid.

### Options

* **DeleteInputs**

  Delete the selected planar curves.

* **Threshold**

  Minimum dimension of the offset to apply. Default 0.1.

Notes:

* All curve geometries&apos; end points will be snapped together based on current model&apos;s tolerance.

### See Also

* [PO_AlignInPlan](./po_aligninplan.md)
* [PO_AlignToRoom](./po_aligntoroom.md)

---

## PO_AlignToRoom

Align geometries (generic geometries or Pollination geometries) to a target room.
Non-planar faces will be triangulated.

<div>
</div>

{% embed url="https://drive.google.com/file/d/1LfpFUosXkFCl-8xsoj69kcGllQAz30DB/view" %}

### Options

* **Threshold**

  A distance tolerance for how far away from each grid line that a vertex should be affected and snapped to. Default 10x of document tolerance.


### See Also

* [PO_AlignInPlan](./po_aligninplan.md)
* [PO_RemoveShortSegments](./po_removeshortsegments.md)

---

## PO_AperturesDoorsSwap

Swap selected apertures and doors. All properties (modifier, construction, ventilation opening, etc) from the original geometries will be kept.

### Video Tutorials

{% embed url="https://github-production-user-asset-6210df.s3.amazonaws.com/9031066/312660008-f77256c1-9776-43ec-a648-273696a0e9a1.mp4?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAVCODYLSA53PQK4ZA%2F20240314%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20240314T004516Z&X-Amz-Expires=300&X-Amz-Signature=78d4e54bc1f58a1d4901ba41614ced9bb66e49fc52a3cc47c6244d3ef5882611&X-Amz-SignedHeaders=host&actor_id=0&key_id=0&repo_id=226602047" %}Swap objects between apertures and doors{% endembed %}

---

## PO_Check2DOrtho

Analysis 2D plans (curves) and visualize non-orthogonal geometries based on a reference plane.

### Options

* **Custom Plane**

  Set a custom plane by two points (X axis). Default is a World XY plane.

* **Angle Tolerance**

  A degree number from 0 to 360 used for non-orthogonal checks. A perfect orthogonal geometry means 90 degree from a base axis when angle tolerance is set to 0. Increase the angle tolerance would consider lines orthogonal within a range of 90 +- the angle tolerance. Default 0.01.

Notes:

* The results are non-orthogonal lines.

---

## PO_EditInPlace

Enter editing mode for a selected room or orphaned object. It is same as double clicking the geometry.

---

## PO_EditProperties

Modify Honeybee properties for selected objects.

---

## PO_EmbedUserLibrary

Embed all user&apos;s custom resources from the local library folder, so that this 3dm contains all resource objects and you can share this file without worrying about the missing resource objects on the other machine.

### Useful Links

{% embed url="https://discourse.pollination.solutions/t/build-and-edit-a-library-of-reusable-constructions-schedules-programs-and-more/3097" %}

---

## PO_Extract2DPlans

Extract 2D plans from solid. New added curves contain original solid heights which can be used directly in PO_Extrude2DPlans command.

### Options

* **DeleteInputs**

  set to true to delete input geometries. 

* **SimplifyCurves**

  set to true to simplify the generated curves and convert it to polylines. 


---

## PO_Extrude2DPlans

Extrude 2D plans (curves) to solid Breps based on height data. A default height will be used if curves do not contains height information.

### Options

* **GlobalHeight**

  set a number for the height of extrusion globally. If the UseLocalHeightIfAny option is set to true and there is height data found within geometry, then this global height will be ignored for this geometry individually.

* **UseLocalHeightIfAny**

  set to true to use embedded height data that is stored within each curve if any as opposed to use the global height.

* **DeleteInputs**

  set to true to delete input geometries. 

* **SimplifyCurves**

  set to true to simplify the generated curves and convert it to polylines. 


---

## PO_FixRoomChildrenLinks

Search globally and relink all child objects (Aperture and Door) with their host room object. 
Note that these child objects should be valid Aperture or Door objects and for unknown reasons that their host room failed to link them.

---

## PO_GenAlignGrids

Generate reference grids for alignments based on input geometries

### Video Tutorials

{% embed url="https://youtu.be/GrH6br4DQrg" %}Fix Models with Alignment Errors{% endembed %}

---

## PO_ProjectSrf

Check all child objects (apertures and doors) of selected rooms to ensure they are coplanar with their host faces. 

Notes:
- This command will automatically project the child geometry to its host&apos;s plane.
- It is important apertures and doors are coplanar to get a valid energy and radiance model.

---

## PO_PurgeUserLibrary

Use this command with caution!!! Purge the library of all user energy standards that it contains. This command calls &apos;honeybee-energy lib purge [OPTIONS]&apos;, see https://www.ladybug.tools/honeybee-energy/docs/cli/lib.html#honeybee-energy-lib-purge for more details.

### Useful Links

{% embed url="https://discourse.pollination.solutions/t/build-and-edit-a-library-of-reusable-constructions-schedules-programs-and-more/3097" %}

---

## PO_RebuildAperturesDoors

Rebuild apertures and doors that are part of rooms (orphaned apertures and doors won&apos;t be processed in this command).

<div>
</div>

{% embed url="https://drive.google.com/file/d/1LAbuvjCyiydwBs8iDhV86oUeM4uvgNSD/view" %}

---

## PO_RemoveProperties

Remove all attached properties from selected geometries.

---

## PO_RemoveShortSegments

Removes short edges that have a length smaller than the minimum distance for selected solid geometries.

<div>
</div>

{% embed url="https://drive.google.com/file/d/1KruUxyUFsgBfTd8nM7zp6dC46Z5Tbi4M/view" %}

### See Also

* [PO_AlignInPlan](./po_aligninplan.md)
* [PO_AlignToRoom](./po_aligntoroom.md)

---

## PO_ResetDisplayName

Reset an object&apos;s display name. You can also select partial room&apos;s sub-faces.
Users can input any object&apos;s properties such as: Identifier, Story, DisplayName, etc., and format the new name as the following with the properties:
{Story}_my new name {Identifier}

Find all objects&apos; properties: https://www.ladybug.tools/honeybee-schema/model.html#tag/room_model

---

## PO_ResetIdentifier

Reset a honeybee object&apos;s identifier and boundary condition. You can also select partial room&apos;s sub-faces for resetting boundary conditions.

### Options

* **ID**

  Reset identifier criteria.

* **GenerateNewID**

  Create a new ID randomly.

* **ByDisplayName**

  Use display name as ID.

* **ByDisplayNameAndID**

  It combines display name and random ID.

* **Face**

  Yes to reset all faces&apos; ID.

* **Room**

  Yes to reset rooms&apos; ID.

* **SensorGrid_View**

  Yes to reset sensor grids&apos; ID.

* **Validate**

  Yes to run model validation after resetting.

Notes:

* All geometries&apos; boundary condition will be reset to Outdoor, unless geometry touches the ground (0) and then it will be set to Ground.

### Video Tutorials

{% embed url="https://youtu.be/_Nyi8JTHpiA" %}How to use PO_ResetIdentifier command{% endembed %}

---

## PO_ResetResourceIDs

Reset all resource objects&apos; identifiers across the entire model. If two objects of the same type have the same display_name, only one of them will be updated. This command calls &apos;honeybee-energy edit reset-resource-ids [OPTIONS] MODEL_FILE&apos;, see https://www.ladybug.tools/honeybee-energy/docs/cli/edit.html#honeybee-energy-edit-reset-resource-ids for more details.

### Useful Links

{% embed url="https://discourse.pollination.solutions/t/build-and-edit-a-library-of-reusable-constructions-schedules-programs-and-more/3097" %}

---

## PO_ReverseConstruction

Change geometry&apos;s construction with an inverted material order.
Adjacent geometry will be updated with inverted construction at the same time if there is any.

### Video Tutorials

{% embed url="https://user-images.githubusercontent.com/9031066/283316902-4569626c-0227-43ea-8598-8ac7a151f708.mp4" %}Update surface's construction with a new reversed construction{% endembed %}

---

## PO_SaveToUserLibrary

Export and save all resource objects from the current model to local user&apos;s resource library.

### Useful Links

{% embed url="https://discourse.pollination.solutions/t/build-and-edit-a-library-of-reusable-constructions-schedules-programs-and-more/3097" %}

---

## PO_SetRoomStoryByElevation

Update selected rooms&apos;s story by their elevation

---

## PO_SimplifyApertures

Merge all apertures of a room and generate one aperture per face based on the original window-wall-ratio.

### Video Tutorials

{% embed url="https://user-images.githubusercontent.com/9031066/268597783-4390ed34-5d91-4996-a805-76ac91b99275.mp4" %}Merge apertures as a single geometry{% endembed %}

---

## PO_SyncModel

Sync current model with a new updated Pollination model.

---

