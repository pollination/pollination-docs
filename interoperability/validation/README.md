# Rhino Plugin Errors

## Installation Issues

**I can log in and have a valid CAD plugin license, but the plugin doesn't recognize the license.**

If your office has a firm-wide firewall, it may block Pollination's CAD plugins from accessing the internet. This will prevent the CAD plugin from completing the login process, even if are successfully logged into Pollination using your preferred browser.&#x20;

Additionally, we use the third-party licensing service from Cryptlex, and the internet connection between the CAD plugin and Cryptlex's server can also cause an error with recognizing a license. \
Adding Cryptlex's server, Rhino, and Pollination's CAD plugin to your firewall or antivirus software whitelist should solve the issue. Your office IT department can use Cryptlex's documentation to further troubleshoot this issue: [https://docs.cryptlex.com/node-locked-licenses/proxies-and-firewall](https://docs.cryptlex.com/node-locked-licenses/proxies-and-firewall)

**I get the following error message `System.ArgumentException: The path is not of a legal form.`**

Type in the `GrasshopperDeveloperSettings` command in Rhino and uncheck the “Memory Load …” option.

![](<../../../.gitbook/assets/image (152) (2).png>)

## Decoding Model Validation Error Codes

Getting error codes when validating your model for simulation? Check out our list of common errors and how to fix them.&#x20;

{% content-ref url="help-with-modeling-error-codes.md" %}
[help-with-modeling-error-codes.md](help-with-modeling-error-codes.md)
{% endcontent-ref %}
