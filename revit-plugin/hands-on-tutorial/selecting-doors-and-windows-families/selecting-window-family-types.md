# Selecting Windows Family Types

The next step is to go through the list of windows and curtain wall panels and select the ones that should be exported as windows.

{% embed url="https://youtu.be/zFnQpQIJmXc" %}

There are two ways to identify the families in the Revit model:

1.  Right-click on the family name and click on `Select All`. That will select all the families with the same type in the Revit active view. It's usually easier to see the windows if you are in a 3D view.\\

    <figure><img src="../../../.gitbook/assets/image (18) (2).png" alt=""><figcaption><p>Highlighting the family type in the viewport</p></figcaption></figure>
2.  Select the family, and use the \`Preview\` button to preview them in the Pollination 3D viewer inside the menu.

    <figure><img src="../../../.gitbook/assets/image (20).png" alt=""><figcaption><p>Preview a family inside the menu</p></figcaption></figure>

In this sample model, there are only 3 different family types, and it is quite straightforward which ones should be exported as windows. This is how the menu should look after selecting the correct families. Pay attention to the `Export Status` column and the `Export Summary` to ensure you have selected the correct families.

<figure><img src="../../../.gitbook/assets/image (21).png" alt=""><figcaption><p>If the numbers inside the Export summary section is 0 you have forgotten to change the status to export</p></figcaption></figure>

{% hint style="info" %}
In larger models, you might have to review tens of different families. In those cases, pay attention to the count column and start with the ones with the highest number and work your way towards the less frequent ones.
{% endhint %}

## Understanding "Panel Calculation" options

Pollination provides 3 different options for calculating window panels:

* Single Panel
* Multi Panel
* Bounding Box

The Revit sample model includes simple windows family types, and the default _Single Panel_ mode works without any issues, but in the real world, you will see more complex examples. Here is an example of a window that also includes 2 different shading elements and the frames as part of the window.

<figure><img src="../../../.gitbook/assets/image (13).png" alt=""><figcaption><p>A window family which also includes the exterior shade</p></figcaption></figure>

The _Single Panel_ option tries to create a single panel from all the geometries. Since the shade elements are not aligned with the window, this is how the window would look when the Single Panel option is selected. Note the diagonal edge on the left side of the window.

<figure><img src="../../../.gitbook/assets/image (194).png" alt=""><figcaption></figcaption></figure>

In cases like this, the easiest way to address the issue is to use the _Bounding Box_ option that creates a rectangle around all the geometry to generate a rectangular panel. This will, however, make the window area slightly larger than it needs to be.

<figure><img src="../../../.gitbook/assets/image (195).png" alt=""><figcaption></figcaption></figure>

Another option is to deselect the non-glass materials. That will only create a bounding box or a single panel around the glass pieces.

<figure><img src="../../../.gitbook/assets/image (196).png" alt=""><figcaption></figcaption></figure>

If you want to be very specific and create a separate panel for each piece of glass, you should use the _Multi Panel_ option. This option is only useful when there are several pieces of glass in the window family.

<figure><img src="../../../.gitbook/assets/image (197).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
To get the desired results, you must deselect all the other materials except for the glass pieces. Otherwise, you will see a piece of glass for every element in the window family.
{% endhint %}

<figure><img src="../../../.gitbook/assets/image (198).png" alt=""><figcaption></figcaption></figure>

## Confirming your selection

Once you have reviewed the windows and doors, press OK to confirm your selection. It is time to move to the next step for creating rooms.

{% hint style="warning" %}
If you don't save the Revit model, this selection will only be available in the current session, and you'll have to select the windows and doors again.
{% endhint %}

## Frequently Asked Questions

### Is it possible to only export the exterior doors and windows?

We currently don't support this option directly in Revit, but you can use the "[Simplify Windows](../../../model-editor/commands/me_simplify_windows.md)" command in the Model Editor to remove the interior windows after exporting the model.

### Does Pollination include the frame thickness in the exported window?

The answer to this question is different for windows vs curtain wall panels. See [this page](../../../model-editor/typical-editing-process-for-windows-and-doors.md) for a detailed answer to this question.

### How can I load the windows and doors from linked Revit models?

Both windows and doors menus have a dropdown for loading families from linked models. Simply select the linked model, and you will see the families loaded in the table. See [this page](../../core-concepts-and-best-practices/setting-up-linked-models.md) for more information about setting up linked models.

<figure><img src="../../../.gitbook/assets/image (12).png" alt=""><figcaption></figcaption></figure>
