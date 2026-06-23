# Room Visualize Commands

Below are the commands that visualize the rooms or properties of the rooms.

## <img src="images/3d-preview.svg" width="30" height="30"> 3D preview

Show the selected rooms and shades in 3D. The preview shows up in a new floating window.

<details>

<summary>Options</summary>

**Inter-Story Adjacencies**

  Select to have the adjacency between the stories solved

**Exclude Plenums**

  Select to have ceiling and floor plenum depths ignored. This results in each room in the table translating to a single room in 3D instead of a base room with plenums split off of it

**Merge Method**

  Select how the rooms are merged during the translation. Merging rooms can reduce the complexity of the resulting Model and ultimately yield a faster simulation time with fewer results to manage. Note that rooms will only be merge-able if they form a contiguous volume across their solved adjacencies.

</details>

---

## <img src="images/find-adjacency-gaps.svg" width="30" height="30"> Find adjacency gaps

Identify gaps smaller than a specified gap distance. Such gaps typically do not make the model invalid or un-simulate-able but they can create cases where adjacency solving fails to set interior boundary conditions where they likely should be. Small gaps can also result in sliver geometries for floors/ceilings in the case the inter-story adjacencies are solved.

<details>

<summary>Options</summary>

**Gap Distance**

  The maximum distance between two rooms that is considered an unwanted adjacency gap. Differences between rooms that are higher than this distance are considered meaningful separations between rooms that should be preserved. Typical recommended values might be around 15 cm or 6''.

</details>

---

## <img src="images/validate-model.svg" width="30" height="30"> Validate

Check whether the selected rooms are valid/simulate-able. Valid models should export to any of the supported BEM engines without errors. Invalid models will have their errors presented in a table with the option to select the part of the model where the error originates so that it can be fixed.

---

## <img src="images/validate-model.svg" width="30" height="30"> Validate model

Check whether the selected rooms are valid/simulate-able. Valid models should export to any of the supported BEM engines without errors. Invalid models will have their errors presented in a table with the option to select the part of the model where the error originates so that it can be fixed.

<details>

<summary>Options</summary>

**Destination engine**

  The destination engine for which validation will be performed. Selecting an option here will ignore checks that are not relevant for the engine. Use the 'Generic' option if the intention is to make a model for multiple engines.

**Include Warnings**

  Select to have validation run checks for cases that are not true errors but are likely still indicative of poor modeling that should be fixed. For example, selecting this option will run a check for small gaps between rooms, which does not make the model invalid but will probably result in interior boundary conditions not being assigned in cases where they are expected.

</details>

---