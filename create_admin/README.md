# create_admin 

This script leverages keyboard key injection via HID (Human Interface Device) to first open a PowerShell window with administrative privileges and then proceed to create a new local administrator user on the target Windows machine.

**Functionality:**

The script simulates the following sequence of keyboard actions:

1.  **Open the Run dialog:** Simulates pressing the `WIN` + `R` keys to open the "Run" dialog.
2.  **Enter "powershell":** Types the command `powershell` into the "Open" field.
3.  **Open with Administrator Privileges:** Simulates pressing `CTRL` + `SHIFT` + `ENTER`. This combination, when used with the "Run" dialog, attempts to launch the specified application with administrator rights.
4.  **Bypass User Account Control (UAC):** Simulates pressing `ALT` + `Y`. This is a common keyboard shortcut to select "Yes" on the User Account Control (UAC) prompt that appears when trying to run an application with administrative privileges.
5.  **Type the `net user` command:** Once the administrative PowerShell window is open and active, the script types the PowerShell command `net user` followed by a space.
6.  **Type the new username:** Types the desired username for the new administrator account (currently set to `attacker`, you may need to modify this in the script).
7.  **Type the password:** Types the desired password for the new administrator account (currently set to `P@$$wOrd123`, you may need to modify this in the script).
8.  **Add the `/add` switch:** Types the `/add` switch to create the user.
9.  **Execute the command:** Simulates pressing the `ENTER` key to execute the `net user` command.
10. **Type the `net localgroup administrators` command:** Types the PowerShell command `net localgroup administrators` followed by a space.
11. **Type the new username again:** Types the username of the newly created account (`attacker`).
12. **Add the `/add` switch:** Types the `/add` switch to add the user to the administrators group.
13. **Execute the command:** Simulates pressing the `ENTER` key to execute the `net localgroup administrators` command.

**Important Considerations:**

* **HID Injection Dependency:** This script relies on HID (Human Interface Device) injection. Its functionality is entirely dependent on the target system interpreting the USB device as a keyboard and processing the injected keystrokes.
* **Requires Unlocked Machine:** This script **will only function** on a Windows PC that is already unlocked and the user is logged in. It cannot bypass the login page.
* **UAC Settings:** The script assumes that the default UAC prompt is displayed and that `ALT` + `Y` will select the "Yes" option. If the target machine has different UAC settings or a different language pack, this shortcut might not work.
* **Username and Password:** The username (`attacker`) and password (`P@$$wOrd123`) are hardcoded in this script. **It is highly recommended to modify these values** within the `.ds` file before execution for security and customization purposes.
* **Localization:** The `net user` and `net localgroup` commands are generally language-independent in Windows. However, any additional commands you might add in future iterations could be affected by the target system's language settings.
* **DELAY Calibration is Crucial:** The `DELAY` commands within this script are critical for its proper execution. You **must recalibrate** these delay values based on the expected speed of the target machine in opening the "Run" dialog, launching PowerShell, displaying the UAC prompt, and processing commands within the PowerShell window. A machine that is slow or under heavy load will require adjusted delays for the script to type and execute commands reliably. Insufficient delays may lead to the script failing at any stage.
* **Base Script for PowerShell Operations:** This script directly creates an administrative user. You can adapt and expand upon this script to execute further PowerShell commands after the user is created.

**Usage:**

1.  Ensure the target Windows PC is unlocked and the user is logged in.
2.  Plug in the USB Army Knife with this `create_admin_user.ds` (or `add_admin_powershell.ds`) script loaded.
3.  The script will automatically attempt to open a PowerShell window with administrator privileges and then create a new local administrator user with the specified username and password.

**Next Steps:**

With a new administrative user created, subsequent scripts can be developed to log in as this user (if automation of login is possible and desired) or to execute further commands with elevated privileges.

**Disclaimer:**

This script is provided for educational and testing purposes only. Use it responsibly and only on systems you have explicit permission to test. Unauthorized use is illegal and unethical. The author assumes no responsibility for any misuse or damage caused by this script.
