---
description: Below is the list of commands that are added to Rhino by Pollination Rhino plugin
---

# Pollination Commands for Rhino

## General

#### <mark style="background-color:yellow;">PO\_CheckUpdates</mark>

Check the Pollination server for a new version of the Rhino plugin. [Read more](./po_checkupdates.md).

#### <mark style="background-color:yellow;">PO\_LicenseManager</mark>

Activate license with a new key. [Read more](./po_licensemanager.md).

#### <mark style="background-color:yellow;">PO\_PluginInfo</mark>

Show the about dialog for displaying plugin related data. [Read more](./po_plugininfo.md).

#### <mark style="background-color:yellow;">PO\_Pollination</mark>

Turn on the main control panel for managing rooms, orphaned objects, resources (program types, constructions, schedules, etc.). [Read more](./po_pollination.md).

#### <mark style="background-color:yellow;">PO\_TestLocalAppEnvironment</mark>

This command is useful to test the local App&apos;s environment. It runs Podman commands to ensure the virtual machine runs correctly before executing any local Apps. [Read more](./po_testlocalappenvironment.md).

#### <mark style="background-color:yellow;">PO\_UnitsSetting</mark>

Show the unit dialog for setting up display units on UI. [Read more](./po_unitssetting.md).

#### <mark style="background-color:yellow;">PO\_UploadModel</mark>

Upload the current model to Pollination cloud. [Read more](./po_uploadmodel.md).

#### <mark style="background-color:yellow;">PO\_UserManual</mark>

Open https://docs.pollination.cloud/user-manual/rhino-plugin/getting-started. [Read more](./po_usermanual.md).

## Geometry Setup

### `Rooms`

#### <mark style="background-color:yellow;">PO\_AddRooms</mark>

Convert closed geometries to rooms. New created rooms contains default energy and radiance properties. Use &quot;Pollination&quot; command to open Room Manager to check and edit each room. [Read more](./po_addrooms.md).

#### <mark style="background-color:yellow;">PO\_AddRoomsByLayer</mark>

Convert closed geometries to rooms by layers. Use &quot;Pollination&quot; command to open Room Manager to check and edit each room. [Read more](./po_addroomsbylayer.md).

#### <mark style="background-color:yellow;">PO\_DrawRoom</mark>

Draw a room. [Read more](./po_drawroom.md).

#### <mark style="background-color:yellow;">PO\_EditRoomProperties</mark>

Edit room properties for one or more selected rooms. [Read more](./po_editroomproperties.md).

#### <mark style="background-color:yellow;">PO\_MatchRoomProperties</mark>

Duplicate all Honeybee properties from a source room to selected target rooms or solid Breps. [Read more](./po_matchroomproperties.md).

#### <mark style="background-color:yellow;">PO\_MergeRooms</mark>

Merge multiple rooms into one room. [Read more](./po_mergerooms.md).

#### <mark style="background-color:yellow;">PO\_RebuildRooms</mark>

Rebuild selected rooms with following options: 1) merge all coplanar faces; 2) rebuild all room faces; 3) reset all boundary conditions; In this command, it also checks all child objects (apertures and doors)&apos;s normal to be matched with their host surfaces. [Read more](./po_rebuildrooms.md).

#### <mark style="background-color:yellow;">PO\_SelRooms</mark>

Select all visible rooms in the current Rhino document. [Read more](./po_selrooms.md).

#### <mark style="background-color:yellow;">PO\_SplitRooms</mark>

Split rooms by selected cutters. The selected existing cutter has to cut through the entire room so that it could perform a clean cut. [Read more](./po_splitrooms.md).

### `Surfaces`

#### <mark style="background-color:yellow;">PO\_AddOpaqueFaces</mark>

Add orphaned faces from selected geometries. Use &quot;Pollination&quot; command to open Orphaned Object Manager to check and edit each orphaned face. [Read more](./po_addopaquefaces.md).

#### <mark style="background-color:yellow;">PO\_DrawPlanarSurface</mark>

Set CPlane and draw plane surfaces on it. [Read more](./po_drawplanarsurface.md).

#### <mark style="background-color:yellow;">PO\_EditFaceProperties</mark>

Edit face properties for one or more selected faces. [Read more](./po_editfaceproperties.md).

#### <mark style="background-color:yellow;">PO\_SelOpaqueFaces</mark>

Select all visible orphaned faces in the current Rhino document. [Read more](./po_selopaquefaces.md).

### `Apertures, Skylights & Doors`

