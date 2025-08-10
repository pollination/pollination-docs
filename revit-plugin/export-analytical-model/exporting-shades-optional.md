# Exporting Shades (optional)

To start exporting shades as a Pollination snapshot, click on the Export Shades button.

<figure><img src="../../.gitbook/assets/image (52).png" alt=""><figcaption></figcaption></figure>

The button opens up a menu that allows you to select Revit elements and export them as shade objects in an energy model. Like the "Export Rooms" menu, you can visualize the shades in the UI before exporting them.

<figure><img src="../../.gitbook/assets/image (175).png" alt=""><figcaption></figcaption></figure>

There are 3 options for adding elements as shades:

1.  "Add Shades" allows you to select the items from the Revit viewport and add them to the selection. Don't forget to click on the small button in Revit.\


    <figure><img src="../../.gitbook/assets/image (176).png" alt=""><figcaption></figcaption></figure>
2. "Add Shades from Selection" is similar to the previous item, with the difference that it allows you to add the current selection as shades.
3. "Add Shades from Links" allows you to select elements from linked models and add them as shades.

## Understanding the "Detached" option

Shade elements can be attached to the building (such as window overhangs) or detached from the building (such as neighbor buildings and trees). Use the "Detached" property in the table to indicate if the shade is attached or detached from the building.

{% hint style="info" %}
This property only translates to DFJSON, HBJSON, and GEM file formats. Attached shades translate to local shade in IESVE.
{% endhint %}

## Additional parsing options

The Export Shades menu provides two options to control the export process.

<figure><img src="../../.gitbook/assets/image (177).png" alt=""><figcaption></figcaption></figure>

### Ignore non-planar faces

Use this option to ignore the non-planar faces in the selection. By default, the Pollination plugin converts non-planar faces to several planar mesh faces.

### Area filter

Revit models can include many details that are "too much detail" for energy models. This option helps you filter out these small geometries. The default value is 1 m<sup>2</sup>.
