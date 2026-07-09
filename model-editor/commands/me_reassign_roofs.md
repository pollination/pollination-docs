# Reassign roofs

<img src="../../.gitbook/assets/reassign-roofs (1).svg" alt="" height="50" width="50">

Reassign the model's roof geometries to the stories to which they are most applicable. This is useful after splitting roof geometries with story boundaries such that different roof elements are now applicable to different stories.

## Options

*   **Overlap Threshold**

    A number between 0 and 100 for the percent of a room's area that must be covered by a given roof geometry for it to be considered covering that room. Using a non-zero value can prevent incorrect roof assignment in cases where roofs extend slightly past the room they are intended for.
