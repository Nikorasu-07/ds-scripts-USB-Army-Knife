# USB Army Knife - LilyGo T-Dongle S3 DuckyScript Payloads

This repository contains a collection of simple DuckyScript files (.ds) designed and tested for use with the LilyGo T-Dongle S3 running the "USB Army Knife" firmware.

These scripts leverage Human Interface Device (HID) capabilities to inject keystrokes into the target machine, automating various actions.

## Compatibility

**Tested Operating Systems:**

* ✅ **Windows:** These scripts have been specifically tested and confirmed to function correctly on Windows operating systems with an Italian keyboard layout.

**Untested/Incompatible Operating Systems:**

* ❌ **macOS:** These scripts are **not** designed for macOS and are confirmed **not to work** on this platform due to differences in HID handling and command syntax.
* ⚠️ **Linux:** These scripts have **not** been tested on Linux. However, due to potential differences in HID handling and command syntax compared to Windows, they are **expected not to function** correctly on Linux distributions.

**Important Considerations:**

* **HID Injection Dependency:** These scripts rely on HID (Human Interface Device) injection. Their functionality is entirely dependent on the target system interpreting the USB device as a keyboard and processing the injected keystrokes.
* **DELAY Calibration is Crucial:** The `DELAY` commands within these scripts are critical for their proper execution. You **must recalibrate** these delay values based on the expected speed of the target machine in opening applications, executing commands, and processing input. A machine that is slow, under heavy load, or has different animation settings will require adjusted delays for the scripts to function reliably. Insufficient delays may lead to the script failing to navigate the interface correctly.
* **Potential Security Measures:** On certain computers equipped with security software that monitors USB device input or implements protections against HID injection attacks, these scripts **may not function as intended or may be detected and blocked**. Similarly, systems employing mechanisms for verifying newly inserted USB drives might prevent the scripts from executing automatically or at all.
* **RAW_HID for Italian Keyboard Layout:** Some of the scripts in this repository are written using the `RAW_HID` function, which is essential for precise control over the emulated keyboard layout. These particular scripts are specifically configured and tested for **Italian keyboard layouts**.
* **US Firmware Layout and Character Mapping:** The base "USB Army Knife" firmware typically utilizes a **United States (US) keyboard layout**. Due to the differences between the US and Italian keyboard layouts, you might observe seemingly strange or incorrect symbols within the `.ds` script files when viewed directly. This is because certain characters that have different physical key positions or require modifier keys (like Shift or AltGr) in the Italian layout might correspond to different, but visually similar, characters in the US layout.
* **Example of Character Mapping:** For instance, the forward slash `/` character, which is often located on a different key in the Italian layout compared to the US layout, might be represented by the hyphen `-` character (or another symbol) within the `.ds` file. This is intentional, as the `RAW_HID` codes used in the script are specifically chosen to produce the correct Italian symbol when the HID input is processed by a system with an Italian keyboard layout. Therefore, trust that the seemingly misplaced symbols in the code are correctly mapped for Italian keyboards.

**Usage:**

Refer to the `README.md` file within each individual script's folder for specific instructions and details on its functionality, including whether the script utilizes standard `STRING` commands or `RAW_HID` for keyboard layout compatibility. **Pay close attention to the intended target keyboard layout mentioned in each script's README.**

**Ethical and Legal Considerations:**

Please remember to use these scripts responsibly and ethically. They are intended for use in **authorized testing environments** or **professional engagements** where you have explicit permission to assess the security of systems. **Unauthorized use of these scripts on systems you do not own or have permission to test is illegal and unethical.**

This repository is provided for educational and research purposes only. The author(s) assume no responsibility for any misuse or damage caused by the use of these scripts.