#### <mark style="background-color:yellow;">PO\_AddApertures</mark>

Add planar window surfaces to selected rooms or orphaned faces. For adding an orphaned windows, press ENTER to skip selecting the host objects. Use &quot;Pollination&quot; command to open Room Manager or Orphaned Object Manager to check and edit each hosted window object or orphaned windows. [Read more](./po_addapertures.md).

#### <mark style="background-color:yellow;">PO\_AddAperturesByWWR</mark>

Add windows by window to wall ratio for each outdoor walls of selected rooms. Use &quot;Pollination&quot; command to open Room Manager or Orphaned Object Manager to check and edit each hosted window object. [Read more](./po_addaperturesbywwr.md).

#### <mark style="background-color:yellow;">PO\_AddDoors</mark>

Add planar door surfaces to selected rooms or orhpaned faces. For adding an orphaned door, press ENTER to skip selecting the host objects. Use &quot;Pollination&quot; command to open Room Manager or Orphaned Object Manager to check and edit each hosted door object or orphaned door. [Read more](./po_adddoors.md).

#### <mark style="background-color:yellow;">PO\_AddSkylightsByRatio</mark>

Add skylights by ratio for each outdoor roof of selected rooms. [Read more](./po_addskylightsbyratio.md).

#### <mark style="background-color:yellow;">PO\_DrawApertures</mark>

Draw apertures on a selected room&apos;s surface. [Read more](./po_drawapertures.md).

#### <mark style="background-color:yellow;">PO\_DrawDoors</mark>

Draw doors on a selected room&apos;s surface. [Read more](./po_drawdoors.md).

#### <mark style="background-color:yellow;">PO\_DupAperturesDoors</mark>

Duplicate apertures and doors from one location to another point. [Read more](./po_dupaperturesdoors.md).

#### <mark style="background-color:yellow;">PO\_EditApertureProperties</mark>

Edit aperture properties for one or more selected apertures. [Read more](./po_editapertureproperties.md).

#### <mark style="background-color:yellow;">PO\_EditDoorProperties</mark>

Edit door properties for one or more selected doors. [Read more](./po_editdoorproperties.md).

#### <mark style="background-color:yellow;">PO\_MatchChildGeometry</mark>

This command updates the source geometry from the guide geometry while keeping all other properties. [Read more](./po_matchchildgeometry.md).

#### <mark style="background-color:yellow;">PO\_OffsetChildObjects</mark>

Offset all child objects (apertures and doors) of selected rooms to ensure they don&apos;t touch the edges of rooms. [Read more](./po_offsetchildobjects.md).

#### <mark style="background-color:yellow;">PO\_ProjectChildToHost</mark>

Check all child objects (apertures and doors) of selected rooms to ensure they are coplanar with their host faces. [Read more](./po_projectchildtohost.md).

#### <mark style="background-color:yellow;">PO\_SelApertures</mark>

Select all visible apertures in the current Rhino document. [Read more](./po_selapertures.md).

#### <mark style="background-color:yellow;">PO\_SelDoors</mark>

Select all visible doors in the current Rhino document. [Read more](./po_seldoors.md).

### `Context`

#### <mark style="background-color:yellow;">PO\_AddSiteContext</mark>

Add selected geometries as site contexts to model. This can be used to add trees, surrounding buildings, or site structures that are not directly attached to the building. Use &quot;Pollination&quot; command to open Orphaned Object Manager to check and edit each shade object. [Read more](./po_addsitecontext.md).

#### <mark style="background-color:yellow;">PO\_SelSiteContexts</mark>

Select all visible site contexts in the current Rhino document. [Read more](./po_selsitecontexts.md).

### `Shades`

#### <mark style="background-color:yellow;">PO\_AddApertureShades</mark>

Add shades to apertures. It works with two different modalities, BorderShades and LouverShades. [Read more](./po_addapertureshades.md).

#### <mark style="background-color:yellow;">PO\_AddBuildingShades</mark>

Add selected shade surfaces to model. Use &quot;Pollination&quot; command to open Orphaned Object Manager to check and edit each shade. [Read more](./po_addbuildingshades.md).

#### <mark style="background-color:yellow;">PO\_AddShades</mark>

Add shades to a host. A host can be room, orphaned face, aperture, or door. Use &quot;Pollination&quot; command to open Room Manager or Orphaned Object Manager to check and edit each hosted shade object. [Read more](./po_addshades.md).

