# Room Visualize Commands

## ![](../../.gitbook/assets/3d-preview.svg#thumbnail) 3D preview

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

## ![](../../.gitbook/assets/find-adjacency-gaps.svg#thumbnail) Find adjacency gaps

Identify gaps smaller than a specified gap distance. Such gaps typically do not make the model invalid or un-simulate-able but they can create cases where adjacency solving fails to set interior boundary conditions where they likely should be. Small gaps can also result in sliver geometries for floors/ceilings in the case the ceiling adjacencies are solved.

<details>

<summary>Options</summary>

**Gap Distance**

  The maximum distance between two rooms that is considered an unwanted adjacency gap. Differences between rooms that are higher than this distance are considered meaningful separations between rooms that should be preserved. Typical recommended values might be around 15 cm or 6''.

</details>

---

## Floor area change

Visualize the change in floor area that has happened as a result of editing operations.

<details>

<summary>Options</summary>

**Legend Min**

  The minimum value of the legend for the change in floor area

**Legend Max**

  The maximum value of the legend for the change in floor area

**Color Scheme**

  The color scheme for the visualization

</details>

---

## ![](../../.gitbook/assets/validate-model.svg#thumbnail) Validate model

Check whether the selected rooms are valid/simulate-able. Valid models should export to any of the supported BEM engines without errors. Invalid models will have their errors presented in a table with the option to select the part of the model where the error originates so that it can be fixed.

{% embed url="https://drive.google.com/open?id=1K4iUHPC9lKHDfJenTkUSycjKys9rvw_j&usp=drive_fs" %}
Validate Model
{% endembed %}

---

<style>
img[src*="#thumbnail"] {
   width:30px;
   height:30px;
}
</style>