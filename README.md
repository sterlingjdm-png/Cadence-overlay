# Cadence Overlay - Open Source BLE Cadence RPM Overlay for Android TV
Tiny open-source app: connects to a standard Bluetooth Cycling Speed & Cadence (CSC) sensor (Wahoo RPM Cadence, Coospo, Garmin, Magene, etc.) and shows a floating RPM number on top of any app - e.g. SmartTube in fullscreen on a MINIX box.
## Build (no Android Studio needed)
1. Upload this folder to a new GitHub repo > Actions > Build APK > Download artifact `CadenceOverlay-APK`.
2. Or in Android Studio: Open folder > Build > Build APK(s) > Build APK(s).
## Install on MINIX
1. Send APK to MINIX via `Send Files to TV` / USB / Downloader.
2. Settings > Apps > Security & Restrictions > Install unknown apps > Allow your file manager.
3. Open Cadence Overlay > Allow Bluetooth / Location / Notifications.
4. Settings > Apps > Special app access > Display over other apps > Cadence Overlay > Allow. (On Android 13+ if toggle is greyed: App info > tap 3-dot > Allow restricted settings first.)
## Use
1. Pedal to wake sensor. Do NOT pair in Android Settings Bluetooth.
2. In app: SCAN > tap your sensor > START OVERLAY.
3. Press HOME, open SmartTube. RPM stays top-right. Drag it with mouse/air-mouse. Overlay is not-focusable so your remote still controls SmartTube.
## How it works
Reads CSC Measurement (0x2A5B), calculates RPM = delta crank revs * 61440 / delta time (1/1024s). Drops to 0 after 3s no pedal.
License: MIT - do what you want.
