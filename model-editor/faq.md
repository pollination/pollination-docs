---
description: A list of frequently asked questions about the Model Editor.
---

# FAQ

## Does the data leave my local machine when I use the Model Editor from inside Revit?

No. When you use the Model Editor from inside Revit all the data stays on your local machine. Model Editor uses the [Microsoft Edge WebView2](https://learn.microsoft.com/en-us/microsoft-edge/webview2/) technology to embed the Model Editor into the Pollination Revit plugin. The data are stored in the browser's local cache using `Local storage`, `Session storage` , or `IndexedDB`. The files are stored on your local hard drive.

All the commands for exporting the files or generating a 3D preview are also executed locally ensuring your model date never leaves you local computer.

## Why do I see the "The Model Editor is built against a newer version of the Revit plugin." warning message when I open the Model Editor?

The short answer is because you are using an older version of the Pollination Revit plugin. Try to download and install the latest version of the plugin and you won't see the message anymore.

## What are the differences between the online version of the Model Editor, and the embedded version of the Model Editor in Revit?

They are both using the same technology under the hood but the web-based version of the Model Editor is meant to only be used for demo-ing the editor and practicing. It only works with the sample models, and it has a limited number of export options. In contrary, the embedded version of the Model Editor, includes supports all the [import and export file formats](supported-file-formats/).

## I encountered an error. What is the best way to get help?

The best way to get help is to open a new topic on [Pollination discourse](https://discourse.pollination.solutions/). You should provide enough information including an explanation of how to recreate the error message and screenshots of the error message and the logs. You can download the logs by clicking on the Pollination logo at the bottom right corner of the screen and selecting Advanced > Download logs.

<figure><img src="../.gitbook/assets/image (170).png" alt=""><figcaption></figcaption></figure>

In some cases, we might ask you to share the model or part of the model with us for debugging. Use the SaveAs option to save the model as a PoMF file.

<figure><img src="../.gitbook/assets/image (171).png" alt=""><figcaption></figcaption></figure>

