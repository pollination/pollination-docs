# Understanding the Export Process

Pollination breaks down the export process into 3 main steps:

* Selecting windows and doors
* Exporting rooms, areas, or spaces as Pollination snapshots
* Cleaning up and exporting the snapshots in the Model Editor

<figure><img src="../../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

In many cases, you might also want to export some elements in your Revit model as shades.

## 1. Selecting windows and doors

In the first step, we need to select the family types that should be exported as windows and doors. Pollination lists all the possible families and helps you visualize them so you can pick the right families to be exported as windows and doors.

{% hint style="warning" %}
In the Pollination world, we call windows and skylight apertures. Hopefully, that is not confusing. It is one of those choices that, if we could have gone back in time, we would have changed.
{% endhint %}

## 2. Exporting rooms, areas, or spaces as Pollination snapshots

Once we have picked the doors and windows, we go through the process of reviewing and exporting the Revit rooms, spaces, or areas as Pollination rooms. Pollination helps you to create clean plan floors in Revit so you can review them quickly, and insert any missing rooms with exterior faces. It also helps you visualize the rooms with windows before exporting them as snapshots to ensure they look as expected.

{% hint style="info" %}
We don't worry about cleaning up gaps and small holes in this step. That's for step 3.
{% endhint %}

## 3. Cleaning up and exporting the snapshots in the Model Editor

Once you have the snapshots, you are free from the slowness of Revit and into the fast and _magical_ world of Model Editor. I know that I said there is no magic in our process, but some of the Model Editor features might feel magical. The Model Editor provides automated commands to remove all the holes, align all the gaps, and fill the larger holes with rooms. It also helps you find and fix any validation issues in the model and export them as energy models!

## 4. Exporting shades (optional)

You can also use the Pollination Revit plugin to export shades. It is not a required step but a popular one nevertheless. Pollination provides several options for selecting shades, and an easy way to visualize them before the export. It also provides options to remove small faces from the shade automatically. This feature is particularly useful when exporting non-planar geometries as shades from Revit.

