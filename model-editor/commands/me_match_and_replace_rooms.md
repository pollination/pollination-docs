# Match and replace rooms

![](../../.gitbook/assets/match-and-replace.svg)

Replace the room floor plate geometry of selected rooms using the rooms of a base story in the selection. This is useful for the case that several stories with repeated room geometry exist over the building all with unique room names and window geometry. However, only one story represents the clean room floor plates such that a desired result can be achieved by simply replacing the room geometry of the other stories with that of the base story.

## Options

*   **Base Story Name**

    Text for the name of the level in the building that represents the clean room geometry to be used as a base for all of the stories to be replaced
*   **Overlap Percent**

    A number between that represents the percentage of total floor area overlap between a given base room and a room in the replaced stories at which point the room will be replaced with the geometry from the base story. It is recommended that 50% be used as the lowest and most lenient overlap here given that lower numbers have the potential to match a room to two or more rooms in the base story
*   **Projection Distance**

    A number to be used to project the original window and door geometry back onto the wall segments of each room after the floor geometry has been replaced. If the windows/doors on the original geometry do not differ by more than this distance between the base room and the replaced room, these original windows will be preserved
*   **Angle Tolerance**

    Angle tolerance in degrees, which sets the maximum angle difference between the normal vectors of a window and wall at which point the window will be projected onto the wall and assigned to it
*   **Remove Unmatched**

    Select to have the rooms in the selection the that are not matched to any room on the base story removed from the model. This is useful when the clean up of the base story included deletion of several small rooms, which you want to be removed from the other stories during replacement
