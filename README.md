
<img width="730" height="320" alt="disa-logo" src="https://github.com/user-attachments/assets/6be6cc8f-2a3c-41b7-b554-67cc12e455b1" />

# DISA-STIG-Hardening-Lab
This lab will demonstrate device hardening techniques in an Active Directory environment following the guidance of DISA STIGs.

## Environments and Technologies Used
- OracleVM VirtualBox (7.0.16_Ubuntur162802)
- Active Directory Domain Services
- STIG Viewer 3.7

## Operating Systems Used
- Windows Server 2022 (21H2) | DC
- Windows 11 (24H2) | Client

## Homelab Overview
This is a home lab where I simulate hardening client devices within my virtualized Active Directory environment. I will be using the STIG Viewer application that is available for download from the cyber exchange website. I will also be downloading a STIG from its library that will be the source of the hardening techniques that will be implemented.

## What is A DISA STIG?
A DISA STIG (Defense Information Systems Agency Security Technical Implementation Guide) is a cybersecurity framework used to secure U.S. Department of Defense (DoD) IT systems. They act as instructions that lock down software, hardware, and networks to minimize vulnerabilites. Compliance to these guidelines are a mandatory requirement for all DoD information systems, networks, and contractor systems. These guidelines are regularly updated by DISA to address new vulnerabilities and security requirements.

## Who is DISA?
The Defense Information Systems Agency (DISA) is an agency within the US Department of Defense responsible for serving as the military's central IT and communications provider, managing the global enterprise networks, secure communications, and cybersecurity infrastructure used by the president, joint warfighters, and national command centers. They also manage the DoD's public key infrastructure (PKI) for secure device access, and monitors networks for potential threats.

