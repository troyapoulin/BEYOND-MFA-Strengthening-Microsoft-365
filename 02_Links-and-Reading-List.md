# Links & Additional Reading List

### [2025 Verizon Data Breach Investigations Report](https://www.verizon.com/business/resources/Ta1a/reports/2025-dbir-data-breach-investigations-report.pdf)
The Data Breach Investigations Report (DBIR) focuses on the analysis of anonymized
cybersecurity incident data that Verizon collects every year from almost a hundred
data contributors

### [Defending against evolving identity attack techniques](https://www.microsoft.com/en-us/security/blog/2025/05/29/defending-against-evolving-identity-attack-techniques/)
Microsoft details how identity-based attacks are evolving, from token theft to MFA fatigue and consent phishing. The post outlines new defenses in Entra ID — including token protection, stronger authentication strengths, and enhanced anomaly detection — to help organizations stay ahead of attackers.

### [State-of-the-art phishing: MFA bypass](https://blog.talosintelligence.com/state-of-the-art-phishing-mfa-bypass/)
Cisco Talos explains modern phishing and MFA-bypass techniques (including reverse proxies and Adversary-in-the-Middle kits), shows how attackers capture session tokens, and outlines practical detection and mitigation steps for defenders.


## Password Reuse
### [8 Scary Statistics about the Password Reuse Problem](https://www.enzoic.com/blog/8-stats-on-password-reuse/)
Passwords are still the weakest link in the security chain. While organizations often neglect tools that detect and block compromised credentials, users continue to reuse the same few passwords across dozens of accounts. That habit is putting personal and corporate data in jeopardy.

### [50+ Password Statistics & Trends to Know in 2024](https://jumpcloud.com/blog/password-statistics-trends)
Whether passwords are personal or professional, users tend to follow the same (bad) habits — and utilize a lot of the same passwords. These are some of the emerging and recurring password trends and statistics so far this year.

## InfoStealer Malware
### [Infostealers fueled cyberattacks and snagged 2.1B credentials last year](https://cyberscoop.com/infostealers-cybercrime-surged-2024-flashpoint/)
Cybercriminals used information-stealing malware to a devastating effect last year, capturing sensitive data that fueled ransomware, breaches and attacks targeting supply chains and critical infrastructure, according to a new report.

### [Lumma Stealer: Breaking down the delivery techniques and capabilities of a prolific infostealer](https://www.microsoft.com/en-us/security/blog/2025/05/21/lumma-stealer-breaking-down-the-delivery-techniques-and-capabilities-of-a-prolific-infostealer/)
Over the past year, Microsoft observed the persistent growth and operational sophistication of Lumma Stealer, an infostealer malware used by multiple financially motivated threat actors to target various industries. Our investigation into Lumma Stealer’s distribution infrastructure reveals a dynamic and resilient ecosystem that spans phishing, malvertising, abuse of trusted platforms, and traffic distribution systems. 

### [Katz and Mouse Game: MaaS Infostealers Adapt to Patched Chrome Defenses](https://www.elastic.co/security-labs/katz-and-mouse-game)
Elastic Security Labs breaks down bypass implementations from the infostealer ecosystem’s reaction to Chrome 127's Application-Bound Encryption scheme.

### [Millions of people spied on by malicious browser extensions in Chrome and Edge](https://www.malwarebytes.com/blog/news/2025/07/millions-of-people-spied-on-by-malicious-browser-extensions-in-chrome-and-edge)
Researchers have discovered a campaign that tracked users’ online behavior using 18 browser extensions available in the official Chrome and Edge webstores. The total number of installs is estimated to be over two million.

### [Detecting browser data theft using Windows Event Logs](https://security.googleblog.com/2024/04/detecting-browser-data-theft-using.html)
This blog describes one set of signals for use by system administrators or endpoint detection agents that should reliably flag any access to the browser’s protected data from another application on the system. By increasing the likelihood of an attack being detected, this changes the calculus for those attackers who might have a strong desire to remain stealthy, and might cause them to rethink carrying out these types of attacks against our users.

## MFA
### [MFA Fatigue Attack](https://www.beyondtrust.com/resources/glossary/mfa-fatigue-attack)
A multi-factor authentication (MFA) fatigue attack—also known as MFA Bombing or MFA Spamming—is a social engineering cyberattack strategy. This strategy involves repeatedly pushing second-factor authentication requests to the target victim’s email, phone, or registered devices. The goal is to coerce the victim into confirming their identity via notification, thus authenticating the attacker's attempt at entering their account or device.

### [How Does FIDO2 Authentication Work, and Why Is It Important?](https://www.trio.so/blog/fido2-authentication)
Discover how FIDO2 Authentication enhances security, improves user experience, and streamlines access management for your organization.

