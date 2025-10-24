# Alerting on Email Inbox Rules

Misconfigured Conditional Access Policies (CAPs) can leave hidden gaps that attackers exploit, like unprotected legacy auth or unmanaged device access. This article explains how to audit and test CAPs to uncover weaknesses, validate enforcement, and ensure your policies truly protect every identity and session.

---

**Disclaimer:** The information and scripts provided in this article are for educational and informational purposes only. Use them at your own risk. Always review and test any configuration changes in a controlled environment before applying them to production systems. The author makes no warranties, express or implied, and assumes no liability for any loss or damage resulting from the use of this material.

---

## Option 1: Microsoft Purview Alerting or Audit
This is the MS preferred way, but unfortunately it requires additional licensing and is not included in Business Premium licenses.  
1. You can create Activity alerts right inside the Purview [Compliance portal](https://compliance.microsoft.com)
2. Navigate to Audit → Alerts → Activity alerts
3. Click + New alert policy
4. Give it a name (e.g., “Inbox Rule Added or Modified”)
5. Choose activities:
  - User created inbox rule
  - User modified inbox rule
  - User deleted inbox rule
6. Scope: All users (or specific accounts)
7. Actions: Add email recipients 

## Option 2: Power Automate + Graph API or PowerShell
1. Create a scheduled flow (say every hour or every day)
2. Use a HTTP call or PowerShell script to query: Microsoft Graph audit logs or the Search-UnifiedAuditLog PowerShell command 
3. Filter for: New-InboxRule, Set-InboxRule, Remove-InboxRule
4. Send yourself an email notification (or Teams message) when results are found.

## Option 3: Azure Automation Runbook (PowerShell)
1. Create an [Automation Account](https://learn.microsoft.com/en-us/azure/automation/overview)
2. Add a Runbook that runs every X minutes/hours
3. Use this PowerShell logic:

```powershell
Connect-ExchangeOnline -Organization "yourtenant.onmicrosoft.com"
$start = (Get-Date).AddHours(-1)
$events = Search-UnifiedAuditLog -StartDate $start -EndDate (Get-Date) -Operations New-InboxRule,Set-InboxRule,Remove-InboxRule

if ($events.Count -gt 0) {
    $body = $events | Select-Object UserIds, Operations, CreationDate, AuditData | ConvertTo-Html | Out-String
    Send-MailMessage -To "alerts@yourbank.com" -From "o365alerts@yourbank.com" -Subject "New Inbox Rule Detected" -BodyAsHtml $body -SmtpServer "smtp.office365.com" -UseSsl -Port 587 -Credential (Get-Credential)
}
```
