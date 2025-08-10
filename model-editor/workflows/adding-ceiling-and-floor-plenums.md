# Adding Ceiling and Floor Plenums

Starting from Pollination Revit v2.138.4, the Model Editor supports the functionality for adding ceiling or roof plenums to your rooms. Here is a recording that gives you an overview of the feature

{% embed url="https://youtu.be/pEZ04AD7n-M" %}

## How it works

### Set the ceiling plenum depth or floor plenum depth in the room properties

Each Pollination room has a property to set up `Ceiling plenum depth` and `Floor plenum depth`. By default, the value is set to 0.

<figure><img src="https://discourse.pollination.solutions/uploads/default/original/2X/d/d94f31cc878eacf33552bbab498f1b82290d66f8.png" alt=""><figcaption></figcaption></figure>

### QA/QC

By default, changing the properties does not create new plenum rooms in the model editor. This is by design to keep the number of rooms as small as possible. But when you export the model from Model Editor, these plenum depth properties are converted to a separate room.

There are 3 ways to check the plenums before exporting the model:

#### Use Alt + P to highlight the rooms with plenums.

{% embed url="https://drive.google.com/open?id=10436DheS3FihZ1llqXIg04RcenAwGRv2&usp=drive_fs" %}

#### Use Color-by to color the rooms by plenum depth.

{% embed url="https://drive.google.com/open?id=103ddZZ30BFAm-2TLKttgXZbesIjqn4Wg&usp=drive_fs" %}

#### Use the 3D preview to visualize them in 3D.

<figure><img src="https://discourse.pollination.solutions/uploads/default/original/2X/7/752a3ef091a3543cb2cd7f9b3d374c2148000bb5.png" alt=""><figcaption></figcaption></figure>

### Adding plenums as rooms inside the Model Editor

If, for any reason, you need to convert the plenums to rooms inside the model editor, you can use the `Separate Plenums` button. The button is located on top of the `Levels` table. Using this button creates new levels with plenums as separate rooms. It also resets the `plenum depth` property to 0 in the host rooms.

{% embed url="https://drive.google.com/open?id=104CrP9vV4NC679J3XO1ZOko5y3R6rS6a&usp=drive_fs" %}

### IES VE export

The plenums are exported to IES VE GEM files as voids.

<figure><img src="https://discourse.pollination.solutions/uploads/default/original/2X/2/2f33d677effa82232be051e9bd65d1d7278d026e.png" alt=""><figcaption></figcaption></figure>

See the original announcement post here:

{% embed url="https://discourse.pollination.solutions/t/model-editor-update-plenums-plenums-plenums/7525" %}

