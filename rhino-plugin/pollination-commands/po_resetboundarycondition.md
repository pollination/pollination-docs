# PO_ResetBoundaryCondition

Resets the boundary condition for all child faces of a room or for selected child faces. You can select specific sub-faces of a room by holding the Shift + Ctrl keys.

Notes:
- The boundary condition for all geometries will be reset to Outdoor, except for geometries touching the ground (0), which will be set to Ground.
- Apertures and doors will also be reset to the Outdoor boundary condition.
- Face type with AirBoundary will be reset to Wall.

