---
title: Protect your Salesforce environment
description: This article provides information about the benefits of connecting your Salesforce app to Defender for Cloud Apps using the API connector for visibility and control over use.
ms.date: 03/06/2023
ms.topic: article
---

# How Defender for Cloud Apps helps protect your Salesforce environment

[!INCLUDE [Banner for top of topics](includes/banner.md)]

As a major CRM cloud provider, Salesforce incorporates large amounts of sensitive information about customers, pricing playbooks, and major deals inside your organization. Being a business-critical app, Salesforce is accessed and used by people inside your organization and by others outside of it (such as partners and contractors) for various purposes. In many cases, a large proportion of your users accessing Salesforce have low awareness of security and might put your sensitive information at risk by unintentionally sharing it. In other instances, malicious actors may gain access to your most sensitive customer-related assets.

Connecting Salesforce to Defender for Cloud Apps gives you improved insights into your users' activities, provides threat detection using machine learning based anomaly detections and information protection detections (such as detecting external information sharing), enables automated remediation controls, and detects threats from enabled third-party apps in your organization.

[!INCLUDE [security-posture-management-connector](includes/security-posture-management-connector.md)]

## Main threats

- Compromised accounts and insider threats
- Data leakage
- Elevated privileges
- Insufficient security awareness
- Malicious third-party apps and Google add-ons
- Ransomware
- Unmanaged bring your own device (BYOD)

## How Defender for Cloud Apps helps to protect your environment

- [Detect cloud threats, compromised accounts, and malicious insiders](best-practices.md#detect-cloud-threats-compromised-accounts-malicious-insiders-and-ransomware)
- [Discover, classify, label, and protect regulated and sensitive data stored in the cloud](best-practices.md#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)
- [Discover and manage OAuth apps that have access to your environment](manage-app-permissions.md)
- [Enforce DLP and compliance policies for data stored in the cloud](best-practices.md#enforce-dlp-and-compliance-policies-for-data-stored-in-the-cloud)
- [Limit exposure of shared data and enforce collaboration policies](best-practices.md#limit-exposure-of-shared-data-and-enforce-collaboration-policies)
- [Use the audit trail of activities for forensic investigations](best-practices.md#use-the-audit-trail-of-activities-for-forensic-investigations)

## Control Salesforce with built-in policies and policy templates

You can use the following built-in policy templates to detect and notify you about potential threats:

| Type | Name |
| ---- | ---- |
| Built-in anomaly detection policy | [Activity from anonymous IP addresses](anomaly-detection-policy.md#activity-from-anonymous-ip-addresses)<br />[Activity from infrequent country](anomaly-detection-policy.md#activity-from-infrequent-country)<br />[Activity from suspicious IP addresses](anomaly-detection-policy.md#activity-from-suspicious-ip-addresses)<br />[Impossible travel](anomaly-detection-policy.md#impossible-travel)<br />[Activity performed by terminated user](anomaly-detection-policy.md#activity-performed-by-terminated-user) (requires Azure Active Directory as IdP)<br />[Multiple failed login attempts](anomaly-detection-policy.md#multiple-failed-login-attempts)<br />[Unusual administrative activities](anomaly-detection-policy.md#unusual-activities-by-user)<br />[Unusual file deletion activities](anomaly-detection-policy.md#unusual-activities-by-user)<br />[Unusual file share activities](anomaly-detection-policy.md#unusual-activities-by-user)<br />[Unusual impersonated activities](anomaly-detection-policy.md#unusual-activities-by-user)<br />[Unusual multiple file download activities](anomaly-detection-policy.md#unusual-activities-by-user) |
| Activity policy template | Logon from a risky IP address<br />Mass download by a single user|
| File policy template | Detect a file shared with an unauthorized domain<br />Detect a file shared with personal email addresses<br />Detect files with PII/PCI/PHI |

For more information about creating policies, see [Create a policy](control-cloud-apps-with-policies.md#create-a-policy).

## Automate governance controls

In addition to monitoring for potential threats, you can apply and automate the following Salesforce governance actions to remediate detected threats:

| Type | Action |
| ---- | ---- |
| User governance | - Notify users of pending alerts<br />- Send DLP violation digest to file owners<br />- Suspend user<br />- Notify user on alert (via Azure AD)<br />- Require user to sign in again (via Azure AD)<br />- Suspend user (via Azure AD) |
| OAuth app governance | - Revoke OAuth app for users |

For more information about remediating threats from apps, see [Governing connected apps](governance-actions.md).

## Protect Salesforce in real time

Review our best practices for [securing and collaborating with external users](best-practices.md#secure-collaboration-with-external-users-by-enforcing-real-time-session-controls) and [blocking and protecting the download of sensitive data to unmanaged or risky devices](best-practices.md#block-and-protect-download-of-sensitive-data-to-unmanaged-or-risky-devices).

## Next steps

> [!div class="nextstepaction"]
> [How to connect Salesforce to Microsoft Defender for Cloud Apps](./connect-salesforce.md)


