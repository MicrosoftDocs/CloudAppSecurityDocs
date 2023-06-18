---
title: Protect your Okta environment
description: This article provides information about the benefits of connecting your Okta app to Defender for Cloud Apps using the API connector for visibility and control over use.
ms.date: 01/29/2023
ms.topic: article
---
# How Defender for Cloud Apps helps protect your Okta environment

[!INCLUDE [Banner for top of topics](includes/banner.md)]

As an identity and access management solution, Okta holds the keys to your organizations most business critical services. Okta manages the authentication and authorization processes for your users and customers. Any abuse of Okta by a malicious actor or any human error may expose your most critical assets and services to potential attacks.

Connecting Okta to Defender for Cloud Apps gives you improved insights into your Okta admin activities, managed users, and customer sign-ins and provides threat detection for anomalous behavior.

[!INCLUDE [security-posture-management-connector](includes/security-posture-management-connector.md)]


## Main threats

- Compromised accounts and insider threats

## How Defender for Cloud Apps helps to protect your environment

- [Detect cloud threats, compromised accounts, and malicious insiders](best-practices.md#detect-cloud-threats-compromised-accounts-malicious-insiders-and-ransomware)
- [Use the audit trail of activities for forensic investigations](best-practices.md#use-the-audit-trail-of-activities-for-forensic-investigations)

## Control Okta with built-in policies and policy templates

You can use the following built-in policy templates to detect and notify you about potential threats:

| Type | Name |
| ---- | ---- |
| Built-in anomaly detection policy | [Activity from anonymous IP addresses](anomaly-detection-policy.md#activity-from-anonymous-ip-addresses)<br />[Activity from infrequent country](anomaly-detection-policy.md#activity-from-infrequent-country)<br />[Activity from suspicious IP addresses](anomaly-detection-policy.md#activity-from-suspicious-ip-addresses)<br />[Impossible travel](anomaly-detection-policy.md#impossible-travel)<br />[Multiple failed login attempts](anomaly-detection-policy.md#multiple-failed-login-attempts)<br />[Ransomware detection](anomaly-detection-policy.md#ransomware-activity)<br />[Unusual administrative activities](anomaly-detection-policy.md#unusual-activities-by-user) |
| Activity policy template | Logon from a risky IP address |

For more information about creating policies, see [Create a policy](control-cloud-apps-with-policies.md#create-a-policy).

## Automate governance controls

Currently, there are no governance controls available for Okta. If you are interested in having governance actions for this connector, you can [send the Defender for Cloud Apps team feedback](support-and-ts.md#feedback) with details of the actions you want.

For more information about remediating threats from apps, see [Governing connected apps](governance-actions.md).

## Protect Okta in real time

Review our best practices for [securing and collaborating with external users](best-practices.md#secure-collaboration-with-external-users-by-enforcing-real-time-session-controls) and [blocking and protecting the download of sensitive data to unmanaged or risky devices](best-practices.md#block-and-protect-download-of-sensitive-data-to-unmanaged-or-risky-devices).

## Next steps

> [!div class="nextstepaction"]
> [How to connect Okta to Microsoft Defender for Cloud Apps](./connect-okta.md)
