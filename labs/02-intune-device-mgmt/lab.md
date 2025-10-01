## Obective
- Configure Windows Autopilot to automatically provision a device from OOBE using a pre-imported hardware hash.

# Prerequisities:
- Microsoft 365 Business Premium Tenant
- Intune(Endpoint Manager) admin access.
- A Windows 10/11(Physical or VM)
- Gathering Hardware Hash

# Steps:
1. Gather Device Hardware Hash:
    - When the device is on Setting region stage type Shift + F10 and CMD prompt pop up. Go to Powershell First with Administrator permission.
    - Write the following commands:
        - Set-ExecutionPolicy Bypass -Scope Process -Force
        - Use the WindowsAutopilot script provided by Microsoft and save the output as csv file. 
2. Import Device into Autopilot:
    - Go to Microsoft Intune admin Center: https://intune.microsoft.com → Devices → Enrollment → Import the CSV file that gathered the H/W hash. I used a VM to gather the hash. But it will work with other physical device as well. 
    ![Device Import](C:\Users\greywire\m365-labs-portfolio\labs\02-intune-device-mgmt\scrennshots)
3. Create/Assign Autopilot Deployment Profile:
    - Go to Windows Enrollment → Deployment Profiles
    - Click + Create profile.
    - Platform: Windows PC.
    - Deployment mode: User-Driven
    - Included groups: All devices
4. Configure the Compliance Policy:
- Devices → Compliance → Create New Policy → I name the Policy as Compliance Test
- Compliance Settings:
    - Device Health - Bitlocker(Require)
    - Antivirus(Require)
    - Microsoft Defender Antimalware(Require)
    - On Assignments I included All devices 
    ![Compliance Policy](/scrennshots/devicecompliance.png)
    ![Compliance Policy 2](/scrennshots/deviceencryption.png)

# Test Autopilot Deployment
- Reset the VM
- ![VM Reset](/scrennshots/vmreset.png) 
- Connect with Internet
- Give user credential
- ![User Creds](/scrennshots/giveusercredential.png)
- Then wait until the setup is complete. 
- Verify the Device is intuned from Entra side (Screenshot Reference.)
-![Device Status](/scrennshots/devicesuccessfullyintuned.png)
-![Device Status 02](/scrennshots/deviceintunedfromentraside.png)


[def]: /scrennshots/importeddevice.png