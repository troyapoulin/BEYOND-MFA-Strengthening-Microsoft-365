# Managing & Monitoring Chrome Extensions

Unmanaged Chrome settings can quietly undermine security—especially when users install unapproved extensions, sync passwords, or sign in with personal accounts. This article explains how to lock down Chrome using enterprise policies to block add-ins and password sync, and how to monitor compliance through PowerShell and Windows event logs.

---

**Disclaimer:** The information and scripts provided in this article are for educational and informational purposes only. Use them at your own risk. Always review and test any configuration changes in a controlled environment before applying them to production systems. The author makes no warranties, express or implied, and assumes no liability for any loss or damage resulting from the use of this material.

---

## Managing Google Chrome with Group Policy

### Get and Install the ADMX Templates
You’ll need Chrome Enterprise and (maybe depding on server version) Edge ADMX templates:

👉 CHROME: https://chromeenterprise.google/policies/

👉 EDGE: https://www.microsoft.com/en-us/edge/business/download?cs=2282084340&form=MA13FJ

Copy chrome.admx and chrome.adml (language files) into your Group Policy Central Store:

```
\\yourdomain\SYSVOL\yourdomain\Policies\PolicyDefinitions
```

### Create Your Group Policies 
On a domain controller or admin workstation, open Group Policy Management Console (GPMC). Create or edit a GPO linked to your OU containing your users or computers. You need to manage the settings for both Google Chrome and Edge.  The group policy settings will be located: 

- Google Chrome Policies will be located at: Computer Configuration → Administrative Templates → Google → Google Chrome → Extensions
- Edge Policies will be located at: Computer Configuration → Administrative Templates → Microsoft Edge → Extensions

### GPOs For Extension Management
##### 1. Block all extensions by default:
- CHROME: Double-click "Configure extension installation blocklist", Set it to Enabled. In the Options field, enter: *
- EDGE: Double-click "Control which extension cannot be installed", Set it to Enabled. In the Options field, enter: *

This blocks all Chrome and Edge extensions from being installed.

##### 2. Allow only approved extensions
- CHROME: Double-click "Configure extension installation allowlist", Set it to Enabled. In the Options box, add specific extension IDs (comma-separated or one per line) that you want to allow.
- EDGE: Double-click "Allow specific extensions to be installed", Set it to Enabled. In the Options box, add specific extension IDs (comma-separated or one per line) that you want to allow.

(You can find extension IDs from the Chrome Web Store URL:
https://chrome.google.com/webstore/detail/<extension-name>/<EXTENSION_ID>)

##### 3. Optional: To force-install key extensions (e.g., password manager, security agent):
- CHROME: Double-click "Configure the list of force-installed apps and extensions", Set it to Enabled. In the Options field, enter in the following format: ```<extension_id>;<update_url>```
- EDGE: Double-click "Control which extension are installed silently", Set it to Enabled. In the Options box, add specific extension IDs (comma-separated or one per line) that you want to allow.


### GPOs For Browser Sync Management
- Google Chrome Policies will be located at: Computer Configuration → Administrative Templates → Google → Sign-in
- Edge Policies will be located at: Computer Configuration → Administrative Templates → Microsoft Edge → Browser sign-in settings

##### 1. Disable Browser Sign In:
- CHROME: Double-click "BrowserSignin", Set it to a value of 0. 
- EDGE: Double-click "Disable browser sign-in", Set it to Enabled. 

##### 2. Disable Browser Sync:
- CHROME: Double-click "SyncDisabled", Set it to Enabled. 
- EDGE: Double-click "SyncDisabled", Set it to Enabled. 

**Edge Registry Paths**
```
HKLM\SOFTWARE\Policies\Microsoft\Edge
"BrowserSignin"=dword:00000000
"SyncDisabled"=dword:00000001
```
**Edge Registry Paths**
```
HKLM\SOFTWARE\Policies\Google\Chrome
"BrowserSignin"=dword:00000000
"SyncDisabled"=dword:00000001
```

**Verifying Settings With Powershell**
```powershell
Get-ItemProperty "HKLM:\SOFTWARE\Policies\Microsoft\Edge" | Select BrowserSignin, SyncDisabled
Get-ItemProperty "HKLM:\SOFTWARE\Policies\Google\Chrome" | Select BrowserSignin, SyncDisabled
```

**NOTE:** You can also monitor sign in logs via Windows Event Logs: Event Viewer → Applications and Services Logs → Microsoft → Windows → User Profile Service
(Watch for new browser profile or account sign-ins.)

### GPOs For Browser Password Management





🔒 4. Additional Hardening Settings
Setting	Chrome Policy	Edge Policy	Purpose
Block Developer Mode	Block extensions from being installed in Developer mode	Allow developer mode extensions → set to Disabled	Prevent sideloading
Block External Extensions	Block external extensions	Block external extensions	Stops injection from local sources
Safe Browsing	Enable Safe Browsing / Enhanced Safe Browsing	SmartScreen settings → Enable Microsoft Defender SmartScreen	Protects against known malicious extensions