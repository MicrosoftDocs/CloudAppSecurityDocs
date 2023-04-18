---
title: Protect your Smartsheet
description: This article provides information about the benefits of connecting your Smartsheet app to Defender for Cloud Apps using the API connector for visibility and control over use.
ms.date: 04/17/2023
ms.topic: article
---
# How Defender for Cloud Apps helps protect your Smartsheet

[!INCLUDE [Banner for top of topics](includes/banner.md)]

As a productivity and collaboration cloud solution, Smartsheet holds sensitive information to your organization. Any abuse of Smartsheet by a malicious actor or any human error may expose your most critical assets and services to potential attacks.

Connecting Smartsheet to Defender for Cloud Apps gives you improved insights into your Smartsheet activities and provides threat detection for anomalous behavior.

## Main threats

- Compromised accounts and insider threats

- Data leakage

- Insufficient security awareness

- Unmanaged bring your own device (BYOD)

## How Defender for Cloud Apps helps to protect your environment

- [Detect cloud threats, compromised accounts, and malicious insiders](best-practices.md#detect-cloud-threats-compromised-accounts-malicious-insiders-and-ransomware)

- [Use the audit trail of activities for forensic investigations](best-practices.md#use-the-audit-trail-of-activities-for-forensic-investigations)

## Control Smartsheet with policies

| **Type**                           | **Name**                                                     |
| ---------------------------------- | ------------------------------------------------------------ |
| Built-in  anomaly detection policy | [Unusual file share activities](anomaly-detection-policy.md#unusual-activities-by-user)  <br /> [Unusual file deletion activities](anomaly-detection-policy.md#unusual-activities-by-user) <br /> [Unusual   administrative activities](anomaly-detection-policy.md#unusual-activities-by-user)  <br /> [Unusual multiple file download activities](anomaly-detection-policy.md#unusual-activities-by-user)  |
| Activity  policy                   | Build a customized policy by the Smartsheet [Audit Log](https://smartsheet.redoc.ly/tag/eventsObjects) activities |

>[!NOTE]
>
>- Login/Logouts activities are not supported by Smartsheet.
>- Smartsheet activities does not contain IP addresses.

For more information about creating policies, see [Create a policy](control-cloud-apps-with-policies.md#create-a-policy).

## Automate governance controls

In addition to monitoring for potential threats, you can apply and automate the following Smartsheet governance actions to remediate detected threats:

| **Type**        | **Action**                                                   |
| --------------- | ------------------------------------------------------------ |
| User governance | Notify user on  alert (via Azure AD)<br />  Require user to sign in again (via Azure AD)   <br /> Suspend user (via Azure AD) |

For more information about remediating threats from apps, see [Governing connected apps](governance-actions.md).

## Protect Smartsheet in real time

Review our best practices for [securing and collaborating with external users](best-practices.md#secure-collaboration-with-external-users-by-enforcing-real-time-session-controls) and [blocking and protecting the download of sensitive data to unmanaged or risky devices](best-practices.md#block-and-protect-download-of-sensitive-data-to-unmanaged-or-risky-devices).

## Next steps

> [!div class="nextstepaction"]
> [Connect Smartsheet to Microsoft Defender for Cloud Apps](./connect-smartsheet.md)