## Tasks
Here are the tasks that will be completed in this lab:
- [Install STIG Viewer from the Cyber Exchange website](#install)
- [Download a DISA STIG from the the Cyber Exchange website](#download)
- [Import the DISA STIG into STIG Viewer](#import)
- [Build a STIG Checklist to Implement](#checklist)
- [Implement Hardening Techniques](#harden)

During implementation, I will be documenting the following for each STIG rule:
-  Any findings
-  Status
-  Remediations applied
-  Evidence proving the STIG requirements were met
 

<a name="install"> </a>
## Installing STIG Viewer
Using a web browser visit the [Cyber Exchange](https://www.cyber.mil/) website. This is where we will download the STIG Viewer software. On the home page, select the tab **SRGs/STIGs** located in the upper right-hand corner of the web page.
<img width="1443" height="1039" alt="Screenshot from 2026-05-16 13-02-21" src="https://github.com/user-attachments/assets/4e4c47f9-d2f1-4e10-be93-38d1ec1a95e6" />


Then on the right-hand side of the web page, expand the dropdown menu labeled **More** and select **SRG/STIG Tools**.
<img width="1443" height="1039" alt="Screenshot from 2026-05-16 13-02-21" src="https://github.com/user-attachments/assets/3ed5b702-cae5-4fae-9887-65cee294f51d" />


Scroll down until you get to a list of downloads. Download the file that's appropriate for your operating system.
<img width="1443" height="1039" alt="Screenshot from 2026-05-16 13-19-42" src="https://github.com/user-attachments/assets/a617c608-4feb-418b-9f29-cc79e79d7c29" />


Once the .zip file is downloaded, extract the file and run the installer. Once it is finished installing, open it and you should be brought to the STIG viewer dashboard.
<img width="1042" height="792" alt="Screenshot from 2026-05-16 13-30-26" src="https://github.com/user-attachments/assets/9480375a-3694-4a26-b1f0-772c1bdb50ba" />


<a name="download"></a>
## Download a DISA STIG 
Going back to the Cyber Exchange web page, select the **Document Library** tab located at the top of the web page.
<img width="1443" height="1039" alt="Screenshot from 2026-05-16 13-34-22" src="https://github.com/user-attachments/assets/84cc7804-e197-4bf0-9397-412e699b130d" />


In the search bar on this page, type **Windows** and a list of STIGs associated with Windows operating systems should populate. Select the one titled **Microsoft Windows 11 STIG - Ver 2, Rel 7**
> If that specific version isn't there it may have been replaced with a newer version.
<img width="1443" height="1039" alt="Screenshot from 2026-05-16 13-46-32" src="https://github.com/user-attachments/assets/f82343a1-9c5d-4b8d-92dd-e0809db1dc39" />

Once the .zip file is downloaded, extract it.
Feel free to browse through each individual STIG rule to gain a bit more knowledge of the hardening techniques used.


<a name="import"></a>
## Import the DISA STIG into STIG Viewer
Now that I have my STIG I can import it into the STIG Viewer. On the left-hand side of the STIG Viewer dashboard click **Open** next to the panel labeled **STIG Viewer**. 
<img width="1042" height="792" alt="Screenshot from 2026-05-16 14-18-53" src="https://github.com/user-attachments/assets/cc4b2795-16ea-47ef-805a-18902d7f41aa" />


Navigate the file explorer to the location you extracted the .zip file and open the .xml file within it.
<img width="1042" height="792" alt="Screenshot from 2026-05-16 14-21-14" src="https://github.com/user-attachments/assets/f94cf49e-0a7f-408a-b17c-219150d8d291" />


Below is the full list of STIGS that are included in this STIG file. As you can see there are many requirements to ensure systems are compliant to. Since this is only a homelab to demonstrate implementing STIG controls and not a DoD system we will not be making all of the configurations.
<img width="1042" height="792" alt="Screenshot from 2026-05-16 14-23-07" src="https://github.com/user-attachments/assets/6f27d13e-9363-49b0-aca1-a0cfad1cb0d7" />


<a name="checklist"></a>
## Build a STIG Checklist to Implement
To begin building out our checklist, click the **Home** icon at the top of the window to bring you back to the dashboard. Then select **New** in the panel titled **Checklists**
<img width="1042" height="792" alt="Screenshot from 2026-05-16 14-30-55" src="https://github.com/user-attachments/assets/2d877229-0101-427d-a7f5-c6af477999d5" />


Under the section labeled **Library STIGs**, you should see the Microsoft Windows 11 STIG file that we just imported. Click the **Magnifying glass** to add individual STIG rules.
> If you don't see it, simply select **Open STIG** and select the .xml file from earlier.
<img width="1042" height="792" alt="Screenshot from 2026-05-16 14-36-13" src="https://github.com/user-attachments/assets/f8acbcf6-59f4-44af-aef0-b8ce7d6ba5de" />


Search through the list and click the **+** icon next to each rule to add it to the checklist. I will be adding the following rules to my checklist:
- [V-268317](#copilot)
- [V-253298](#logon)
- [V-253261](#bitlocker)
- [V-253269](#only-admin)
- [V-253272](#standard-user)
- [V-523289](#secondary)
<img width="1042" height="792" alt="Screenshot from 2026-05-16 14-48-37" src="https://github.com/user-attachments/assets/9efa1149-7229-445b-aa31-0a8c600bc9a4" />


At the upper right-hand corner of the window select **Back to Checklist Builder** to return to the checklist menu
<img width="1042" height="792" alt="Screenshot from 2026-05-16 14-51-11" src="https://github.com/user-attachments/assets/1d96242f-32a8-4d79-98c4-5d8d7d090744" />


In the checklist menu, select **Save** in the upper left-hand corner of the window to save the checklist. I will be naming mine "Home-Lab-STIG-Checklist"
<img width="1042" height="792" alt="Screenshot from 2026-05-16 14-54-25" src="https://github.com/user-attachments/assets/bec59545-0715-43e1-8031-7f77d5b3d78a" />


Select **Fill Checklist** in the upper right-hand corner of the screen
<img width="1042" height="792" alt="Screenshot from 2026-05-16 14-58-23" src="https://github.com/user-attachments/assets/c32fd540-b391-4cd6-8313-07fe948f00fd" />


<a name="harden"></a>
## Implement Hardening Techniques
Next I'll fill in the information on the right-hand side under the vulnerability chart with the information regarding my target client device.
<img width="1042" height="792" alt="Screenshot from 2026-05-16 15-14-27" src="https://github.com/user-attachments/assets/6ab0cd12-da96-498a-83bf-3e0446ccebd6" />


<a name="copilot"></a>
### V-268317
The first STIG rule I'll be checking against our client will be the STIG under the Group ID: V-268317. The rule states that CoPilot must be disabled for Windows 11.
<img width="1042" height="792" alt="Screenshot from 2026-05-16 15-21-44" src="https://github.com/user-attachments/assets/237ab2cb-24fe-4351-9150-c72482c21508" />


On the client machine type the following command into PowerShell as an admin:
` Get-AppxPackage -AllUsers | Where-Object { $_.Name -like "*Copilot*" }`
If Microsoft.CoPilot displays, this is a finding.
<img width="1051" height="881" alt="Screenshot from 2026-05-16 15-28-05" src="https://github.com/user-attachments/assets/eecf77be-b22c-4622-a8d9-6f4c2cac1a83" />


To remediate this finding you can run the PowerShell command below as admin to remove the Microsoft CoPilot package
`Get-AppxPackage -AllUsers *CoPilot* | Remove-AppxPackage -AllUsers`
<img width="1051" height="881" alt="Screenshot from 2026-05-16 15-36-44" src="https://github.com/user-attachments/assets/96be72ec-b2ff-4eb5-bb73-47acdd5636b2" />


Running the command from earlier to list the CoPilot package should result in an empty output
<img width="1051" height="881" alt="Screenshot from 2026-05-16 15-38-16" src="https://github.com/user-attachments/assets/acb267d6-be61-4d43-82f1-bcd0305110cb" />


In the **Comments** section of the STIG rule I document my findings. In the **Finding Details** section I explain the action taken to remediate the finding. Click the gray box in the left-hand side of the STIG Rule once to mark it as not a finding since we remediated the finding
<img width="1042" height="792" alt="Screenshot from 2026-05-16 15-46-08" src="https://github.com/user-attachments/assets/5cfe4ed5-791c-42a7-b22c-3fa81835a906" />


<a name="logon"></a>
### V-253298
The next STIG rule I'll be implementing is under the Group ID: V-253298. The rule states the number of allowed bad logon attempts must be configured to three or less. To verify, do the following:
Run "gpedit.msc" as admin if using a standard account. Then navigate to Local Computer Policy >> Computer Configuration >> Windows Settings >> Security Settings >> Account Policies >> Account Lockout Policy.
If the "Account lockout threshold" is "0" or more than "3" attempts, this is a finding.
<img width="1051" height="881" alt="Screenshot from 2026-05-16 16-03-21" src="https://github.com/user-attachments/assets/e27fa96e-715d-4e62-88d6-5828b4e507a0" />


To remediate, we will add a Group Policy that will maintain this policy across all client devices. In my Domain Cotroller, I open the Group Policy Management Console (gpmc.msc) and navigate to the OU my client devices are stored. I right-click the OU and select 
**Create a GPO in this domain and link it here...**
<img width="1042" height="792" alt="Screenshot from 2026-05-16 16-09-15" src="https://github.com/user-attachments/assets/667d8abd-ee37-492c-b9b2-558c35929fee" />


I will name the new policy **Account Lockout Policy**
<img width="1042" height="792" alt="Screenshot from 2026-05-16 16-13-20" src="https://github.com/user-attachments/assets/f9ea518e-c20d-4fc1-834e-a5b0169dd73a" />


Right-click the newly created policy and select **Edit**
<img width="1042" height="792" alt="Screenshot from 2026-05-16 16-17-53" src="https://github.com/user-attachments/assets/aeabba62-0c22-4d98-94aa-19e9c83f2188" />


Navigate to Computer Configuration >> Policies >> Windows Settings >> Security Settings >> Account Policies >> Account Lockout Policy and double-click on **Account lockout threshold**
<img width="1042" height="792" alt="Screenshot from 2026-05-16 16-21-52" src="https://github.com/user-attachments/assets/cf10c5a3-ded5-48e6-bf2f-6f5499cc5541" />


Check the box **Define this policy setting** and set the account lockout to **three**. Click apply Making this change also triggers gpmc to make recommended changes to **Account lockout duration** and **Reset account lockout counter after** valuse to 30 minutes.
<img width="1042" height="792" alt="Screenshot from 2026-05-16 16-26-14" src="https://github.com/user-attachments/assets/756ef2ae-35d1-49d8-bfeb-8049f61cc124" />


On the client device in a command prompt window, type the command `gpupdate /force`. This will force the pc to update it's group policy settings to match the policy created earlier.
<img width="1051" height="881" alt="Screenshot from 2026-05-16 16-29-09" src="https://github.com/user-attachments/assets/da322d30-e5ed-4829-b4bf-456b3f3a6617" />


Now navigate to Local Computer Policy >> Computer Configuration >> Windows Settings >> Security Settings >> Account Policies >> Account Lockout Policy. Note that the policies have updated to match the changes made on the DC.
<img width="1051" height="881" alt="Screenshot from 2026-05-16 16-32-23" src="https://github.com/user-attachments/assets/6de6c06e-3dd4-4fff-b4bd-f1e5d6f4b08d" />

In the **Comments** section of the STIG rule I document my findings. In the **Finding Details** section I explain the action taken to remediate the finding. Click the gray box in the left-hand side of the STIG Rule once to mark it as not a finding since we remediated the finding


<a name="secondary"></a>
### V-523289
Thist STIG rule states the Secondary Logon service must be disabled on Windows 11. It explains that the Secondary Logon service provides a means for entering alternate credentials, typically used to run commands with elevated privileges. Using privileged credentials in a standard user session can expose those credentials to theft. On the client device I will run **services.msc** to access the services utility.
<img width="1051" height="881" alt="Screenshot from 2026-05-16 16-54-38" src="https://github.com/user-attachments/assets/2694bfdb-38b7-4ea4-b1f7-3f1f1d169eeb" />


Search for **Secondary Logon**. If the **Startup Type** is not **Disabled** or the status is **Running**, this is a finding. In my case the startup type is set to **Manual**. 
<img width="1051" height="881" alt="Screenshot from 2026-05-16 16-59-43" src="https://github.com/user-attachments/assets/8df454b3-580c-4215-9689-ad42a128543a" />


To remediate this finding, we will be making another GPO. Follow the steps before to create a new policy in GPMC named **Secondary Logon**. Navigate to Computer Configuration >> Policies >> Windows Settings >> Security Settings >> System Services >> Secondary Logon. Check **Define this policy setting** select **Disabled**, and click **Apply**
<img width="1042" height="792" alt="Screenshot from 2026-05-16 17-05-07" src="https://github.com/user-attachments/assets/a3453993-4e7a-4cda-adc8-9ad3b1ce37bb" />


I'm going to switch back to my client and run another gpupdate. Once it is complete I will check the service to see if the change was applied.
> As you can see, the service's startup type has been changed to match the policy setting.
<img width="1051" height="881" alt="Screenshot from 2026-05-16 17-11-41" src="https://github.com/user-attachments/assets/6b58616a-90b8-4afc-9a36-07d0c11472f9" />

In the **Comments** section of the STIG rule I document my findings. In the **Finding Details** section I explain the action taken to remediate the finding. Click the gray box in the left-hand side of the STIG Rule once to mark it as not a finding since we remediated the finding
















































































































