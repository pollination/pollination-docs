# Understanding the Export Process

Let's first breakdown the overall process for exporting Revit models using the Pollination Revit Plugin. You can watch this video or read the text below to understand the overall process.

{% embed url="https://youtu.be/s4_lPqhRx-k" %}

Pollination breaks down the export process into 3 required and 2 optional steps.

<figure><img src="../../.gitbook/assets/image (55) (1).png" alt=""><figcaption><p>Typical steps for exporting the model from Revit</p></figcaption></figure>

These steps are:

* Selecting windows and doors
* Selecting roofs (optional)
* Exporting rooms, areas, or spaces as Pollination snapshots
* Exporting shades as Pollination snapshots (optional)
* Cleaning up and exporting the snapshots in the Model Editor

<figure><img src="../../.gitbook/assets/image (46) (1).png" alt=""><figcaption><p>Export buttons in the Revit UI</p></figcaption></figure>

## 1. Selecting doors and windows

In the first step, we need to select the family types that should be exported as windows and doors. Pollination lists all the possible families and helps you visualize them so you can pick the right families to be exported as windows and doors.

<figure><img src="../../.gitbook/assets/image (6) (1).png" alt=""><figcaption><p>Select Windows/Doors Menu</p></figcaption></figure>

## 2. Selecting roofs (optional)

In the second step, we have the option to review and select the roofs that should be included in the model. In most cases, you would only want to include the non-horizontal roofs as part of the model.

This step is mainly useful for models with many different roof segments that you may not want to be included in the model.

By default, all the roofs will be exported to the Model Editor. That gives you the option to bypass this step and [edit them later in the Model Editor](../../model-editor/workflows/editing-roofs.md) - also see step 5.

<figure><img src="../../.gitbook/assets/image (44) (1).png" alt=""><figcaption></figcaption></figure>

## 3. Exporting rooms, areas, or spaces as Pollination snapshots

Once we have picked the doors and windows, we go through the process of reviewing and exporting the Revit rooms, spaces, or areas as Pollination rooms. Pollination helps you to create clean plan floors in Revit so you can review them quickly, and insert any missing rooms with exterior faces. It also helps you visualize the rooms with windows before exporting them as snapshots to ensure they look as expected.

<figure><img src="../../.gitbook/assets/image (7) (1).png" alt=""><figcaption><p>Export Rooms Menu</p></figcaption></figure>

{% hint style="info" %}
We don't worry about cleaning up gaps and small holes in this step. That's for step 5.
{% endhint %}

## 4. Exporting shades (optional)

You can also use the Pollination Revit plugin to export shades. It is not a required step but a popular one nevertheless. Pollination provides several options for selecting shades, and an easy way to visualize them before the export. It also provides options to remove small faces from the shade automatically. This feature is particularly useful when exporting non-planar geometries as shades from Revit.

<figure><img src="../../.gitbook/assets/image (9).png" alt=""><figcaption><p>Export Shades Menu</p></figcaption></figure>

## 5. Cleaning up and exporting the snapshots in the Model Editor

Once you have the snapshots, you are free from the slowness of Revit and into the fast and _magical_ world of Model Editor. I know that I said there is no magic in our process, but some of the Model Editor features might feel magical. The Model Editor provides automated commands to remove all the holes, align all the gaps, and fill the larger holes with rooms. It also helps you find and fix any validation issues in the model and export them as energy models!

<figure><img src="https://lh7-rt.googleusercontent.com/slidesz/AGV_vUe5OTyXZlK8K602zCHUaAM1GdePmCBeAUT8BDcvOktrfh94RbpawhVzYVOhmgKTwxEH-QCKWRC47GiyEomXh9uaaRV93CacL-DXRaDOI4VAl8V7DafXZtJkPbpfRMPVXqUvXRGZ_fQAfmxKml6ML_voj9PzIu4=s2048?key=69VFaahfemNak-Zx-4pI2w" alt=""><figcaption><p>Model Editor</p></figcaption></figure>

And finally, you can export your model to all the supported file formats with a single click.

<figure><img src="../../.gitbook/assets/image (8).png" alt=""><figcaption><p>Exported Revit Model</p></figcaption></figure>
