# Setting Up Linked Models

Most of the larger Revit projects are created as linked models. Pollination supports importing windows, doors, and shades from linked models. However, you can only export rooms, spaces, or areas created inside the host model. This means that if your project has rooms in multiple Revit files, you must open each file individually to export the rooms.

{% hint style="info" %}
We understand opening several Revit models is not ideal, but unfortunately, there is not much that we can do to address this issue because of [this bug in the Revit API](https://forums.autodesk.com/t5/revit-api-forum/getboundarysegments-with-linked-models/m-p/13382343). We will revisit this limitation once the bug has been fixed.
{% endhint %}

This video walks you through the process of setting up a linked model.

{% embed url="https://youtu.be/qrdmFTJKsYc" %}

[You can download the sample models that are used in this video from here](https://drive.google.com/drive/folders/101O3R74LbmvXGYSbKX6G6sKl4AjDPLn-?usp=sharing).

To use linked Models:

## 1. Save the host model as a Central Model

The first step in the process is to ensure you open the model with the rooms, areas, or spaces as the host model, and save the model as a Central Model. You can see if the model is already saved as a Central Model in the `File Save Options` menu.

<figure><img src="../../.gitbook/assets/image (175) (1) (1).png" alt=""><figcaption></figcaption></figure>

## 2. Review the linked Revit models

Ensure all the other Revit models are linked to the host model correctly. The `Manage Links` button is under the Manage tab in Revit.

<figure><img src="../../.gitbook/assets/image (8) (1).png" alt=""><figcaption></figcaption></figure>

## 3. Load the families from linked models

Use the `Links` dropdown in `Select Apertures/Doors` and `Create Shades` menus to load the families from the linked model to the selection.\\

<figure><img src="../../.gitbook/assets/image (12).png" alt=""><figcaption></figcaption></figure>

Once you add the linked models in the Pollination UIs, you can select them just like how you would select the families from the host model.
