---
description: >-
  This page explains the process for trying the Pollination Rhino and Revit
  plugins for free before purchasing a subscription.
---

# Free Trial of Pollination Products

Both Pollination Rhino and Revit plugins offer a 30-day free trial license. To begin your trial, first [create a Pollination account](create-a-pollination-account.md), and then simply download the plugins and start using them.

## Downloading the installers

You can download the installers from [this page on our website](https://app.pollination.solutions/cad-plugins). You can also find the link on the landing page.

<figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

Once you download the installer double click on it and follow the steps.

## Frequently Asked Questions

### Silent Installation

For silent machine-wide installation use the command below.

```
path-to-the-installer.exe --TargetDir "C:\Program Files\Pollination" --mode unattended --unattendedmodeui minimal
```

### Debugging Installation Issues

If you get an error during the installation see the installation log file in the `%TEMP%` folder or your computer. Look for a file that is named `installbuilder_installer_{number}.log`. You may see several log files in the folder if you have used the installer several times. You should select the file that was created last.

### License Population

You do not need to populate the licenses after the installation. As long as the users have been added to the license pool they will be able to check out a license from inside the CAD plugins. [Refer to this section to learn more about managing license pools](account-setup/managing-license-pools.md).

Each plugin includes a license manager that allows you to activate your trial after answering a few questions. To use the license manager in Rhino, use the command `PO_LicenseManager`. In Revit, navigate to the Pollination tab and click the `License Manager` button. For more information, [visit this ](../revit-plugin/core-concepts-and-best-practices/managing-pollination-revit-license.md)[page](../revit-plugin/core-concepts-and-best-practices/managing-pollination-revit-license.md).

### Do I need a credit card to start the trial?

No credit card is needed, and you don't need to get in touch with us to start your trial! You can do it all on your own. Enjoy the free ride, and let us know if you have any questions or feedback. We're always looking for questions and feedback! Just have a look at the discussions in [Pollination Discourse forum](https://discourse.pollination.solutions/), and you will see that we mean it. Many of the features are developed directly based on our customers' feedback.

You can get in touch with us directly via [our website](https://www.pollination.solutions/contact) or by posting on [Discourse](https://discourse.pollination.solutions/).
