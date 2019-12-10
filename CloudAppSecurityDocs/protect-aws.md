---
# required metadata
title: How Cloud App Security helps protect your AWS environment
description: This article provides information about the benefits of connecting your AWS app to Cloud App Security using the API connector for visibility and control over use.
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

# How Cloud App Security helps protect your AWS environment

*Applies to: Microsoft Cloud App Security*

Amazon Web Services (AWS) is a provider that enables your organization to host and manage their entire workloads in the cloud. Along with the benefits of leveraging infrastructure in the cloud (IaaS), your organization's most critical assets may be exposed to threats, including:

- Storage instances with potentially sensitive information
- Compute resources that operate some of your most critical applications
- Ports and virtual private networks that enable access to your organization

Connecting AWS to Cloud App Security helps you secure your assets by detecting potential threats by:

- Monitoring administrative and sign-in activities
- Detecting and notifying about:
  - Possible brute force attacks
  - Malicious use of a privileged user accounts
  - Unusual deletions of VMs and publicly exposed storage buckets

## Main threats

- Data leakage
- Resource misconfiguration and insufficient access control
- Compromised accounts and insider threats
- Abuse of cloud resources

## How Cloud App Security helps to protect your environment

- [Detect cloud threats, compromised accounts, and malicious insiders](best-practices.md#detect-cloud-threats-compromised-accounts-malicious-insiders-and-ransomware)
- [Use the audit trail of activities for forensic investigations](best-practices.md#use-the-audit-trail-of-activities-for-forensic-investigations)
- [Stay up to date with latest security configuration recommendation](security-config-aws.md)
- [Limit exposure of shared data and enforce collaboration policies](best-practices.md#limit-exposure-of-shared-data-and-enforce-collaboration-policies)

## Monitor and detect suspicious activities

You can use the following built-in policy templates to detect and notify you about potential threats:

- Alert on virtual private network changes
- Alert on IAM policy changes
- Alert on admin console sign-in failures
- Alert on CloudTrail configuration changes
- Alert on EC2 instance configuration changes
- Alert on any S3 configuration changes
- Alert on Network gateway changes
- Alert on Network access control list (ACL) changes
- Alert on security group configuration changes
- Alert when an S3 bucket in AWS is publicly accessible

For more information about creating policies, see [Create a policy](control-cloud-apps-with-policies.md#create-a-policy).

## Automate governance controls

In addition to monitoring for potential threats, you can apply and automate the following AWS governance actions to remediate detected threats:

- Make an S3 bucket private
- Remove a collaborator for an S3 bucket
- Notify user on alert (via Azure AD)
- Suspend user (via Azure AD)
- Require user to sign in again (via Azure AD)

For more information about remediating threats from apps, see [Governing connected apps](governance-actions.md).

## Protect AWS in real time

Review our [best practices](best-practices.md#block-and-protect-download-of-sensitive-data-to-unmanaged-or-risky-devices) for blocking and protecting the download of sensitive data to unmanaged or risky devices.

## Next steps

> [!div class="nextstepaction"]
> [How to connect AWS to Microsoft Cloud App Security](connect-aws-to-microsoft-cloud-app-security.md)
