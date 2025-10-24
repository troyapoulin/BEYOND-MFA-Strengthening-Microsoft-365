# Auditing and Testing Conditional Access Policies

Misconfigured Conditional Access Policies (CAPs) can leave hidden gaps that attackers exploit, like unprotected legacy auth or unmanaged device access. This article explains how to audit and test CAPs to uncover weaknesses, validate enforcement, and ensure your policies truly protect every identity and session.

---

**Disclaimer:** The information and scripts provided in this article are for educational and informational purposes only. Use them at your own risk. Always review and test any configuration changes in a controlled environment before applying them to production systems. The author makes no warranties, express or implied, and assumes no liability for any loss or damage resulting from the use of this material.

---

## [Troubleshoot Conditional Access Policies with the What If Tool](https://learn.microsoft.com/en-us/entra/identity/conditional-access/what-if-tool)
The Conditional Access What If policy tool helps you understand the result of Conditional Access policies in your environment. It can be useful when simulating uncommon scenarios, enabling you to design more comprehensive security policies. Instead of manually testing your policies with multiple sign-ins, this tool helps you simulate a sign-in for a user or service principal. The simulation estimates how your policies affect this sign-in and generates a report.

## [Maester](https://maester.dev/)
Maester is a PowerShell based test automation framework to help you stay in control of your Microsoft security configuration. Maester provides a framework for you to bring DevOps practices to managing your Microsoft security configuration. Maester helps you monitor your Microsoft 365 tenant by running a set of tests to ensure your configuration is in compliance with your security policies.
- Define your security policies as code and store them in a version control system.
- Continuously run tests that ensure your tenant configuration is complying with the defined policies.
- Found an incorrect configuration? Create a new test to ensure it doesn't happen again.
- Write tests using Pester, a popular testing framework for PowerShell.
- Use the built-in tests to quickly get started with monitoring your tenant.
- Write custom tests as you introduce new configuration and codify your intent for the configuration.

## [Document Conditional Access with PowerShell](https://github.com/nicolonsky/ConditionalAccessDocumentation)
This PowerShell script documents your Entra ID Conditional Access policies while translating directory object IDs of targeted users, groups and apps to readable names. The script exports all data as a csv file which can be pretty formatted as excel workbook.

## [Microsoft365DSC](https://microsoft365dsc.com/)
Microsoft365DSC is an Open-Source initiative lead by Microsoft engineers and maintained by the community. It allows you to write a definition for how your Microsoft 365 tenant should be configured, automate the deployment of that configuration and ensures the monitoring of the defined configuration, notifying and acting on detected configuration drifts. It also allows you to extract a full-fidelity configuration out of any existing Microsoft 365 tenant. The tool covers all major Microsoft 365 workloads such as Exchange Online, Teams, SharePoint, OneDrive, Security and Compliance, Power Platforms, Intune and Planner.