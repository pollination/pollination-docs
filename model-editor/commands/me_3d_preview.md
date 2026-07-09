# 3D preview

<img src="../../.gitbook/assets/3d-preview (1).svg" alt="" height="50" width="50">

Show the selected rooms and shades in 3D. The preview shows up in a new floating window.

## Options

*   **Inter-Story Adjacencies**

    Select to have the adjacency between the stories solved
*   **Exclude Plenums**

    Select to have ceiling and floor plenum depths ignored. This results in each room in the table translating to a single room in 3D instead of a base room with plenums split off of it
*   **Merge Method**

    Select how the rooms are merged during the translation. Merging rooms can reduce the complexity of the resulting Model and ultimately yield a faster simulation time with fewer results to manage. Note that rooms will only be merge-able if they form a contiguous volume across their solved adjacencies.
