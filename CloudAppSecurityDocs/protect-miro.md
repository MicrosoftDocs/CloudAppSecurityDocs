---
# Required metadata
		# For more information, see https://review.learn.microsoft.com/en-us/help/platform/learn-editor-add-metadata?branch=main
		# For valid values of ms.service, ms.prod, and ms.topic, see https://review.learn.microsoft.com/en-us/help/platform/metadata-taxonomies?branch=main

		title:       # Add a title for the browser tab
description: # Add a meaningful description for search results
author:      NagarajVenkatesh # GitHub alias
ms.author:   naven # Microsoft alias
ms.service:  # Add the ms.service or ms.prod value
# ms.prod:   # To use ms.prod, uncomment it and delete ms.service
ms.topic:    # Add the ms.topic value
ms.date:     07/17/2023
---

# How Defender for Cloud Apps helps protect your Miro environment (Preview)

[!INCLUDE [Banner for top of topics](includes/banner.md)]

Miro is an online workspace that enables distributed, cross-functional teams organize and collaborate on projects. Miro holds critical data of your organization, and this makes it a target for malicious actors. 

Connecting Miro to Defender for Cloud Apps gives you improved insights into your users' activities and provides threat detection using machine learning based anomaly detections.

## Main threats

- Compromised accounts and insider threats
- Data leakage
- Insufficient security awareness
- Unmanaged bring your own device (BYOD)

## How Defender for Cloud Apps helps to protect your environment

- [Detect cloud threats, compromised accounts, and malicious insiders](best-practices.md#detect-cloud-threats-compromised-accounts-malicious-insiders-and-ransomware)
- [Use the audit trail of activities for forensic investigations](best-practices.md#use-the-audit-trail-of-activities-for-forensic-investigations)

## Control Miro with policies

| **Type**                           | **Name**                                                     |
| ---------------------------------- | ------------------------------------------------------------ |
| Built-in  anomaly detection policy | [Activity from   anonymous IP addresses](anomaly-detection-policy.md#activity-from-anonymous-ip-addresses)  <br /> [Activity from   infrequent country](anomaly-detection-policy.md#activity-from-infrequent-country) <br /> [Activity from   suspicious IP addresses](anomaly-detection-policy.md#activity-from-suspicious-ip-addresses)  <br /> [Impossible travel](anomaly-detection-policy.md#impossible-travel)  <br /> [Activity   performed by terminated user](anomaly-detection-policy.md#activity-performed-by-terminated-user) (requires Azure Active Directory as IdP)   <br />[Multiple failed   login attempts](anomaly-detection-policy.md#multiple-failed-login-attempts)  <br /> [Unusual   administrative activities](anomaly-detection-policy.md#unusual-activities-by-user)<br />   [Unusual impersonated activities](anomaly-detection-policy.md#unusual-activities-by-user) |
| Activity  policy                   | Built a customized policy by using the [Miro Audit Log](https://help.miro.com/hc/en-us/articles/360017571434-Audit-logs) activities |

For more information about creating policies, see [Create a policy](control-cloud-apps-with-policies.md#create-a-policy).

## Automate governance controls

In addition to monitoring for potential threats, you can apply and automate the following Miro governance actions to remediate detected threats:

| **Type**        | **Action**                                                   |
| --------------- | ------------------------------------------------------------ |
| User governance | Notify user on  alert (via Azure AD)<br />  Require user to sign in again (via Azure AD)   <br /> Suspend user (via Azure AD) |

For more information about remediating threats from apps, see [Governing connected apps](governance-actions.md).

Next steps

> [!div class="nextstepaction"]
> [Connect Miro to Microsoft Defender for Cloud Apps (Preview)](./connect-miro.md)
