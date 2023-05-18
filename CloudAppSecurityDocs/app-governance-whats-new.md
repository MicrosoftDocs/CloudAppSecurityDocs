---
title: What's new in app governance
ms.date: 02/28/2023
ms.topic: conceptual
description: Learn about new features and enhancements in app governance
---

# What's new in the app governance add-on to Defender for Cloud Apps

For more information on what's new with other Microsoft Defender security products, see:

- [What's new in Microsoft Defender for Cloud Apps](release-notes.md)
- [What's new in Microsoft 365 Defender](/microsoft-365/security/defender/whats-new)
- [What's new in Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/whats-new-in-microsoft-defender-endpoint)
- [What's new in Microsoft Defender for Identity](/defender-for-identity/whats-new)

## App governance June 2023 release

- **Enhanced hunting experience for OAuth app activities:** App governance enables you to take hunting with app data to the next level by providing deeper OAuth app insights to help your SOC identify an app’s activities and the resources it has accessed. This includes pre-built queries to streamline the investigation, visibility into the data in the results view and the ability to include OAuth app data such as resource, app, user, and app activity details in custom detections. Learn more about the enhanced hunting experience for OAuth app activities.

## App governance February 2023 release

- **Enhanced alert investigation experience:** App governance now provides additional information admins need to investigate and remediate incidents and alerts. This enhancement includes more details under **What happened** and **Recommended actions** in the alert story on Microsoft 365 Defender alert pages. This information will be available for all app governance alerts, including alerts triggered by threat detection rules, predefined policies, and user-defined policies. [Learn more about the enhanced alert experience.](/defender-cloud-apps/app-governance-detect-remediate-detect-threats)
   
## App governance October 2022 release

- **Added insights and remediation for sensitive content**: App governance provides insights and automated remediation capabilities through predefined and custom policies for apps that access content with Microsoft Purview Information Protection labels. Enterprise admins now have visibility into the workloads that these apps access and whether they access sensitive data in these workloads. With predefined and custom policies, admins are alerted about apps that have attempted to access sensitive data. Moreover, app governance can automatically deactivate noncompliant apps.
- **Expanded coverage to include all non-Graph API apps** - App governance has expanded coverage to secure more apps in your tenant. In addition to OAuth apps that use Microsoft Graph API, app governance will now provide visibility and protection for all OAuth apps registered on Azure Active Directory. [Learn more about app governance coverage.](/defender-cloud-apps/app-governance-secure-apps-access-non-graph-api)

## App governance July 2022 release

- **Added more predefined policies**: App governance released five more out of the box policies to detect anomalous app behaviors. These policies are activated by default, but you can deactivate them if you choose to. [Learn more here](app-governance-predefined-policies.md)
- **New video library**: App governance created a new library of short videos on features in app governance, how to use them, and info on how to learn more. [Check it out here](https://youtube.com/playlist?list=PLyhj1WZ29G66k4F_OZeMkQymRGyqHwZVp)
- **Secure Score integration GA**: Microsoft Secure Score integration with the app governance (AppG) add-on to Microsoft Defender for Cloud Apps (MDA) has reached general availability. AppG customers will now receive recommendations in Secure Score, helping them secure their Microsoft 365 OAuth apps.
   Why is this integration important?
   Secure Score is a representation of an organization's security posture and an entry point to various opportunities to improve that posture. By following Secure Score recommendations, customers improve resilience against known and emerging threats.
   AppG is a security and policy management capability designed for OAuth-enabled apps that access Microsoft 365 data. With deep integration into workloads and threat detection capabilities, AppG is well-suited to significantly reduce large attack surfaces in enterprise app ecosystems. By following AppG-related recommendations and enabling proposed policy settings, enterprises can protect both apps and data from misuse and actual bad actor activity.

## App governance May 2022 release

- **Predefined policies GA**: App governance released a set of out of the box policies to detect anomalous app behaviors. These policies are activated by default, but you can deactivate them if you choose to. [Learn more here](app-governance-predefined-policies.md)
- **Teams workload GA**: App governance added insights, policy capabilities, and governance for the Teams workload. You can see data usage, permissions usage, and create policies on Teams permissions and usage.
- **App governance alerts unified in the M365D alerts and incidents queues**: The app governance alerts queue has been unified with the Microsoft 365 Defender alerts experience and are aggregated into incidents.



