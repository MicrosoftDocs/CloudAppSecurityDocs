---
title: What's new 
description: This article is updated frequently to let you know what's new in the latest release of Microsoft Defender for Cloud Apps.
ms.date: 04/02/2023
ms.topic: overview
---
# What's new in Microsoft Defender for Cloud Apps

[!INCLUDE [Banner for top of topics](includes/banner.md)]

*Applies to: Microsoft Defender for Cloud Apps*

This article is updated frequently to let you know what's new in the latest release of Microsoft Defender for Cloud Apps.

RSS feed: Get notified when this page is updated by copying and pasting the following URL into your feed reader: `https://learn.microsoft.com/api/search/rss?search=%22frequently+to+let+you+know+what%27s+new+in+the+latest+release+of+Microsoft+Defender+for+Cloud+Apps%22&locale=en-us&facet=`

> [!NOTE]
>
> Threat protection product names from Microsoft are changing. Read more about this and other updates [here](https://www.microsoft.com/security/blog/?p=91813). We'll be using the new names in future releases.

For more information on what's new with other Microsoft Defender security products, see:

- [What's new in Microsoft 365 Defender](/microsoft-365/security/defender/whats-new)
- [What's new in Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/whats-new-in-microsoft-defender-endpoint)
- [What's new in Microsoft Defender for Identity](/defender-for-identity/whats-new)

> [!NOTE]
> As of August 28 2022, users who were assigned an Azure AD **Security Reader** role won't be able to manage the Microsoft Defender for Cloud Apps alerts. This change will be gradually rolled out to all customers over the next several weeks. To continue to manage alerts, the user's role should be updated to an Azure AD **Security Operator**.

## Defender for Cloud Apps release 250

April 2, 2023

- New "behaviors" data type in Microsoft 365 Defender advanced hunting (Preview)  
To enhance our threat protection and reduce alert fatigue, we've added a new data layer called "behaviors" to the Microsoft Defender for Cloud Apps experience in Microsoft 365 Defender advanced hunting. This feature is intended to provide relevant information for investigations by identifying anomalies or other activities that may be related to security scenarios, but don't necessarily indicate malicious activity or a security incident. In this first stage, some of the Microsoft Defender for Cloud App anomaly detections will also be presented as behaviors. In future phases, these detections will only generate behaviors and not alerts. For more information, see [Investigate behaviors with advanced hunting (Preview)](behaviors.md).

## Defender for Cloud Apps release 249

March 19, 2023

- **Automatic redirection from Microsoft Defender for Cloud Apps to the Microsoft 365 Defender portal (Preview)**  
A new automatic redirection toggle will allow you to trigger the automatic redirection from Microsoft Defender for Cloud Apps to Microsoft 365 Defender. Once the redirection setting is enabled, users accessing the Microsoft Defender for Cloud Apps portal will be automatically routed to the Microsoft 365 Defender portal. The toggle default value is set to **Off**, and admins will need explicitly to opt-in to the automatic redirection and start using the Microsoft 365 Defender exclusively. You still have an option to opt-out from the Microsoft 365 Defender experiences and to use Microsoft Defender for Cloud Apps standalone portal. This can be done by switching off the toggle. For more information, see [Redirecting accounts from Microsoft Defender for Cloud Apps to Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-security-mda-redirection).

## Defender for Cloud Apps release 248

March 5, 2023

- **Faster load time for protected sessions**  
We've made significant improvements to the loading time of web pages protected by session policies. End users that are scoped to session policies, either from a desktop or mobile device, can now enjoy a faster and more seamless browsing experience.
We've witnessed an improvement of between 10% and 40%, depending on the application, the network, and the complexity of the web page.

- **Support for Tokyo ServiceNow version**  
The Defender for Cloud Apps connector for ServiceNow now supports the ServiceNow Tokyo version. With this update, you can protect the latest versions of ServiceNow using Defender for Cloud Apps. For more information, see [Connect ServiceNow to Microsoft Defender for Cloud Apps](connect-servicenow.md).

## Defender for Cloud Apps release 246 and 247

February 19, 2023

- **SaaS Security Posture Management (SSPM) capabilities update announcements (GA and Public preview)**  
We have made important improvements to our governance and protection of third-party software-as-a-service (SaaS) applications. These improvements include assessments to identify risky security configurations using Microsoft Defender for Cloud Apps, as well as smoother integration into the Microsoft Secure Score experience. We have now released Salesforce and ServiceNow to general availability, while Okta, GitHub, Citrix ShareFile, and DocuSign are currently in public preview. For more information, see [Connect apps to get visibility and control with Microsoft Defender for Cloud Apps](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md).

- **Malware detection policy governance actions now available (preview)**  
Automatic actions for files detected by the malware detection policy are now available as part of the policy configuration. The actions differ from app to app. For more information, see [Malware governance actions (Preview)](governance-actions.md#malware-governance-actions-preview).

- **Log Collector Version Update**  

    We've released a new log collector version with the latest vulnerabilities fixes.

    New version: **columbus-0.246.0-signed.jar**  
    Image name: **mcaspublic.azurecr.io/public/mcas/logcollector tag: latest/0.246.0 image id : eeb3c4f1a64c**

    The Docker image was rebuilt with these updates:

    | Dependency  name               | From  version        | To  version          | Comments                                                     |
    | ------------------------------ | -------------------- | -------------------- | ------------------------------------------------------------ |
    | amazon-corretto                | 8.222.10.1-linux-x64 | 8.352.08.1-linux-x64 |                                                              |
    | openssl  1.1.1                 | 1.1.1q               | 1.1.1s               | The  1.1.1 series is available and is supported until Sep 11, 2023. |
    | Pure  ftpd                     | 1.0.49               | 1.0.50               |                                                              |
    | fasterxml.jackson.core.version | 2.13.3               | 2.14.1               | 2.14  was released in Nov 2022                               |
    | org.jacoco                     | 0.7.9                | 0.8.8                | Version  0.8.8 from Apr 05, 2022                             |

    To begin using the new version, you'll need to stop your log collectors, remove the current image, and install the new one.

    To verify the new version is running, run the following command inside the Docker container:

    `cat /var/adallom/versions | grep columbus-`

## Defender for Cloud Apps release 244 and 245

January 22, 2023

- **File policy – exploring multiple SITs**  
Defender for Cloud Apps already includes the ability to explore policy file matches that contain sensitive information types (SITs). Now, Defender for Cloud Apps also allows you to differentiate between multiple SITs in the same file match. This feature, known as short evidence, lets Defender for Cloud Apps better manage and protect your organization's sensitive data. For more information, see [Examine evidence (preview)](dcs-inspection.md#examine-evidence-preview).

## Defender for Cloud Apps release 240, 241, 242, and 243

December 25, 2022

- **Azure AD identity protection**  
Azure AD identity protection alerts will arrive directly to Microsoft 365 Defender. The Microsoft Defender for Cloud Apps policies won't affect the alerts in the Microsoft 365 Defender portal. Azure AD identity protection policies will be removed gradually from the cloud apps policies list in the Microsoft 365 Defender portal. To configure alerts from these policies, see [Configure Azure AD IP alert service](/microsoft-365/security/defender/investigate-alerts#configure-aad-ip-alert-service).

## Defender for Cloud Apps release 237, 238 and 239

October 30, 2022

- **Native Integration of Microsoft Defender for Cloud Apps in Microsoft 365 Defender is now in public preview**  
  The entire Defender for Cloud Apps experience in Microsoft 365 Defender is now available for public preview.

  SecOps and security admins will experience these major benefits:

  - Time and costs saved
  - Holistic investigation experience
  - Additional data and signals in advanced hunting
  - Integrated protection across all security workloads

  For more information, see [Microsoft Defender for Cloud Apps in Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-security-center-defender-cloud-apps).

## Defender for Cloud Apps release 236

September 18, 2022

- **Egnyte API connector is generally available**  
The Egnyte API connector is generally available, providing you with deeper visibility and control over your organization's usage of the Egnyte app. For more information, see [How Defender for Cloud Apps helps protect your Egnyte environment](protect-egnyte.md).

## Defender for Cloud Apps release 235

September 4, 2022

- **Log Collector version update**  
We've released a new log collector version with the latest vulnerabilities fixes.

  New version: **columbus-0.235.0-signed.jar**

  Main changes:
  - Docker image was rebuilt with latest updates
  - Openssl library was update from 1.1.1l to 1.1.1q
  - fasterxml.jackson.core.version was updated from 2.13.1 to 2.13.3

  If you wish to update the version, stop your log collectors, remove the current image, and install a new one.  
  To verify the version, run this command inside the Docker container: `cat var/adallom/versions | grep columbus-`  
  For more information, see [Configure automatic log upload for continuous reports](discovery-docker.md).

- **Onboarding application to session controls (Preview)**  
  The process of onboarding an application to be used for session controls has been improved and should increase the success rate of the onboarding process. To onboard an application:

  1. Go to the Conditional Access App Control list in **Settings** -> **Conditional access app control**.
  1. After selecting **Onboard with session control**, you're presented with an **Edit this app** form.
  1. To onboard the application to session controls, you must select the **Use the app with session controls** option.
  
  For more information, see [Deploy Conditional Access App Control for catalog apps with Azure AD](proxy-deployment-aad.md).

## Defender for Cloud Apps release 234

August 21, 2022

- **Feature parity between commercial and government offerings**  
We've consolidated the flow that allows Microsoft Defender for Cloud Apps data to be consumed through Microsoft 365 Defender. To consume this data in Microsoft Defender for Cloud, Microsoft 365 Defender should be used. For more information, see [Microsoft 365 Defender delivers unified XDR experience to GCC, GCC High and DoD customers](https://techcommunity.microsoft.com/t5/public-sector-blog/microsoft-365-defender-delivers-unified-xdr-experience-to-gcc/ba-p/3263702) and [Connect Microsoft 365 Defender data to Microsoft Sentinel](/azure/sentinel/connect-microsoft-365-defender?tabs=MDE#connect-to-microsoft-365-defender).

- **Protecting apps that use non-standard ports with session controls**  
This feature allows Microsoft Defender for Cloud Apps to enforce session policies for applications that use port numbers other than 443.
 Splunk and other applications that use ports other than 443 will now be eligible for session control.  
There's no configuration requirement for this feature.  The feature is currently in preview mode. For more information, see [Session controls](proxy-intro-aad.md#session-controls).

## Defender for Cloud Apps release 232 and 233

August 7, 2022

- **MITRE techniques**  
The Defender for Cloud Apps threat protection anomaly detections will now include MITRE techniques and sub-techniques where relevant, in addition to the MITRE tactic that already exists. This data will also be available in the alert's side pane in Microsoft 365 Defender. For more information, see [How to investigate anomaly detection alerts](investigate-anomaly-alerts.md).

> [!IMPORTANT]
> **Deprecation of old proxy suffix domains for session controls (gradual rollout)**  
> From September 15 2022, Defender for Cloud Apps will no longer support suffix domains in the form `<appName>.<region>.cas.ms.`  
In November 2020, we moved to suffix domains in the form of `<appName>.mcas.ms`, but still provided grace time to switch from the old suffixes.  
> End users will have very little chance of encountering navigation problems on such a domain. However, there may be situations where they may have issues -  for example, if bookmarks are saved in the old domain form or an old link is stored somewhere.
>
> If users encounter the following message:
>  
> **The connection for this site is not secure.**  
> **missing.cert.microsoft.sharepoint.com.us.cas.ms sent an invalid response**
>
> They should manually replace the URL section `.<region>.cas.ms` with `.mcas.us`.

## Defender for Cloud Apps release 231

July 10, 2022

- **Malware hashes available for SharePoint and OneDrive (Preview)**  
In addition to file hashes available for malware detected in non-Microsoft storage apps, now new malware detection alerts will provide hashes for malware detected in SharePoint and OneDrive. For more information, see [Malware detection](anomaly-detection-policy.md#malware-detection).

## Defender for Cloud Apps release 230

June 26, 2022

- **SaaS Security Posture Management capabilities for Salesforce and ServiceNow**  
Security posture assessments are available for Salesforce and ServiceNow. For more information, see [Security posture management for SaaS apps](security-saas.md).

## Defender for Cloud Apps release 227, 228, and 229

June 14, 2022

- **Admin audit enhancements**  
Additional Defender for Cloud Apps admin activities have been added:
  - File monitoring status - switching on/off
  - Creating and deleting policies
  - Editing of policies has been enriched with additional data
  - Admin management: adding and deleting admins

  For each of the activities listed above, you can find the details in the activity log. For more information, see [Admin activity auditing](manage-admins.md#admin-activity-auditing).

- **DocuSign API Connector is generally available**  
The DocuSign API connector is generally available, providing you deeper visibility and control over your organization’s usage of DocuSign app. For more information, see [How Defender for Cloud Apps helps protect your DocuSign environment](protect-docusign.md).

## Defender for Cloud Apps release 226

May 1, 2022

- **Improvements in malware detection for non-Microsoft storage apps**  
Defender for Cloud Apps has introduced major improvements in the non-Microsoft storage apps detection mechanism. This will reduce the number of false positive alerts.

## Defender for Cloud Apps release 225

April 24, 2022

- **Support for Rome and San Diego ServiceNow versions**  
The Defender for Cloud Apps connector for ServiceNow now supports Rome and San Diego versions of ServiceNow. With this update, you can protect the latest versions of ServiceNow using Defender for Cloud Apps. For more information, see [Connect ServiceNow to Microsoft Defender for Cloud Apps](connect-servicenow.md).

## Defender for Cloud Apps release 222, 223, and 224

April 3, 2022

- **Updated severity levels for Defender for Cloud Apps anomaly detections**  
The severity levels for Defender for Cloud Apps built-in anomaly detection alerts are being changed to better reflect the risk level in the event of true positive alerts. The new severity levels can be seen in the policies page: <https://portal.cloudappsecurity.com/#/policy>

## Defender for Cloud Apps release 221

February 20, 2022

- **Egnyte app connector available in public preview**  
A new app connector for Egnyte is available in public preview. You can now connect Microsoft Defender for Cloud Apps to Atlassian to monitor and protect users and activities. For more information, see [Connect Egnyte to Microsoft Defender for Cloud Apps (Preview)](connect-egnyte.md).

## Defender for Cloud Apps release 220

February 6, 2022

- **New Cloud discovery log collector**  
The Cloud Discovery log collector has been updated to Ubuntu 20.04. To install it, see [Configure automatic log upload for continuous reports](discovery-docker.md).

## Defender for Cloud Apps release 218 and 219

January 23, 2022

- **Atlassian app connector available in public preview**  
A new app connector for Atlassian is available in public preview. You can now connect Microsoft Defender for Cloud Apps to Atlassian to monitor and protect users and activities. For more information, see [Connect Atlassian to Microsoft Defender for Cloud Apps (Preview)](connect-atlassian.md).

## Defender for Cloud Apps release 216 and 217

December 26, 2021

- **Non-Microsoft activities in advanced hunting**  
Non-Microsoft apps activities are now included the [CloudAppEvent table](/microsoft-365/security/defender/advanced-hunting-cloudappevents-table) in Microsoft 365 Defender [advanced hunting](/microsoft-365/security/defender/advanced-hunting-overview). For more information, see [the Microsoft 365 Defender Tech Community blog post](https://techcommunity.microsoft.com/t5/microsoft-365-defender-blog/cloudappevents-in-advanced-hunting-now-includes-non-microsoft/ba-p/3036692).

- **NetDocuments API connector is now in general availability**  
The NetDocuments API connector is in general availability, giving you more visibility into, and control over, how your NetDocument app is used in your organization. For more information, see [How Cloud App Security helps protect your NetDocuments](protect-netdocuments.md)

## Defender for Cloud Apps release 214 and 215

November 28, 2021

- **NetDocuments app connector available in public preview**  
A new app connector for NetDocuments is available in public preview. You can now connect Microsoft Defender for Cloud Apps to NetDocuments to monitor and protect users and activities. For more information, see [Connect NetDocuments to Microsoft Defender for Cloud Apps](connect-netdocuments-to-microsoft-defender-for-cloud-apps.md).

<!--
- **Reset user investigation priority score**  
The user investigation priority score can now be reset to 0 if an investigation was done and there's no need to see the user score for past events. For more information, see [Identify top risky users](tutorial-ueba.md#phase-2-identify-top-risky-users).
-->

## Cloud App Security release 212 and 213

October 31, 2021

- **Impossible travel, activity from infrequent countries/regions, activity from anonymous IP addresses, and activity from suspicious IP addresses alerts will not apply on failed logins.**  
After a thorough security review, we decided to separate failed login handling from the alerts mentioned above. From now on, they'll only be triggered by successful login cases and not by unsuccessful logins or attack attempts. Mass failed login alert will still be applied if there are anomalous high amount of failed login attempts on a user. For more information, see [Behavioral analytics and anomaly detection](anomaly-detection-policy.md).

- **New anomaly detection: Unusual ISP for an OAuth app**  
We've extended our anomaly detections to include suspicious addition of privileged credentials to an OAuth app. The new detection is now available out-of-the-box and automatically enabled. The detection can indicate that an attacker has compromised the app and is using it for malicious activity. For more information, see  [Unusual ISP for an OAuth app](investigate-anomaly-alerts.md#unusual-isp-for-an-oauth-app).

- **New detection: Activity from password-spray associated IP addresses**  
This detection compares IP addresses performing successful activities in your cloud applications to IP addresses identified by Microsoft’s threat intelligence sources as recently performing password spray attacks. It alerts about users that were victims of password spray campaigns and managed to access your cloud applications from those malicious IPs. This new alert will be generated by the existing **Activity from suspicious IP addresses** policy. For more information, see [Activity from suspicious IP addresses](investigate-anomaly-alerts.md#activity-from-suspicious-ip-addresses).

- **Smartsheet and OneLogin API connectors are now in general availability**  
Smartsheet and OneLogin API connectors are now in general availability. You can now connect Microsoft Cloud App Security to Smartsheet and to OneLogin to monitor and protect users and activities. For more information, see  [Connect Smartsheet](./connect-smartsheet.md) and [Connect OneLogin](./connect-onelogin.md).

- **New Shadow IT integration with Open Systems**  
We've added native integration with Open Systems providing you with Shadow IT visibility into app use and control over app access. For more information, see [Integrate Cloud App Security with Open Systems](open-systems-integration.md).

## Cloud App Security release 209, 210, and 211

October 10, 2021

- **Slack API connector is now in general availability**  
Slack API connector is in general availability, giving you more visibility in to, and control over, how your app is used in your organization. For more information, see [How Cloud App Security helps protect your Slack Enterprise](protect-slack.md).

- **New warn experience for monitored apps with Microsoft Defender for Endpoint is now in general availability**  
Cloud App Security has extended its native integration with Microsoft Defender for Endpoint. You can now apply soft block on access to apps marked as monitored using Microsoft Defender for Endpoint's network protection capability. End users will be able to bypass the block. The block bypass report will be available in Cloud App Security’s discovered app experience. For more information, see:
  - [Warn and educate users on risky app usage](https://techcommunity.microsoft.com/t5/security-compliance-and-identity/warn-and-educate-users-on-risky-app-usage/ba-p/2630982)
  - [Govern discovered apps using Microsoft Defender for Endpoint](mde-govern.md)

- **New discovered app experience in general availability**  
As part of continuous improvement of our entity experiences, we're introducing a modernized discovered app experience to cover discovered web apps and OAuth apps and provide a unified view of an application entity. For more information, see [Working with the app page](working-with-app-page.md).

## Cloud App Security release 208

August 22, 2021

- **New discovered app experience in public preview**  
As part of continuous improvement of our entity experiences, we're introducing a modernized discovered app experience to cover discovered web apps and OAuth apps and provide a unified view of an application entity. For more information, see [Working with the app page](working-with-app-page.md).

- **App governance add-on to Cloud App Security available in public preview**  
The app governance add-on to Microsoft Cloud App Security is a security and policy management capability designed for OAuth-enabled apps that access Microsoft 365 data through Microsoft Graph APIs.  App governance delivers full visibility, remediation, and governance into how these apps access, use, and share your sensitive data stored in Microsoft 365 through actionable insights and automated policy alerts and actions. For more information:
  - [Learn more about app governance](/microsoft-365/compliance/app-governance-manage-app-governance)
  - [Learn about customer eligibility](/microsoft-365/compliance/app-governance-get-started)
  - [Sign up for a free trial](https://www.microsoft.com/microsoft-365/try)

- **Smartsheet app connector available in public preview**  
A new app connector for Smartsheet is available in public preview. You can now connect Microsoft Cloud App Security to Smartsheet to monitor and protect users and activities. For more information, see [Connect Smartsheet to Microsoft Cloud App Security](./connect-smartsheet.md).

## Cloud App Security release 207

August 8, 2021

- **New warn experience for monitored apps with Microsoft Defender for Endpoint (public preview)**  
  Cloud App Security has extended its native integration with Microsoft Defender for Endpoint (MDE). You can now apply soft block on access to apps marked as monitored using Microsoft Defender for Endpoint's network protection capability. End users will be able to bypass the block. The block bypass report will be available in Cloud App Security’s discovered app experience. For more information, see:
  - [Warn and educate users on risky app usage](https://techcommunity.microsoft.com/t5/security-compliance-and-identity/warn-and-educate-users-on-risky-app-usage/ba-p/2630982)
  - [Govern discovered apps using Microsoft Defender for Endpoint](mde-govern.md)

## Cloud App Security release 206

July 25, 2021

- **New Cloud Discovery Open Systems log parser**  
Cloud App Security's Cloud Discovery analyzes a wide range of traffic logs to rank and score apps. Now Cloud Discovery includes a built-in log parser to support the Open Systems format. For a list of supported log parsers, see [Supported firewalls and proxies](set-up-cloud-discovery.md#supported-firewalls-and-proxies).

## Cloud App Security release 205

July 11, 2021

- **Zendesk app connector available in public preview**  
A new app connector for Zendesk is available in public preview. You can now connect Microsoft Cloud App Security to Zendesk to monitor and protect users and activities. For more information, see [Connect Zendesk](./connect-zendesk.md).

- **New Cloud Discovery parser for Wandera**  
Cloud Discovery in Cloud App Security analyzes a wide range of traffic logs to rank and score apps. Now, Cloud Discovery includes a built-in log parser to support the Wandera format. For a list of supported log parsers, see [Supported firewalls and proxies](set-up-cloud-discovery.md#supported-firewalls-and-proxies).

## Cloud App Security release 204

June 27, 2021

- **Slack and OneLogin app connectors available in public preview**  
New app connectors are now available for Slack and OneLogin in public preview. You can now connect Microsoft Cloud App Security to Slack and to OneLogin to monitor and protect users and activities. For more information, see [Connect Slack](./connect-slack.md) and [Connect OneLogin](./connect-okta.md).

## Cloud App Security release 203

June 13, 2021

- **Expose verified publisher indicating in O365 OAuth apps**  
Cloud App Security now surfaces whether a publisher of an Office 365 OAuth app has been verified by Microsoft to enable higher app trust. This feature is in a gradual rollout. For more information, see [Working with the OAuth app page](manage-app-permissions.md#working-with-the-oauth-apps-page).

- **Azure Active Directory Cloud App Security admin**  
A Cloud App Security admin role has been added to Azure Active Directory (Azure AD), allowing the assignment of global admin capabilities to Cloud App Security alone via Azure AD. For more information, see [Office 365 and Azure AD roles with access to Cloud App Security](manage-admins.md#office-365-and-azure-ad-roles-with-access-to-cloud-app-security).

- **Export custom tag and app domains per discovered app**  
  **Export to CSV** in the discovered apps page now include the application's custom app tags and associated web domains. For more information, see [Working with discovered apps](discovered-apps.md).

  >[!IMPORTANT]
  >**Enhanced proxy URL for access controls (gradual rollout)**  
  Starting in early July 2021, we will change our access endpoint from `<mcas-dc-id>.access-control.cas.ms` to `access.mcas.ms`. Make sure you update your network appliance rules before the end of June, as this can lead to access issues. For more information, see [Access and session controls](network-requirements.md#access-and-session-controls)

## Cloud App Security release 200, 201, and 202

May 30, 2021

- **Authentication Context (Step-Up Authentication) in public preview**  
We've added the ability to protect users working with proprietary and privileged assets by requiring Azure AD Conditional Access policies to be reassessed in the session. For example, if a change in IP address is detected because an employee in a highly sensitive session has moved from the office to the coffee shop downstairs, step-up can be configured to reauthenticate that user. For more information, see [Require step-up authentication (authentication context) upon risky action](tutorial-step-up-authentication.md).

## Cloud App Security release 199

April 18, 2021

- **Service Health Dashboard availability**  
The enhanced Cloud App Security [Service Health Dashboard](https://admin.microsoft.com/Adminportal/Home#/servicehealth) is now available within the Microsoft 365 Admin portal for users with **Monitor service health** permissions. Learn more about [Microsoft 365 Admin roles](/microsoft-365/admin/add-users/about-admin-roles).
In the dashboard, you can configure notifications, allowing relevant users to stay updated with the current Cloud App Security status. To learn how to configure email notifications and additional information about the dashboard, see [How to check Microsoft 365 service health](/microsoft-365/enterprise/view-service-health).

- **AIP support deprecated**  
Label management from the Azure Information Protection portal (classic) is deprecated beginning April 1, 2021. Customers without AIP extended support should migrate their labels to Microsoft Purview Information Protection to continue using sensitivity labels in Cloud App Security. Without migration to Microsoft Purview Information Protection or AIP extended support, file policies with sensitivity labels will be disabled. For more information, see [Understanding Unified Labeling migration](https://techcommunity.microsoft.com/t5/security-compliance-and-identity/understanding-unified-labeling-migration/ba-p/783185).

- **DLP near real-time rollout completed for Dropbox, ServiceNow, AWS, and Salesforce**  
New near real-time file scanning is available in Dropbox, ServiceNow and Salesforce. New near real-time S3 bucket discovery is available in AWS. For more information, see [Connect apps](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md).

- **Public preview for overriding privilege sensitivity labels**  
Cloud App Security supports overriding sensitivity labels for files that were labeled outside Cloud App Security. For more information, see [How to integrate Microsoft Purview Information Protection with Defender for Cloud Apps](azip-integration.md#how-to-integrate-microsoft-purview-information-protection-with-defender-for-cloud-apps).

- **Extended Advanced Hunting events**  
We've expanded the available events in Cloud App Security. Microsoft 365 Defender Advanced Hunting now includes telemetry from Microsoft OneDrive, SharePoint Online, Office 365, Dynamics 365, Dropbox, Power BI, Yammer, Skype for Business, and Power Automate, in addition to Exchange Online and Teams, which were available until now. For more information, see [Apps and services covered](/microsoft-365/security/defender/advanced-hunting-cloudappevents-table#apps-and-services-covered).

## Cloud App Security release 198

Released April 4, 2021

- **Exclusion of Azure Active Directory groups entities from discovery**  
We've added the ability to exclude discovered entities based on imported Azure Active Directory groups. Excluding Azure AD groups will hide all discovery-related data for any users in these groups. For more information, see [Exclude entities](discovered-apps.md#exclude-entities).

- **API connector support for ServiceNow Orlando and Paris versions**  
We have added support for the ServiceNow API connector to the Orlando and Paris versions. For more information, see [Connect ServiceNow to Microsoft Cloud App Security](./connect-servicenow.md).

- **Always apply the selected action even if data cannot be scanned**  
  We've added a new checkbox to [Session policies](session-policy-aad.md) that treats any data that can't be scanned as a match for the policy.

  >[!NOTE]
  >Deprecation notice: this feature replaces both **Treat encrypted as match**, and **Treat files that cannot be scanned as match**, in addition to adding new functionality. New policies will contain the new checkbox by default, deselected by default. Pre-existing policies will be migrated to the new checkbox on May 30. Policies with either or both options selected will have the new option selected by default; all other policies will have it deselected.

## Cloud App Security release 197

Released March 21, 2021

- **Status page deprecation notice**  
On April 29, Cloud App Security will deprecate the service health status page, replacing it with the [Service Health Dashboard](https://admin.microsoft.com/Adminportal/Home?ref=/servicehealth) within the Microsoft 365 Admin portal. The change aligns Cloud App Security with other Microsoft services and provides an enhanced service overview.

  >[!NOTE]
  >Only users with **Monitor service health** permissions can access the dashboard. For more information, see [About admin roles](/microsoft-365/admin/add-users/about-admin-roles).  
  >
  >In the dashboard, you can configure notifications, allowing relevant users to stay updated with the current Cloud App Security status. To learn how to configure email notifications and additional information regarding dashboard, see [How to check Microsoft 365 service health](/microsoft-365/enterprise/view-service-health).

- **OAuth app consents link**  
We've added the ability to scope activity investigations to specific OAuth app's consent activities directly from the OAuth app view. For more information, see [How to investigate suspicious OAuth apps](investigate-risky-oauth.md#how-to-investigate-suspicious-oauth-apps).

## Cloud App Security release 195 and 196

Released March 7, 2021

- **Enhanced Shadow IT discovery with Microsoft Defender for Endpoint**  
We've further improved our Defender for Endpoint integration by leveraging enhanced signals for the Defender agent, providing more accurate app discovery and organizational user context.

  To benefit from the latest enhancements, make sure your organizational endpoints are updated with the latest Windows 10 updates:

  - [KB4601383](https://support.microsoft.com/topic/february-16-2021-kb4601383-os-build-17763-1790-preview-9535653c-8012-47f0-0f90-44cdd57cdc36): Windows 10, version 1809
  - [KB4601380](https://support.microsoft.com/topic/february-16-2021-kb4601380-os-build-18363-1411-preview-2e3c38e1-a947-1033-8006-a30f3806da18): Windows 10, version 1909
  - [KB4601382](https://support.microsoft.com/topic/february-24-2021-kb4601382-os-builds-19041-844-and-19042-844-preview-1a7ed2b4-017d-2644-a1e8-dd6bf14cba76): Windows 10, version 20H2, version [21H1 Insider](https://blogs.windows.com/windows-insider/2021/02/17/announcing-windows-10-insider-preview-build-19043-844-21h1/)

- **Configurable session lifetime**  
We're enabling customers to configure a shorter session lifetime for Conditional Access App Control. By default, sessions proxied by Cloud App Security have a maximum lifetime of 14 days. For more information about shortening session lifetimes, contact us at mcaspreview@microsoft.com.

## Cloud App Security release 192, 193, and 194

Released February 7, 2021

- **Updates to Policies page**  
We've updated the **Policies** page, adding a tab for every policy category. We also added an **All policies** tab to give you a complete list of all your policies. For more information about the policy categorization, see [Policy types](control-cloud-apps-with-policies.md#policy-types).

- **Enhanced Office 365 OAuth apps export**  
We've enhanced the Office 365 OAuth apps activities export to CSV file with the *Redirect URL* of the OAuth apps. For more information about exporting OAuth app activities, see [OAuth app auditing](manage-app-permissions.md#oauth-app-auditing).

- **Updates to the portal interface**  
In the coming months, Cloud App Security will be updating its User Interface to provide a more consistent experience across Microsoft 365 security portals. [Learn more](https://techcommunity.microsoft.com/t5/security-compliance-and-identity/microsoft-cloud-app-security-user-interface-updates/ba-p/2083113)

## Cloud App Security release 189, 190, and 191

Released January 10, 2021

- **New log collector version**  
Upgraded Log collector for Shadow IT discovery is now available. It includes the following updates:

  - We've upgraded our Pure-FTPd version to the latest version: 1.0.49. TLS < 1.2 is now disabled by default.
  - We've disabled the "octet-counted" framing feature in RSyslog to prevent failed processing.

  For more information, see [Configure automatic log upload for continuous reports](discovery-docker.md).

- **New anomaly detection: Suspicious addition of credentials to an OAuth app**  
We've extended our anomaly detections to include suspicious addition of privileged credentials to an OAuth app. The new detection is now available out-of-the-box and automatically enabled. The detection can indicate that an attacker has compromised the app and is using it for malicious activity. For more information, see [Unusual addition of credentials to an OAuth app](investigate-anomaly-alerts.md#unusual-addition-of-credentials-to-an-oauth-app).

- **Enhanced auditing for Shadow IT discovery activities**  
We've updated the auditing for [Shadow IT](tutorial-shadow-it.md) activities to include actions performed by administrators. The following new activities are now available in the activity log and can be used as part of your Cloud App Security [investigation experience](investigate.md#use-the-investigation-tools).
  - Tagging or untagging apps
  - Creating, updating, or deleting log collectors
  - Creating, updating, or deleting  data sources

- **New Data Enrichment REST API endpoints**  
  We've added the following [Data Enrichment API endpoints](api-data-enrichment.md) enabling you to fully manage your IP address ranges using the API. Use our [sample management script](api-data-enrichment-manage-script.md) to help you get started. For more information about ranges, see [Working with IP ranges and tags](ip-tags.md).
  - [List IP address range](api-data-enrichment-list.md)
  - [Update IP address range](api-data-enrichment-update.md)
  - [Delete IP address range](api-data-enrichment-delete.md)

## Cloud App Security release 187 and 188

Released November 22, 2020

- **New Shadow IT integration with Menlo Security**  
We've added native integration with Menlo Security providing you with Shadow IT visibility into app use and control over app access. For more information, see [Integrate Cloud App Security with Menlo Security](menlo-integration.md).

- **New Cloud Discovery WatchGuard log parser**  
Cloud App Security Cloud Discovery analyzes a wide range of traffic logs to rank and score apps. Now Cloud Discovery includes a built-in log parser to support the WatchGuard format. For a list of supported log parsers, see [Supported firewalls and proxies](set-up-cloud-discovery.md#supported-firewalls-and-proxies).

- **New permission for Cloud Discovery global admin role**  
Cloud App Security now allows users with the Cloud Discovery global admin role to create API tokens and use all Cloud Discovery related APIs. For more information about the role, see [Built-in Cloud App Security admin roles](manage-admins.md#built-in-cloud-app-security-admin-roles).

- **Enhanced sensitivity slider: Impossible travel**  
We've updated the sensitivity slider for impossible travel to configure different sensitivity levels for different user scopes, allowing enhanced control over the fidelity of alerts for user scopes. For example, you can define a higher sensitivity level for administrators than for other users in the org. For more information about this anomaly detection policy, see [Impossible travel](anomaly-detection-policy.md#impossible-travel).

- **Enhanced proxy URL suffix for session controls (gradual rollout)**  
On June 7, 2020, we started gradually rolling out our enhanced proxy session controls to use one unified suffix that doesn't include named regions. For example, users will see `<AppName>.mcas.ms` suffix instead of `<AppName>.<Region>.cas.ms`. If you routinely block domains in your network appliances or gateways, make sure you allowlist all the domains listed under [Access and session controls](network-requirements.md#access-and-session-controls).

## Cloud App Security release 184, 185, and 186

Released October 25, 2020

- **New enhanced alert monitoring and management experience**  
As part of our ongoing improvements to monitoring and managing alerts, the Cloud App Security Alerts page has been improved based on your feedback. In the enhanced experience, the **Resolved** and **Dismissed** statuses are replaced by the **Closed** status with a resolution type. [Learn more](monitor-alerts.md#deployment-of-our-enhanced-alert-monitoring-and-management-experience)

- **New global severity setting for signals sent to Microsoft Defender for Endpoints**  
We've added the ability to set the global severity setting for signals sent to Microsoft Defender for Endpoint. For more information, see [How to integrate Microsoft Defender for Endpoint with Cloud App Security](mde-integration.md#).

- **New security recommendations report**  
Cloud App Security provides you with security configuration assessments for your Azure, Amazon Web Services (AWS), and Google Cloud Platform (GCP) giving you insights into security configuration gaps in your multi-cloud environment. Now you can export detailed security recommendation reports to help you monitor, understand, and customize your cloud environments to better protect your organization. For more information about exporting the report, see [Security recommendations report](security-config.md#security-recommendations-report).

- **Enhanced proxy URL suffix for session controls (gradual rollout)**  
On June 7, 2020, we started gradually rolling out our enhanced proxy session controls to use one unified suffix that doesn't include named regions. For example, users will see `<AppName>.mcas.ms` suffix instead of `<AppName>.<Region>.cas.ms`. If you routinely block domains in your network appliances or gateways, make sure you allowlist all the domains listed under [Access and session controls](network-requirements.md#access-and-session-controls).

- **Updates to the Cloud App Catalog**  
We've made the following updates to our Cloud App Catalog:

  - Teams Admin Center has been updated as a standalone app
  - Microsoft Office 365 Admin Center has been renamed to Office Portal

- **Terminology update**  
We've updated the term **machine** to **device** as part of the general Microsoft effort to align terminology across products.

## Cloud App Security release 182 and 183

Released September 6, 2020

- **Access and session controls for Azure portal GA**  
Conditional Access App Control for the Azure portal is now generally available. For information about configuring these controls, see the [Deployment guide](proxy-deployment-aad.md).

## Cloud App Security release 181

Released August 9, 2020

- **New Cloud Discovery Menlo Security log parser**  
Cloud App Security Cloud Discovery analyzes a wide range of traffic logs to rank and score apps. Now Cloud Discovery includes a built-in log parser to support the Menlo Security CEF format. For a list of supported log parsers, see [Supported firewalls and proxies](set-up-cloud-discovery.md#supported-firewalls-and-proxies).

- **Azure Active Directory (AD) Cloud App Discovery name displays in portal**  
For Azure AD P1 and P2 licenses, we've updated the product name in the portal to **Cloud App Discovery**. Learn more about [Cloud App Discovery](editions-cloud-app-security-aad.md).

## Cloud App Security release 179 and 180

Released July 26, 2020

- **New anomaly detection: Suspicious OAuth app file download activities**  
We've extended our anomaly detections to include suspicious download activities by an OAuth app. The new detection is now available out-of-the-box and automatically enabled to alert you when an OAuth app downloads multiple files from Microsoft SharePoint or Microsoft OneDrive in a manner that is unusual for the user.

- **Performance improvements using proxy caching for Session Controls (gradual rollout)**  
We've made additional performance improvements to our session controls, by improving our content caching mechanisms. The improved service is even more streamlined and provides increased responsiveness when using session controls. Note that session controls don't cache private content, aligning with the appropriate standards to only cache shared (public) content. For more information, see [How session control works](proxy-intro-aad.md#how-session-control-works).

- **New feature: Save security configuration queries**  
We've added the ability to save queries for our security configuration dashboard filters for Azure, Amazon Web Services (AWS), and Google Cloud Platform (GCP). This can help make future investigations even simpler by reusing common queries. Learn more about [Security configuration recommendations](security-config.md).

- **Enhanced anomaly detection alerts**  
We've extended the information we provide for anomaly detection alerts to include a mapping to the corresponding MITRE ATT\&CK tactic. This mapping will help you understand the phase and impact of the attack and assist with your investigations. Learn more about [How to investigate anomaly detection alerts](investigate-anomaly-alerts.md).

- **Enhanced detection logic: Ransomware activity**  
We've updated the detection logic for Ransomware activity to provide improved accuracy and reduced alert volume. For more information about this anomaly detection policy, see [Ransomware activity](anomaly-detection-policy.md#ransomware-activity).

- **Identity Security Posture reports: Tags visibility**  
We've added entity tags to Identity Security Posture reports providing additional insights about entities. For example, the **Sensitive** tag can help you identify risky users and prioritize your investigations. Learn more about [Investigating risky users](tutorial-ueba.md).

## Cloud App Security release 178

Released June 28, 2020

- **New security configurations for Google Cloud Platform (gradual rollout)**  
We've expanded our multi-cloud security configurations to provide security recommendations for Google Cloud Platform, based on the GCP CIS benchmark. With this new capability, Cloud App Security provides organizations with a single view for monitoring the compliance status across all cloud platforms, including [Azure subscriptions](security-config-azure.md), [AWS accounts](security-config-aws.md), and now [GCP projects](security-config-gcp.md).

- **New app connectors GA**  
We've added the following app connectors to our portfolio of generally available API connectors, giving you more visibility into and control over how your apps are used in your organization:
  - [GitHub Enterprise Cloud](protect-github.md)
  - [Google Cloud Platform](protect-gcp.md)
  - [Workday](protect-workday.md)

- **New real-time malware detection GA**  
We've expanded our session controls to detect potential malware using Microsoft Threat Intelligence upon file uploads or downloads. The new detection is now generally available out-of-the-box and can be configured to automatically block files identified as potential malware. For more information, see [Block malware on upload](session-policy-aad.md#block-malware-on-upload).

- **Enhanced access and session controls with any IdP GA**  
Access and session controls support for SAML apps configured with any identity provider is now generally available. For information about configuring these controls, see the [Deployment guide](proxy-deployment-aad.md).

- **Risky machine investigation enhancement**  
Cloud App Security provides the ability to identify risky machines as part of your shadow IT discovery investigation. Now, we've added the Microsoft Defender Advanced Threat Protection **Machine risk level** to the **machines** page giving analysts more context when investigating machines in your organization. For more information, see [Investigate devices in Cloud App Security](mde-investigation.md).

- **New feature: Self-service disable app connector (gradual rollout)**  
We've added the ability to disable app connectors directly in Cloud App Security. For more information, see [Disable app connectors](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md#disable-app-connectors).

## Cloud App Security release 177

Released June 14, 2020

- **New real-time malware detection (preview, gradual rollout)**  
We've expanded our session controls to detect potential malware using Microsoft Threat Intelligence upon file uploads or downloads. The new detection is now available out-of-the-box and can be configured to automatically block files identified as potential malware. For more information, see [Block malware on upload](session-policy-aad.md#block-malware-on-upload).

- **New access token support for access and session controls**  
We've added the ability to treat access token and code requests as logins when onboarding apps to access and session controls. To use tokens, select the settings cog icon, select **Conditional Access App Control**, edit the relevant app (three dots menu > **Edit app**), select **Treat access token and code requests as app logins**, and then select **Save**. For more information about onboarding apps, see [Onboard and deploy any app](proxy-deployment-any-app.md) and [Deploy featured apps](proxy-deployment-aad.md).

- **Enhanced proxy URL suffix for session controls (gradual rollout)**  
On June 7, 2020, we started gradually rolling out our enhanced proxy session controls to use one unified suffix that doesn't include named regions. For example, users will see `<AppName>.mcas.ms` suffix instead of `<AppName>.<Region>.cas.ms`. If you routinely block domains in your network appliances or gateways, make sure you allowlist all the domains listed under [Access and session controls](network-requirements.md#access-and-session-controls).

- **New documentation**  
  Cloud App Security documentation has been expanded to include the following new content:

  - **[Using the Cloud App Security REST API](api-introduction.md)**: Learn about our API capabilities and start integrating your applications with Cloud App Security.
  - **[Investigate anomaly detection alerts](investigate-anomaly-alerts.md)**: Get familiar with the available UEBA alerts, what they mean, identify the risk they pose, understand the scope of a breach, and the action you can take remediate the situation.

## Cloud App Security release 176

Released May 31, 2020

- **New activity privacy feature**  
We've enhanced your ability to granularly determine which users you want to monitor with the ability to make activities private. This new feature enables you to specify users based on group membership whose activities will be hidden by default. Only authorized admins have the option to choose to view these private activities, with each instance being audited in the governance log. For more information, see [Activity privacy](activity-privacy.md).

- **New integration with Azure Active Directory (Azure AD) Gallery**  
We've leveraged our native integration with Azure AD to give you the ability to navigate directly from an app in the Cloud App Catalog to its corresponding Azure AD Gallery app, and manage it in the gallery. For more information, see [Manage apps with Azure AD Gallery](tutorial-shadow-it.md#gallery-apps).

- **New feedback option available in selected policies**  
We're interested in receiving your feedback and learning how we can help. So now a new feedback dialog gives you the opportunity to help improve Cloud App Security, when creating, modifying, or deleting a file, anomaly detection, or session policy.

- **Enhanced proxy URL suffix for session controls (gradual rollout)**  
Starting June 7, 2020, we are gradually rolling out our enhanced proxy session controls to use one unified suffix that doesn't include named regions. For example, users will see `<AppName>.mcas.ms` suffix instead of `<AppName>.<Region>.cas.ms`. If you routinely blocklist domains in your network appliances or gateways, make sure you allowlist all the domains listed under [Access and session controls](network-requirements.md#access-and-session-controls).

- **Performance improvements for Session Controls (gradual rollout)**  
We've made significant network performance improvements to our proxy service. The improved service is even more streamlined and provides increased responsiveness when using session controls.

- **New risky activity detection: Unusual failed logon**  
We've expanded our current capability to detect risky behavior. The new detection is now available out-of-the-box and automatically enabled to alert you when an unusual failed login attempt is identified. Unusual failed login attempts may be an indication of a potential *password-spray* brute force attack (also known as the *low and slow* method). This detection impacts the overall [investigation priority score](tutorial-ueba.md) of the user.

- **Enhanced table experience**  
We've added the ability to resize table column widths so that you can widen or narrow columns to customize and improve the way you view tables. You also have the option to restore the original layout by selecting the table settings menu and choosing **Default width**.

## Cloud App Security release 175

Released May 17, 2020

- **New Shadow IT Discovery integration with Corrata (preview)**  
We've added native integration with Corrata providing you with Shadow IT visibility into app use and control over app access. For more information, see [Integrate Cloud App Security with Corrata](corrata-integration.md).

- **New Cloud Discovery log parsers**  
Cloud App Security Cloud Discovery analyzes a wide range of traffic logs to rank and score apps. Now Cloud Discovery includes a built-in log parser to support Corrata and Cisco ASA with FirePOWER 6.4 log formats. For a list of supported log parsers, see [Supported firewalls and proxies](set-up-cloud-discovery.md#supported-firewalls-and-proxies).

- **Enhanced dashboard (gradual rollout)**
As part of our ongoing improvements to the portal design, we are now gradually rolling out the improved Cloud App Security dashboard. The dashboard has been modernized based on your feedback and offers an enhanced user experience with updated content and data. For more information, see [Gradual deployment of our enhanced dashboard](daily-activities-to-protect-your-cloud-environment.md).

- **Enhanced governance: Confirm User Compromised for anomaly detections**  
We've expanded our current governance actions for anomaly policies to include **Confirm User Compromised** allowing you to proactively protect your environment from suspicious user activity. For more information, see [Activity governance actions](governance-actions.md#activity-governance-actions).

## Cloud App Security release 173 and 174

Released April 26, 2020

- **New SIEM agent CEF format for alerts**  
  As part of our effort to enrich the alert information provided in the CEF files used by generic SIEM servers, we've extended the format to include the following client fields:
  - IPv4 address
  - IPv6 address
  - IP address location

    For more information, see [CEF file format](siem.md#sample-cloud-app-security-alerts-in-cef-format).
- **Enhanced detection logic: Impossible travel**  
We've updated the detection logic for impossible travel to provide improved accuracy and reduced alert volume. For more information about this anomaly detection policy, see [Impossible travel](anomaly-detection-policy.md#impossible-travel).

## Cloud App Security release 172

Released April 5, 2020

- **Enhanced access and session controls with any IdP (preview)**  
Access and session controls now support SAML apps configured with any identity provider. The public preview of this new feature is now gradually rolling out. To configure these controls, see the [Deployment guide](proxy-deployment-aad.md).

- **New bulk deanonymization of users and machines**  
We've expanded and simplified the process of deanonymizing one or more users and machines under investigation. For more information about bulk deanonymization, see [How data anonymization works](cloud-discovery-anonymizer.md#how-data-anonymization-works).

## Cloud App Security release 170 and 171

Released March 22, 2020

- **New anomaly detection: Unusual region for cloud resource (preview)**  
We've expanded our current capability to detect anomalous behavior for AWS. The new detection is now available out-of-the-box and automatically enabled to alert you when a resource is created in an AWS region where the activity is not normally performed. Attackers often leverage an organization's AWS credits to perform malicious activities such as crypto-mining. Detecting such anomalous behavior can help mitigate an attack.

- **New activity policy templates for Microsoft Teams**  
Cloud App Security now provides the following new activity policy templates enabling you to detect potentially suspicious activities in Microsoft Teams:
  - **Access level change (Teams):** Alerts when a team's access level is changed from private to public.
  - **External user added (Teams):** Alerts when an external user is added to a team.
  - **Mass deletion (Teams):** Alerts when a user deletes a large number of teams.

- **Azure Active Directory (Azure AD) Identity Protection Integration**  
You can now control the severity of Azure AD Identity Protection alerts that are ingested into Cloud App Security. Additionally, if you haven't already enabled the **Azure AD Risky sign-in** detection, the detection will be automatically enabled to ingest high severity alerts. For more information, see [Azure Active Directory Identity Protection integration](aadip-integration.md).

## Cloud App Security release 169

Released March 1, 2020

- **New detection for Workday**  
We've expanded our current anomalous behavior alerts for Workday. The new alerts include the following user geolocation detections:
  - [Activity from anonymous IP addresses](anomaly-detection-policy.md#activity-from-anonymous-ip-addresses)
  - [Activity from infrequent country](anomaly-detection-policy.md#activity-from-infrequent-country)
  - [Activity from suspicious IP addresses](anomaly-detection-policy.md#activity-from-suspicious-ip-addresses)
  - [Impossible travel](anomaly-detection-policy.md#impossible-travel)

- **Enhanced Salesforce log collection**  
Cloud App Security now supports Salesforce's hourly event log. Hourly event logs give you accelerated, near real-time monitoring of user activities. For more information, see [Connect Salesforce](./connect-salesforce.md).

- **Support for AWS security configuration using a master account**  
Cloud App Security now supports using a master account. Connecting your master account allows you to receive security recommendations for all member accounts across all regions. For more information about connecting with a master account, see [How to connect AWS security configuration to Defender for Cloud Apps](connect-aws.md#how-to-connect-aws-security-configuration-to-defender-for-cloud-apps).

- **Session controls support for modern browsers**  
Cloud App Security session controls now includes support for the new Microsoft Edge browser based on Chromium. While we'll continue supporting the most recent versions of Internet Explorer and the legacy version of Microsoft Edge, the support will be limited and we recommend using the new Microsoft Edge browser.

## Cloud App Security release 165, 166, 167, and 168

Released February 16, 2020

- **New block unsanctioned apps with Microsoft Defender ATP**  
Cloud App Security has extended its native integration with Microsoft Defender Advanced Threat Protection (ATP). You can now block access to apps marked as unsanctioned using Microsoft Defender ATP's network protection capability. For more information, see [Block access to unsanctioned cloud apps](mde-govern.md).

- **New OAuth app anomaly detection**  
We've expanded our current capability to detect malicious OAuth app consent. The new detection is now available out-of-the-box and automatically enabled to alert you when a potentially malicious OAuth app is authorized in your environment. This detection leverages Microsoft security research and threat intelligence expertise to identify malicious apps.

- **Log collector updates**  
The Docker-based log collector was enhanced with the following important updates:

  - Container OS version upgrade

  - Java security vulnerabilities patches

  - Syslog service upgrade

  - Stability and performance improvements

    We strongly recommend that you upgrade your environment to this new version. For more information, see [Log collector deployment modes](discovery-docker.md#deployment-modes).

- **Support for ServiceNow New York**  
Cloud App Security now supports the latest version (New York) of ServiceNow. To learn about securing ServiceNow, see [Connect ServiceNow to Microsoft Cloud App Security](./connect-servicenow.md).

- **Enhanced detection logic: Impossible travel**  
We've updated the detection logic for impossible travel to provide enhanced coverage and better accuracy. As part of this update, we also updated the detection logic for [impossible travel from corporate networks](anomaly-detection-policy.md#impossible-travel).

- **New threshold for activity policies**  
We've added a threshold for [activity policies](user-activity-policies.md) to help you manage the volume of alerts. Policies that trigger a large volume of matches for several days are automatically disabled. If you receive a system alert about this, you should try refining policies by adding additional filters or, if you're using policies for reporting purposes, consider saving them as queries instead.

## Next steps

- For a description of releases prior to those listed here, see [Past releases of Microsoft Cloud App Security](release-note-archive.md).

[!INCLUDE [Open support ticket](includes/support.md)]
