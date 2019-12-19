---
# required metadata
title: How Cloud App Security helps protect your Cisco Webex environment
description: This article provides information about the benefits of connecting your Cisco Webex app to Cloud App Security using the API connector for visibility and control over use.
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

# How Cloud App Security helps protect your Cisco Webex environment

*Applies to: Microsoft Cloud App Security*

As a communication and collaboration platform, Cisco Webex enables streamlined communication and collaboration across your organization. Using Cisco Webex for your data and assets exchange may expose your sensitive organizational information to external users, for example, in chat rooms where they may also be participating in a conversation with your employees.

Connecting Cisco Webex to Cloud App Security gives you improved insights into your users’ activities, provides information protection detections, and enables automated governance controls.

## Main threats

- Compromised accounts and insider threats
- Data leakage
- Insufficient security awareness
- Ransomware
- Unmanaged bring your own device (BYOD)

## How Cloud App Security helps to protect your environment

- [Enforce DLP and compliance policies for data stored in the cloud](best-practices.md#enforce-dlp-and-compliance-policies-for-data-stored-in-the-cloud)
- [Limit exposure of shared data and enforce collaboration policies](best-practices.md#limit-exposure-of-shared-data-and-enforce-collaboration-policies)
- [Use the audit trail of activities for forensic investigations](best-practices.md#use-the-audit-trail-of-activities-for-forensic-investigations)

## Control Cisco Webex with built-in policies and policy templates

You can use the following built-in policy templates to detect and notify you about potential threats:

| Type | Name |
| ---- | ---- |
| Built-in anomaly detection policy | [Activity performed by terminated user](anomaly-detection-policy.md#activity-performed-by-terminated-user) (requires AAD as IdP)<br />[Multiple failed login attempts](anomaly-detection-policy.md#multiple-failed-login-attempts)<br />[Ransomware detection](anomaly-detection-policy.md#ransomware-activity)<br />[Unusual file deletion activities](anomaly-detection-policy.md#unusual-activities-by-user)<br />[Unusual file share activities](anomaly-detection-policy.md#unusual-activities-by-user)<br />[Unusual multiple file download activities](anomaly-detection-policy.md#unusual-activities-by-user) |
| File policy template | Detect a file shared with an unauthorized domain<br />Detect a file shared with personal email addresses<br />Detect files with PII/PCI/PHI |
| Activity policy template | Mass download by a single user<br />Potential ransomware activity |

For more information about creating policies, see [Create a policy](control-cloud-apps-with-policies.md#create-a-policy).

## Automate governance controls

In addition to monitoring for potential threats, you can apply and automate the following Cisco Webex governance actions to remediate detected threats:

| Type | Action |
| ---- | ---- |
| User governance | - Notify user on alert (via Azure AD)<br />- Require user to sign in again (via Azure AD)<br />- Suspend user (via Azure AD) |
| Data governance | - Trash file |

For more information about remediating threats from apps, see [Governing connected apps](governance-actions.md).

## Protect Cisco Webex in real time

Review our best practices for [securing and collaborating with external users](best-practices.md#secure-collaboration-with-external-users-by-enforcing-real-time-session-controls) and [blocking and protecting the download of sensitive data to unmanaged or risky devices](best-practices.md#block-and-protect-download-of-sensitive-data-to-unmanaged-or-risky-devices).

## Next steps

> [!div class="nextstepaction"]
> [How to connect Cisco Webex to Microsoft Cloud App Security](connect-webex-to-microsoft-cloud-app-security.md)
