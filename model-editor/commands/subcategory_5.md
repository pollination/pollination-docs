# Room Visualize Commands

Below are the commands that visualize the rooms or properties of the rooms.

## <img src="images/3d-preview.svg" width="30" height="30"> 3D preview

Show the selected rooms and shades in 3D. The preview shows up in a new floating window.

<details>

<summary>Options</summary>

**Ceiling Adjacencies**

  Select to have the adjacency between the stories solved

**Exclude Plenums**

  Select to have ceiling and floor plenum depths ignored. This results in each room in the table translating to a single room in 3D instead of a base room with plenums split off of it

</details>

{% embed url="https://drive.google.com/open?id=1XXyLpIH1oNf8FZ4CV9fvfH15tyQ8E5Ty&usp=drive_fs" %}
3D Preview
{% endembed %}

---

## <img src="images/find-adjacency-gaps.svg" width="30" height="30"> Find adjacency gaps

Identify gaps smaller than a specified gap distance. Such gaps typically do not make the model invalid or un-simulate-able but they can create cases where adjacency solving fails to set interior boundary conditions where they likely should be. Small gaps can also result in sliver geometries for floors/ceilings in the case the ceiling adjacencies are solved.

<details>

<summary>Options</summary>

**Gap Distance**

  The maximum distance between two rooms that is considered an unwanted adjacency gap. Differences between rooms that are higher than this distance are considered meaningful separations between rooms that should be preserved. Typical recommended values might be around 15 cm or 6''.

</details>

---

## <img src="images/validate-model.svg" width="30" height="30"> Validate model

Check whether the selected rooms are valid/simulate-able. Valid models should export to any of the supported BEM engines without errors. Invalid models will have their errors presented in a table with the option to select the part of the model where the error originates so that it can be fixed.

<details>

<summary>Options</summary>

**Destination Engine**

  The destination engine for which validation will be performed. Selecting an option here will ignore checks that are not relevant for the engine. Use the 'All' option to validate for all engines.

</details>

{% embed url="https://drive.google.com/open?id=1K4iUHPC9lKHDfJenTkUSycjKys9rvw_j&usp=drive_fs" %}
Validate Model
{% endembed %}

---