### [Fido Alliance: Passkeys](https://fidoalliance.org/passkeys/)
A passkey is a FIDO authentication credential based on FIDO standards, that allows a user to sign in to apps and websites with the same process that they use to unlock their device (biometrics, PIN, or pattern). 

### [WebAuthn Guide/](https://webauthn.guide/)
The Web Authentication API (also known as WebAuthn) is a specification written by the W3C and FIDO, with the participation of Google, Mozilla, Microsoft, Yubico, and others. The API allows servers to register and authenticate users using public key cryptography instead of a password.

### [How to Test Adversary-in-the-Middle Without Hacking Tools w/ Michael Allen](https://www.youtube.com/live/Esu8blIcyuA)
In today's webcast, Michael Allen will explain the technical nuts and bolts of how various Adversary-in-the-Middle hacking tools work and their varying degrees of sophistication. Then he'll present a low-tech, do-it-yourself process that ANYONE can use to test whether their own multifactor authentication configuration is vulnerable to an AitM attack.


## Open Redirects
### [Widespread credential phishing campaign abuses open redirector links](https://www.microsoft.com/en-us/security/blog/2021/08/26/widespread-credential-phishing-campaign-abuses-open-redirector-links/)
Microsoft has been actively tracking a widespread credential phishing campaign using open redirector links. Attackers combine these links with social engineering baits that impersonate well-known productivity tools and services to lure users into clicking.

### [Understanding and Discovering Open Redirect Vulnerabilities](https://www.trustwave.com/en-us/resources/blogs/spiderlabs-blog/understanding-and-discovering-open-redirect-vulnerabilities/)
One of the most common and largely overlooked vulnerabilities by web developers is Open Redirect (also known as "Unvalidated Redirects and Forwards"). A website is vulnerable to Open Redirect when parameter values (the portion of URL after "?") in an HTTP GET request allow for information that will redirect a user to a new website without any validation of the target of redirect.

## URL Filtering to Prevent AiTM
### [About MS365 SafeLinks](https://learn.microsoft.com/en-us/defender-office-365/safe-links-about)
In organizations with Microsoft Defender for Office 365, Safe Links scanning protects your organization from malicious links that are used in phishing and other attacks. Specifically, Safe Links provides URL scanning and rewriting of inbound email messages during mail flow, and time-of-click verification of URLs and links in email messages, Teams, and supported Office 365 apps.

### [Setting Up SafeLink Policies](https://learn.microsoft.com/en-us/defender-office-365/safe-links-policies-configure)
Explains how to configure Microsoft Defender for Office 365 Safe Links policies to protect users from malicious URLs in emails and Office documents. Covers real-time URL scanning, time-of-click verification, policy scopes, and best practices for securing your organization’s email environment.

## MS365 Conditional Access

### [What is Conditional Access?](https://learn.microsoft.com/en-us/entra/identity/conditional-access/overview)
Conditional Access policies at their simplest are if-then statements; if a user wants to access a resource, then they must complete an action. For example: If a user wants to access an application or service like Microsoft 365, then they must perform multifactor authentication to gain access.

### [Conditional Access authentication strength](https://learn.microsoft.com/en-us/entra/identity/authentication/concept-authentication-strengths)
Authentication strength is a Conditional Access control that specifies which combinations of authentication methods can be used to access a resource. Users can satisfy the strength requirements by authenticating with any of the allowed combinations.

### [Token Protection in Microsoft Entra Conditional Access](https://learn.microsoft.com/en-us/entra/identity/conditional-access/concept-token-protection)
Token Protection is a Conditional Access session control that attempts to reduce token replay attacks by ensuring only device bound sign-in session tokens, like Primary Refresh Tokens (PRTs), are accepted by Entra ID when applications request access to protected resources.

### [Configure and enable risk policies](https://learn.microsoft.com/en-us/entra/id-protection/howto-identity-protection-configure-risk-policies)
There are two types of risk policies in Microsoft Entra Conditional Access you can set up. You can use these policies to automate the response to risks allowing users to self-remediate when risk is detected: Sign-in risk policy and User risk policy

### [Configure and enable risk policies](https://learn.microsoft.com/en-us/entra/id-protection/howto-identity-protection-configure-risk-policies)
There are two types of risk policies in Microsoft Entra Conditional Access you can set up. You can use these policies to automate the response to risks allowing users to self-remediate when risk is detected: Sign-in risk policy and User risk policy

### [Conditional Access: Session](https://learn.microsoft.com/en-us/entra/identity/conditional-access/concept-conditional-access-session)
In a Conditional Access policy, an admin can use session controls to enable limited experiences in specific cloud applications.

### [Block authentication flows with Conditional Access policy](https://learn.microsoft.com/en-us/entra/identity/conditional-access/policy-block-authentication-flows)
To bolster security posture, Microsoft recommends blocking or restricting device code flow wherever possible. The following steps help create Conditional Access policies to restrict how device code flow and authentication transfer are used within your organization.








## Auditing and Testing MS365

