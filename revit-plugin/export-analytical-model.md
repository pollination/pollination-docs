# Export Analytical Model

## Step 1 Export Model

To export a model, click on the `Export Model`button.

![](<../.gitbook/assets/image (147).png>)

## Step 2 Select Settings

Review and select model export settings, then click on `Next`.

![](<../.gitbook/assets/image (138).png>)

### "Pull up" Room Height and Compute Volumes

The "Pull up" Room Height and Compute Volumes checkboxes allow users to automatically extended rooms to the ceiling or roof level only in the exported file. All geometry in Revit stays as-is. Read more about why extending room heights and computing volumes is essential here:

{% content-ref url="modeling-best-practices/rooms.md" %}
[rooms.md](modeling-best-practices/rooms.md)
{% endcontent-ref %}

### Format

We are currently only supporting export to HBJSON, DFJSON, gbXML, and GEM. We plan to add support for IDF and OSM in the future.

### Levels

The levels feature allows users to export selected levels instead of the whole model. Users can further choose individual rooms to export in the next window. Individual room or level selection allows users to debug a model more efficiently or use partial exports for shoebox studies.

### Glazing

In order for Pollination to recognize all glazed elements in a model, you must select wall, window, and door types from the prepopulated list one by one.

{% hint style="info" %}
Saving glazing one by one is only required one time, as the user selection is saved with the Revit file. However, if the model changes and new glazed families are added, the glazing selection requires a manual update by the user.
{% endhint %}

![](<../.gitbook/assets/image (141).png>)

## Step 3 Select Rooms and Check for Errors

The export tab generates a list of all rooms and their related settings for a final review prior to exporting the model. Errors are indicated on a room-by-room basis in the Messages column by an exclamation point ![](../.gitbook/assets/2021-09-05\_exclamation.png) . Error details are only visible by clicking on the![](../.gitbook/assets/2021-09-05\_dot-dot-dot.png)symbol on the left-hand side of the window. Once all errors are addressed, click on the `Export`button and save the file.

{% hint style="info" %}
Right-click on a room name to bring up a menu of options.

1. **Select** will zoom to the room location in Revit
2. **Delete** will remove duplicate or non-existent rooms from the list only.
3. **Edit Properties** will bring up the Pollination Room properties, where you can assign or modify the room name, story, material set, construction set, program type, or HVAC type.
{% endhint %}

![](<../.gitbook/assets/image (142).png>)

### Common Errors

1. **Rooms with an area of 0**. In most cases, this error indicates that a room is not bound or is not placed.
2. **Face has no Surface Type assigned**. This is most likely because the room volume doesn’t extend to floor or roof above. This may require a manual room volume adjustment in the model.
3. **Smaller edges than tolerance**. This is usually the result of slightly non-orthogonal lines in the room, which can be fixed by editing the room profile.

### Context shade

The Revit plugin automatically selects all plant families in the scene, but will not select any massing elements for context buildings or structures or shading structures. Select the ![](<../.gitbook/assets/image (144).png>)symbol located at the top right hand side of the screen to `Select Faces`.

![](<../.gitbook/assets/image (139).png>)
