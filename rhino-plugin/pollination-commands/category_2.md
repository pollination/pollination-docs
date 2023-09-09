# Model Alignment & Updates

## PO\_AlignInElevation

Align geometries (generic geometries or Pollination geometries) to elevation reference lines. Non-planar faces will be triangulated.

### Options

*   **Threshold**

    A distance tolerance for how far away from each grid line that a vertex should be affected and snapped to. Default 10x of document tolerance.
*   **Angle Tolerance**

    A degree number from 0 to 360 to filter each input geometry edges that have a angle difference from the grids. Input -1 to disable checking the angle tolerance. Default to the current document angle tolerance.

### See Also

* [PO\_AlignInPlan](po\_aligninplan.md)
* [PO\_RemoveShortSegments](po\_removeshortsegments.md)

***

## PO\_AlignInPlan

Align geometries (generic geometries or Pollination geometries) to a grid system. Non-planar faces will be triangulated.

<figure><img src="https://user-images.githubusercontent.com/9031066/211238032-5833de73-ac07-48e7-8bb7-d3289a81649a.gif" alt=""><figcaption><p>This command automatically triangulates non-planar surfaces.</p></figcaption></figure>

{% embed url="https://drive.google.com/file/d/1GQwN4L0hVmVsVX0nDVwAIOQPWdJrlVCw/view" %}
The command also accepts multiple rooms.
{% endembed %}

### Options

*   **Threshold**

    A distance tolerance for how far away from each grid line that a vertex should be affected and snapped to. Default 10x of document tolerance.
*   **Angle Tolerance**

    A degree number from 0 to 360 to filter each input geometry edges that have a angle difference from the grids. Input -1 to disable checking the angle tolerance. Default to the current document angle tolerance.

### See Also

* [PO\_AlignToRoom](po\_aligntoroom.md)
* [PO\_RemoveShortSegments](po\_removeshortsegments.md)
* [PO\_AlignInElevation](po\_aligninelevation.md)

### Video Tutorials

{% embed url="https://youtu.be/GrH6br4DQrg" %}
Fix Models with Alignment Errors
{% endembed %}

***

## PO\_AlignInPlan2D

Rebuild all 2D plan curves by aligning them to Rhino grid.

### Options

*   **DeleteInputs**

    Delete the selected planar curves.
*   **Threshold**

    Minimum dimension of the offset to apply. Default 0.1.

Notes:

* All curve geometries' end points will be snapped together based on current model's tolerance.

### See Also

* [PO\_AlignInPlan](po\_aligninplan.md)
* [PO\_AlignToRoom](po\_aligntoroom.md)

***

## PO\_AlignToRoom

Align geometries (generic geometries or Pollination geometries) to a target room. Non-planar faces will be triangulated.

\### Options

*   **Threshold**

    A distance tolerance for how far away from each grid line that a vertex should be affected and snapped to. Default 10x of document tolerance.

### See Also

* [PO\_AlignInPlan](po\_aligninplan.md)
* [PO\_RemoveShortSegments](po\_removeshortsegments.md)

***

## PO\_Check2DOrtho

Analysis 2D plans (curves) and visualize non-orthogonal geometries based on a reference plane.

### Options

*   **Custom Plane**

    Set a custom plane by two points (X axis). Default is a World XY plane.
*   **Angle Tolerance**

    A degree number from 0 to 360 used for non-orthogonal checks. A perfect orthogonal geometry means 90 degree from a base axis when angle tolerance is set to 0. Increase the angle tolerance would consider lines orthogonal within a range of 90 +- the angle tolerance. Default 0.01.

Notes:

* The results are non-orthogonal lines.

***

## PO\_EditInPlace

Enter editing mode for a selected room or orphaned object. It is same as double clicking the geometry.

***

## PO\_EditProperties

Modify Honeybee properties for selected objects.

***

## PO\_EmbedUserLibrary

Embed all user's custom resources from the local library folder, so that this 3dm contains all resource objects and you can share this file without worrying about the missing resource objects on the other machine.

### Useful Links

{% embed url="https://discourse.pollination.cloud/t/build-and-edit-a-library-of-reusable-constructions-schedules-programs-and-more/3097" %}

***

## PO\_Extract2DPlans

Extract 2D plans from solid. New added curves contain original solid heights which can be used directly in PO\_Extrude2DPlans command.

### Options

*   **DeleteInputs**

    set to true to delete input geometries.
*   **SimplifyCurves**

    set to true to simplify the generated curves and convert it to polylines.

***

## PO\_Extrude2DPlans

Extrude 2D plans (curves) to solid Breps based on height data. A default height will be used if curves do not contains height information.

### Options

