---
title: App governance in Microsoft Defender for Cloud Apps and Microsoft 365 Defender
ms.date: 05/28/2023
ms.topic: conceptual
description: Implement Microsoft app governance capabilities over Microsoft Defender for Cloud Apps and Microsoft 365 Defender to govern your apps.
---

# App governance in Microsoft Defender for Cloud Apps and Microsoft 365 Defender

Cyber attacks have become increasingly sophisticated in the ways they exploit the apps you have deployed in your on-premises and cloud infrastructure, establishing a starting point for privilege escalation, lateral movement, and data exfiltration.

To understand the potential risks and stop these types of attacks, you need to gain clear visibility into your organization’s app compliance posture. You need to be able to quickly identify when an app exhibits anomalous behaviors and respond when these behaviors present risks to your environment, data, and users.

## App governance features

App governance in Defender for Cloud Apps is a set of security and policy management capabilities designed for OAuth-enabled apps registered on Azure Active Directory (Azure AD), Google, and Salesforce. App governance delivers visibility, remediation, and governance into how these apps and their users access, use, and share sensitive data in Microsoft 365 and other cloud platforms through actionable insights and automated policy alerts and actions.

App governance also enables you to see which user-installed OAuth applications have access to data on Microsoft 365, Google Workspace, and Salesforce. It tells you what permissions the apps have and which users have granted access to their accounts.

App governance insights enable you to make informed decisions around blocking or restricting apps that present significant risk to your organization. For example:

- **Insights**: See a view of all non-Microsoft apps registered to Azure Active Directory in your organization on a single dashboard. You can see the status of apps and their activities, and react or respond to them.

- **Governance**: Create proactive or reactive policies for app and user patterns and behaviors and protect your users from using non-compliant or malicious apps and limiting the access of risky apps to your data.

- **Detection**: Be alerted and notified when there are anomalies in app activity and when non-compliant, malicious, or risky apps are used.

- **Remediation**: Along with automatic remediation capabilities, use remediation controls in a timely manner to respond to anomalous app activity detections.

## Share data across Microsoft services

View app governance data together with other Defender for Cloud Apps data and Azure AD data to aggregate information and jump between views.

For example:

- On the app governance **OAuth apps** page, view aggregated sign-in activity for each app. From there, select links to go to the Azure Active Directory admin center for the details of sign-in events.

- On other **Cloud apps** pages in Microsoft 365 Defender, view API usage levels and aggregate data transfer. From there, select links to go to the app governance **OAuth apps** page for more details.
<!--need new image without "addin" and the classic portal-->

App governance alerts show up in the Microsoft 365 Defender alerts list as alerts with the **Detection source** field set to *App Governance*.

## Next steps

To see the app governance dashboard, go to [aka.ms/appgovernance](https://aka.ms/appgovernance). Note that your sign-in account must have one of the [administrator roles](app-governance-get-started.md#roles) to view any app governance data.

For more information, see [Get started with app governance](app-governance-get-started.md).
