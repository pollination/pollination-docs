# PO_SolveAdjacency

Use this command to split and match walls between rooms. If non-room geometries are selected, this command only splits for each subsurface.

## Options

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

* Apertures and doors will be adjusted to match new walls.
* The boundary condition of the aperture or door won&apos;t be changed if its outdoor walls become indoor surfaces.

## Video Tutorials

{% embed url="https://youtu.be/5T9VWc96hyk" %}Solve adjacency in a model{% endembed %}

