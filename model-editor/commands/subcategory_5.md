# Room Visualize Commands

Below are the commands that visualize the rooms or properties of the rooms.

## <img src="images/3d-preview.svg" width="30" height="30"> 3D preview

Show the selected rooms and shades in 3D. The preview shows up in a new floating window.

---

## <img src="images/find-adjacency-gaps.svg" width="30" height="30"> Find adjacency gaps

Identify gaps smaller than a specified gap distance. Such gaps typically do not make the model invalid or un-simulate-able but they can create cases where adjacency solving fails to set interior boundary conditions where they likely should be. Small gaps can also result in sliver geometries for floors/ceilings in the case the inter-story adjacencies are solved.

---

## <img src="images/validate-model.svg" width="30" height="30"> Validate

Check whether the selected rooms are valid/simulate-able. Valid models should export to any of the supported BEM engines without errors. Invalid models will have their errors presented in a table with the option to select the part of the model where the error originates so that it can be fixed.

---

## <img src="images/validate-model.svg" width="30" height="30"> Validate model

Check whether the selected rooms are valid/simulate-able. Valid models should export to any of the supported BEM engines without errors. Invalid models will have their errors presented in a table with the option to select the part of the model where the error originates so that it can be fixed.

---