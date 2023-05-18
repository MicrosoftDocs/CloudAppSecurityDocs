---
title: Protect your NetDocuments environment
description: This article provides information about the benefits of connecting your NetDocuments app to Defender for Cloud Apps using the API connector for visibility and control over use.
ms.date: 01/29/2023
ms.topic: article
---
# How Defender for Cloud Apps helps protect your NetDocuments environment

[!INCLUDE [Banner for top of topics](includes/banner.md)]

As a productivity and collaboration cloud solution, NetDocuments holds sensitive information to your organization. Any abuse of NetDocuments by a malicious actor or any human error may expose your most critical assets and services to potential attacks.

Connecting NetDocuments to Defender for Cloud Apps gives you improved insights into your NetDocuments activities and provides threat detection for anomalous behavior.

## Main threats

- Compromised accounts and insider threats

- Data leakage

- Insufficient security awareness

- Unmanaged bring your own device (BYOD)

## How Defender for Cloud Apps helps to protect your environment

- [Detect cloud threats, compromised accounts, and malicious insiders](best-practices.md#detect-cloud-threats-compromised-accounts-malicious-insiders-and-ransomware)

- [Use the audit trail of activities for forensic investigations](best-practices.md#use-the-audit-trail-of-activities-for-forensic-investigations)

## Control NetDocuments with policies

| **Type**                           | **Name**                                                     |
| ---------------------------------- | ------------------------------------------------------------ |
| Built-in  anomaly detection policy | [Activity from   anonymous IP addresses](anomaly-detection-policy.md#activity-from-anonymous-ip-addresses)  <br /> [Activity from   infrequent country](anomaly-detection-policy.md#activity-from-infrequent-country) <br /> [Activity from   suspicious IP addresses](anomaly-detection-policy.md#activity-from-suspicious-ip-addresses)  <br /> [Impossible travel](anomaly-detection-policy.md#impossible-travel)  <br /> [Activity   performed by terminated user](anomaly-detection-policy.md#activity-performed-by-terminated-user) (requires Azure Active Directory as IdP) <br /> [Unusual file share activities](anomaly-detection-policy.md#unusual-activities-by-user)  <br /> [Unusual file deletion activities](anomaly-detection-policy.md#unusual-activities-by-user) <br /> [Unusual   administrative activities](anomaly-detection-policy.md#unusual-activities-by-user)  <br /> [Unusual multiple file download activities](anomaly-detection-policy.md#unusual-activities-by-user)  |
| Activity  policy                   | Built a customized policy by the NetDocuments [Audit Log](https://support.netdocuments.com/hc/en-us/articles/205220260-Consolidated-Activity-Log) activities |

>[!NOTE]
>Login/Logouts activities are not supported by NetDocuments.

For more information about creating policies, see [Create a policy](control-cloud-apps-with-policies.md#create-a-policy).

## Automate governance controls

In addition to monitoring for potential threats, you can apply and automate the following NetDocuments governance actions to remediate detected threats:

| **Type**        | **Action**                                                   |
| --------------- | ------------------------------------------------------------ |
| User governance | Notify user on  alert (via Azure AD)<br />  Require user to sign in again (via Azure AD)   <br /> Suspend user (via Azure AD) |

For more information about remediating threats from apps, see [Governing connected apps](governance-actions.md).

## Protect NetDocuments in real time

Review our best practices for [securing and collaborating with external users](best-practices.md#secure-collaboration-with-external-users-by-enforcing-real-time-session-controls) and [blocking and protecting the download of sensitive data to unmanaged or risky devices](best-practices.md#block-and-protect-download-of-sensitive-data-to-unmanaged-or-risky-devices).

## Next steps

> [!div class="nextstepaction"]
> [Connect NetDocuments to Microsoft Defender for Cloud Apps](connect-netdocuments-to-microsoft-defender-for-cloud-apps.md)
