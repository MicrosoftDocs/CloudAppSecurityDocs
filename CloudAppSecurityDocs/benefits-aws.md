---
# required metadata
title: Benefits of connecting Amazon Web Services to Microsoft Cloud App Security
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

# Benefits of connecting AWS to Microsoft Cloud App Security

*Applies to: Microsoft Cloud App Security*

Connecting Amazon Web Services (AWS) to Cloud App Security helps you improve your threat detection capabilities. By monitoring administrative and sign-in activities, you can detect and be notified about possible brute force attack, malicious use of a privileged user account, and other threats in your environment. For example, you can identify risks such as unusual deletions of VMs, or impersonation activities in these apps.

## How Cloud App Security help protect your AWS environment

Cloud App Security helps protect your environment by monitoring AWS activities and alerting you when suspicious use is detected. The following is a list of common use cases for protecting your environment:

* Detect cloud threats, compromised accounts and malicious insiders

  * [Best practice](best-practices.md#detect-cloud-threats-compromised-accounts-malicious-insiders-and-ransomware)

  * Built-in policy templates

    * Alert on virtual private network changes
    * Alert on IAM policy changes
    * Alert on admin console sign in failures
    * Alert on CloudTrail configuration changes
    * Alert on EC2 instance configuration changes
    * Alert on any S3 configuration changes
    * Alert on Network gateway changes
    * Alert on Network access control list (ACL) changes
    * Alert on security group configuration changes

* Use Audit trail of activities for forensic investigations

  * [Best practice](best-practices.md#use-the-audit-trail-of-activities-for-forensic-investigations)

* Stay up to date with latest security configuration recommendation

  * AWS gives you the ability to gain visibility into your security configurations recommendations on how to improve your cloud security. With these recommendations, you can monitor the compliance status of your AWS accounts. Learn about [Security configuration for AWS](security-config-aws.md).

* Limit exposure of shared data and enforce collaboration policies

  * Built-in policy templates

    * Publicly accessible S3 buckets - Alert when an S3 bucket in AWS is publicly accessible

## Automated governance controls available for AWS

In addition to monitoring, you can apply for following governance actions to remediate threats:

* Make an S3 bucket private

* Remove a collaborator for an S3 bucket

* Notify user on alert (via Azure AD)

* Suspend user (via Azure AD)

* Require user to sign in again (via Azure AD)

## Protecting AWS in real time

* Secure collaboration with external users by enforcing real-time session controls

  * [Best practice](best-practices.md#secure-collaboration-with-external-users-by-enforcing-real-time-session-controls)

## Next steps

> [!div class="nextstepaction"]
> [How to connect AWS to Microsoft Cloud App Security](connect-aws-to-microsoft-cloud-app-security.md)
