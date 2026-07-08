# Auto align

<img src="../../.gitbook/assets/auto-align (1).svg" alt="" height="50" width="50">

Automatically align selected rooms to common axes identified across them. The command is intended to automatically perform most of the alignments that would typically be done manually. Note that having a line selected while running this command will force the generated alignment axes to be generated only in the plane of that line.

## Options

*   **Distance**

    The distance with which room vertices will be aligned to common axes. No vertex in the input rooms will be moved more than this distance
*   **Exclude Angle**

    A positive number in degrees for the maximum difference that a geometry segment can differ from the alignment axes for it to be ignored/excluded from alignment
*   **Axes Only**

    Select to have this command only output the common axes of the selected rooms into the scene and not perform any auto-alignment of rooms with these axes. This can give more control over which axes are or are not used by allowing manual selection and aligning with desired axes
*   **Use Anchor Lines**

    Select to have the currently selected line geometry override any suggested alignment axes. This can be used to ensure that auto-aligning does not move parts of the model that are already correct.
*   **Constrain Group Boundary**

    Select to have the boundary around the rooms set as anchor lines, ensuring that the outer edges of the group do not move during alignment and only cases within the room group are aligned
*   **Group by Base Plane**

    Select to have the command group the selected rooms by the underlying base plane that best fits the room geometry before auto-aligning them. This is useful in cases where the selected rooms contain different structural grids that are at angles to one another.
*   **Base Story Name**

    Optional text for the name of the level among the selected rooms to be used as a base for auto-aligning the other rooms in the selection. Rooms on this base story will not be edited during the alignment operation.
