# Getting Started in Rhino

There are two interfaces for Pollination in Rhino. You can use the Pollination panel to use buttons to create your analytical model, or you can type Pollination commands in the command line.&#x20;

## Pollination Panel

To pull up the Pollination panel, type `Pollination` in the command line. Once you hit Enter, the Pollination panel will emerge. You can dock it in your window as you would a native Rhino panel.

{% embed url="https://youtu.be/qJQCc59EdCw" %}

## Pollination Commands

A list of Pollination Commands for Rhino with detailed descriptions is available in this user manual. You can also type "PO\_" in the command line to preview a list of commands in Rhino.

{% content-ref url="pollination-commands/" %}
[pollination-commands](pollination-commands/)
{% endcontent-ref %}

### Native Rhino Command Compatibility

Besides custom Pollination commands, there are several native Rhino commands that can be used to modify custom Pollination RhinoObjects.

|                              ACTION                             | COMMAND LINE |       | KEYBOARD SHORTCUT |
| :-------------------------------------------------------------: | :----------: | :---: | :---------------: |
|                          COPY / CTRL+C                          |     **✔**    | **✔** |       **✔**       |
|                           CUT / CTRL+X                          |     **✔**    |       |       **✔**       |
|                          PASTE / CTRL+V                         |     **✔**    | **✔** |       **✔**       |
|                          UNDO / CTRL+Z                          |     **✔**    |       |       **✔**       |
|                          REDO / CTRL+Y                          |     **✔**    |       |       **✔**       |
|                              DELETE                             |     **✔**    |       |       **✔**       |
|                               MOVE                              |     **✔**    | **✔** |                   |
|  <p>MOVE SUB-GEOMETRY</p><p><em>(Hold Shift+Ctrl keys)</em></p> |     **✔**    | **✔** |                   |
|                    SCALE, SCALE 1D, SCALE 2D                    |     **✔**    | **✔** |                   |
|                      MOVE FACE / MOVE EDGE                      |     **✔**    |       |                   |
| <p>EXPLODE</p><p><em>(RoomObject=> OrphanedFaces only)</em></p> |     **✔**    |       |                   |
|       <p>JOIN</p><p>(OrphanedFaces => RoomObject only)</p>      |     **✔**    |       |                   |
|                      SPLITFACE / MERGEFACE                      |     **✔**    |       |                   |
|                             FLIP/DIR                            |     **✔**    |       |                   |
|                               CAP                               |     **✔**    |       |                   |
|                           TRIM/UNTRIM                           |     **✔**    |       |                   |



![Edit Room Geometry](<../.gitbook/assets/editroomgeometry (1).gif>)

![Undo and Redo Commands](../.gitbook/assets/undoredo.gif)

![Move Face & Move Edge Using Rhino Command line](../.gitbook/assets/moveface\_moveedge\_cmd.gif)

![Move Face & Move Edge Using Gumball](../.gitbook/assets/moveface\_moveedge.gif)
