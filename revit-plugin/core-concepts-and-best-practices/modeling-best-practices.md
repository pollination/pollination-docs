---
description: The ideal Revit model for Pollination
---

# Modeling Best Practices

The Pollination Revit plugin is designed to work with any Revit model, but following these best practices will save you and your team the time needed for extracting valid analytical models from Revit. You can share this document with the person who is in charge of managing the Revit model.

\
**Review rooms, spaces**, **or areas to be placed correctly**\
The Pollination Revit plugin uses rooms, spaces, or areas as the source of the geometry for creating Pollination rooms (also known as thermal zones in energy modeling tools). Make sure they are placed correctly in the Revit file, as well as that they are placed on the desired Level.\
\
**Minimize the use of separation lines**\
There are cases in which one might need to use separation lines to bound the rooms or break them down, but try to minimize the use of separation lines as long as possible. Instead, rely on the room-bounding properties of the Revit elements to create the rooms and spaces.\
\
**Review the model for unintended room-bounding objects**\
The geometry of rooms, spaces, or areas in Revit can be affected by various room-bounding objects in the model. Primarily, these are Walls/Floors and Ceilings, but other objects and Families can also be room-bounding. It's a good practice to turn off room-bounding for Columns, Casework, or even sometimes Walls that were modeled with the intent to represent a Wall Finish.\
\
**Minimize the number of window and curtain wall types**\
The Pollination plugin uses the windows and curtain walls to identify the apertures in the model. The plugin can manage as many types as needed, but the user needs to select the ones that represent an aperture in the model. The fewer the number of them, the easier the review process.\
\
**Simplify Revit families whenever possible**\
The pollination plugin parses all of the windows, curtain walls, and doors in the model. The simpler they are, the better. Complex nested Families and over-detailed geometries in families can lead to slower performance and lower quality. If possible, simplify your Families or replace them with less detailed versions.\
\
**Minimize the use of design options**\
Since most of the building simulation specialists are not advanced Revit users, it will be much easier for them to use the plugin with a Revit file that only has the primary design option. Multiple design options in the model can confuse an inexperienced Revit user.
