# Setup & Run Simulation

## PO_RunSimulation

Start submitting a new simulation job.

---

## PO_SimulationParameter

Set up or modify SimulationParameter for energy simulation.

---

## `Sensor Grids`

## PO_AddRadialGrid

Add radial sensor grids for running Radiance grid based simulations. Use &quot;Pollination&quot; command to open Radiance Object Manager to check and edit each sensor grid.

### Options

* **GridSize**

  Space between any two sensor points. (in Rhino&apos;s unit)

* **Offset**

  Offset distance from the input geometries. (in Rhino&apos;s unit)

* **Directions**

  A positive integer for the number of radial directions to be generated around each position. (Default: 8)

Notes:

* **The input geometries can be Rhino surfaces, rooms or orphaned faces. **

  

* **For rooms, only sub-surfaces with floor type will be used for generating sensor grids.**

  

* **This type of sensor grid is particularly helpful for studies of multiple view directions, such as imageless glare studies.
**

  

---

## PO_AddSensorGrid

Add sensor grids for running Radiance grid based simulations. Use &quot;Pollination&quot; command to open Radiance Object Manager to check and edit each sensor grid.

<div>
<figure>
  <img src="https://user-images.githubusercontent.com/2915573/209876729-cd50c983-a1d6-413e-a1ae-e8148705cecc.gif" alt="">
</figure>
</div>

### Options

* **GridSize**

  space between any two sensor points. (in Rhino&apos;s unit)

* **Offset**

  offset distance from the input geometries. (in Rhino&apos;s unit)

Notes:

* **The input geometries can be Rhino surfaces, rooms or orphaned faces. **

  

* **For rooms, only sub-surfaces with floor type will be used for generating sensor grids.
**

  

---

## PO_AddView

Setting up the camera view for running Radiance view based simulations. Use &quot;Pollination&quot; command to open Radiance Object Manager to check and edit each view object.

### Options

* **Points**

  Select Rhino Points. The normal is aligned with Z axis and the direction is aligned with X axis.

* **Lines**

  Select Rhino Linecurve. The normal is aligned with the Z axis and the direction is aligned with line direction.

* **CurrentView**

  It uses the current location of the camera. The direction is the target direction.


---

## PO_EditSensorGridProperties

Edit sensor grid properties for one or more selected objects.

---

## PO_EditViewProperties

Edit view properties for selected objects.

---

## PO_SelSensorGrids

Select all visible sensor grids in the current Rhino document.

---

## PO_SelViews

Select all visible Radiance views in the current Rhino document.

---

## `Energy Properties`

## PO_EnergyConstructionSets

This command brings up the energy ConstructionSets manager for users to add/edit/remove energy construction sets.

---

## PO_EnergyConstructions

This command brings up the energy Constructions manager for users to add/edit/remove energy constructions.

---

## PO_EnergyHVACs

This command brings up the energy HVACs manager for users to add/edit/remove energy HVACs.

---

## PO_EnergyMaterials

This command brings up the energy materials manager for users to add/edit/remove energy materials.

---

## PO_EnergyProgramTypes

This command brings up the energy ProgramTypes manager for users to add/edit/remove energy program types.

---

## PO_EnergySHWs

This command brings up the energy SHW manager for users to add/edit/remove energy service hot water systems.

---

## PO_EnergySchedules

This command brings up the energy Schedules manager for users to add/edit/remove energy schedules.

---

## `Energy Validation`

## PO_CheckAdjacency

Analysis geometries (Curve, Brep, Extrusion, or Pollination object) for adjacencies.

Notes:
- The results are points that grouped by a test distance.

Tips:
- Use it to detect and fix apparent adjacencies of rooms.

---

## PO_CheckPlanarity

Analysis selected surfaces for planarity and visualize non-planar surfaces.

Notes:
- A pollination model is made by planar geometries.

---

## PO_IsolateAdjacencies

Isolate selected rooms and their adjacent rooms.

---

## PO_ResetBoundaryCondition

Reset a room to reset all child faces&apos; boundary condition. You can also select partial room&apos;s sub-faces for resetting boundary condition.

Notes:
- All geometries&apos; boundary condition will be reset to Outdoor, unless geometry touches the ground (0) and then it will be set to Ground.

---

## PO_SetAirBoundariesByGuides

Use this command to set rooms&apos; interior surface to air boundary type based on guide surfaces.

Notes:
- Guide surfaces have to be coplanar to target interior surfaces and fully cover the interior surface geometries.
- It requires adjacencies to be already solved before using. So run PO_SolveAdjacency first before using this command.

---

## PO_SolveAdjacency

Use this command to split and match walls between rooms. If non-room geometries are selected, this command only splits for each subsurface.

### Options

* **DoIntersect**

  Yes to perform geometry intersections. It will split faces.

* **DoMatch**

  Yes to match energy and radiance properties of adjacent faces.

* **CustomConstructions**

  Yes to select custom constructions to apply to adjacent faces.

* **CustomModifiers**

  Yes to select custom modifiers to apply to adjacent faces.

* **SetAirBoundary**

  Yes to apply air boundary to adjacent faces.

Notes:

* **Apertures and doors will be adjusted to match new walls.**

  

* **The boundary condition of the aperture or door won&apos;t be changed if its outdoor walls become indoor surfaces.
**

  

---

## PO_ValidateModel

Validate the current model to ensure it is simulate-able for daylight or energy.

Notes:
- If the model is not valid it shows the log with errors. 
- Use the log as a guide to fix the model.

---

## `Daylight Settings`

## PO_RadianceModifierSets

This command brings up the energy RadianceModifierSets manager for users to add/edit/remove Radiance modifier sets.

---

## PO_RadianceModifiers

This command brings up the energy RadianceModifiers manager for users to add/edit/remove Radiance modifiers.

---

