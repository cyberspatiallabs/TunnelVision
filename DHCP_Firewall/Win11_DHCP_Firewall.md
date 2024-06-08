# Adding a DHCP Firewall Rule for Windows 10/11

**Note:  This firewall rule will restrict your computer to only conduct DHCP exchange with a designated IP.  If you move to another network and rely on DHCP, you will need to remove this rule for your DHCP to work properly**


1. **Open the Windows Security Center**:
   - Press the Windows key + I to open the Settings app.
   - Navigate to "Privacy & Security" and then select "Windows Security".

2. **Access the Firewall & network protection settings**:
   - In the Windows Security window, click on "Firewall & network protection".
   - Under the "Firewall & network protection" section, click on "Domain network".

3. **Create a new outbound rule for the DHCP server**:
   - In the "Domain network" settings, scroll down to the "Outbound rules" section.
   - Click on "Add a new rule".
   - In the "New Outbound Rule Wizard", select "Custom" and click "Next".
   - Select "UDP" as the protocol type and enter the port number for your local DHCP server (usually port 67).
   - In the "Remote IP address" section, select "These IP addresses" and enter the IP address of your local gateway.
   - Choose "Allow the connection" and click "Next".
   - Name the rule (e.g., "Allow DHCP from local gateway") and click "Finish".

4. **Create a new inbound rule for the DHCP client**:
   - Repeat the previous steps, but this time, select "Inbound rule" instead of "Outbound rule".
   - For the inbound rule, select "UDP" as the protocol type and enter the port number for your local DHCP client (usually port 68).
   - In the "Remote IP address" section, select "These IP addresses" and enter the IP address of your local gateway (e.g. 192.168.1.1).

5. **Disable all other DHCP-related firewall rules**:
   - In the "Firewall & network protection" section, click on "Advanced settings".
   - In the "Windows Defender Firewall with Advanced Security" window, navigate to "Inbound Rules" and "Outbound Rules".
   - Locate and disable any other DHCP-related rules that may be present.