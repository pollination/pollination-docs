---
description: Object for managing and accessing objects from the Model Editor
---

# Editor Class API Documentation

The `Editor` class is a special class that allows you to manage and access the objects from the Model Editor. Use the line below to access the Editor.

```python
from model_editor import Editor
```



See below for the list of Properties and methods.

## Properties

### model

Get the entire Dragonfly Model currently on the canvas.

### selected\_room\_2ds

Get the currently selected Room2Ds on the canvas.

### selected\_room\_3ds

Get the currently selected 3D Rooms on the canvas.

### selected\_shades

Get the currently selected ContextShade objects on the canvas.

### clines

Get a list of LineSegment2D, Polyline2D, and Polygon2D objects on the canvas.

### units

Get the units system of the Model currently on the canvas.

### tolerance

Get the tolerance of the Model currently on the canvas.

### angle\_tolerance

Get the angle tolerance of the Model currently on the canvas.

## Methods

### Update()

Update the Model in the editor with any edits that have been made.
