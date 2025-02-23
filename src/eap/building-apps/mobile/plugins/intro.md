---
summary: Plugins for your mobile apps.
tags:
locale: en-us
guid: 55ef1d73-dac8-48e6-8b15-dc6990779660
app_type: mobile apps, reactive web apps
platform-version: odc
---

# Mobile plugins

Plugins provide important functionalities to native mobile apps, letting you use many of the hardware capabilities of mobile devices. You can add notifications, use camera or global positioning services, read QR codes, and more.

## The list of supported mobile plugins

The table shows the OutSystems-supported mobile plugins that you can find in the Forge repository. Some of them are already supported when distributing your app as a Progressive Web App (PWA).


| Plugin                    | Description                                                  | Supported in PWA |
| ------------------------- | ------------------------------------------------------------ | ---------------- |
| Barcode Plugin            | Access the camera to scan barcodes.                          | Yes              |
| Camera Plugin             | Access the camera capabilities of the device.                | Yes              |
| Health and Fitness Plugin | Access data from Apple HealthKit and Google Fit.             | NA               |
| File Plugin               | Manage files and folders within the app sandbox.             | NA               |
| File Transfer Plugin      | Upload and download files in background.                     | NA               |
| File Viewer Plugin        | View remote or app resource files.                           | NA               |
| Key Store Plugin          | Store encrypted key-value pairs with optional authentication | NA               |
| Location Plugin           | Access the GPS capabilities the device.                      | Yes              |

### Notes

When working with the plugins:

* Use the plugin that supports iOS or Android, depending on your target platform. The app generation fails if you use a plugin that isn't supported on the target platform.
* Each time you add, remove, or modify the plugin in an app, OutSystems creates a mobile package which you then have to distribute to the users for installation.
* Include the plugin license in your app to respect the license agreements of that plugin. These license agreements are usually placed in the About page of the app that uses them.

## Installing a plugins and adding a public element to your app

The plugins are available from the Forge repository. To use a plugin in your app, you first need to install the plugin to your organization and add the plugin elements to your app.

To install a supported plugin from Forge:

1. Find the plugin you want to use in the [list of supported mobile plugins](#the-list-of-supported-mobile-plugins).

1. In **ODC Portal** > **Forge** find the plugin and open the details page.

1. Click **Install** and follow the instructions to install the plugin. Optionally, install the demo app that comes with the plugin.

1. Once the installation finishes, add the actions you want to use as public elements in your mobile app.

## Built-in plugins

All mobile apps generated by OutSystems include a native shell with the following built-in plugins that are used internally, handling a variety of housekeeping and infrastructure tasks. While you may see the names of these built-in plugins in the native mobile shell logs they're not user-configurable.


| Plugin            | Description                                                                                                                         |
| ----------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| OS Auth           | Handles OAuth flows and ensures compliance with the guidelines for SSO using the right WebView instances types for Android and iOS. |
| OS Cache          | Lets your application to run offline or with bad network conditions.                                                                |
| OS Cordova Loader | Loads the Cordova engine on your app.                                                                                               |
| OS Deeplinks      | Opens hyperlinks to specific screens of your app.                                                                                   |
| OS DB Upgrader    | Manages the local storage of your app.                                                                                              |
| OS Manifest       | Provides a parser for the app manifest.                                                                                             |
| OS Pre-Bundle     | Handles the content of the app pre-bundled resources.                                                                               |
| OS Security       | Provides the APIs for the security layer.                                                                                           |
| NetworkStatus     | Lets your app know when the device is online/offline and informs of the type of network available (for example, WiFi, 3G, 4G).      |


