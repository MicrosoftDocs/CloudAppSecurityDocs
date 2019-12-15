---
# required metadata
title: How Cloud App Security helps protect your G Suite environment
description: This article provides information about the benefits of connecting your G Suite app to Cloud App Security using the API connector for visibility and control over use.
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

# How Cloud App Security helps protect your G Suite environment

*Applies to: Microsoft Cloud App Security*

As a cloud file storage and collaboration tool, G Suite enables your users to persist and share their documents across your organization in a streamlined and efficient way. Using G Suite may expose your sensitive data not only internally, but also to external collaborators, or even worse make it publicly available via a shared link. Such incidents can be caused by malicious actors, or by unaware employees. G Suite also features a productivity boost by providing a large third-party app eco-system which introduces the risk of malicious apps or use of apps with excessive permissions.

Connecting G Suite to Cloud App Security gives you improved insights into your users’ activities, provide threat detection using machine learning based anomaly detections, information protection related detections such as detecting external information sharing and enabling automated remediation controls, and detecting threats from enabled third-party apps in your organization.

## Main threats

- Compromised accounts and insider threats
- Data leakage
- Insufficient security awareness
- Malicious third-party apps and Google add-ons
- Malware
- Ransomware
- Unmanaged bring your own device (BYOD)

## How Cloud App Security helps to protect your environment

- [Detect cloud threats, compromised accounts, and malicious insiders](best-practices.md#detect-cloud-threats-compromised-accounts-malicious-insiders-and-ransomware)
- [Discover, classify, label, and protect regulated and sensitive data stored in the cloud](best-practices.md#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)
- [Discover and manage OAuth apps that have access to your environment](manage-app-permissions.md)
- [Enforce DLP and compliance policies for data stored in the cloud](best-practices.md#enforce-dlp-and-compliance-policies-for-data-stored-in-the-cloud)
- [Limit exposure of shared data and enforce collaboration policies](best-practices.md#limit-exposure-of-shared-data-and-enforce-collaboration-policies)
- [Use the audit trail of activities for forensic investigations](best-practices.md#use-the-audit-trail-of-activities-for-forensic-investigations)

## Control G Suite with built-in policies and policy templates

You can use the following built-in policy templates to detect and notify you about potential threats:

| Type | Name |
| ---- | ---- |
| Built-in anomaly detection policy | [Activity from anonymous IP addresses](anomaly-detection-policy.md#activity-from-anonymous-ip-addresses)<br />[Activity from infrequent country](anomaly-detection-policy.md#activity-from-infrequent-country)<br />[Activity from suspicious IP addresses](anomaly-detection-policy.md#activity-from-suspicious-ip-addresses)<br />[Activity performed by terminated user](anomaly-detection-policy.md#activity-performed-by-terminated-user) (requires AAD as IdP)<br />[Impossible travel](anomaly-detection-policy.md#impossible-travel)<br />[Malware detection](anomaly-detection-policy.md#malware-detection)<br />[Multiple failed login attempts](anomaly-detection-policy.md#multiple-failed-login-attempts)<br />[Ransomware detection](anomaly-detection-policy.md#ransomware-activity)<br />[Unusual administrative activities](anomaly-detection-policy.md#unusual-activities-by-user)<br />[Unusual file deletion activities](anomaly-detection-policy.md#unusual-activities-by-user)<br />[Unusual file share activities](anomaly-detection-policy.md#unusual-activities-by-user)<br />[Unusual multiple file download activities](anomaly-detection-policy.md#unusual-activities-by-user) |
| Activity policy template | Logon from a risky IP address<br />Mass download by a single user<br />Potential ransomware activity |
| File policy template | Detect a file shared with an unauthorized domain<br />Detect a file shared with personal email addresses<br />Detect files with PII/PCI/PHI |

For more information about creating policies, see [Create a policy](control-cloud-apps-with-policies.md#create-a-policy).

## Automate governance controls

In addition to monitoring for potential threats, you can apply and automate the following G Suite governance actions to remediate detected threats:

- Apply Azure Information Protection classification label
- Grant read permission to domain
- Make a file / folder in Google Drive private
- Notify user on alert (via Azure AD)
- Reduce public access to file/folder
- Remove a collaborator from a file
- Remove Azure Information Protection classification label
- Remove external collaborators on file/folder
- Remove file editor’s ability to share
- Remove public access to file/folder
- Require user to reset password to Google
- Require user to sign in again (via Azure AD)
- Revoke OAuth app permission
- Send DLP violation digest to file owners
- Send DLP violation to last file editor
- Suspend user
- Suspend user (via Azure AD)
- Transfer file ownership
- Trash file

For more information about remediating threats from apps, see [Governing connected apps](governance-actions.md).

## Protect G Suite in real time

Review our best practices for [securing and collaborating with external users](best-practices.md#secure-collaboration-with-external-users-by-enforcing-real-time-session-controls) and [blocking and protecting the download of sensitive data to unmanaged or risky devices](best-practices.md#block-and-protect-download-of-sensitive-data-to-unmanaged-or-risky-devices).

## Next steps

> [!div class="nextstepaction"]
> [How to connect G Suite to Microsoft Cloud App Security](connect-google-apps-to-microsoft-cloud-app-security.md)
