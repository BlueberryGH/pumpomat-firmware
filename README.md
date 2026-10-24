# Pumpomat – Firmware

Firmware files for the **Pumpomat** pump controller.

**Latest version:** [Releases → Latest](https://github.com/BlueberryGH/pumpomat-firmware/releases/latest)

## Updating the firmware

All you need is a phone or laptop with Wi-Fi. No software has to be installed.

1. Download the file `Pumpomat_X.Y_RevD.bin` from the latest release. Do not unzip or rename it.
2. On the Pumpomat, set the **Cloud** switch to **on**. Make sure the display is connected, then restart the Pumpomat (reset button or briefly disconnect power).
3. The display shows **"Service: WEB"**, the Wi-Fi name (`Pumpomat-XXXX`) and a QR code.
4. Scan the QR code with your phone, or select `Pumpomat-XXXX` in your Wi-Fi settings. The network has no password.
   Android may ask whether to stay connected without internet access: choose **Yes**.
5. The page opens automatically. If not, enter `http://192.168.4.1` in your browser.
6. Log in with the **service password** (provided by the manufacturer).
7. **Firmware** → select the file → **Upload**. The pump must be stopped.
8. Wait until the Pumpomat restarts and shows the new version on the display (about 1 minute). **Do not switch off during the update.**
9. Set the **Cloud** switch back to **off** and restart the Pumpomat.

If anything goes wrong, the previous version keeps running. An interrupted update changes nothing.

## Settings

The same menu has a **Settings** page with the control parameters (target pressure etc.). Settings are kept during an update. Before making larger changes, use **"Backup"**.

## Checksum (optional)

Each release lists the SHA-256 checksum of the `.bin` file. Use it to check that the download is complete.
