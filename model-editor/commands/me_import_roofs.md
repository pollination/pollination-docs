# Import roofs

![](<../../.gitbook/assets/import-roofs (1).svg>)

Import roofs from a HBJSON file. All orphaned shades in the HBJSON file are translated to roof elements.

## Options

*   **Replace Current Roofs**

    Select to have all of the roofs currently within the model replaced by the new roof geometries in the imported HBJSON file. If deselected, the roofs will simply be added to the current roof geometries in the model.
*   **Is Revit Sourced**

    Select if the HBJSON file with roofs has been exported directly from the Revit model. If so, the roof geometry will be synchronized with the model's units and coordinate system if they have changed from the original Revit model.
