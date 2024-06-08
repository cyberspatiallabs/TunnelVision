# Adding a DHCP Firewall Rule for MacOS

**Note:  This firewall rule will restrict your computer to only conduct DHCP exchange with a designated IP.  If you move to another network and rely on DHCP, you will need to remove this rule for your DHCP to work properly**

1. **Open the System Preferences**:
   - Click on the Apple icon in the top-left corner of the screen.
   - Select "System Preferences" from the dropdown menu.

2. **Access the Security & Privacy settings**:
   - In the System Preferences window, click on the "Security & Privacy" icon.
   - Click on the "Firewall" tab.
   - If the firewall is not enabled, click the lock icon in the bottom-left corner and enter your administrator password to make changes.
   - Click the "Firewall Options..." button.

3. **Create a new firewall rule for the DHCP client**:
   - In the Firewall Options window, click the "+" button to add a new rule.
   - For the "Application" field, select "SystemUIServer" (this is the macOS system process that handles DHCP).
   - For the "Type" field, select "Outbound".
   - For the "Protocol" field, select "UDP".
   - For the "Port" field, enter "68" (the standard DHCP client port).
   - For the "Remote Address" field, enter "192.168.1.1" (the IP address of your local gateway).
   - Click "Add" to create the new rule.

4. **Create a new firewall rule for the DHCP server**:
   - Repeat the previous steps, but this time:
   - For the "Application" field, select "bootpd" (the macOS DHCP server process).
   - For the "Type" field, select "Inbound".
   - For the "Protocol" field, select "UDP".
   - For the "Port" field, enter "67" (the standard DHCP server port).
   - For the "Remote Address" field, enter "192.168.1.1" (the IP address of your local gateway).
   - Click "Add" to create the new rule.

5. **Disable all other DHCP-related firewall rules**:
   - In the Firewall Options window, review the list of firewall rules.
   - Locate and disable any other DHCP-related rules that may be present.

6. **Close the Firewall Options window and System Preferences**:
   - Click "OK" to close the Firewall Options window.
   - Close the System Preferences window.