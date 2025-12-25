# Frequently Asked Questions about Exporting Rooms

{% embed url="https://youtu.be/95TJoIdu3mo" %}

### I don't see any rooms, spaces, or areas in the generated plan. What should I do?

Most Revit Architecture models include Rooms or Areas. The Revit Mechanical models include Spaces. If you don't see any Rooms, Spaces, or Areas, ensure you have [selected the correct Phase(s) in the Export Settings](export-settings.md#phase).

If you still see the count of all the rooms, spaces, and areas being 0, you need to place the rooms yourself. [See above for more information](frequently-asked-questions-about-exporting-rooms.md#placing-rooms).

### When I click to place a room, it doesn't create the room. Instead, I see a small blue box. What do I need to do?

Revit calculates the perimeter of the rooms based on the room bounding elements in the plan. If you can't place the room, it usually means that some parts of the room elements are not Room Bounding. Use the Pollination "Show Bounding" button to highlight the Room Bounding elements in the plan view and identify the leak.

<figure><img src="../../../.gitbook/assets/image (36).png" alt=""><figcaption><p>Use the Show Bounding button to hightlight the Room Bounding elements in the floor plan</p></figcaption></figure>

Once you find the leak, you can either change the element properties to be Room Bounding or use a Revit Room Separation Line to stop the leak. You can find the Room Separation line under the "Architecture" tab and next to the "Room" button.

### Can I only export the building perimeter to create a core and perimeter model?

Yes. Export the rooms to the Model Editor. There, you can [combine the rooms to include the exterior walls](../../../model-editor/workflows/exporting-the-exterior-envelope.md) and then [use the "Split Core and Perimeter" command](../../../model-editor/workflows/creating-core-and-perimeter-models.md).

### Can I merge the rooms with similar program types and orientation into spaces?

Yes. Export the rooms to the Model Editor, and then use the "[Merge Rooms](../../../model-editor/commands/me_merge_rooms.md)" command to merge them.

### Should I build a separate level for plenums in Revit? What's the best practice for modeling floor and ceiling plenums?

We don't recommend building a separate level for plenums in Revit. You can easily add the plenums to the rooms inside the Model Editor. [See here for more information](../../../model-editor/workflows/adding-ceiling-and-floor-plenums.md).
