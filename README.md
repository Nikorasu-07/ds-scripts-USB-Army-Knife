# USB Army Knife - LilyGo T-Dongle S3 DuckyScript Payloads

This repository contains a collection of simple DuckyScript files (.ds) designed and tested for use with the LilyGo T-Dongle S3 running the "USB Army Knife" firmware.

These scripts leverage Human Interface Device (HID) capabilities to inject keystrokes into the target machine, automating various actions.

## Compatibility

**Tested Operating Systems:**

* ✅ **Windows:** These scripts have been specifically tested and confirmed to function correctly on Windows operating systems.

**Untested/Incompatible Operating Systems:**

* ❌ **macOS:** These scripts are **not** designed for macOS and are confirmed **not to work** on this platform due to differences in HID handling and command syntax.
* ⚠️ **Linux:** These scripts have **not** been tested on Linux. However, due to potential differences in HID handling and command syntax compared to Windows, they are **expected not to function** correctly on Linux distributions.

**Important Considerations:**

* **HID Injection Dependency:** These scripts rely on HID (Human Interface Device) injection. Their functionality is entirely dependent on the target system interpreting the USB device as a keyboard and processing the injected keystrokes.
* **DELAY Calibration is Crucial:** The `DELAY` commands within these scripts are critical for their proper execution. You **must recalibrate** these delay values based on the expected speed of the target machine in opening applications, executing commands, and processing input. A machine that is slow, under heavy load, or has different animation settings will require adjusted delays for the scripts to function reliably. Insufficient delays may lead to the script failing to navigate the interface correctly.
* **Potential Security Measures:** On certain computers equipped with security software that monitors USB device input or implements protections against HID injection attacks, these scripts **may not function as intended or may be detected and blocked**. Similarly, systems employing mechanisms for verifying newly inserted USB drives might prevent the scripts from executing automatically or at all.

**Usage:**

Refer to the `README.md` file within each individual script's folder for specific instructions and details on its functionality.

**Ethical and Legal Considerations:**

Please remember to use these scripts responsibly and ethically. They are intended for use in **authorized testing environments** or **professional engagements** where you have explicit permission to assess the security of systems. **Unauthorized use of these scripts on systems you do not own or have permission to test is illegal and unethical.**

This repository is provided for educational and research purposes only. The author(s) assume no responsibility for any misuse or damage caused by the use of these scripts.
