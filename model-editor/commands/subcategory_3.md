# Room Adjacency Commands

## <img src="../../.gitbook/assets/air-boundaries.svg" width="30" height="30"> Set air boundaries

Set the adjacencies between the selected rooms to use air boundaries. Note that adjacencies should be solved between rooms before running this method in order for it to have any effect. If lines are selected while running this command, they will be used to set air boundaries for only the adjacencies that are coincident with those lines.

---

## <img src="../../.gitbook/assets/solve-adjacency.svg" width="30" height="30"> Solve adjacency

Solve adjacency between selected rooms by assigning interior boundary conditions where rooms touch one another

<details>

<summary>Options</summary>

**Ceiling Adjacencies**

  Select to have the adjacency between the stories solved

</details>

You can optionally turn off the `Ceiling Adjacency` if you are planing to export to a platform with it's own adjacency-solving routine (eg. IES-VE) or you are primarily interested in simulating each Story as a distinct unit with adiabatic floors and ceilings. This command will only be visible when more than one room is selected.

---