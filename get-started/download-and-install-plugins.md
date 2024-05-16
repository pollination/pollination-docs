---
description: Use the tabs to see instructions for each of our plugins.
---

# Install CAD Plugins

After [downloading the installers](download-plugins.md) you can install the plugin by following the following steps. See[ the link below](download-and-install-plugins.md#silent-installation) for silent installation.

{% tabs %}
{% tab title="Rhino" %}
{% hint style="info" %}
The Pollination Rhino plugin is designed for optimal compatibility with Rhino 7 and Rhino 8.

If you are using Rhino 6, there is an incompatibility issue with the way Rhino 6 loads plugins. After installing Pollination, you will need to open and close Rhino **three times** to load the Pollination plugin.
{% endhint %}

{% hint style="info" %}
The Rhino installer also includes the Grasshopper plugin. You can consider it the Pollination Rhino and Pollination Grasshopper plugin installer.

You do NOT need to install the Grasshopper plugin separately. If you do, it will remove the Pollination Rhino plugin.
{% endhint %}

**Step 1**

{% hint style="warning" %}
Rhino must be closed before running the installer to install or uninstall Pollination.
{% endhint %}

![](<../.gitbook/assets/image (150) (1) (1) (1).png>)

Double-click on the `PollinationRHGHInstaller.exe` file to start the installation. The installer can also be used to remove components, update Pollination, or uninstall previous versions of Pollination. If you already have a version of Pollination installed then the installer will automatically show these options.



**Step 2**

Follow the instructions in the Pollination Rhino Plugin Setup Wizard to install the plugin.

![](<../.gitbook/assets/image (149) (1) (1) (1).png>)

#### Troubleshooting your installation

Visit our [troubleshooting](troubleshooting/ "mention") section to see common errors and installation issues.
{% endtab %}

{% tab title="Revit" %}
{% hint style="info" %}
The Pollination Revit plugin currently supports Revit 2019 - 2024. If you are using an older version of Revit, you will need to upgrade to a more recent Revit release to use Pollination.
{% endhint %}

**Step 1**

Double-click on the `PollinationRevitPluginInstaller.exe` file to start the installation. The installer can also be used to remove components, update Pollination, or uninstall previous versions of Pollination. If you already have a version of the Pollination Revit plugin installed then the installer will automatically show these options.

![](<../.gitbook/assets/image (148) (1) (1).png>)

**Step 2**

Follow the instructions in the Pollination Revit Plugin Setup Wizard application to install the plugin.

![](<../.gitbook/assets/image (151) (1) (1) (1).png>)
{% endtab %}

{% tab title="Grasshopper" %}
#### Installation

**Step 1**

{% hint style="warning" %}
Rhino must be closed before running the installer.
{% endhint %}

{% hint style="danger" %}
The Grasshopper plugin is also packaged in the Rhino installer. You only need to install the Grasshopper plugin separately if you do NOT have the Rhino plugin installed. Installing the Grasshopper plugin will remove any previous versions of the Pollination Rhino and Pollination Grasshopper plugins.
{% endhint %}

Double-click on the `PollinationGHInstaller.exe` file to start the installation. The installer will automatically remove any previous versions of Pollination.

![](<../.gitbook/assets/image (40).png>)

**Step 2**

Follow the prompts to install the plugin.

![](<../.gitbook/assets/image (35).png>)
{% endtab %}
{% endtabs %}

## Silent Installation

For silent machine-wide installation use the command below.

```
path-to-the-installer.exe --TargetDir "C:\Program Files\Pollination" --mode unattended --unattendedmodeui minimal
```

## Debugging Installation Issues

If you get an error during the installation see the installation log file in the `%TEMP%` folder or your computer. Look for a file that is named `installbuilder_installer_{number}.log`. You may see several log files in the folder if you have used the installer several times. You should select the file that was created last.

## License Population

You do not need to populate the licenses after the installation. As long as the users have been [added to the license pool](manage-license-pool.md) they will be able to check out a license from inside the CAD plugins.
