# Xbox Controller Battery Indicator

A small Windows tray application that shows the battery and connection status for Xbox-compatible controllers that Windows exposes through XInput.

The app is meant to stay out of the way. It runs in the notification area, updates the tray icon once per second, and shows a quick status popup when you click the tray icon.

![Controller status popup](img/controller-status-popup.png "Controller status popup")

## What it shows

- A tray icon for the connected controller status that needs attention first.
- A popup with a large battery meter for each connected controller.
- Wireless battery level as one of the broad XInput ranges: Empty, Low, Medium, or Full.
- Wired or USB-connected status when XInput reports the controller as wired.
- The last known wireless battery level when a controller is later connected by USB, when that value is available.
- Low or empty battery warnings, with optional sound settings.
- Startup, update check, warning, appearance, and language options from the right-click menu.

![Tray status icons](img/tray-status-icons.png "Tray status icons")

## Important battery note

After a controller is connected or turned on, Windows/XInput may not report a usable battery value until the controller sends input. Press any button on the controller once after connecting it. Until then, the app may show the controller as waiting for battery data or unknown.

## Battery level ranges

XInput does not report an exact percentage. It only reports broad battery levels. The app displays those levels as estimated ranges:

| XInput level | Displayed range |
| --- | --- |
| Full | 75-100% |
| Medium | 50-75% |
| Low | 25-50% |
| Empty | 0-25% |

## Supported controllers

This app should work with controllers that Windows exposes through XInput, including many Xbox and Xbox-compatible controllers. Known controller families include:

- Xbox 360 controllers
- Xbox One controllers
- Xbox One S controllers
- Xbox One Elite controllers
- Xbox Elite Series 2 controllers
- Xbox Series X/S controllers
- Other gamepads that appear to Windows as XInput controllers

Best results are usually with wired USB or the Xbox Wireless Adapter. Bluetooth behavior depends on the controller model, firmware, Windows version, and driver stack.

## Known limitations

- Windows only.
- XInput only. Controllers that only expose DirectInput, HID, Steam Input, or vendor-specific APIs may not appear here.
- XInput supports up to four controller slots, so the app checks up to four controllers.
- Battery values are broad ranges, not exact percentages.
- Battery data can be delayed until a button is pressed on the controller.
- Bluetooth-connected controllers may report no battery data, stale battery data, or incorrect battery data. This is a Windows/XInput limitation, not something the app can fully correct.
- USB or wired status does not always prove the battery is actively charging. The app can show USB connected or likely charging, but exact charging state may not be available through XInput.
- Tray icons are limited by Windows notification-area scaling. The icons were simplified to be more readable, but the taskbar can still make small icons hard to read on some displays.

## How to use

1. Download the latest release package from the Releases page.
2. Extract the zip file.
3. Run `XB1ControllerBatteryIndicator.exe`.
4. Connect or turn on your controller.
5. Press any controller button once if the app is waiting for battery data.
6. Left-click the tray icon to view the status popup.
7. Right-click the tray icon to change settings or exit the app.

## Settings

Right-click the tray icon to access:

- Start with Windows
- Check for new version on start
- USB connected notification
- Empty battery warning sound
- Repeat warning sound loop
- Compact popup
- Animated charging icon
- Flash empty battery alert
- Language selection
- Exit
