---
# required metadata
title: Best practices for protecting your organization - Cloud App Security
description: This article provides a set of best practices for protecting your organization.
author: ShlomoSagir-MS
ms.author: shsagir
ms.service: cloud-app-security
ms.topic: conceptual
ms.date: 9/8/2019

# optional metadata
#ROBOTS: NOINDEX # Used to prevent showing on search pages
#services: na
#ms.subservice: na
ms.collection: M365-security-compliance
---

# Cloud App Security best practices

*Applies to: Microsoft Cloud App Security*

This article provides best practices for protecting your organization by using Microsoft Cloud App Security. These best practices come from our experience with Cloud App Security and the experiences of customers like you.

The best practices discussed in this article include:

> [!div class="checklist"]
> * Discover and assess cloud apps
> * Apply cloud governance policies
> * Limit exposure of shared data and enforce collaboration policies
> * Discover, classify, label, and protect regulated and sensitive data stored in the cloud
> * Enforce DLP and compliance policies for data stored in the cloud
> * Block and protect download of sensitive data to unmanaged or risky devices
> * Secure collaboration with external users by enforcing real-time session controls
> * Detect cloud threats, compromised accounts, malicious insiders, and ransomware

## Discover and assess cloud apps

Integrating Cloud App Security with Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP) gives you the ability to use Cloud Discovery beyond your corporate network or secure web gateways. With the combined user and machine information, you can identify risky users or machines, see what apps they are using, and investigate further in the Microsoft Defender ATP portal.

**Best practice**: Enable Shadow IT Discovery using Microsoft Defender ATP<br>
**Detail**: Cloud Discovery analyzes traffic logs collected by Microsoft Defender ATP and assesses identified apps against the cloud app catalog to provide compliance and security information. By configuring Cloud Discovery, you gain visibility into cloud use, Shadow IT, and continuous monitoring of the unsanctioned apps being used by your users.<br>
**For more information**:

* [Microsoft Defender ATP integration with Cloud App Security](wdatp-integration.md)
* [Set up Cloud Discovery](set-up-cloud-discovery.md)
* [Discover and manage shadow IT in your network](tutorial-shadow-it.md)

**Best practice**: Configure App Discovery policies to proactively identify risky, non-complaint, and trending apps<br>
**Details**: App discovery policies make it easier to track of the significant discovered applications in your organization to help you manage these applications efficiently. Create Cloud Discovery policies to receive alerts when discovering newly discovered apps that are identified as either risky, non-compliant, trending, or high-volume.<br>
**For more information**:

* [Cloud Discovery policies](cloud-discovery-policies.md)
* [Cloud Discovery anomaly detection policy](cloud-discovery-anomaly-detection-policy.md)
* [Get instantaneous behavioral analytics and anomaly detection](anomaly-detection-policy.md)

**Best practice**: Manage OAuth apps that are authorized by your users<br>
**Detail**: Many users casually grant OAuth permissions to third-party apps to access their account information and, in so doing, inadvertently also give access to their data in other cloud apps. Usually, IT has no visibility into these apps in order to weigh the security risk of an app against the productivity benefit that it provides.

Cloud App Security provides you with the ability to investigate and monitor the app permissions your users granted. You can use this information to identify a potentially suspicious app and, if you determine that it is risky, you can be ban access to it.<br>
**For more information**:

* [Manage OAuth apps](manage-app-permissions.md)
* [OAuth app policies](app-permission-policy.md)

## Apply cloud governance policies

**Best practice**: Tag apps and export block scripts<br>
**Detail**: After you've reviewed the list of discovered apps in your organization, you can secure your environment against unwanted app use. You can apply the **Sanctioned** tag to apps that are approved by your organization and the **Unsanctioned** tag to apps that are not. You can monitor unsanctioned apps using discovery filters or export a script to block unsanctioned apps using your on-premises security appliances. Using tags and export scripts allows you to organize your apps and protect your environment by only allow safe apps to be accessed.<br>
**For more information**:

* [Govern discovered apps](governance-discovery.md)

