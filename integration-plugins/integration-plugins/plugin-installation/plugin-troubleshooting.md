---
description: View some basic troubleshooting steps when installing Sonoran CAD plugins.
---

# Plugin Troubleshooting

## Framework Commands

Sonoran CAD's framework includes powerful built-in commands. **These commands are entered into your server console.**

**Ex:** A [support member](https://support.sonoransoftware.com) may ask you to send detailed logging information to them. They will give you the specific ID number to enter. (ex: 123)\
Entering `sonoran support 123` in your server console will send your plugin configuration directly to our support application.

| Command                    | Description                                                                                                                                                                                                                                                                                            |
| -------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| sonoran debugmode          | Enables detailed debug logging                                                                                                                                                                                                                                                                         |
| sonoran info               | Displays version and config information                                                                                                                                                                                                                                                                |
| sonoran support <_NUMBER_> | <p>Sends important information for <a href="https://support.sonoransoftware.com">customer support</a> purposes.</p><p>The <em>NUMBER</em> parameter will be provided to you by a support team member.</p><p></p><p>Ex: <code>sonoran support 123</code> sends us your plugin information for help.</p> |
| sonoran plugin <_NAME_>    | <p>Displays plugin information</p><p></p><p>Ex: <code>sonoran plugin callcommands</code></p>                                                                                                                                                                                                           |

## Quick Checks

### 1. Ensure your community is on a paid version.

Your community's subscription may have expired and failed to renew. Do a quick check on your [community limits](../../../tutorials/getting-started/view-your-limits.md) to make sure your community version includes the plugin you are trying to install.

{% hint style="info" %}
Each plugin install guide lists the required subscription version at the top.
{% endhint %}

### 2. Ensure your plugin is enabled

Be sure to follow the [framework installation](../framework-installation.md) and [plugin installation](./) guides thoroughly, depending on the specific plugin you are trying to install.

\
Make sure you have not forgotten to enable the plugin in the plugin config file!

Enter `sonoran info` into your server console.

![Sonoran Info - Disabled Plugins](<../../../.gitbook/assets/image (52).png>)

If the plugin you are having trouble with is listed as DISABLED, you may have forgotten to enable it in the plugin configuration.

![The "enabled" field should be set to "true"](../../../.gitbook/assets/enable\_config.png)

### 3. Ensure your plugin is up-to-date and download the latest release.

Plugin updates are released often. Make sure your server is running on the latest release.

![](../../../.gitbook/assets/plugin\_1.png)

### 4. Ensure your API ID is set correctly.

Ensure you have set your [API ID in the CAD](../../../sonoran-cad/api-integration/getting-started/setting-your-api-id.md) using the value from the [API ID plugin](../available-plugins/api-id-checker.md).

## Debug Mode

The plugin framework includes a powerful debug mode. Enable this by entering `sonoran debugmode` into your server console.

Debug mode will print out additional error information and JSON data for all API calls or push events.

### 1. Check your API ID:

For plugins that require your individual CAD user account to have the API ID set (live map, unit locations, panic, etc.) you can view this data in the console output.

The image below shows an API Call being made from the server to Sonoran CAD. This API call is type `UNIT_LOCATION` and includes all the data necessary.

Ensure the `APIID` listed in the API call matches the [API ID set in your CAD's user account](../../../sonoran-cad/api-integration/getting-started/setting-your-api-id.md).

![Debug Mode - Unit Location API Call](../../../.gitbook/assets/debug\_console.png)

### 2. Check the Community ID and API Key

Your community ID and API key is also listed in the debug API call information. Be sure that the [community ID and API key](../../../sonoran-cad/api-integration/getting-started/retrieving-your-credentials.md) are correct.

## Live Map and Push Events

For live map and push event troubleshooting, see our dedicated guide here:

{% content-ref url="broken-reference" %}
[Broken link](broken-reference)
{% endcontent-ref %}

## Still Having Trouble?

If you're still having trouble, our dedicated support team is here to help.

[Reach out to us and generate a support ticket at any time](https://support.sonoransoftware.com).

## Common Errors

### Error: Ensure config.json is present

Your framework or plugin config is not correctly named `config.json`. Ensure that is has been spelt correctly, is not `config.json.json`, etc.

You may need to open the file in a text editor to more easily see the file extension, and ensure that it is correctly named as `config.json`.

