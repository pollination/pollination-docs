# Validation Error Codes

The validation process happens automatically upon importing a model to the Rhino plugin or whenever the [po\_validatemodel.md](../../../rhino-plugin/pollination-commands/po\_validatemodel.md "mention") command is run. It can also be run on a `.hbjson` file from the command line by installing [lbt-honeybee](https://pypi.org/project/lbt-honeybee/) and then running the [`honeybee validate model`](https://www.ladybug.tools/honeybee-core/docs/cli/validate.html) command.

The validation process runs a number of tests on the model, each of which corresponds to a specific validation error code. A model failing a specific test will return this error code along with a message about the failing Model object. A model that passes all validation can be simulated in the engines that Honeybee connects to without error (eg. OpenStudio/EnergyPlus, RAdiance, etc.). Validation is therefore meant to be a comprehensive check of all things that could make a model un-simulate-able, including things like compliance with [the 5 golden rules of honeybee schema geometry](https://github.com/ladybug-tools/honeybee-schema/wiki/2.1-Face3D-Schema#the-5-golden-rules-of-honeybee-schema-geometry) as well as engine-specific checks like adjacent constructions being in reverse order of materials for EnergyPlus simulation.

Invalid models may still be simulate-able in some engines but not others. For this reason, it is helpful to check the consequences of each error code since it can sometimes be ok to ignore them. Furthermore, in the event that an error must be fixed, it is important to know how to fix it and errors sharing the same error code can usually be corrected with similar methods. This document describes all validation error codes used by Honeybee and Dragonfly and includes recommendations for how to fix them.

**Note**: While a valid model can be simulated in simulation engines, it is always the modeler's responsibility to ensure that the assumptions of the valid model align with the real building design that they are informing.

## Validation Error Codes

Below is a list of all validation error codes that can be obtained from the Honeybee model validation process. Each one is described in detail and many include suggestions for how to fix them.

## Core Error Codes

### 000000

**Unknown Error** - A blank error code reserved for cases where the specific origin of the error is unknown. This error code should not appear in "normal" usage of the validation process and is typically an artifact of new honeybee extensions that are just starting to add their own validators.

### 000001

**Duplicate Shade Identifier** - Two or more Shades in the model have the same identifier. This is not only illegal in EnergyPlus and can cause strange behavior in Radiance, but it can also result in errors during the serialization of the model to/from any file format. For example, properties for EnergyPlus or Radiance may be assigned to the incorrect object.

This issue should be fixed by finding the object with the duplicate identifier and changing its ID or deleting the object. In Rhino, the [po\_resetidentifier.md](../../../rhino-plugin/pollination-commands/po\_resetidentifier.md "mention")command can be used to change object identifiers.

### 000002

**Duplicate Sub-Face Identifier** - Two or more Apertures or Doors in the model have the same identifier. This is not only illegal in EnergyPlus and can cause strange behavior in Radiance, but it can also result in errors during the serialization of the model to/from any file format. For example, properties for EnergyPlus or Radiance may be assigned to the incorrect object.

This issue should be fixed by finding the object with the duplicate identifier and changing its ID or deleting the object. In Rhino, the [po\_resetidentifier.md](../../../rhino-plugin/pollination-commands/po\_resetidentifier.md "mention")command can be used to change object identifiers.

### 000003

**Duplicate Face Identifier** - Two or more Faces in the model have the same identifier. This is not only illegal in EnergyPlus and can cause strange behavior in Radiance, but it can also result in errors during the serialization of the model to/from any file format. For example, properties for EnergyPlus or Radiance may be assigned to the incorrect object.

This issue should be fixed by finding the object with the duplicate identifier and changing its ID or deleting the object. In Rhino, the [po\_resetidentifier.md](../../../rhino-plugin/pollination-commands/po\_resetidentifier.md "mention")command can be used to change object identifiers.

### 000004

**Duplicate Room Identifier** - Two or more Rooms in the model have the same identifier. This is not only illegal in EnergyPlus and can cause strange behavior in Radiance, but it can also result in errors during the serialization of the model to/from any file format. For example, properties for EnergyPlus or Radiance may be assigned to the incorrect object.

This issue should be fixed by finding the object with the duplicate identifier and changing its ID or deleting the object. In Rhino, the [po\_resetidentifier.md](../../../rhino-plugin/pollination-commands/po\_resetidentifier.md "mention")command can be used to change object identifiers.

### 000101

**Non-Planar Geometry** - Not all of the vertices of a given geometry object (Face, Aperture, Door, Shade) lie within the same plane. In order to fail this test, a vertex must be further from the plane by the Model's tolerance.

This error must be fixed for simulation in both Radiance and EnergyPlus since these engines only accept planar geometry.

If the non-planarity of the geometry is not that severe, it can sometimes be fixed by using the [PO\_RebuildRooms](../../../rhino-plugin/pollination-commands/po\_rebuildrooms.md) command with the `RebuildFaces` option or by using the [PO\_AlignInPlan](../../../rhino-plugin/pollination-commands/po\_aligninplan.md) command. Otherwise, more detailed editing of vertices on the individual geometry object may be required.

### 000102

**Self-Intersecting Geometry** - The edges of a geometry object (Face, Aperture, Door, Shade) intersect one another (like a bowtie shape). This can cause issues when performing shading calculations in both Radiance and EnergyPlus.

Note that duplicated vertices are still considered valid in Honeybee model geometry and vertices are considered duplicates if they are close to each other within the Model tolerance. So this error will typically only arise when the edges of the object noticeably intersect one another.

Typically, the geometry must be redrawn in order to fix it, though it is sometimes possible to fix it simply by rearranging vertices.

### 000103

**Zero-Area Geometry** - The area of the geometry is smaller than the model tolerance. These geometries do not affect Radiance simulation and are automatically removed upon export to EnergyPlus so there is usually no requirement to fix them. However, it is often nice to do so in order to clean up the model.

The typical way to address these zero-area geometries is to simply delete them.

### 000104

**Invalid Sub-Face Geometry** - An Aperture or a Door is not co-planar with its parent Face or does not lie completely inside the parent Face boundary. Fixing this is a requirement for both EnergyPlus and Radiance. In EnergyPlus, this error can result in an incorrect estimation of solar gains if an Aperture is significantly larger than its parent Face or is facing the incorrect direction. In Radiance, the parent Face will not have the child geometries properly "punched" out of it, often resulting in odd visuals.

Note that this error will still arise even when the child Aperture or Door is only sharing an edge with the parent Face, which is technically still acceptable for certain Energy simulations but will often cause issues in Radiance and will result in display issues for most model viewers.

The best way to address the issue is to zoom into the geometry and move or scale the incorrect sub-face until it is valid. Completely removing the sub-face and redrawing it is also an option when many of these errors arise at once.

### 000105

**Overlapping Sub-Face Geometry** - The Apertures and/or Doors of a Face overlap with one another such that the sum of their areas is greater than the parent Face. Fixing this is a requirement for both EnergyPlus and Radiance. In EnergyPlus, this error can result in over-estimation of solar gains as multiple overlapping Apertures each contribute solar energy to the parent Room. In Radiance, the parent Face will not have the child geometries properly "punched" out of it, often resulting in parts of the Aperture that overlap with others becoming opaque.

The best way to address the issue is to zoom into the geometry and delete any sub-faces that are known to be incorrect or duplicated.

### 000106

**Non-Solid Room Geometry** - There is a Room in the model that is not a closed solid to within the model tolerance. Closed Room solids are required for EnergyPlus simulation since the volume of air in the Room cannot be calculated if the Room does not form a closed solid. Furthermore, the orientation of Walls, Roofs, Floors, and Apertures in relation to the inside/outside of the Room volume cannot be verified when the Room is not solid, which is required for correct solar calculations.

While a Radiance simulation with non-closed Room solids can technically succeed, there will usually be light leaks into the Room if it is not a closed solid, resulting in potentially inaccurate radiance/luminance values. Furthermore, some modifiers that behave differently depending on the orientation of the geometry they are applied to maybe assigned incorrectly given that the relation of the Walls, Roofs, Floors, and Apertures to the inside/outside of the Room volume cannot be verified. This is particularly dangerous with BSDF modifiers and 3 or 5-phase simulations.

There are two ways that a Room is not recognized as a solid:

1. Naked Edges - The Room volume is open resulting in edges that belong to only one Face. This case should be fixed by patching the hole with a new Face geometry or moving the geometries around the hole to close it up.
2. Non-manifold Edges - The Room has an edge that is shared by three or more Faces. This often means that there is a Face extending inward or outward from the Room volume, thereby interfering with the Room's volumetric calculations. Non-manifold edges can also result from tiny "sliver Faces" that are smaller than the Model tolerance and therefore collapse into a single edge shared by multiple Faces. Non-manifold edges should typically be fixed by deleting the sliver Face or the Face extending inward/outward from the Room volume.

The message associated with the error should list the number of naked and non-manifold edges contained in the Room geometry.

### 000107

**Degenerate Room Volume** - There is a Room in the model that effectively has zero volume from the perspective of the Model tolerance. This can happen when all of the Faces of a Room are coplanar with one another, effectively making a "sliver" Room. It is a common side-effect of aligning small rooms to an axis in plan. Often, the best fix for this case is to simply delete the degenerate Room from the model.

### 000108

**Colliding Room Volumes** - There are two Rooms in the Model with volumes that collide with one another such that each Room geometry extends into the other. While this will not cause a simulation failure for either EnergyPlus or Radiance, it may cause a failure to translate to IES-VE, eQuest, or IDA-ICE (or it will result in warnings when the model is opened in these programs). It's also generally considered poor modeling in the EnergyPlus documentation, even though it does not cause the simulation to stop.

The issue can often be corrected by using the [PO\_AlignInPlan](../../../rhino-plugin/pollination-commands/po\_aligninplan.md) command or the [PO\_AlignToRoom](../../../rhino-plugin/pollination-commands/po\_aligntoroom.md) command in the Rhino plugin. In the Revit plugin, checking room bounding elements or using alignment lines can usually correct the issue.

### 000201

**Self-Referential Adjacency** - The model contains a Face, Aperture, or Door with a Surface boundary condition that references itself. This is illegal for EnergyPlus simulation, though it may have little to no effect on Radiance simulation if the geometry is clean.

It should be fixed by either re-solving adjacency or, if the Face, Aperture, or Door has no adjacent geometry object in the model, the boundary condition could be changed to be Adiabatic or Outdoors.

### 000202

**Intra-Room Adjacency** - The model contains a Room with two Faces that are adjacent to each other and reference each other in their Surface boundary conditions. This cannot be possible if the Room is a closed solid and this particular type of error may sometimes be accompanied by a "Non-Solid Room Geometry" error (often with non-manifold edges). This condition is illegal for EnergyPlus simulation, though it may have little to no effect on Radiance simulation if the geometry is clean.

It should be fixed by either deleting the self-referencing Faces or (if the parent Room is solid) by re-solving adjacency.

### 000203

**Object with Multiple Adjacencies** - The model contains Faces, Apertures, or Doors with Surface boundary conditions that indicate multiple objects are adjacent to a single Face, Aperture, or Door object. This is illegal for EnergyPlus simulation, though it may have little to no effect on Radiance simulation if the geometry is clean.

It should usually be fixed by deleting one of the objects that are among the "multiple adjacent objects." Alternatively, if the geometry is clean, it might also be fixed by re-solving adjacency.

### 000204

**Missing Adjacency** - The model contains a Face, Aperture, or Door with a Surface boundary condition referencing another object that is not in the model. This can often happen if a previously existing Room has been deleted from the model or some change has been made to reset identifiers or boundary conditions in the model. It is illegal for EnergyPlus simulation and will usually result in duplicated interior geometries in Radiance simulations, which may succeed but have patchy or incorrect modifiers.

It can usually be fixed by re-solving adjacency.

### 000205

**Mismatched Area Adjacency** - The model contains an adjacent pair of Faces, Apertures, or Doors that are otherwise valid but do not have equivalent areas to each other within the model tolerance. Matching areas are required for EnergyPlus simulation in order to ensure there is matching heat flow across adjacent Faces. Otherwise, conservation of energy is usually violated and EnergyPlus will give a severe error. This condition may have little to no effect on Radiance simulation if the geometry is otherwise "clean."

This error can usually be fixed by re-solving adjacencies with the intersection step selected in order to ensure any mismatched geometries are correctly split with their neighboring geometry.

### 000206

**Non-Adjacent AirBoundary** - The model contains an AirBoundary Face that does not have a Surface boundary condition and is not adjacent to another Room in the Model. All AirBoundary Faces must be adjacent to another Room for EnergyPlus simulation since EnergyPlus expects to simulate detailed radiant heat and air exchange between Rooms across an AirBoundary. In Radiance simulation, a non-adjacent AirBoundary is permissible, though it's effectively equivalent to having a Room geometry open to the outdoors.

The error might be fixed by re-solving adjacency or, if the erroneous AirBoundary Face is not between two Rooms, then it should be changed to a different face type like a Wall, Roof, or Floor.

### 000207

**Room Composed Entirely of AirBoundaries** - The model contains a Room composed entirely of AirBoundary Faces. This condition is currently illegal in EnergyPlus since EnergyPlus is not equipped to model Rooms that contain no "real" geometry (Walls, Roofs, and Floors). This may change in the future depending on the outcome of [this issue](https://github.com/NREL/EnergyPlus/issues/9335) and this condition is currently completely valid for Radiance simulation.

It should be fixed by merging the Room composed entirely of AirBoundaries into a neighboring Room that contains "real" geometry (Walls, Roofs, and Floors).

## Radiance Error Codes

### 010001

**Duplicate Modifier Identifier** - Two or more Modifiers in the model have the same identifier. While Radiance will often let the simulation proceed with this situation, it can result in confusing results since Radiance will always use the first occurrence of the modifier that is found in the input files. This situation can also result in issues during the serialization of the model to/from any file format. For example, a geometry object may be assigned the incorrect modifier between the two duplicate identifiers.

This issue should be fixed by finding the object with the duplicate identifier and changing its identifier.

### 010002

**Duplicate ModifierSet Identifier** - Two or more ModifierSets in the model have the same identifier. This situation can result in issues during the serialization of the model to/from any file format. For example, a Room object may be assigned the incorrect ModifierSet between the two duplicate identifiers.

This issue should be fixed by finding the object with the duplicate identifier and changing its identifier.

### 010003

**Duplicate SensorGrid Identifier** - Two or more SensorGrids in the model have the same identifier. While this situation is typically safe for serializing the model to/from file formats, it will result in one sensor grid result overwriting another in any Radiance simulation of the model.

This issue should be fixed by finding the object with the duplicate identifier and changing its identifier.

### 010004

**Duplicate View Identifier** - Two or more Views in the model have the same identifier. While this situation is typically safe for serializing the model to/from file formats, it will result in one view overwriting another in any Radiance simulation of the model.

This issue should be fixed by finding the object with the duplicate identifier and changing its identifier.

### 010005

**SensorGrid Room Not In Model** - The model contains a SensorGrid that references a Room that is not in the Model (via the SensorGrid's room\_identifier property). This can often happen if a previously existing Room has been deleted from the model or some change has been made to reset identifiers of Rooms in the model. This situation may not need to be fixed for many simple types of Radiance simulations but will cause issues in more complex 3 or 5-phase simulations, which rely on the Room reference to determine the light sources.

This issue should be fixed by finding the SensorGrid and either removing its room\_identifier or changing it to match the Room that it is actually assigned to.

### 010006

**View Room Not In Model** - The model contains a View that references a Room that is not in the Model (via the View's room\_identifier property). This can often happen if a previously existing Room has been deleted from the model or some change has been made to reset identifiers of Rooms in the model. This situation may not need to be fixed for many simple types of Radiance simulations but will cause issues in more complex 3 or 5-phase simulations, which rely on the Room reference to determine the light sources.

This issue should be fixed by finding the View and either removing its room\_identifier or changing it to match the Room that it is actually assigned to.

## Energy Error Codes

### 020001

**Duplicate Material Identifier** - Two or more Material layers in the model have the same identifier. This is illegal in EnergyPlus, and it can also result in issues during the serialization of the model to/from any file format. For example, a construction may be assigned the incorrect material layer between the two duplicate identifiers.

This issue should be fixed by finding the object with the duplicate identifier and changing its identifier.

### 020002

**Duplicate Construction Identifier** - Two or more Constructions in the model have the same identifier. This is illegal in EnergyPlus, and it can also result in issues during the serialization of the model to/from any file format. For example, a Face or Aperture may be assigned the incorrect construction between the two duplicate identifiers.

This issue should be fixed by finding the object with the duplicate identifier and changing its identifier.

### 020003

**Duplicate ConstructionSet Identifier** - Two or more ConstructionSets in the model have the same identifier. This can result in issues during the serialization of the model to/from any file format. For example, a Room may be assigned the incorrect construction set between the two duplicate identifiers.

This issue should be fixed by finding the object with the duplicate identifier and changing its identifier.

### 020004

**Duplicate ScheduleTypeLimit Identifier** - Two or more ScheduleTypeLimits in the model have the same identifier. This is illegal in EnergyPlus and can result in issues during the serialization of the model to/from any file format. For example, a Schedule may be assigned the incorrect schedule type limit between the two duplicate identifiers.

This issue should be fixed by finding the object with the duplicate identifier and changing its identifier.

### 020005

**Duplicate Schedule Identifier** - Two or more Schedules in the model have the same identifier. This is illegal in EnergyPlus and can result in issues during the serialization of the model to/from any file format. For example, a ProgramType may be assigned the incorrect schedule between the two duplicate identifiers.

This issue should be fixed by finding the object with the duplicate identifier and changing its identifier.

### 020006

**Duplicate ProgramType Identifier** - Two or more ProgramTypes in the model have the same identifier. This can result in issues during the serialization of the model to/from any file format. For example, a Room may be assigned the incorrect program type between the two duplicate identifiers.

This issue should be fixed by finding the object with the duplicate identifier and changing its identifier.

### 020007

**Duplicate HVAC Identifier** - Two or more Heating, Ventilation, and Air Conditioning (HVAC) systems in the model have the same identifier. This can result in issues during the serialization of the model to/from any file format. For example, a Room may be assigned the incorrect HVAC system between the two duplicate identifiers.

This issue should be fixed by finding the object with the duplicate identifier and changing its identifier.

### 020008

**Duplicate SHW Identifier** - Two or more Service Hot Water (SHW) systems in the model have the same identifier. This can result in issues during the serialization of the model to/from any file format. For example, a Room may be assigned the incorrect SHW system between the two duplicate identifiers.

This issue should be fixed by finding the object with the duplicate identifier and changing its identifier.

### 020009

**SHW System Room Not In Model** - The model contains a Service Hot Water (SHW) system that references a Room under its ambient\_condition, which is not present in the model. SHW Systems can be placed within Honeybee Rooms in order to model the heat loss from the hot water tank to the Room. In the case of heat pump water heaters, this is also used to model the fact that the water heater will pull heat from the room in order to heat the water in the tank. So this Room that contains the SHW system must be present in the model for it to be simulate-able.

This issue is most easily fixed by changing the SHW Systems' ambient\_condition to a temperature value in Celsius or to a Room that is known to be within the model.

### 020010

**Multiple Vegetation Materials** - The model contains more than one Vegetation Material across its Constructions, which are used to model green roofs and approximate the temperatures of vegetated surfaces. EnergyPlus is unable to simulate models with more than one vegetation material because of its own internal limitations.

The easiest way to fix the issue is to remove one of the vegetation materials or make sure that only one vegetation material is assigned to the geometry in the model.

### 020011

**Room With HVAC Lacks Setpoint** - The model contains a Room without a thermostat setpoint specification but with a detailed HVAC assigned to it. This creates a situation that cannot be simulated in EnergyPlus since it is unclear what temperature the assigned HVAC system should heated and cool the space to.

This issue is most easily fixed by assigning a Program with a Setpoint specification to the Room with the HVAC. Alternatively, if the Room is actually unconditioned, then the HVAC assigned to the Room must be removed.

### 020012

**DetailedHVAC Rooms Not In Model** - The model contains a Detailed HVAC system, which references Rooms that are not in the model. This can happen when some of the original Rooms that the HVAC was assigned to have been deleted. The model will be un-simulate-able in EnergyPlus if the Detailed HVAC system continues to reference the non-existent Room.

This issue can typically be fixed by editing the Detailed HVAC system and reassigning Rooms to it from the Model.

### 020013

**Room Referenced by Multiple Detailed HVAC** - The model contains two or more Detailed HVAC systems that reference the same Room. This can create situations where it is unclear which HVAC is intended to deliver the heating and cooling.

This issue can typically be fixed by editing the Detailed HVAC systems of the model and reassigning Rooms to each system such that each Room has only one HVAC.

### 020201

**Mismatched Adjacent Constructions** - Two adjacent Faces, Apertures, or Doors do not have constructions with material layers that are in reversed order from each other, thereby making the order of material layers for the interior Wall, Floor, or Window ambiguous. This is illegal in EnergyPlus and typically results from applying the same asymmetric construction to an adjacent Face or Aperture pair. It can also happen if two adjacent geometry objects have completely different constructions from one another.

The simplest way to fix the issue is to re-assign a symmetric construction to both adjacent objects. Symmetric constructions are ones where the reversed order of materials is the same as the non-reversed order. The issue can also be solved by taking an existing asymmetric construction, duplicating it, reversing its material order, giving it a new name/identifier, and assigning it to the other adjacent object.

## Dragonfly Error Codes

### 100001

**Duplicate ContextShade Identifier** - Two or more ContextShades in the model have the same identifier. This is not only illegal in EnergyPlus and can cause strange behavior in Radiance, but it can also result in errors during the serialization of the model to/from any file format. For example, properties for EnergyPlus or Radiance may be assigned to the incorrect object. This issue should be fixed by finding the object with the duplicate identifier and changing its ID or deleting the object.

### 100002

**Duplicate Room2D Identifier** - Two or more Rooms in the model have the same identifier. This is not only illegal in EnergyPlus and can cause strange behavior in Radiance, but it can also result in errors during the serialization of the model to/from any file format. For example, properties for EnergyPlus or Radiance may be assigned to the incorrect object. This issue should be fixed by finding the object with the duplicate identifier and changing its ID or deleting the object.

### 100003

**Duplicate Story Identifier** - Two or more Stories in the model have the same identifier. This can result in errors during the serialization of the model to/from any file format. For example, properties for EnergyPlus or Radiance may be assigned to the incorrect object. This issue should be fixed by finding the object with the duplicate identifier and changing its ID or deleting the object.

### 100004

**Duplicate Building Identifier** - Two or more Buildings in the model have the same identifier. This can result in errors during the serialization of the model to/from any file format. For example, properties for EnergyPlus or Radiance may be assigned to the incorrect object. This issue should be fixed by finding the object with the duplicate identifier and changing its ID or deleting the object.

### 100101

**Degenerate Room Geometry** - There is a Room in the model that effectively has zero volume from the perspective of the Model tolerance. This can happen when all of the wall segments of a Room2D are colinear with one another, effectively making a "sliver" Room. It is a common side-effect of aligning small rooms. Often, the best fix for this case is to simply delete the degenerate room from the model.

In the dragonfly Python libraries, the `Story.delete_degenerate_room_2ds()` method can be used to remove all degenerate Room2Ds from a Story.

### 100102

**Self-Intersecting Room Geometry** - There is a Room in the model with floor geometry that intersects itself (like a bowtie). This can cause issues when performing shading calculations in both Radiance and EnergyPlus and other interfaces like IES-VE, IDA-ICE, and eQuest will throw errors if they discover this type of condition.

Note that duplicated vertices are still considered valid and vertices are considered duplicates if they are close to each other within the Model tolerance. So this error will typically only arise when the edges of the object noticeably intersect one another.

Typically, the geometry must be redrawn in order to fix it, though it is sometimes possible to fix it simply by rearranging vertices.

### 100103

**Invalid Window Parameters** - Window parameters are formatted such that the resulting Apertures do not lie completely inside the parent Wall Face boundary. When the dragonfly geometry is translated to honeybee, the windows that are outside the boundary of the Walls will be automatically clipped. So this error does not produce an invalid Honeybee Model. However, it does mean that properties of the dragonfly Model like `exterior_aperture_area` will not be correct and, ideally, it should be corrected.

Note that this error will still arise even when the window parameters produce an Aperture or Door that is only sharing an edge with the parent Wall Face, which is technically still acceptable for certain Energy simulations but will often cause issues in Radiance and will result in display issues for most model viewers.

In the dragonfly Python libraries, the `Story.rebuild_detailed_windows()` method can be used to automatically clip detailed window parameters so they are bounded by the parent walls.

### 100104

**Overlapping Room Geometries** - Rooms of the same Story have floor geometries that overlap with one another in plan. Overlaps in Room floor geometries mean that the Room volumes collide with one another. While this condition is not necessarily un-simulate-able in EnergyPlus or Radiance, it represents a condition that would not be logical in reality and several other energy modeling interfaces like IES-VE, IDA-ICE, and eQuest will throw errors if they discover this type of condition.

Note that this validation check accounts for the Model tolerance such that room overlaps smaller than the tolerance are ignored. So this validation error only arises for cases where the room floors noticeably overlap with one another or one room completely encompasses another.

Typically, the Room geometry must either be redrawn or a different type of bounding element must be used to generate the rooms in order to fix it. Visualizing the rooms that overlap and finding the exact overlapping region can sometimes make it possible to fix the error just by moving the room polygon vertices.

### 100105

**Invalid Roof** - The geometries that make up the Story's Roof are below the floors of the Story's Room2Ds. Roofs that lie below Room2Ds can result in invalid Honeybee Rooms with self-intersecting walls. As a result, these Room2Ds are translated to Honeybee simply by extruding the floor plat to the floor_to_ceiling_height instead of extending walls to the roof geometries.

Correcting this error often involves deleting the roof geometries that are below the Room2Ds or running the routine that resolves the roof geometry's overlaps.

### 100106

**Invalid Room Floor Elevation** - The Story has Room2D floor elevations that are too different from one another to be a part of the same Story. Oftentimes, this can happen because all of the Room2Ds of a Building were accidentally added to the same Story when they should have been placed on separate Stories. However, it can also happen if floor elevations of certain Room2Ds in the Story were edited to the point that it no longer makes sense to have them on the same Story as the other Room2Ds.

The validation error message(s) should give detailed information about the fastest way to make the Story valid by changing the smallest number of Room2D floor heights. These recommendations may be useful in the case where floor elevations of a few Room2Ds in the Story were edited. However, in situations where this error arose by accidentally adding all of the Room2Ds of a Building to the same Story, separating the Room2Ds into different Stories is likely the better approach.

### 100201

**Mismatched Adjacency** - The model contains a Room2D with a Surface boundary condition that references the wall segment of another Room2D, which lacks a Surface boundary condition. The fact that the Surface boundary condition is not reciprocated may not result in a failure to translate the model from dragonfly to honeybee but it can cause unexpected results and validation errors in the resulting honeybee model like mis-matched area adjacencies.

This error can usually be fixed by re-solving adjacencies with the intersection step selected in order to ensure any mismatched wall segments are correctly split with their neighboring geometry.

### 100202

**Mismatched WindowParameter Adjacency** - The model contains a Room2D with a Surface boundary condition referencing another Room2D wall segment that does not have the same window parameters. This can often happen if a previously existing Room2D has been deleted from the model or some change has been made to reset identifiers or boundary conditions in the model. Mis-matched window parameters will cause a failure to translate from dragonfly to honeybee by default. In this case, the `--bypass-adj-check` option can be used to get the translation to honeybee to proceed by replacing the illegal boundary condition with an Outdoors one.

This error can usually be fixed by re-solving adjacency with the intersection step selected to erase the older invalid adjacencies.

### 100203

**Missing Adjacency** - The model contains a Room2D with a Surface boundary condition referencing another Room2D or wall segment that is not in the Story. This can often happen if a previously existing Room2D has been deleted from the model or some change has been made to reset identifiers or boundary conditions in the model. A missing adjacency will cause a failure to translate from dragonfly to honeybee by default. In this case, the `--bypass-adj-check` option can be used to get the translation to honeybee to proceed by replacing the illegal boundary condition with an Outdoors one.

This error can usually be fixed by re-solving adjacency with the intersection step selected to erase the older invalid adjacencies.