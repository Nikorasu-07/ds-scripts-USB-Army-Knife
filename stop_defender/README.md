# stop_defender

This script utilizes keyboard key injection via HID (Human Interface Device) to attempt to disable Windows Defender on a target machine.

**Functionality:**

The script simulates keyboard input to navigate the Windows interface and turn off the real-time protection feature of Windows Defender. It achieves this by:

1.  **Opening Windows Security:** Simulating the keystrokes to open the Windows Security settings.
2.  **Navigating to Virus & threat protection:** Using tab presses and arrow keys to select the "Virus & threat protection" option.
3.  **Accessing Manage settings:** Navigating to and selecting the "Manage settings" option under "Virus & threat protection settings".
4.  **Toggling Real-time protection:** Using tab presses and arrow keys to locate and toggle the "Real-time protection" switch to the "Off" position.

**Important Considerations:**

* **Requires Unlocked Machine:** This script **will only function** on a Windows PC that is already unlocked and the user is logged in. It cannot bypass the login page.
* **Defender Settings Page Remains Open:** After attempting to disable Windows Defender, the "Virus & threat protection" settings page will likely remain open. This behavior makes the script somewhat **obsolete** as the user can easily re-enable the protection.
* **Limitation: Simultaneous Key Press:** The author was unable to implement simultaneous key presses within the current scripting method. If you possess the knowledge of how to execute the pressing of two keys at the same time via DuckyScript or a similar HID injection language compatible with the "USB Army Knife" firmware, please consider sharing this knowledge! This could potentially lead to a more efficient and stealthy method of disabling Defender.
* **DELAY Calibration:** The `DELAY` commands within this script are crucial for its proper execution. You **must recalibrate** these delay values based on the expected speed of the target machine in opening applications and executing commands. A machine that is slow or under heavy load will require longer delays for the script to function reliably. Insufficient delays may result in the script failing to navigate the interface correctly.

**Usage:**

1.  Ensure the target Windows PC is unlocked and the user is logged in.
2.  Plug in the USB Army Knife with this `stop_defender.ds` script loaded.
3.  The script will automatically attempt to disable Windows Defender.

**Disclaimer:**

This script is provided for educational and testing purposes only. Use it responsibly and only on systems you have explicit permission to test. Unauthorized use is illegal and unethical. The author assumes no responsibility for any misuse or damage caused by this script.
