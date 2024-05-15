---
description: >-
  Pollination Model Editor is a modern user interface for editing Pollination
  Snapshots. The model editor is integrated into Rhino and Revit plugins and is
  accessible from the web.
---

# What is Pollination Model Editor

{% embed url="https://editor.pollination.cloud" %}

## Model Editor UI

The screenshot below shows the different sections of the model editor. When the model editor is accessed from inside the CAD plugins you will see a `Snapshots` button in the bottom left corner. Click on the button to open the snapshot manager that shows all the available snapshots.

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

If you are using the snapshot from the web, you can open a snapshot to the model editor from the `File Menu`.

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption><p>How to open a local snapshot into the model editor</p></figcaption></figure>

You can also try one of the sample files to familiarize yourself with the model editor functionalities.

<figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

## How to create a snapshot

### Rhino

In Rhino you can create a snapshot by using the `PO_TakeSnapshot` command. You can create a snapshot from the whole model or a selected number of rooms and shades. Use the `PO_SnapshotManager` command to edit the snapshot information, and open the snapshot in the editor.

### Revit

In Revit, press the `Export Model` button and follow the steps for exporting the model. Click on the Snapshot button to create a snapshot from the selected rooms.

<figure><img src="../.gitbook/assets/image (1) (1).png" alt=""><figcaption><p>Creating a Sanpshot in Revit</p></figcaption></figure>

You can then click on the `Snapshot Manager` button to open the model editor.

<figure><img src="../.gitbook/assets/image (1) (1) (1).png" alt=""><figcaption><p>Click on the Snapshot Manager Button to Open the manager and the model editor</p></figcaption></figure>