## Limit exposure of shared data and enforce collaboration policies

**Best practice**: Connect Office 365<br>
**Detail**: Connecting Office 365 to Cloud App Security gives you immediate visibility into your users activities, files they are accessing, and provides governance actions for Office 365, SharePoint, OneDrive, Teams, PowerBI, Exchange and Dynamics.<br>
**For more information**:

* [Connect apps](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md)
* [Connect Office 365 to Microsoft Cloud App Security](connect-office-365-to-microsoft-cloud-app-security.md)

**Best practice**: Connect third-party apps<br>
**Detail**: Connecting third-party apps to Cloud App Security gives you improved insights into your users activities, threat detection, and governance capabilities. The following third-party app APIs are supported: [AWS](connect-aws-to-microsoft-cloud-app-security.md), [Box](connect-box-to-microsoft-cloud-app-security.md), [Dropbox](connect-dropbox-to-microsoft-cloud-app-security.md), [G Suite](connect-google-apps-to-microsoft-cloud-app-security.md), [Okta](connect-okta-to-microsoft-cloud-app-security.md), [Salesforce](connect-salesforce-to-microsoft-cloud-app-security.md), [ServiceNow](connect-servicenow-to-microsoft-cloud-app-security.md), [WebEx](connect-webex-to-microsoft-cloud-app-security.md), and [Workday](connect-workday-to-microsoft-cloud-app-security.md).<br>
**For more information**:

* [Connect apps](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md)

**Best practice**: Review your organization's data exposure<br>
**Detail**: Use the file exposure reports to gain visibility into how your users are sharing files with cloud apps. The following reports are available and can be exported to for further analysis in tools such as Microsoft Power BI:

* **Data sharing overview**: Lists files by access permissions stored in each of your cloud apps
* **Outbound sharing by domain**: Lists the domains with which corporate files are shared by your employees
* **Owners of shared files**: Lists users who are sharing corporate files with the outside world<br>
**For more information**:

* [Generate data management reports](built-in-reports.md)

**Best practice**: Create policies to remove sharing with personal accounts<br>
**Detail**: Connecting Office 365 to Cloud App Security gives you immediate visibility into your users activities, files they are accessing, and provides governance actions for Office 365, SharePoint, OneDrive, Teams, PowerBI, Exchange and Dynamics.<br>
**For more information**:

* [Governing connected apps](governance-actions.md)

## Discover, classify, label, and protect regulated and sensitive data stored in the cloud

**Best practice**: Integrate with Azure Information Protection<br>
**Detail**: Integrating with Azure Information Protection gives you the capability to automatically apply classification labels and optionally add encryption protection. Once the integration is turned on, you can apply labels as a governance action, view files by classification, investigate files by classification level, and create granular policies to make sure classified files are being handled properly. If you do not turn on the integration, you cannot benefit from the ability to automatically scan, label and encrypt files in the cloud.<br>
**For more information**:

* [Azure Information Protection integration](azip-integration.md)
* [Tutorial: Automatically apply Azure Information Protection classification labels](use-case-information-protection.md)

**Best practice**: Create data exposure policies<br>
**Detail**: Use file policies to detect information sharing and scan for confidential information in your cloud apps. Create the following file policies to alert you when data exposures are detected:

* Files shared externally containing sensitive data
* Files shared externally and labeled as **Confidential**
* Files shared with unauthorized domains
* Protect sensitive files on SaaS apps

**For more information**:

* [Content inspection](content-inspection.md)
* [File policies](data-protection-policies.md)
* [Information protection policies](policies-information-protection.md)

**Best practice**: Review reports in the **Files** page<br>
**Detail**: Once you’ve connected various SaaS apps using app connectors, Cloud App Security scans files stored by these apps. In addition, each time a file is modified it is scanned again. You can use the **Files** page to understand and investigate the types of data being stored in your cloud apps. To help you investigate, you can filter by domains, groups, users, creation date, extension, file name and type, file ID, classification label, and more. Using these filters puts you in control of how you choose to investigate files to make sure none of your data is at risk. Once you have a better understanding of how your data is being used, you can create policies to scan for sensitive content in these files.<br>
**For more information**:

