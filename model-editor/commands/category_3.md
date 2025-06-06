# Model Commands

Below are all commands that only operate on the entire model at once.

## <img src="images/auto-top-ground.svg" width="30" height="30"> Auto top ground

Automatically assign top exposed properties to any rooms with no room above them and assign ground contact to all rooms of the bottom story.

<details>

<summary>Options</summary>

**Basement Count**

  A positive integer to set the number of unique Stories on Building to make into basements. Setting this to a positive number will cause some walls to be set to underground and the floors of more rooms to be set to ground

</details>

---

## <img src="images/auto-top-ground.svg" width="30" height="30"> Change units

Change units and/or tolerance.

<details>

<summary>Options</summary>

**Units**

  Units to apply

**Angle Tolerance**

  Angle tolerance to apply

**Tolerance**

  Tolerance to apply

**Reset Coordinate System**

  Select to have this command reset the origin of the coordinate system in which the model exists to the lower left corner of the bounding box around the model. Useful when the model lies very far from the origin.

</details>

---

## <img src="images/convert-to-room2d.svg" width="30" height="30"> Convert to room2D

Convert a room3D to a room2D. Room3D are not editable.

---

## <img src="images/multipliers-to-geo.svg" width="30" height="30"> Multipliers to geometry

Click to convert multipliers assigned to stories into explicit room geometry.

---

## <img src="images/separate-plenums.svg" width="30" height="30"> Separate plenums

Click to convert ceiling and floor plenum depths assigned to rooms into explicit plenum room geometry.

---