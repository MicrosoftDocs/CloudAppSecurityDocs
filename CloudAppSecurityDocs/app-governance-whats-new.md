---
title: What's new in app governance
ms.date: 5/17/2022
ms.topic: conceptual
description: Learn about new features and enhancements in app governance
---

# What's new in the app governance add-on to Defender for Cloud Apps

> [!NOTE]
> To sign up for app governance, see [Get started with app governance](app-governance-get-started.md).

abc

App governance provides you with comprehensive:

- **Insights**: See a view of all the third-party apps for the Microsoft 365 platform in your tenant on a single dashboard. You can see all the apps’ status and alert activities and react or respond to them.
- **Governance**: Create proactive or reactive policies for app and user patterns and behaviors and protect your users from using non-compliant or malicious apps and limiting the access of risky apps to your data.
- **Detection**: Be alerted and notified when there are anomalies in app activity and when non-compliant, malicious, or risky apps are used.
- **Remediation**: Along with automatic remediation capabilities, use remediation controls in a timely manner to respond to anomalous app activity detections.

App governance is a platform-based solution that is an integral part of the Microsoft 365 app ecosystem. App governance oversees and governs OAuth-enabled apps that are registered with Azure Active Directory (Azure AD) and access data through the Microsoft Graph API. App governance provides you with application behavior controls to help strengthen the security and compliance posture of your IT infrastructure.

## A first glimpse at app governance

To see the app governance dashboard, go to [aka.ms/appgovernance](https://aka.ms/appgovernance). Note that your sign-in account must have one of the [administrator roles](app-governance-get-started.md#administrator-roles) to view any app governance data.

## App governance integration with Azure AD and Defender for Cloud Apps

App governance, Azure AD, and Defender for Cloud Apps collect and provide different data sets:

- App governance provides detailed information about an app’s activity at the API level.
- Azure AD provides foundational app metadata and detailed information on sign-ins to apps.
- Defender for Cloud Apps provides app risk information.

By sharing information across app governance, Azure AD, and Defender for Cloud Apps, you can display aggregate information in one portal and easily link to another portal for more information. Here are some examples:

- App sign-in information in app governance:

  From the app governance portal, you can see the aggregated sign-in activity for each app and link back to the Azure Active Directory admin center for the details of sign-in events.

<!--
- App API usage information in the Azure Active Directory admin center:

  From the Azure Active Directory admin center, you can see the aggregated app usage information and link to the app governance portal for the details of app usage.
-->

- API usage information in the Defender for Cloud Apps portal:

  From the Defender for Cloud Apps portal, you can see API usage level and aggregate data transfer and link to the app governance portal for the details.

Here's a summary of the integration.

:::image type="content" source="media\app-governance\app-governance-add-on-arch.png" alt-text="The integration of app governance with Azure AD and Defender for Cloud Apps." lightbox="media\app-governance\app-governance-add-on-arch.png":::

App governance sends its alerts to Defender for Cloud Apps and Microsoft 365 Defender, and receives alerts from Defender for Cloud Apps, to enable more detailed analysis of app-based security incidents.

- App governance alerts show up in Microsoft 365 Defender alerts list as alerts with the Detection source field set to "App Governance"
- App governance alerts show up in the Defender for Cloud Apps alerts list as alerts with the Policy field set to one of the following:
  - Microsoft 365 OAuth App Governance
  - Microsoft 365 OAuth Phishing Detection
  - Microsoft 365 OAuth App Reputation
- Defender for Cloud Apps alerts appear in the app governance alerts list as alerts with Source set to Defender for Cloud Apps
