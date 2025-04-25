# powershell_admin

This script leverages keyboard key injection via HID (Human Interface Device) to open a PowerShell window with administrative privileges on a target Windows machine.

**Functionality:**

The script simulates the following sequence of keyboard actions:

1.  **Open the Run dialog:** Simulates pressing the `WIN` + `R` keys to open the "Run" dialog.
2.  **Enter "powershell":** Types the command `powershell` into the "Open" field.
3.  **Open with Administrator Privileges:** Simulates pressing `CTRL` + `SHIFT` + `ENTER`. This combination, when used with the "Run" dialog, attempts to launch the specified application with administrator rights.
4.  **Bypass User Account Control (UAC):** Simulates pressing `ALT` + `Y`. This is a common keyboard shortcut to select "Yes" on the User Account Control (UAC) prompt that appears when trying to run an application with administrative privileges.

**Important Considerations:**

* **HID Injection Dependency:** This script relies on HID (Human Interface Device) injection. Its functionality is entirely dependent on the target system interpreting the USB device as a keyboard and processing the injected keystrokes.
* **Requires Unlocked Machine:** This script **will only function** on a Windows PC that is already unlocked and the user is logged in. It cannot bypass the login page.
* **UAC Settings:** The script assumes that the default UAC prompt is displayed and that `ALT` + `Y` will select the "Yes" option. If the target machine has different UAC settings or a different language pack, this shortcut might not work.
* **DELAY Calibration is Crucial:** The `DELAY` commands within this script are critical for its proper execution. You **must recalibrate** these delay values based on the expected speed of the target machine in opening the "Run" dialog, launching PowerShell, and displaying the UAC prompt. A machine that is slow, under heavy load, or has different animation settings will require adjusted delays for the scripts to function reliably. Insufficient delays may lead to the script failing to navigate the interface correctly.
* **Base Script for PowerShell Operations:** This script serves as a foundational step for executing further PowerShell commands. Once an administrative PowerShell window is open, subsequent scripts can be designed to inject commands into this shell to perform more advanced actions, such as creating administrative user accounts (as you mentioned for a future script).

**Usage:**

1.  Ensure the target Windows PC is unlocked and the user is logged in.
2.  Plug in the USB Army Knife with this `powershell_admin.ds` script loaded.
3.  The script will automatically attempt to open a PowerShell window with administrator privileges.

**Disclaimer:**

This script is provided for educational and testing purposes only. Use it responsibly and only on systems you have explicit permission to test. Unauthorized use is illegal and unethical. The author assumes no responsibility for any misuse or damage caused by this script.
