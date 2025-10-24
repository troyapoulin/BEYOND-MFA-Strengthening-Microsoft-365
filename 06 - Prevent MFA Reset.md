# Prevent MFA Resets

By default, Microsoft 365 / Entra ID (formerly Azure AD) allows users to manage their own authentication methods (like adding MFA devices), which creates a risk if an attacker gains session-level access to the portal.

---

**Disclaimer:** The information and scripts provided in this article are for educational and informational purposes only. Use them at your own risk. Always review and test any configuration changes in a controlled environment before applying them to production systems. The author makes no warranties, express or implied, and assumes no liability for any loss or damage resulting from the use of this material.

---

## OPTION 1: Prevent users from managing their own MFA devices
You can do this by blocking access to the “MySecurityInfo” page via Conditional Access.  
1. Go to Entra admin center → Protection → Conditional Access → Policies
2. Create new policy, e.g., “Restrict MFA registration page access”
3. Assign:
  - Users: All or targeted users
  - Cloud apps or actions: Choose “User actions” → “Register security information”
  - Grant: Block access (or restrict to trusted networks / compliant devices)
4. Enable policy.

**NOTE:** Before enforcing Conditional Access policies, always exclude at least one break-glass Global Admin account. Test new policies in Report-only mode first to confirm expected behavior and avoid locking yourself or critical services out.

You can also accomplish this without CAPs for some MFA factors, however this is probably not the best option.  
1. Go to Microsoft Entra admin center → Protection → Authentication methods → Authentication method policy
2. Select each method (Microsoft Authenticator, FIDO2, Email, etc.).
3. Under Target, remove All users and assign only, A specific admin or pilot group, not end users.

## OPTION 2: Require re-authentication (MFA) before adding new MFA methods
If you don’t want to block it outright, require step-up authentication when managing security info.

- Same as above, but instead of blocking: Under Grant, choose Require multifactor authentication.

This forces a valid MFA challenge before users can access the MFA management portal — even if they’re already signed into M365.

