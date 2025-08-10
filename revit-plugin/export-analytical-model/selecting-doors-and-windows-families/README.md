# Selecting Doors and Windows Families

Unlike many other Revit plugins, Pollination doesn't try to guess the windows and doors families in a Revit model. Instead, we ask you to pick the families that should be exported from Revit as windows and doors.

To select the windows and doors families, click on the `Select Doors & Windows` button.

<figure><img src="../../../.gitbook/assets/image (48) (1).png" alt=""><figcaption></figcaption></figure>

You should see a UI similar to the screenshot below. There are two tabs for windows and doors. You see the list of families on the left side and a preview window on the right. By default, the status of all the families is set to "Ready to review".

<figure><img src="../../../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

{% hint style="warning" %}
For models with many windows and doors family types, it could take up to several minutes for the UI to be fully loaded. This is one of the main items on our list to improve in the upcoming versions. Until then, be patient and let the plugin load all the window families and list their materials!
{% endhint %}

{% hint style="info" %}
Ensure to select the correct Phases in the project. In some projects, like renovation projects, the windows and doors might be in a different Phase (e.g., Existing) from the rooms (e.g., New construction).
{% endhint %}
