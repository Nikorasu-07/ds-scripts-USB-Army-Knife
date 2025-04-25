# create_admin_user

This script relies on an already open PowerShell window with administrative privileges (achieved, for example, by the `powershell_admin.ds` script in this repository) to create a new local administrator user on the target Windows machine. It utilizes keyboard key injection via HID (Human Interface Device) to type and execute PowerShell commands.

**Prerequisites:**

* A PowerShell window with administrative privileges must be open and active on the target machine **before** running this script. This script does not handle opening the administrative PowerShell window itself.

**Functionality:**

The script simulates the following sequence of keyboard actions within the active administrative PowerShell window:

1.  **Type the `net user` command:** Types the PowerShell command `net user` followed by a space.
2.  **Type the new username:** Types the desired username for the new administrator account (currently set to `attacker`, you may need to modify this in the script).
3.  **Type the password:** Types the desired password for the new administrator account (currently set to `P@$$wOrd123`, you may need to modify this in the script).
4.  **Add the `/add` switch:** Types the `/add` switch to create the user.
5.  **Execute the command:** Simulates pressing the `ENTER` key to execute the `net user` command.
6.  **Type the `net localgroup administrators` command:** Types the PowerShell command `net localgroup administrators` followed by a space.
7.  **Type the new username again:** Types the username of the newly created account (`attacker`).
8.  **Add the `/add` switch:** Types the `/add` switch to add the user to the administrators group.
9.  **Execute the command:** Simulates pressing the `ENTER` key to execute the `net localgroup administrators` command.

**Important Considerations:**

* **HID Injection Dependency:** This script relies on HID (Human Interface Device) injection. Its functionality is entirely dependent on the target system interpreting the USB device as a keyboard and processing the injected keystrokes within the active PowerShell window.
* **Administrative PowerShell Required:** As stated in the prerequisites, this script **will only function** if a PowerShell window with administrator privileges is already open and in focus.
* **Username and Password:** The username (`attacker`) and password (`P@$$wOrd123`) are hardcoded in this script. **It is highly recommended to modify these values** within the `.ds` file before execution for security and customization purposes.
* **Localization:** The `net user` and `net localgroup` commands are generally language-independent in Windows. However, any additional commands you might add in future iterations could be affected by the target system's language settings.
* **DELAY Calibration is Crucial:** The `DELAY` commands within this script are critical for its proper execution. You **must recalibrate** these delay values based on the expected speed of the target machine in processing commands within the PowerShell window. A machine that is slow or under heavy load will require adjusted delays for the script to type and execute commands reliably. Insufficient delays may lead to the script failing to create the user or add them to the administrators group.

**Usage:**

1.  Ensure a PowerShell window with administrator privileges is open and active on the target Windows PC. This can be achieved using the `powershell_admin.ds` script or other methods.
2.  Plug in the USB Army Knife with this `create_admin_user.ds` script loaded.
3.  The script will automatically attempt to create a new local administrator user with the specified username and password.

**Next Steps:**

This script provides a basic framework for interacting with the target system via PowerShell. Future scripts can be developed to execute more complex commands and automate further actions once an administrative PowerShell session has been established.

**Disclaimer:**

This script is provided for educational and testing purposes only. Use it responsibly and only on systems you have explicit permission to test. Unauthorized use is illegal and unethical. The author assumes no responsibility for any misuse or damage caused by this script.
