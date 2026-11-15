# Pumpomat – Firmware

Firmware files for the **Pumpomat** pump controller (board Rev D).

**Latest version:** [Releases → Latest](https://github.com/BlueberryGH/pumpomat-firmware/releases/latest)

**Quick guide (PDF):** [English](docs/Pumpomat_Quick_Guide_EN.pdf) · [Deutsch](docs/Pumpomat_Kurzanleitung_DE.pdf)

All you need is a phone or laptop with Wi-Fi and the service password. No software has to be installed.

## Service mode

1. On the Pumpomat board, set switch **SW1 "WLAN"** to **open** (slider **up**), then press **Reset**.
   The green LED **double-flashes** while Wi-Fi is on. After the start the display shows a Wi-Fi QR code 3 times, with the box ID `Pumpomat-XXXX` and the address `192.168.4.1`. After that the status line alternates with the Wi-Fi name.
2. Scan the Wi-Fi QR code, or select `Pumpomat-XXXX` in your Wi-Fi settings. The network has no password.
   - **Android:** when asked whether to stay connected without internet access, choose **Yes**. The page usually opens by itself.
   - **iPhone:** in the login window tap **Cancel**, choose **Use Without Internet**, then open `http://192.168.4.1` in Safari. Do not choose "Use Other Network", it disconnects from the Pumpomat Wi-Fi.
   - Without a QR code: enter `http://192.168.4.1` in the browser.
3. Log in with the **service password**. After **3 wrong entries** the login is locked and the display shows "WEB GESPERRT". Press **Reset** to unlock.
4. When you are done, set **SW1** back to **closed** (slider **down**) and press **Reset**. If you forget, Wi-Fi switches itself off after 15 minutes without access.

The pump keeps running normally in service mode.

## Updating the firmware

1. Download `Pumpomat_X.Y_RevD.bin` from the latest release. Do not unzip or rename it.
2. Open service mode and log in (see above).
3. Under **Now**, switch the pump off. Uploading only works while the motor is stopped.
4. Under **Firmware**, choose the file and tap **Upload**. The page refuses files for another board, and accepts older versions only with an extra tick.
5. Wait until the Pumpomat restarts and shows the new version on the display (about 1 minute). **Do not switch off during the update.**
6. Connect and log in again if you want to check the version.

If anything goes wrong, the previous version keeps running. An interrupted update changes nothing. If the new version crashes 3 times within 10 minutes, the Pumpomat goes back to the previous version by itself. You can also go back manually with **Start previous version** (tap twice).

## Settings and statistics

- **Settings:** the control parameters (target pressure etc.). Change a value and tap **Apply**. Settings are kept during an update.
- **Save and load:** save the settings to a file before larger changes, and load them back later. On the iPhone use Safari for this, downloads do not work in the Wi-Fi login window.
- **Statistics:** operating hours, motor starts, faults and the most recent events. The "since service" column can be reset (tap twice).
- **Factory settings** (under **More**, tap twice) sets all parameters back to their defaults.

## Checksum (optional)

Each release lists the SHA-256 checksum of the `.bin` file. Use it to check that the download is complete:

- Windows: `certutil -hashfile Pumpomat_X.Y_RevD.bin SHA256`
- macOS / Linux: `shasum -a 256 Pumpomat_X.Y_RevD.bin`
