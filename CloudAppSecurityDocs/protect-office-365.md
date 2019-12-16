---
# required metadata
title: How Cloud App Security helps protect your Office 365 environment
description: This article provides information about the benefits of connecting your Office 365 app to Cloud App Security using the API connector for visibility and control over use.
author: shsagir
ms.author: shsagir
ms.service: cloud-app-security
ms.topic: article
ms.date: 12/04/2019

# optional metadata
#ROBOTS: NOINDEX # Used to prevent showing on search pages
#services: na
#ms.subservice: na
ms.collection: M365-security-compliance
---

# How Cloud App Security helps protect your Office 365 environment

*Applies to: Microsoft Cloud App Security*

As a major productivity suite providing cloud file storage, collaboration, BI, and CRM tools, Office 365 enables your users to persist and share their assets (documents, reports, and other assets) across your organization in a streamlined and efficient way. Using Office 365 may expose your sensitive data not only internally, but also to external collaborators, or even worse make it publicly available via a shared link. Such incidents might occur due to malicious actor, or by an unaware employee. Office 365 also features a productivity boost by providing a large third-party app eco-system which introduces the risk of malicious apps or use of apps with excessive permissions.

Connecting Office 365 to Cloud App Security gives you improved insights into your users’ activities, provides threat detection using machine learning based anomaly detections and information protection detections (such as detecting external information sharing), enables automated remediation controls, and detects threats from enabled third-party apps in your organization.

Using the Office 365 connector provides protection for the following products:

- Office 365
- Dynamics 365 CRM
- Exchange
- OneDrive
- Power BI
- SharePoint
- Teams

## Main threats

- Compromised accounts and insider threats
- Data leakage
- Insufficient security awareness
- Malicious third-party apps
- Malware
- Phishing
- Ransomware
- Unmanaged bring your own device (BYOD)

## How Cloud App Security helps to protect your environment

- [Detect cloud threats, compromised accounts, and malicious insiders](best-practices.md#detect-cloud-threats-compromised-accounts-malicious-insiders-and-ransomware)
- [Discover, classify, label, and protect regulated and sensitive data stored in the cloud](best-practices.md#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)
- [Discover and manage OAuth apps that have access to your environment](manage-app-permissions.md)
- [Enforce DLP and compliance policies for data stored in the cloud](best-practices.md#enforce-dlp-and-compliance-policies-for-data-stored-in-the-cloud)
- [Limit exposure of shared data and enforce collaboration policies](best-practices.md#limit-exposure-of-shared-data-and-enforce-collaboration-policies)
- [Use the audit trail of activities for forensic investigations](best-practices.md#use-the-audit-trail-of-activities-for-forensic-investigations)

## Control Office 365 with built-in policies and policy templates

You can use the following built-in policy templates to detect and notify you about potential threats:

| Type | Name |
| ---- | ---- |
| Built-in anomaly detection policy | [Activity from anonymous IP addresses](anomaly-detection-policy.md#activity-from-anonymous-ip-addresses)<br />[Activity from infrequent country](anomaly-detection-policy.md#activity-from-infrequent-country)<br />[Activity from suspicious IP addresses](anomaly-detection-policy.md#activity-from-suspicious-ip-addresses)<br />[Impossible travel](anomaly-detection-policy.md#impossible-travel)<br />[Activity performed by terminated user](anomaly-detection-policy.md#activity-performed-by-terminated-user) (requires AAD as IdP)<br />[Malware detection](anomaly-detection-policy.md#malware-detection)<br />[Multiple failed login attempts](anomaly-detection-policy.md#multiple-failed-login-attempts)<br />[Ransomware detection](anomaly-detection-policy.md#ransomware-activity)<br />[Suspicious email deletion activity (Preview)](anomaly-detection-policy.md#suspicious-email-deletion-activity-preview)<br />[Suspicious inbox forwarding](anomaly-detection-policy.md#suspicious-inbox-forwarding)[Unusual file deletion activities](anomaly-detection-policy.md#unusual-activities-by-user)<br />[Unusual file share activities](anomaly-detection-policy.md#unusual-activities-by-user)<br />[Unusual multiple file download activities](anomaly-detection-policy.md#unusual-activities-by-user) |
| Activity policy template | Logon from a risky IP address<br />Mass download by a single user<br />Potential ransomware activity |
| File policy template | Detect a file shared with an unauthorized domain<br />Detect a file shared with personal email addresses<br />Detect files with PII/PCI/PHI |
| OAuth app anomaly detection policy | [Misleading OAuth app name](app-permission-policy.md#oauth-app-anomaly-detection-policies)<br />[Misleading publisher name for an OAuth app](app-permission-policy.md#oauth-app-anomaly-detection-policies) |

For more information about creating policies, see [Create a policy](control-cloud-apps-with-policies.md#create-a-policy).

## Automate governance controls

In addition to monitoring for potential threats, you can apply and automate the following Office 365 governance actions to remediate detected threats:

| Type | Action |
| ---- | ---- |
| Data governance | **OneDrive:**<br /> - Inherit parent folder permissions<br /> - Make file/folder private<br /> - Put file/folder in admin quarantine<br /> - Put file/folder in user quarantine<br /> - Trash file/folder<br /> - Remove a specific collaborator<br /> - Remove external collaborators on file/folder<br /> - Apply Azure Information Protection classification label<br /> - Remove Azure Information Protection classification label<br /> **SharePoint:**<br /> - Inherit parent folder permissions<br /> - Make file/folder private<br /> - Put file/folder in admin quarantine<br /> - Put file/folder in user quarantine<br /> - Put file/folder in user quarantine and add owner permissions<br /> - Trash file/folder<br /> - Remove external collaborators on file/folder<br /> - Remove a specific collaborator<br /> - Apply Azure Information Protection classification label<br /> - Remove Azure Information Protection classification label |
| User governance | - Notify user on alert (via Azure AD)<br /> - Require user to sign in again (via Azure AD)<br /> - Suspend user (via Azure AD) |
| OAuth app governance | - Revoke OAuth app permission |

For more information about remediating threats from apps, see [Governing connected apps](governance-actions.md).

## Protect Office 365 in real time

Review our best practices for [securing and collaborating with external users](best-practices.md#secure-collaboration-with-external-users-by-enforcing-real-time-session-controls) and [blocking and protecting the download of sensitive data to unmanaged or risky devices](best-practices.md#block-and-protect-download-of-sensitive-data-to-unmanaged-or-risky-devices).

## Next steps

> [!div class="nextstepaction"]
> [How to connect Office 365 to Microsoft Cloud App Security](connect-office-365-to-microsoft-cloud-app-security.md)
