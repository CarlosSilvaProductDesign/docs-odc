---
summary: Location Plugin to enables your apps to access the GPS capabilities of the device. 
tags:
locale: en-us
guid: f2b0feab-c558-4d7f-b507-4511ae094677
app_type: mobile apps
platform-version: odc
---

# Location Plugin

Use the Location Plugin to enable an application to access the GPS capabilities of the user device, like latitude, longitude, and altitude. This plugin works with native mobile apps, progressive web apps (PWAs), and web apps.

<div class="info" markdown="1">

See [Adding plugins](../intro.md#adding-plugins) to learn how to install and reference a plugin in your OutSystems apps, and how to install a demo app.

</div> 

## Creating logic to get the device location

The Location Plugin actions are in the **Logic** tab of ODC Studio, in **Client Actions** > **LocationPlugin**.

To prevent errors, it's a best practice to first check if the plugin is available (1) with the action **CheckLocationPlugin**. If the plugin isn't available to the app, display an error to the user.

Otherwise, you can use the **GetLocation** action to get the device current location (2). In the GetLocation action you can enable the high accuracy mode, define the timeout of the action and set the maximum age (in milliseconds) to use the cached location.

Check if getting device location works by verifying the value of **GetLocation.Success** (3) is **True**. If yes, you can handle the device location data and apply any logic that you want. If **False**, you can show an **Error** to the user.

![Getting device location](images/logic-to-get-device-location-odcs.png)

## Check current device location in real time

To check the device location in real time and have a good user experience:

* Add the **LocationTracker** block on your screen
* Use the **WatchPosition** action to update location in real time
* Create logic to handle the event of the position changing
* Create logic to handle errors
* See the sections that follow for more information

## Add the LocationTracker block on your screen

To check if the device location changed, you can drag the **LocationTracker** block on your screen (4). This block handles the **OnPositionChanged** event to trigger another action in your app logic.

![A block to track location](images/add-location-tracker-ocds.png)

## Use the WatchPosition action to update location in real time

After adding the **LocationTracker** block in your app, you need to use the **WatchPosition** action to trigger and start monitoring the device position (5). Use the **WatchPosition** action in the flow that suits your app use case. The inputs are the same as in **GetLocation** action to update the device location in real time. 

As an output, this **WatchPosition** action returns a **WatchId**, an identifier that you can use in the **ClearWatch** action to stop the process of actively updating the device position. 

![A block to watch position](images/watch-position-action-odcs.png)

## Create logic to handle the event of the position changing

At last, you need to create a custom action and use it as the **Handler** of the **OnPositionChanged** event in the **LocationTracker** block (6). This event of the position changing returns the **Location** structure and the **WatchId**.

![Event handler ](images/logic-handle-event-odcs.png)

## Handling errors

The app with the Location Plugin can run on many Android or iOS devices, with different hardware and configurations. To ensure a good user experience and prevent the app from crashing, handle the errors within the app.

Here is the list of actions you can use to handle the errors. Use these actions with the **If** nodes to check for errors and control how the app works.


| Variable    | Action              | Description                                                                    |
| ----------- | ------------------- | ------------------------------------------------------------------------------ |
| IsAvailable | CheckLocationPlugin | True if the Location Plugin is available in the app.                           |
| Success     | GetLocation         | True if there aren't errors while getting the device location.                 |
| Success     | WatchPosition       | True if there aren't errors while updating the position in real time.          |
| Success     | ClearWatch          | True if there aren't errors while stopping updating the position in real time. |

![Handling errors](images/handling-errors-odcs.png)

## Actions

Here is the reference of the actions you can use from the plugin. Location Plugin uses a Cordova plugin, and for more information check [cordova-plugin-geolocation](https://github.com/OutSystems/cordova-plugin-geolocation).

| Action              | Description                                                                                 | Available in PWA |
| ------------------- | ------------------------------------------------------------------------------------------- | ---------------- |
| CheckLocationPlugin | Checks if the location plugin is available in the app.                                      | Yes              |
| GetLocation         | Get the current GPS information if the GPS is enabled on the device.                        | Yes              |
| WatchPosition       | Tracks the device position and triggers OnPositionChanged event from LocationTracker block. | Yes              |
| ClearWatch          | Clears a previously registered position watch.                                              | Yes              |

## MABS compatibility

The table shows the compatibility of the Location Plugin with the Mobile Apps Builds Service (MABS).

| Plugin version  | Compatible with MABS version | Notes |
| --------------- | ---------------------------- | ----- |
| 1.0.0 and later | MABS 9.0 and later.          |       |
