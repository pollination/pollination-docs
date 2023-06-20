# Model Alignment & Updates

## PO_Align2DPlans



---

## PO_AlignToGrid



<div>
<figure>
  <img src="https://user-images.githubusercontent.com/9031066/211238032-5833de73-ac07-48e7-8bb7-d3289a81649a.gif" alt="">
  <figcaption>
    <p>This command automatically triangulates non-planar surfaces.</p>
  </figcaption>
</figure>
</div>

### Video Tutorials

{% embed url="https://youtu.be/GrH6br4DQrg" %}Fix Models with Alignment Errors{% endembed %}

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

## PO_GenRoomPerimeters

Split room and generate core/perimeter rooms.

<div>
<figure>
  <img src="https://user-images.githubusercontent.com/9031066/212973442-61d5ecb7-32c0-48e4-867a-a699f6ba524e.gif" alt="">
  <figcaption>
    <p>Split a room to perimeter and core rooms</p>
  </figcaption>
</figure>
</div>

---

## PO_RemoveProperties

Remove all attached properties from selected geometries.

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

## PO_SyncModel

Sync current model with a new updated Pollination model.

---

