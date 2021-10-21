# Getting Started

## Compatibility

The Pollination Rhino plugin is designed for optimal compatibility with Rhino 7. If you are using Rhino 6, there is an incompatibility issue with the way Rhino 6 loads plugins. After installing Pollination, you will need to open and close Rhino **three times** to load the Pollination plugin.&#x20;

You can use the Pollination in Rhino using the Pollination panel or type Pollination commands in the command line. A list of [Pollination Commands for Rhino](pollination-commands-for-rhino/) with detailed descriptions in available in this user manual. You can also type "PO\_" in the command line to preview a list of commands in Rhino.

## Sample Analytical Model

{% file src="../.gitbook/assets/model.zip" %}
Download the sample model
{% endfile %}

## Pollination Panel

To pull up the Pollination panel, type `Pollination` in the command line. Once you hit Enter, the Pollination panel will emerge. You can dock it in your window as you would a native Rhino panel.&#x20;

{% embed url="https://youtu.be/qJQCc59EdCw" %}

## Native Rhino Command Compatibility

Besides custom [Pollination Commands for Rhino](pollination-commands-for-rhino/), there are several native Rhino commands that can be used to modify custom Pollination RhinoObjects.

| ACTION                                                           | COMMAND-LINE | GUMBALL | <p>KEYBOARD </p><p>SHORTCUT</p> |
| ---------------------------------------------------------------- | :----------: | :-----: | :-----------------------------: |
| COPY / CTRL+C                                                    |     **✔**    |  **✔**  |              **✔**              |
| CUT / CTRL+X                                                     |     **✔**    |         |              **✔**              |
| PASTE / CTRL+V                                                   |     **✔**    |  **✔**  |              **✔**              |
| UNDO / CTRL+Z                                                    |     **✔**    |         |              **✔**              |
| REDO / CTRL+Y                                                    |     **✔**    |         |              **✔**              |
| DELETE                                                           |     **✔**    |         |              **✔**              |
| MOVE                                                             |     **✔**    |  **✔**  |                                 |
| <p>MOVE SUB-GEOMETRY</p><p><em>(Hold Shift+Ctrl keys)</em></p>   |     **✔**    |  **✔**  |                                 |
| SCALE, SCALE 1D, SCALE 2D                                        |     **✔**    |  **✔**  |                                 |
| MOVE FACE / MOVE EDGE                                            |     **✔**    |         |                                 |
| <p>EXPLODE </p><p><em>(RoomObject=> OrphanedFaces only)</em></p> |     **✔**    |         |                                 |
| <p>JOIN </p><p>(OrphanedFaces => RoomObject only)</p>            |     **✔**    |         |                                 |
| SPLITFACE / MERGEFACE                                            |     **✔**    |         |                                 |
| FLIP/DIR                                                         |     **✔**    |         |                                 |
| CAP                                                              |     **✔**    |         |                                 |
| TRIM/UNTRIM                                                      |     **✔**    |         |                                 |

![Edit Room Geometry](<../.gitbook/assets/editroomgeometry (1) (1).gif>)



![Undo and Redo Commands](../.gitbook/assets/undoredo.gif)

![Move Face & Move Edge Using Rhino Command line](../.gitbook/assets/moveface\_moveedge\_cmd.gif)

![Move Face & Move Edge Using Gumball](../.gitbook/assets/moveface\_moveedge.gif)
