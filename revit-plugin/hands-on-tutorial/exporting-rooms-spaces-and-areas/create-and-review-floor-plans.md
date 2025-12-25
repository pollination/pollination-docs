# Create and Review Floor Plans

{% embed url="https://youtu.be/LrA3JoSZzag" %}

Now that you understand the export settings, it is time to export your first level as a snapshot.

In step 2, you see the list of levels in the Revit model. Note that not every Revit level includes rooms, spaces, or areas. Check the Rooms, Spaces, and Areas columns to get a quick sense of which levels are the ones with the data that you need.

The Revit advanced sample model includes 3 levels with Rooms:

* 01 - Entry Level
* 02 - Floor, and
* 03 - Floor

For each of those levels, you need to:

1. Create and review the floor plans
2. Set the extrusion height.

<figure><img src="../../../.gitbook/assets/image (29) (1).png" alt=""><figcaption></figcaption></figure>

## Creating and Reviewing Floor Plans

To create the floor plans, click on the small (+) icon on the right side and select "Create Floor Plan". This will create a new floor plan for this level and open it up in Revit.

<figure><img src="../../../.gitbook/assets/image (31) (1).png" alt=""><figcaption></figcaption></figure>

If the plan already exists, you will see the options to "Open Floor Plan" and "Delete Floor Plan".

<figure><img src="../../../.gitbook/assets/image (32) (1).png" alt=""><figcaption></figcaption></figure>

Pollination floor plans are standard Revit views with customized visibility and graphics to make it easy to only see the relevant information. In particular, the Pollination floor plan views highlight walls, windows, rooms, areas, and spaces in addition to separation lines.

<figure><img src="../../../.gitbook/assets/image (33) (1).png" alt=""><figcaption></figcaption></figure>

### Placing rooms

After creating the floor plans, ensure there are no missing rooms with exterior walls in the model. This is an important step to ensure you won't miss any exterior windows and doors in the export process. Even though you can place rooms in the Model Editor, you cannot add windows to those rooms.

In the Revit sample model, there is a missing room on the third floor that must be placed before exporting the rooms from Revit. There are also smaller missing rooms on the south side between the bathrooms.

You can place a room in Revit by selecting the "Room" button under the "Architecture" tab. [For more information about creating rooms, see the Revit documentation](https://help.autodesk.com/view/RVT/2023/ENU/?guid=GUID-B3420A54-A9BC-4AEE-A07C-CD7A9DC782FB).

<figure><img src="../../../.gitbook/assets/image (34) (1).png" alt=""><figcaption></figcaption></figure>

## Setting up the Extrusion Height

After reviewing the plans and placing rooms, you should set the extrusion height for each level. You can do this either by typing the number manually or by right-clicking in the cell and selecting the top level. The plugin calculates the extrusion height based on the difference between the level elevations of the current level and the top level.

<figure><img src="../../../.gitbook/assets/image (35) (1).png" alt=""><figcaption><p>Setting up the Extrusion Height</p></figcaption></figure>

{% hint style="warning" %}
If the extrusion height is left empty, Pollination tries to _guess_ the room height based on the Revit geometry, which is unlikely to be what you would want in an energy model.
{% endhint %}

{% hint style="info" %}
This value is only used in the Extruded Floors mode and will be ignored when Full Geometry is used.
{% endhint %}

After placing the missing rooms and setting up the extrusion height, you're ready to review and export the rooms. We will do this process one level at a time.

{% hint style="info" %}
See [this section](for-those-who-want-to-know-more.md#understanding-the-levels-table) for a detailed explanation of every column in the Levels table.
{% endhint %}