#### <mark style="background-color:yellow;">PO\_EditShadeProperties</mark>

Edit Shade properties for selected Shades. [Read more](./po_editshadeproperties.md).

#### <mark style="background-color:yellow;">PO\_SelShades</mark>

Select all visible shades in the current Rhino document. [Read more](./po_selshades.md).

## Model Alignment & Updates

#### <mark style="background-color:yellow;">PO\_Align2DPlans</mark>

No description.

#### <mark style="background-color:yellow;">PO\_AlignToGrid</mark>

No description.

#### <mark style="background-color:yellow;">PO\_Check2DOrtho</mark>

Analysis 2D plans (curves) and visualize non-orthogonal geometries based on a reference plane. [Read more](./po_check2dortho.md).

#### <mark style="background-color:yellow;">PO\_EditInPlace</mark>

Enter editing mode for a selected room or orphaned object. It is same as double clicking the geometry. [Read more](./po_editinplace.md).

#### <mark style="background-color:yellow;">PO\_EditProperties</mark>

Modify Honeybee properties for selected objects. [Read more](./po_editproperties.md).

#### <mark style="background-color:yellow;">PO\_Extract2DPlans</mark>

Extract 2D plans from solid. New added curves contain original solid heights which can be used directly in PO_Extrude2DPlans command. [Read more](./po_extract2dplans.md).

#### <mark style="background-color:yellow;">PO\_Extrude2DPlans</mark>

Extrude 2D plans (curves) to solid Breps based on height data. A default height will be used if curves do not contains height information. [Read more](./po_extrude2dplans.md).

#### <mark style="background-color:yellow;">PO\_FixRoomChildrenLinks</mark>

Search globally and relink all child objects (Aperture and Door) with their host room object. [Read more](./po_fixroomchildrenlinks.md).

#### <mark style="background-color:yellow;">PO\_GenAlignGrids</mark>

Generate reference grids for alignments based on input geometries. [Read more](./po_genaligngrids.md).

#### <mark style="background-color:yellow;">PO\_GenRoomPerimeters</mark>

Split room and generate core/perimeter rooms. [Read more](./po_genroomperimeters.md).

#### <mark style="background-color:yellow;">PO\_RemoveProperties</mark>

Remove all attached properties from selected geometries. [Read more](./po_removeproperties.md).

#### <mark style="background-color:yellow;">PO\_ResetDisplayName</mark>

Reset an object&apos;s display name. You can also select partial room&apos;s sub-faces. [Read more](./po_resetdisplayname.md).

#### <mark style="background-color:yellow;">PO\_ResetIdentifier</mark>

Reset a honeybee object&apos;s identifier and boundary condition. You can also select partial room&apos;s sub-faces for resetting boundary conditions. [Read more](./po_resetidentifier.md).

#### <mark style="background-color:yellow;">PO\_SyncModel</mark>

Sync current model with a new updated Pollination model. [Read more](./po_syncmodel.md).

## Setup & Run Simulation

#### <mark style="background-color:yellow;">PO\_RunSimulation</mark>

Start submitting a new simulation job. [Read more](./po_runsimulation.md).

#### <mark style="background-color:yellow;">PO\_SimulationParameter</mark>

Set up or modify SimulationParameter for energy simulation. [Read more](./po_simulationparameter.md).

### `Sensor Grids`

#### <mark style="background-color:yellow;">PO\_AddRadialGrid</mark>

Add radial sensor grids for running Radiance grid based simulations. Use &quot;Pollination&quot; command to open Radiance Object Manager to check and edit each sensor grid. [Read more](./po_addradialgrid.md).

#### <mark style="background-color:yellow;">PO\_AddSensorGrid</mark>

Add sensor grids for running Radiance grid based simulations. Use &quot;Pollination&quot; command to open Radiance Object Manager to check and edit each sensor grid. [Read more](./po_addsensorgrid.md).

#### <mark style="background-color:yellow;">PO\_AddView</mark>

Setting up the camera view for running Radiance view based simulations. Use &quot;Pollination&quot; command to open Radiance Object Manager to check and edit each view object. [Read more](./po_addview.md).

#### <mark style="background-color:yellow;">PO\_EditSensorGridProperties</mark>

Edit sensor grid properties for one or more selected objects. [Read more](./po_editsensorgridproperties.md).

#### <mark style="background-color:yellow;">PO\_EditViewProperties</mark>

Edit view properties for selected objects. [Read more](./po_editviewproperties.md).

