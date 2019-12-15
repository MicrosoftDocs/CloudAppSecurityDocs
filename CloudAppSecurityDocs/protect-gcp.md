---
# required metadata
title: How Cloud App Security helps protect your Google Cloud Platform environment
description: This article provides information about the benefits of connecting your Google Cloud Platform app to Cloud App Security using the API connector for visibility and control over use.
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

# How Cloud App Security helps protect your Google Cloud Platform (GCP) environment

*Applies to: Microsoft Cloud App Security*

Google Cloud Platform is an IaaS provider that enables your organization to host and manage their entire workloads in the cloud. Along with the benefits of leveraging infrastructure in the cloud, your organization's most critical assets may be exposed to threats. Exposed assets include storage instances with potentially sensitive information, compute resources that operate some of your most critical applications, ports, and virtual private networks that enable access to your organization.

Connecting GCP to Cloud App Security helps you secure your assets and detect potential threats by monitoring administrative and sign-in activities, notifying on possible brute force attacks, malicious use of a privileged user account, and unusual deletions of VMs.

## Main threats

- Abuse of cloud resources
- Compromised accounts and insider threats
- Data leakage
- Resource misconfiguration and insufficient access control

## How Cloud App Security helps to protect your environment

- [Detect cloud threats, compromised accounts, and malicious insiders](best-practices.md#detect-cloud-threats-compromised-accounts-malicious-insiders-and-ransomware)
- [Use the audit trail of activities for forensic investigations](best-practices.md#use-the-audit-trail-of-activities-for-forensic-investigations)

## Control GCP with built-in policies and policy templates

You can use the following built-in policy templates to detect and notify you about potential threats:

| Type | Name |
| ---- | ---- |
| Built-in anomaly detection policy | [Activity from anonymous IP addresses](anomaly-detection-policy.md#activity-from-anonymous-ip-addresses)<br />[Activity from infrequent country](anomaly-detection-policy.md#activity-from-infrequent-country)<br />[Activity from suspicious IP addresses](anomaly-detection-policy.md#activity-from-suspicious-ip-addresses)<br />[Activity performed by terminated user](anomaly-detection-policy.md#activity-performed-by-terminated-user) (requires AAD as IdP)<br />[Impossible travel](anomaly-detection-policy.md#impossible-travel)<br />[Multiple failed login attempts](anomaly-detection-policy.md#multiple-failed-login-attempts)<br />[Multiple delete VM activities](anomaly-detection-policy.md#multiple-delete-vm-activities)<br />[Unusual administrative activities](anomaly-detection-policy.md#unusual-activities-by-user)<br />[Unusual multiple VM creation activities](anomaly-detection-policy.md#unusual-activities-by-user) (preview) |
| Activity policy template | Changes to compute engine resources<br />Changes to StackDriver configuration<br />Changes to storage resources<br />Changes to Virtual Private Network<br />Logon from a risky IP address |

For more information about creating policies, see [Create a policy](control-cloud-apps-with-policies.md#create-a-policy).

## Automate governance controls

In addition to monitoring for potential threats, you can apply and automate the following GCP governance actions to remediate detected threats:

- Notify user on alert (via Azure AD)
- Require user to reset password to Google (requires connected linked G Suite instance)
- Require user to sign in again (via Azure AD)
- Suspend user (via Azure AD)
- Suspend user (requires connected linked G Suite instance)

For more information about remediating threats from apps, see [Governing connected apps](governance-actions.md).

## Protect GCP in real time

Review our best practices for [securing and collaborating with external users](best-practices.md#secure-collaboration-with-external-users-by-enforcing-real-time-session-controls) and [blocking and protecting the download of sensitive data to unmanaged or risky devices](best-practices.md#block-and-protect-download-of-sensitive-data-to-unmanaged-or-risky-devices).

## Next steps

> [!div class="nextstepaction"]
> [How to connect GCP to Microsoft Cloud App Security](connect-google-gcp-to-microsoft-cloud-app-security.md)