*   **GlobalHeight**

    set a number for the height of extrusion globally. If the UseLocalHeightIfAny option is set to true and there is height data found within geometry, then this global height will be ignored for this geometry individually.
*   **UseLocalHeightIfAny**

    set to true to use embedded height data that is stored within each curve if any as opposed to use the global height.
*   **DeleteInputs**

    set to true to delete input geometries.
*   **SimplifyCurves**

    set to true to simplify the generated curves and convert it to polylines.

***

## PO\_FixRoomChildrenLinks

Search globally and relink all child objects (Aperture and Door) with their host room object. Note that these child objects should be valid Aperture or Door objects and for unknown reasons that their host room failed to link them.

***

## PO\_GenAlignGrids

Generate reference grids for alignments based on input geometries

### Video Tutorials

{% embed url="https://youtu.be/GrH6br4DQrg" %}
Fix Models with Alignment Errors
{% endembed %}

***

## PO\_GenRoomPerimeters

Split room and generate core/perimeter rooms.

<figure><img src="https://user-images.githubusercontent.com/9031066/212973442-61d5ecb7-32c0-48e4-867a-a699f6ba524e.gif" alt=""><figcaption><p>Split a room to perimeter and core rooms</p></figcaption></figure>

***

## PO\_ProjectSrf

Check all child objects (apertures and doors) of selected rooms to ensure they are coplanar with their host faces.

Notes:

* This command will automatically project the child geometry to its host's plane.
* It is important apertures and doors are coplanar to get a valid energy and radiance model.

***

## PO\_PurgeUserLibrary

Use this command with caution!!! Purge the library of all user energy standards that it contains. This command calls 'honeybee-energy lib purge \[OPTIONS]', see https://www.ladybug.tools/honeybee-energy/docs/cli/lib.html#honeybee-energy-lib-purge for more details.

### Useful Links

{% embed url="https://discourse.pollination.cloud/t/build-and-edit-a-library-of-reusable-constructions-schedules-programs-and-more/3097" %}

***

## PO\_RebuildAperturesDoors

Rebuild apertures and doors that are part of rooms (orphaned apertures and doors won't be processed in this command).

\---

## PO\_RemoveProperties

Remove all attached properties from selected geometries.

***

## PO\_RemoveShortSegments

Removes short edges that have a length smaller than the minimum distance for selected solid geometries.

\### See Also

* [PO\_AlignInPlan](po\_aligninplan.md)
* [PO\_AlignToRoom](po\_aligntoroom.md)

***

## PO\_ResetDisplayName

Reset an object's display name. You can also select partial room's sub-faces. Users can input any object's properties such as: Identifier, Story, DisplayName, etc., and format the new name as the following with the properties: {Story}\_my new name {Identifier}

Find all objects' properties: https://www.ladybug.tools/honeybee-schema/model.html#tag/room\_model

***

## PO\_ResetIdentifier

Reset a honeybee object's identifier and boundary condition. You can also select partial room's sub-faces for resetting boundary conditions.

### Options

*   **ID**

    Reset identifier criteria.
*   **GenerateNewID**

    Create a new ID randomly.
*   **ByDisplayName**

    Use display name as ID.
*   **ByDisplayNameAndID**

    It combines display name and random ID.
*   **Face**

    Yes to reset all faces' ID.
*   **Room**

    Yes to reset rooms' ID.
*   **SensorGrid\_View**

    Yes to reset sensor grids' ID.
*   **Validate**

    Yes to run model validation after resetting.

Notes:

* All geometries' boundary condition will be reset to Outdoor, unless geometry touches the ground (0) and then it will be set to Ground.

### Video Tutorials

{% embed url="https://youtu.be/_Nyi8JTHpiA" %}
How to use PO\_ResetIdentifier command
{% endembed %}

***

## PO\_ResetResourceIDs

Reset all resource objects' identifiers across the entire model. If two objects of the same type have the same display\_name, only one of them will be updated. This command calls 'honeybee-energy edit reset-resource-ids \[OPTIONS] MODEL\_FILE', see https://www.ladybug.tools/honeybee-energy/docs/cli/edit.html#honeybee-energy-edit-reset-resource-ids for more details.

### Useful Links

{% embed url="https://discourse.pollination.cloud/t/build-and-edit-a-library-of-reusable-constructions-schedules-programs-and-more/3097" %}

***

## PO\_SaveToUserLibrary

Export and save all resource objects from the current model to local user's resource library.

### Useful Links

{% embed url="https://discourse.pollination.cloud/t/build-and-edit-a-library-of-reusable-constructions-schedules-programs-and-more/3097" %}

***

## PO\_SetRoomStoryByElevation

Update selected rooms's story by their elevation

***

## PO\_SyncModel

Sync current model with a new updated Pollination model.

***
