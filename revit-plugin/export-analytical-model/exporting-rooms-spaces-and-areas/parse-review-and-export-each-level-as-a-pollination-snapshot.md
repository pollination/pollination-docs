# Parse, Review, and Export Each Level as a Pollination Snapshot

After placing the missing rooms and setting up the extrusion height, it is finally time to export the rooms. **We will do this process level by level**. Meaning that we export the Entry Level first, and then export the second floor, and finally the third floor. We will later merge the levels together in the Model Editor.

{% hint style="danger" %}
I understand the urge to select all the levels together, and try to export them as one snapshot, and to be honest, it will probably be fine for this model, but in almost every real-world model, you will save time by exporting the levels one at a time and reviewing them separately. Exporting several models together adds additional overhead to every step in the process, which makes the overall process slower.
{% endhint %}

## Exporting the Entry Level

In Step 2, select the "01 - Entry Level" and click Next to go to Step 3.

<figure><img src="../../../.gitbook/assets/image (63) (1).png" alt=""><figcaption><p>Step 2</p></figcaption></figure>

In step 3, you will see the list of rooms on the first level. This is an opportunity to select only a few rooms from the level, which is useful when you are only interested in exporting part of the floor, or when you're trying to debug a certain room. In most other cases, you simply click next to go to Step 4.

<figure><img src="../../../.gitbook/assets/image (64) (1).png" alt=""><figcaption><p>Step 3</p></figcaption></figure>

In Step 4, the plugin starts parsing all the rooms that have been selected in Step 3. The image below highlights the main parts of the user interface.

<figure><img src="../../../.gitbook/assets/image (66) (1).png" alt=""><figcaption><p>Step 4</p></figcaption></figure>

Once the rooms are parsed, you can do a quick quality check by checking the "Windows" column to ensure the windows have been added to the rooms correctly.

{% hint style="info" %}
If you see the windows count for all the rooms is 0, go back to the step for [selecting windows](../selecting-doors-and-windows-families/selecting-window-family-types.md) and ensure the export status is set to "Export" correctly.
{% endhint %}

Then select all the rooms, either by pressing Ctrl + A or clicking on the select all rooms button, and click on the preview button to see a 3D preview of the rooms in the Pollination UI. There are 3 buttons for creating a preview, and we will discuss the differences between them shortly, but for now, select the button on the right side with the flash icon. You should see something like the image below.

<figure><img src="../../../.gitbook/assets/image (65) (1).png" alt=""><figcaption><p>01 - Entry Level</p></figcaption></figure>

You can use the 3D preview window to inspect the model and identify any possible issues. In the case of the Revit sample model, you will notice that the entry lounge space doesn't look correct. In Revit, it is a double-height space with a slanted roof, but it has currently been extruded to the same height as the rest of the rooms on the level. It also doesn't have a slanted roof.

<figure><img src="../../../.gitbook/assets/image (57) (1).png" alt=""><figcaption></figcaption></figure>

We will fix these issues by overwriting the extrusion height of the room and fixing the "Is Top Exposed" property:

1. Double-click on the Number column to sort the rooms by number.
2. Find room Lounge 120, select the row, right click, and select the "Override/Reset Height" option.
3. Click inside the "Height" cell and change the number from 3800 to 7600.
4. Select the "Is Top Exposed" option for this room.
5. Click on the preview button with the box icon to repart the room from Revit, and visualize it.

Once you go through these steps, you should see an image similar to the screenshot below.

<figure><img src="../../../.gitbook/assets/image (58) (1).png" alt=""><figcaption><p>Steps to fix the Lounge room</p></figcaption></figure>

{% hint style="info" %}
See [this section](for-those-who-want-to-know-more.md#understanding-the-3-preview-options) to better understand the difference between the 3 different options to create a preview.
{% endhint %}

Now that the Lounge room is fixed, we can do another preview to ensure everything looks as expected before going to the last step of the process.

<figure><img src="../../../.gitbook/assets/image (59) (1).png" alt=""><figcaption><p>Quick preview of the 01 - Entery Level after fixing the Lounge room</p></figcaption></figure>

Click on the next button to go to Step 5.

<figure><img src="../../../.gitbook/assets/image (60) (1).png" alt=""><figcaption><p>Click on the "Create Snapshot" button to save the rooms as a Pollination Snapshot</p></figcaption></figure>

In this step, you can set the room program types, construction sets, and HVAC templates, but we won't discuss them as part of this tutorial. For now, we only focus on exporting the geometry. Make sure all the rooms are selected, and then click on the "Create Snapshot" button. You should see a pop-up window to set the name of the Snapshot, optionally add a description, and save it to your hard drive.

<figure><img src="../../../.gitbook/assets/image (61) (1).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Snapshots include all the model information that you set up in Revit. You will use them to clean up the model and export it as an energy model. Save them in a folder that you can remember and access in the future.
{% endhint %}

## Exporting Second and Third Levels

Now, repeat the export process for the second and third levels, creating two distinct snapshots. Neither of these levels contains double-height spaces. However, when processing the third floor, be sure to designate all rooms as "Is Top Exposed".

<figure><img src="../../../.gitbook/assets/image (62) (1).png" alt=""><figcaption><p>Setting the "Is Top Exposed" property for 03 - Floor</p></figcaption></figure>

Once you have the snapshots, you're ready to clean up the model with a few clicks inside the Model Editor. One optional next step is to export the shade elements from the Revit model as a separate snapshot.

## Frequently Asked Questions

### Is it possible to select more than one level in Step 2? Why do we need to export the model level by level?

You might be wondering if it's possible to select multiple levels in Step 2. Additionally, the choice of exporting the model level by level might not be immediately clear. Let's clarify these points.

Yes. It is possible to select several levels at the same time, but unless the model is quite small, we don't recommend doing so. In almost every real-world model, you will save time by exporting the levels one at a time and reviewing them separately. Exporting several models together adds additional overhead to every step in the process, makes it harder to select specific rooms if needed, and adds to the time for creating the 3D preview, which makes the total export process slower.
