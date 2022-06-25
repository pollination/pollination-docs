---
description: Use the tabs to see instructions for each of our plugins.
---

# Plugin Installation

{% tabs %}
{% tab title="Rhino" %}
{% hint style="info" %}
The Pollination Rhino plugin is designed for optimal compatibility with Rhino 7. If you are using Rhino 6, there is an incompatibility issue with the way Rhino 6 loads plugins. After installing Pollination, you will need to open and close Rhino **three times** to load the Pollination plugin.
{% endhint %}



### Step 1

{% hint style="warning" %}
Rhino must be closed before running the installer to install or uninstall Pollination.
{% endhint %}



![](<../.gitbook/assets/image (150) (1) (1) (1).png>)

Double-click on the "PollinationRHGHPluginInstaller-latest.exe" file to start the installation. The installer can also be used to remove components, update Pollination, or uninstall previous versions of Pollination. If you already have a version of Pollination installed then the installer will automatically show these options.

{% hint style="info" %}
The installer also updates Ladybug Tools for Grasshopper. So if are an existing user of Ladybug Tools and have custom libraries for Honeybee that you'd like to maintain, please use the following process to backup your files.

1. Go to C:\Users\\\[USERNAME]\ladybug\_tools\resources\standards\\
2. Copy the "honeybee\_standards" folder to another location before running the installer
3. Once the installer is executed, you can copy "honeybee\_standards" folder back to the original location.
{% endhint %}

###

### Step 2

Follow the instructions in the Pollination Rhino Plugin Setup Wizard to install the plugin.

![](<../.gitbook/assets/image (149) (1) (1).png>)

## Troubleshooting your Installation

####

#### I can log in and have a valid CAD plugin license, but the plugin doesn't recognize the license.&#x20;

If your office has a firm-wide firewall, it may block Pollination's CAD plugins from accessing the internet. This will prevent the CAD plugin from completing the login process, even if are successfully logged into Pollination using your preferred browser.&#x20;

Additionally, we use the third-party licensing service from Cryptlex, and the internet connection between the CAD plugin and Cryptlex's server can also cause an error with recognizing a license.&#x20;

Adding Cryptlex's server, Rhino, and Pollination's CAD plugin to your firewall or antivirus software whitelist should solve the issue. Your office IT department can use Cryptlex's documentation to further troubleshoot this issue: [https://docs.cryptlex.com/node-locked-licenses/proxies-and-firewall](https://docs.cryptlex.com/node-locked-licenses/proxies-and-firewall)
{% endtab %}

{% tab title="Revit" %}
{% hint style="info" %}
The Pollination Revit plugin currently supports Revit 2022 - 2019. If you are using an older version of Revit, you will need to upgrade to a more recent Revit release to use Pollination.
{% endhint %}

### Step 1

Double-click on the "PollinationRevitPluginInstaller-latest.exe" file to start the installation. The installer can also be used to remove components, update Pollination, or uninstall previous versions of Pollination. If you already have a version of the Pollination Revit plugin installed then the installer will automatically show these options.

![](<../.gitbook/assets/image (148) (1) (1).png>)

### Step 2

Follow the instructions in the Pollination Revit Plugin Setup Wizard application to install the plugin.

![](<../.gitbook/assets/image (152) (1) (1).png>)
{% endtab %}

{% tab title="Grasshopper" %}
## Installation

### Step 1

{% hint style="warning" %}
Rhino must be closed before running the installer.
{% endhint %}

Extract the zipped file from your downloads folder and run the .exe file to start the installation.

![](<../.gitbook/assets/image (40).png>)

### Step 2

Follow the prompts to install the plugin.

![](<../.gitbook/assets/image (35).png>)
{% endtab %}
{% endtabs %}
