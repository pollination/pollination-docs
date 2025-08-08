# Setup & Run Simulation

## PO\_RunSimulation

Start submitting a new simulation job.

### Useful Links

{% embed url="https://docs.pollination.solutions/user-manual/rhino-plugin/energy-modeling/run-simulation-and-load-results" %}

{% embed url="https://docs.pollination.solutions/user-manual/rhino-plugin/daylight-modeling/run-simulation-and-visualize-daylighting-results" %}

***

## PO\_SimulationParameter

Set up or modify SimulationParameter for energy simulation.

***

## `Sensor Grids`

## PO\_AddRadialGrid

Add radial sensor grids for running Radiance grid based simulations. Use "Pollination" command to open Radiance Object Manager to check and edit each sensor grid.

### Options

*   **GridSize**

    Space between any two sensor points. (in Rhino's unit)
*   **Offset**

    Offset distance from the input geometries. (in Rhino's unit)
*   **Directions**

    A positive integer for the number of radial directions to be generated around each position. (Default: 8)

Notes:

* The input geometries can be Rhino surfaces, rooms or orphaned faces.
* For rooms, only sub-surfaces with floor type will be used for generating sensor grids.
* This type of sensor grid is particularly helpful for studies of multiple view directions, such as imageless glare studies.

***

## PO\_AddSensorGrid

Add sensor grids for running Radiance grid based simulations. Use "Pollination" command to open Radiance Object Manager to check and edit each sensor grid.\
The input geometries can be generic Rhino Brep/Mesh geometries, or Pollination geometries such as rooms, room's child surfaces (aperture, door, shade), sub-surface (room's wall, or other type of faces selected by Shift+Ctrl+Click), and orphaned faces.

<figure><img src="https://user-images.githubusercontent.com/2915573/209876729-cd50c983-a1d6-413e-a1ae-e8148705cecc.gif" alt=""><figcaption></figcaption></figure>

### Options

*   **GridSize**

    space between any two sensor points. (in Rhino's unit)
*   **Offset**

    offset distance from the input geometries. (in Rhino's unit)
*   **MergeCoplanar**

    set to true to merge all selected surfaces that are coplanar to create minimum amount of sensor grids as possible. (default: false)
*   **Filter**

    filter currently selected geometries based on types (Floor, Wall, Roof, Window, Skylight, Door) if possible. (default: bySelected)
*   **ShrinkDist**

    shrink distance from the input geometries' edges. (in Rhino's unit)
*   **QuadOnly**

    set to true to only generate quad faces. (default: false)

### Useful Links

{% embed url="https://docs.pollination.solutions/user-manual/rhino-plugin/daylight-modeling/add-sensor-grid" %}

### Video Tutorials

{% embed url="https://user-images.githubusercontent.com/9031066/273817127-250e60c3-75f3-45c1-b08a-d2b8a8962281.mp4" %}
Add sensors to a Room and Room faces
{% endembed %}

***

## PO\_AddView

Setting up the camera view for running Radiance view based simulations. Use "Pollination" command to open Radiance Object Manager to check and edit each view object.

### Options

*   **Points**

    Select Rhino Points. The normal is aligned with Z axis and the direction is aligned with X axis.
*   **Lines**

    Select Rhino Linecurve. The normal is aligned with the Z axis and the direction is aligned with line direction.
*   **CurrentView**

    It uses the current location of the camera. The direction is the target direction.

### Useful Links

{% embed url="https://docs.pollination.solutions/user-manual/rhino-plugin/daylight-modeling/add-view" %}

***

## PO\_EditSensorGridProperties

Edit sensor grid properties for one or more selected objects.

***

## PO\_EditViewProperties

Edit view properties for selected objects.

### Useful Links

{% embed url="https://docs.pollination.solutions/user-manual/rhino-plugin/daylight-modeling/add-view" %}

***

## PO\_SelSensorGrids

Select all visible sensor grids in the current Rhino document.

***

## PO\_SelViews

Select all visible Radiance views in the current Rhino document.

***

## `Energy Properties`

## PO\_ConstructionManager

This command brings up the energy Constructions manager for users to add/edit/remove energy constructions.

### Useful Links

{% embed url="https://docs.pollination.solutions/user-manual/rhino-plugin/energy-modeling/assign-construction-sets" %}

***

## PO\_ConstructionSetManager

This command brings up the energy ConstructionSets manager for users to add/edit/remove energy construction sets.

### Useful Links

{% embed url="https://docs.pollination.solutions/user-manual/rhino-plugin/energy-modeling/assign-construction-sets" %}

***

## PO\_HVACManager

This command brings up the energy HVACs manager for users to add/edit/remove energy HVACs.

### Useful Links

{% embed url="https://docs.pollination.solutions/user-manual/rhino-plugin/energy-modeling/assign-hvac-systems" %}

***

## PO\_MaterialManager

This command brings up the energy materials manager for users to add/edit/remove energy materials.

***

## PO\_ProgramTypeManager

This command brings up the energy ProgramTypes manager for users to add/edit/remove energy program types.

<figure><img src="https://user-images.githubusercontent.com/2915573/209991054-6ddb4451-5a66-482b-adfb-d71a68491626.png" alt=""><figcaption><p>Program Type Manager</p></figcaption></figure>

### Useful Links

{% embed url="https://docs.pollination.solutions/user-manual/rhino-plugin/energy-modeling/assign-program-types" %}

***

## PO\_SHWManager

This command brings up the energy SHW manager for users to add/edit/remove energy service hot water systems.

***

## PO\_ScheduleManager

This command brings up the energy Schedules manager for users to add/edit/remove energy schedules.

***

## `Energy Validation`

## PO\_CheckAdjacency

Analysis geometries (Curve, Brep, Extrusion, or Pollination object) for adjacencies.

Notes:

* The results are points that grouped by a test distance.

Tips:

* Use it to detect and fix apparent adjacencies of rooms.

### Video Tutorials

{% embed url="https://user-images.githubusercontent.com/9031066/277900826-85445348-7124-407f-9b2d-2a62f9779b7f.mp4" %}
Visualize tiny edges/gaps
{% endembed %}

***

## PO\_CheckPlanarity

Analysis selected surfaces for planarity and visualize non-planar surfaces.

Notes:

* A pollination model is made by planar geometries.

<figure><img src="https://user-images.githubusercontent.com/2915573/209992073-f5b8db70-4e38-4fc3-a5f9-e16087724b45.gif" alt=""><figcaption><p>Check planarity for input geometry.</p></figcaption></figure>

***

## PO\_IsolateAdjacencies

Isolate selected rooms and their adjacent rooms.

***

## PO\_ResetBoundaryCondition

Resets the boundary condition for all child faces of a room or for selected child faces. You can select specific sub-faces of a room by holding the Shift + Ctrl keys.

Notes:

* The boundary condition for all geometries will be reset to Outdoor, except for geometries touching the ground (0), which will be set to Ground.
* Apertures and doors will also be reset to the Outdoor boundary condition.
* Face type with AirBoundary will be reset to Wall.

***

## PO\_SetAirBoundariesByGuides

Use this command to set rooms' interior surface to air boundary type based on guide surfaces.

Notes:

* Guide surfaces have to be coplanar to target interior surfaces and fully cover the interior surface geometries.
* It requires adjacencies to be already solved before using. So run PO\_SolveAdjacency first before using this command.

***

## PO\_SolveAdjacency

Use this command to split and match walls between rooms. If non-room geometries are selected, this command only splits for each subsurface.

### Options

*   **DoIntersect**

    Yes to perform geometry intersections. It will split faces.
*   **DoMatch**

    Yes to match energy and radiance properties of adjacent faces.
*   **CustomConstructions**

    Yes to select custom constructions to apply to adjacent faces.
*   **CustomModifiers**

    Yes to select custom modifiers to apply to adjacent faces.
*   **SetAirBoundary**

    Yes to apply air boundary to adjacent faces.

Notes:

* Apertures and doors will be adjusted to match new walls.
* The boundary condition of the aperture or door won't be changed if its outdoor walls become indoor surfaces.

### Video Tutorials

{% embed url="https://youtu.be/5T9VWc96hyk" %}
Solve adjacency in a model
{% endembed %}

***

## PO\_ValidateModel

Validate the current model to ensure it is simulate-able for daylight or energy.

Notes:

* If the model is not valid it shows the log with errors.
* Use the log as a guide to fix the model.

***

## `Daylight Settings`

## PO\_ModifierManager

This command brings up the energy RadianceModifiers manager for users to add/edit/remove Radiance modifiers.

### Useful Links

{% embed url="https://docs.pollination.solutions/user-manual/rhino-plugin/daylight-modeling/assign-modifiers" %}

***

## PO\_ModifierSetManager

This command brings up the energy RadianceModifierSets manager for users to add/edit/remove Radiance modifier sets.

### Useful Links

{% embed url="https://docs.pollination.solutions/user-manual/rhino-plugin/daylight-modeling/assign-modifier-sets" %}

***