#### <mark style="background-color:yellow;">PO\_SelSensorGrids</mark>

Select all visible sensor grids in the current Rhino document. [Read more](./po_selsensorgrids.md).

#### <mark style="background-color:yellow;">PO\_SelViews</mark>

Select all visible Radiance views in the current Rhino document. [Read more](./po_selviews.md).

### `Energy Properties`

#### <mark style="background-color:yellow;">PO\_EnergyConstructionSets</mark>

No description.

#### <mark style="background-color:yellow;">PO\_EnergyConstructions</mark>

No description.

#### <mark style="background-color:yellow;">PO\_EnergyHVACs</mark>

No description.

#### <mark style="background-color:yellow;">PO\_EnergyMaterials</mark>

No description.

#### <mark style="background-color:yellow;">PO\_EnergyProgramTypes</mark>

No description.

#### <mark style="background-color:yellow;">PO\_EnergySHWs</mark>

No description.

#### <mark style="background-color:yellow;">PO\_EnergySchedules</mark>

No description.

#### <mark style="background-color:yellow;">PO\_HVACEditor</mark>

No description.

### `Energy Validation`

#### <mark style="background-color:yellow;">PO\_CheckAdjacency</mark>

Analysis geometries (Curve, Brep, Extrusion, or Pollination object) for adjacencies. [Read more](./po_checkadjacency.md).

#### <mark style="background-color:yellow;">PO\_CheckPlanarity</mark>

Analysis selected surfaces for planarity and visualize non-planar surfaces. [Read more](./po_checkplanarity.md).

#### <mark style="background-color:yellow;">PO\_IsolateAdjacencies</mark>

Isolate selected rooms and their adjacent rooms. [Read more](./po_isolateadjacencies.md).

#### <mark style="background-color:yellow;">PO\_ResetBoundaryCondition</mark>

Reset a room to reset all child faces&apos; boundary condition. You can also select partial room&apos;s sub-faces for resetting boundary condition. [Read more](./po_resetboundarycondition.md).

#### <mark style="background-color:yellow;">PO\_SetAirBoundariesByGuides</mark>

Use this command to set rooms&apos; interior surface to air boundary type based on guide surfaces. [Read more](./po_setairboundariesbyguides.md).

#### <mark style="background-color:yellow;">PO\_SolveAdjacency</mark>

Use this command to split and match walls between rooms. If non-room geometries are selected, this command only splits for each subsurface. [Read more](./po_solveadjacency.md).

#### <mark style="background-color:yellow;">PO\_ValidateModel</mark>

Validate the current model to ensure it is simulate-able for daylight or energy. [Read more](./po_validatemodel.md).

### `Daylight Settings`

#### <mark style="background-color:yellow;">PO\_RadianceModifierSets</mark>

No description.

#### <mark style="background-color:yellow;">PO\_RadianceModifiers</mark>

No description.

## Load, Visualize, and Export Results

#### <mark style="background-color:yellow;">PO\_ColorByBoundaryCondition</mark>

Color all objects by their boundary condition. [Read more](./po_colorbyboundarycondition.md).

#### <mark style="background-color:yellow;">PO\_ColorByFaceNormal</mark>

Color all faces (including orphaned objects) by face normal. [Read more](./po_colorbyfacenormal.md).

#### <mark style="background-color:yellow;">PO\_ColorByFaceType</mark>

Color all rooms&apos; faces by boundary condition. [Read more](./po_colorbyfacetype.md).

#### <mark style="background-color:yellow;">PO\_DownloadModel</mark>

Download a model from the Pollination cloud. [Read more](./po_downloadmodel.md).

#### <mark style="background-color:yellow;">PO\_HideRoomNames</mark>

Hide room names. [Read more](./po_hideroomnames.md).

#### <mark style="background-color:yellow;">PO\_LoadResults</mark>

Load results from previous submitted simulations. Download simulation assets if the job is executed on Pollination cloud. [Read more](./po_loadresults.md).

#### <mark style="background-color:yellow;">PO\_ResetLegendLocation</mark>

Move back all legends back to top-left of the view. [Read more](./po_resetlegendlocation.md).

#### <mark style="background-color:yellow;">PO\_ShowObjectNotes</mark>

Display a full report of object&apos;s notes which often is used for errors. [Read more](./po_showobjectnotes.md).

#### <mark style="background-color:yellow;">PO\_ShowRoomNames</mark>

Show selected rooms&apos; display name. [Read more](./po_showroomnames.md).

