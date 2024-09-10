# Getting Started in Rhino

There are several interfaces and interaction points for Pollination in Rhino.&#x20;

* [Pollination Room Manager](getting-started.md#pollination-room-manager): An icon and table-based interface allowing for analytical model creation, edits, and management.
* Pollination Panel: Brings the Pollination [Web Platform](broken-reference) into Rhino so that you can access Pollination [Apps](../developers/apps/).&#x20;
* [Pollination Commands](getting-started.md#pollination-commands): Type in commands from getting a license to building a shade element.&#x20;

## Pollination Room Manager

To pull up the Pollination Room Manager, type `Pollination` in the command line. Once you hit Enter, a panel will emerge that you can dock in your window as you would a native Rhino panel.

{% embed url="https://youtu.be/qJQCc59EdCw" %}

## Pollination Panel&#x20;

To access apps from within Pollination, type `PO_Panel` in the command line.&#x20;

## Pollination Commands

A list of Pollination Commands for Rhino with detailed descriptions is available in this user manual. You can also type "PO\_" in the command line to preview a list of commands in Rhino.

{% content-ref url="pollination-commands/" %}
[pollination-commands](pollination-commands/)
{% endcontent-ref %}

### Native Rhino Command Compatibility

Besides custom Pollination commands, several native Rhino commands can be used to modify custom Pollination RhinoObjects.

|                              ACTION                             | COMMAND LINE | GUMBALL | KEYBOARD SHORTCUT |
| :-------------------------------------------------------------: | :----------: | :-----: | :---------------: |
|                          Copy / CTRL+C                          |     **✔**    |  **✔**  |       **✔**       |
|                           Cut / CTRL+X                          |     **✔**    |         |       **✔**       |
|                          Paste / CTRL+V                         |     **✔**    |  **✔**  |       **✔**       |
|                          Undo / CTRL+Z                          |     **✔**    |         |       **✔**       |
|                          Redo / CTRL+Y                          |     **✔**    |         |       **✔**       |
|                              Delete                             |     **✔**    |         |       **✔**       |
|              Move / GumballDrag / GumballTransform              |     **✔**    |  **✔**  |                   |
|  <p>Move Sub-Geometry</p><p><em>(Hold Shift+Ctrl keys)</em></p> |     **✔**    |  **✔**  |                   |
|                    Scale / Scale1D / Scale2D                    |     **✔**    |  **✔**  |                   |
|                        Rotate / Rotate3D                        |     **✔**    |  **✔**  |                   |
|                       MoveFace / MoveEdge                       |     **✔**    |         |                   |
| <p>Explode</p><p><em>(RoomObject=> OrphanedFaces only)</em></p> |     **✔**    |         |                   |
|       <p>Join</p><p>(OrphanedFaces => RoomObject only)</p>      |     **✔**    |         |                   |
|                      SplitFace / MergeFace                      |     **✔**    |         |                   |
|                            Flip / Dir                           |     **✔**    |         |                   |
|                               Cap                               |     **✔**    |         |                   |
|                   Trim / Untrim / UntrimHoles                   |     **✔**    |         |                   |
|                              Mirror                             |     **✔**    |         |                   |
|                      MergeAllCoplanarFaces                      |     **✔**    |         |                   |

![Undo and Redo Commands](../.gitbook/assets/undoredo.gif)

![Move Face & Move Edge Using Rhino Command line](../.gitbook/assets/moveface\_moveedge\_cmd.gif)

![Move Face & Move Edge Using Gumball](../.gitbook/assets/moveface\_moveedge.gif)
