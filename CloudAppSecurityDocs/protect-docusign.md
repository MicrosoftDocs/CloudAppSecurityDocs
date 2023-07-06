---
title: Protect your DocuSign environment
description: This article provides information about the benefits of connecting your DocuSign app to Defender for Cloud Apps using the API connector for visibility and control over use.
ms.date: 01/29/2023
ms.topic: article
---
# How Defender for Cloud Apps helps protect your DocuSign environment

[!INCLUDE [Banner for top of topics](includes/banner.md)]

DocuSign helps organizations manage electronic agreements, and so your DocuSign environment holds sensitive information for your organization. Any abuse of DocuSign by a malicious actor or any human error may expose your most critical assets to potential attacks.

Connecting your DocuSign environment to Defender for Cloud Apps gives you improved insights into your DocuSign admin activities and managed users sign-ins, and provides threat detection for anomalous behavior.

[!INCLUDE [security-posture-management-connector](includes/security-posture-management-connector.md)]


## Main threats

- Compromised accounts and insider threats
- Data leakage
- Insufficient security awareness
- Unmanaged bring your own device (BYOD)

## How Defender for Cloud Apps helps to protect your environment

- [Detect cloud threats, compromised accounts, and malicious insiders](best-practices.md#detect-cloud-threats-compromised-accounts-malicious-insiders-and-ransomware)

- [Use the audit trail of activities for forensic investigations](best-practices.md#use-the-audit-trail-of-activities-for-forensic-investigations)

## Control DocuSign with policies

| **Type**                           | **Name**                                                     |
| ---------------------------------- | ------------------------------------------------------------ |
| Built-in  anomaly detection policy | [Activity from anonymous IP addresses](anomaly-detection-policy.md#activity-from-anonymous-ip-addresses) <br> [Activity from infrequent countries/regions](anomaly-detection-policy.md#activity-from-infrequent-country) <br> [Activity from suspicious IP addresses](anomaly-detection-policy.md#activity-from-suspicious-ip-addresses) <br> [Impossible travel](anomaly-detection-policy.md#impossible-travel) <br> [Activity performed by terminated user](anomaly-detection-policy.md#activity-performed-by-terminated-user) (requires Azure Active Directory as IdP) <br> [Multiple failed login attempts](anomaly-detection-policy.md#multiple-failed-login-attempts) <br> [Unusual administrative activities](anomaly-detection-policy.md#unusual-activities-by-user) <br> [Unusual impersonated activities](anomaly-detection-policy.md#unusual-activities-by-user) |
| Activity  policy                   | Build a customized policy by the DocuSign audit log           |

For more information about creating policies, see [Create a policy](control-cloud-apps-with-policies.md#create-a-policy).

## Automate governance controls

In addition to monitoring for potential threats, you can apply and automate the following DocuSign governance actions to remediate detected threats:

| **Type**        | **Action**                                                   |
| --------------- | ------------------------------------------------------------ |
| User governance | Notify user on  alert (via Azure AD)<br />  Require user to sign in again (via Azure AD)   <br /> Suspend user (via Azure AD) |

For more information about remediating threats from apps, see [Governing connected apps](governance-actions.md).

## Protect DocuSign in real time

Review our best practices for [securing and collaborating with external users](best-practices.md#secure-collaboration-with-external-users-by-enforcing-real-time-session-controls) and [blocking and protecting the download of sensitive data to unmanaged or risky devices](best-practices.md#block-and-protect-download-of-sensitive-data-to-unmanaged-or-risky-devices).

## Next steps

> [!div class="nextstepaction"]
> [Connect DocuSign to Microsoft Defender for Cloud Apps](./connect-docusign.md)
