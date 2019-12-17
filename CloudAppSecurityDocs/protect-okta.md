---
# required metadata
title: How Cloud App Security helps protect your Okta environment
description: This article provides information about the benefits of connecting your Okta app to Cloud App Security using the API connector for visibility and control over use.
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

# How Cloud App Security helps protect your Okta environment

*Applies to: Microsoft Cloud App Security*

As an identity and access management solution, Okta holds the keys to your organizations most business critical services. Okta manages the authentication and authorization processes for your users and customers. Any abuse of Okta by a malicious actor or any human error may expose your most critical assets and services to potential attacks.

Connecting Okta to Cloud App Security gives you improved insights into your Okta admin activities, managed users, and customer sigh ins and provides threat detection for anomalous behavior.

## Main threats

- Compromised accounts and insider threats

## How Cloud App Security helps to protect your environment

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

Currently, there are no governance controls available for Okta. If you are interested in having governance actions for this connector, you can [send the Cloud App Security team feedback](support-and-ts.md#feedback) with details of the actions you want.

For more information about remediating threats from apps, see [Governing connected apps](governance-actions.md).

## Protect Okta in real time

Review our best practices for [securing and collaborating with external users](best-practices.md#secure-collaboration-with-external-users-by-enforcing-real-time-session-controls) and [blocking and protecting the download of sensitive data to unmanaged or risky devices](best-practices.md#block-and-protect-download-of-sensitive-data-to-unmanaged-or-risky-devices).

## Next steps

> [!div class="nextstepaction"]
> [How to connect Okta to Microsoft Cloud App Security](connect-okta-to-microsoft-cloud-app-security.md)