* [Connect apps](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md)
* [File filters](file-filters.md)
* [Content inspection](content-inspection.md)

## Enforce DLP and compliance policies for data stored in the cloud

**Best practice**: Protect confidential data from being shared with external users<br>
**Detail**: Create a file policy that detects when a user tries to share a file with the **Confidential** classification label with someone external to your organization, and configure its governance action to remove external users. This policy ensures your confidential data doesn’t leave your organization and external users cannot gain access to it.<br>
**For more information**:

* [Governing connected apps](governance-actions.md)

## Block and protect download of sensitive data to unmanaged or risky devices

**Best practice**: Manage and control access to high risk devices<br>
**Detail**: Use Conditional Access App Control to set controls on your SaaS apps. You can create session policies to monitor your high risk, low trust sessions. Similarly, you can create session policies to block and protect downloads by users trying to access sensitive data from unmanaged or risky devices. If you do not to create session policies to monitor high-risk sessions, you will lose the ability to block and protect downloads in the web client, as well as the ability to monitor low-trust session both in Microsoft and third-party apps.<br>
**For more information**:

* [Protect apps with Microsoft Cloud App Security Conditional Access App Control](proxy-intro-aad.md)
* [Session policies](session-policy-aad.md)

## Secure collaboration with external users by enforcing real-time session controls

**Best practice**: Monitor sessions with external users using Conditional Access App Control<br>
**Detail**: To secure collaboration in your environment, you can create a session policy to monitor sessions between your internal and external users. This not only gives you the ability to monitor the session between your users (and notify them that their session activities are being monitored), but it also enables you to limit specific activities as well. When creating session policies to monitor activity, you can choose the apps and users you’d like to monitor.<br>
**For more information**:

* [Protect apps with Microsoft Cloud App Security Conditional Access App Control](proxy-intro-aad.md)
* [Session policies](session-policy-aad.md)

## Detect cloud threats, compromised accounts, malicious insiders, and ransomware

**Best practice**: Tune Anomaly policies, set IP ranges, send feedback for alerts<br>
**Detail**: Anomaly detection policies provide out-of-the-box user and entity behavioral analytics (UEBA) and machine learning (ML) so that you can immediately run advanced threat detection across your cloud environment.

Anomaly detection policies are triggered when there are unusual activities performed by the users in your environment. Cloud App Security continually monitors your users activities and uses UEBA and ML to learn and understand the *normal* behavior of your users. You can tune policy settings to fit your organizations requirements, for example, you can set the sensitivity of a policy, as well as scope a policy to a specific group.

* **Tune and Scope Anomaly Detection Policies**: As an example, to reduce the number of false positives within the impossible travel alert, you can set the policy's sensitivity slider to low. If you have users in your organization that are frequent corporate travelers, you can add them to a user group and select that group in the scope of the policy.

* **Set IP Ranges**: Cloud App Security can identify known IP addresses once IP address ranges are set. With IP address ranges configured, you can tag, categorize, and customize the way logs and alerts are displayed and investigated. Adding IP address ranges helps to reduce false positive detections and improve the accuracy of alerts. If you choose not to add your IP addresses, you may see an increased number of possible false positives and alerts to investigate.

* **Send Feedback for alerts**

    When dismissing or resolving alerts, make sure to send feedback with the reason you dismissed the alert or how it’s been resolved. This information assists Cloud App Security to improve our alerts and reduce false positives.

**For more information**:

* [Get instantaneous behavioral analytics and anomaly detection](anomaly-detection-policy.md)
* [Working with IP ranges and tags](ip-tags.md)
* [Monitor alerts in Cloud App Security](monitor-alerts.md)

**Best practice**: Manage known risky locations and countries you don't expect to see activity from<br>
**Detail**: To protect your environment,  Creating an activity policy to get notified when users are login in from a risky location or country. This will you alert in the case that there is a possible compromised session in your environment and allows you to detect and remediate threats before they occur.<br>
**For more information**:
