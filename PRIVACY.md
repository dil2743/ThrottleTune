# Privacy Policy

ThrottleTunes does not transmit any data. Ride history is optional, off by default, and stays on the device.

## Network access

The app does not request the `INTERNET` permission or any other network permission. Android therefore blocks all network connections from the app at the operating-system level.

The app contains no servers, accounts, advertising, analytics, crash reporting or third-party tracking, and does not use Google Play Services or Firebase. Android cloud backup is disabled.

## Permissions

| Permission | Purpose |
|---|---|
| Location (precise, background) | Read the current speed from GPS while riding. Positions are stored only if ride history is enabled. |
| Nearby devices | Detect when the selected headset connects or disconnects. |
| Notifications | Show the ongoing status notification. |
| Foreground service | Keep running while riding. |
| Ignore battery optimizations | Prevent the system from stopping the app during a ride. |
| Companion device | Allow the app to start when the headset connects. |

## Data stored on the device

The app stores your settings and the name and Bluetooth address of the selected headset in app-private storage.

If **ride history** is enabled, the app also stores the GPS track of each ride (time, position and speed, about every 5 seconds) in app-private storage. Other apps cannot read it. Individual rides or the whole history can be deleted in the app.

All data is removed when the app is uninstalled.

## Sharing routes

Routes leave the device only when you explicitly share them:

- **Share exact route** creates a GPX or KML file and passes it to the app you choose in Android's share menu.
- **Open in Google Maps** opens a link containing the start, end and up to nine points of the route in Google Maps, which sends them to Google.

ThrottleTunes itself never uploads anything.

## Verification

- **Android settings:** Apps → ThrottleTunes → Permissions → *See all permissions*. No network access is listed.
- **In the app:** the *Privacy* section checks the installed permissions at runtime.
- **APK inspection:** `aapt2 dump permissions ThrottleTunes-vX.Y.Z.apk`, or `scripts/check-apk-privacy.sh`.

## Enforcement

- The manifest explicitly removes network permissions that dependencies might add.
- The build fails if the APK requests any permission outside a reviewed allowlist.
- Every release build is checked for network permissions before it is published.
