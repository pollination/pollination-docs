# Auto align

![](<../../.gitbook/assets/auto-align (1).svg>)

Automatically align selected rooms to common axes identified across them. The command is intended to automatically perform most of the alignments that would typically be done manually. Note that having a line selected while running this command will force the generated alignment axes to be generated only in the plane of that line.

## Options

*   **Distance**

    The distance with which room vertices will be aligned to common axes. No vertex in the input rooms will be moved more than this distance
*   **Exclude Angle**

    A positive number in degrees for the maximum difference that a geometry segment can differ from the alignment axes for it to be ignored/excluded from alignment
*   **Story-by-Story**

    Select to have this command run with each story individually rather than all stories of the model together. Running story-by-story tends to produce a more controlled and result with fewer unintended alignments happening. This is useful when the model is large and rooms between stories do not have a strong relation to one another.
*   **Axes Only**

    Select to have this command only output the common axes of the selected rooms into the scene and not perform any auto-alignment of rooms with these axes. This can give more control over which axes are or are not used by allowing manual selection and aligning with desired axes
