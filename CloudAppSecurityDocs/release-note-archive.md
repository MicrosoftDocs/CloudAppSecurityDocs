---
title: Archive of past updates 
description: This article is an archive that describes updates made in past releases of Defender for Cloud Apps.
ms.date: 05/15/2023
ms.topic: conceptual
---
# Archive of past updates for Microsoft Defender for Cloud Apps

[!INCLUDE [Banner for top of topics](includes/banner.md)]

This article is an archive that describes updates made in past releases of Defender for Cloud Apps. To see the latest what's new list, see [What's new in Defender for Cloud Apps](release-notes.md).

## Updates made in 2022

### Defender for Cloud Apps release 240, 241, 242, and 243

December 25, 2022

- **Azure AD identity protection**  
Azure AD identity protection alerts will arrive directly to Microsoft 365 Defender. The Microsoft Defender for Cloud Apps policies won't affect the alerts in the Microsoft 365 Defender portal. Azure AD identity protection policies will be removed gradually from the cloud apps policies list in the Microsoft 365 Defender portal. To configure alerts from these policies, see [Configure Azure AD IP alert service](/microsoft-365/security/defender/investigate-alerts#configure-aad-ip-alert-service).

### Defender for Cloud Apps release 237, 238 and 239

October 30, 2022

- **Native Integration of Microsoft Defender for Cloud Apps in Microsoft 365 Defender is now in public preview**  
  The entire Defender for Cloud Apps experience in Microsoft 365 Defender is now available for public preview.

  SecOps and security admins will experience these major benefits:

  - Time and costs saved
  - Holistic investigation experience
  - Additional data and signals in advanced hunting
  - Integrated protection across all security workloads

  For more information, see [Microsoft Defender for Cloud Apps in Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-security-center-defender-cloud-apps).

### Defender for Cloud Apps release 236

September 18, 2022

- **Egnyte API connector is generally available**  
The Egnyte API connector is generally available, providing you with deeper visibility and control over your organization's usage of the Egnyte app. For more information, see [How Defender for Cloud Apps helps protect your Egnyte environment](protect-egnyte.md).

### Defender for Cloud Apps release 235

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


### Defender for Cloud Apps release 234

August 21, 2022

- **Feature parity between commercial and government offerings**  
We've consolidated the flow that allows Microsoft Defender for Cloud Apps data to be consumed through Microsoft 365 Defender. To consume this data in Microsoft Defender for Cloud, Microsoft 365 Defender should be used. For more information, see [Microsoft 365 Defender delivers unified XDR experience to GCC, GCC High and DoD customers](https://techcommunity.microsoft.com/t5/public-sector-blog/microsoft-365-defender-delivers-unified-xdr-experience-to-gcc/ba-p/3263702) and [Connect Microsoft 365 Defender data to Microsoft Sentinel](/azure/sentinel/connect-microsoft-365-defender?tabs=MDE#connect-to-microsoft-365-defender).

- **Protecting apps that use non-standard ports with session controls**  
This feature allows Microsoft Defender for Cloud Apps to enforce session policies for applications that use port numbers other than 443.
 Splunk and other applications that use ports other than 443 will now be eligible for session control.  
There's no configuration requirement for this feature.  The feature is currently in preview mode. For more information, see [Session controls](proxy-intro-aad.md#session-controls).

### Defender for Cloud Apps release 232 and 233

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


### Defender for Cloud Apps release 231

July 10, 2022

- **Malware hashes available for SharePoint and OneDrive (Preview)**  
In addition to file hashes available for malware detected in non-Microsoft storage apps, now new malware detection alerts will provide hashes for malware detected in SharePoint and OneDrive. For more information, see [Malware detection](anomaly-detection-policy.md#malware-detection).


### Defender for Cloud Apps release 230

June 26, 2022

- **SaaS Security Posture Management capabilities for Salesforce and ServiceNow**  
Security posture assessments are available for Salesforce and ServiceNow. For more information, see [Security posture management for SaaS apps](security-saas.md).

### Defender for Cloud Apps release 227, 228, and 229

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


### Defender for Cloud Apps release 226

May 1, 2022

- **Improvements in malware detection for non-Microsoft storage apps**  
Defender for Cloud Apps has introduced major improvements in the non-Microsoft storage apps detection mechanism. This will reduce the number of false positive alerts.


### Defender for Cloud Apps release 225

April 24, 2022

- **Support for Rome and San Diego ServiceNow versions**  
The Defender for Cloud Apps connector for ServiceNow now supports Rome and San Diego versions of ServiceNow. With this update, you can protect the latest versions of ServiceNow using Defender for Cloud Apps. For more information, see [Connect ServiceNow to Microsoft Defender for Cloud Apps](connect-servicenow.md).

### Defender for Cloud Apps release 222, 223, and 224

April 3, 2022

- **Updated severity levels for Defender for Cloud Apps anomaly detections**  
The severity levels for Defender for Cloud Apps built-in anomaly detection alerts are being changed to better reflect the risk level in the event of true positive alerts. The new severity levels can be seen in the policies page: <https://portal.cloudappsecurity.com/#/policy>


### Defender for Cloud Apps release 221

February 20, 2022

- **Egnyte app connector available in public preview**  
A new app connector for Egnyte is available in public preview. You can now connect Microsoft Defender for Cloud Apps to Atlassian to monitor and protect users and activities. For more information, see [Connect Egnyte to Microsoft Defender for Cloud Apps (Preview)](connect-egnyte.md).

### Defender for Cloud Apps release 220

February 6, 2022

- **New Cloud discovery log collector**  
The Cloud Discovery log collector has been updated to Ubuntu 20.04. To install it, see [Configure automatic log upload for continuous reports](discovery-docker.md).

### Defender for Cloud Apps release 218 and 219

January 23, 2022

- **Atlassian app connector available in public preview**  
A new app connector for Atlassian is available in public preview. You can now connect Microsoft Defender for Cloud Apps to Atlassian to monitor and protect users and activities. For more information, see [Connect Atlassian to Microsoft Defender for Cloud Apps (Preview)](connect-atlassian.md).

## Updates made in 2021

### Defender for Cloud Apps release 216 and 217

December 26, 2021

- **Non-Microsoft activities in advanced hunting**  
Non-Microsoft apps activities are now included the [CloudAppEvent table](/microsoft-365/security/defender/advanced-hunting-cloudappevents-table) in Microsoft 365 Defender [advanced hunting](/microsoft-365/security/defender/advanced-hunting-overview). For more information, see [the Microsoft 365 Defender Tech Community blog post](https://techcommunity.microsoft.com/t5/microsoft-365-defender-blog/cloudappevents-in-advanced-hunting-now-includes-non-microsoft/ba-p/3036692).

- **NetDocuments API connector is now in general availability**  
The NetDocuments API connector is in general availability, giving you more visibility into, and control over, how your NetDocument app is used in your organization. For more information, see [How Cloud App Security helps protect your NetDocuments](protect-netdocuments.md)

### Defender for Cloud Apps release 214 and 215

November 28, 2021

- **NetDocuments app connector available in public preview**  
A new app connector for NetDocuments is available in public preview. You can now connect Microsoft Defender for Cloud Apps to NetDocuments to monitor and protect users and activities. For more information, see [Connect NetDocuments to Microsoft Defender for Cloud Apps](connect-netdocuments-to-microsoft-defender-for-cloud-apps.md).


### Cloud App Security release 212 and 213

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


### Cloud App Security release 209, 210, and 211

October 10, 2021

- **Slack API connector is now in general availability**  
Slack API connector is in general availability, giving you more visibility in to, and control over, how your app is used in your organization. For more information, see [How Cloud App Security helps protect your Slack Enterprise](protect-slack.md).

- **New warn experience for monitored apps with Microsoft Defender for Endpoint is now in general availability**  
Cloud App Security has extended its native integration with Microsoft Defender for Endpoint. You can now apply soft block on access to apps marked as monitored using Microsoft Defender for Endpoint's network protection capability. End users will be able to bypass the block. The block bypass report will be available in Cloud App Security’s discovered app experience. For more information, see:
  - [Warn and educate users on risky app usage](https://techcommunity.microsoft.com/t5/security-compliance-and-identity/warn-and-educate-users-on-risky-app-usage/ba-p/2630982)
  - [Govern discovered apps using Microsoft Defender for Endpoint](mde-govern.md)

- **New discovered app experience in general availability**  
As part of continuous improvement of our entity experiences, we're introducing a modernized discovered app experience to cover discovered web apps and OAuth apps and provide a unified view of an application entity. For more information, see [Working with the app page](working-with-app-page.md).


### Cloud App Security release 208

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

### Cloud App Security release 207

August 8, 2021

- **New warn experience for monitored apps with Microsoft Defender for Endpoint (public preview)**  
  Cloud App Security has extended its native integration with Microsoft Defender for Endpoint (MDE). You can now apply soft block on access to apps marked as monitored using Microsoft Defender for Endpoint's network protection capability. End users will be able to bypass the block. The block bypass report will be available in Cloud App Security’s discovered app experience. For more information, see:
  - [Warn and educate users on risky app usage](https://techcommunity.microsoft.com/t5/security-compliance-and-identity/warn-and-educate-users-on-risky-app-usage/ba-p/2630982)
  - [Govern discovered apps using Microsoft Defender for Endpoint](mde-govern.md)


### Cloud App Security release 206

July 25, 2021

- **New Cloud Discovery Open Systems log parser**  
Cloud App Security's Cloud Discovery analyzes a wide range of traffic logs to rank and score apps. Now Cloud Discovery includes a built-in log parser to support the Open Systems format. For a list of supported log parsers, see [Supported firewalls and proxies](set-up-cloud-discovery.md#supported-firewalls-and-proxies).

### Cloud App Security release 205

July 11, 2021

- **Zendesk app connector available in public preview**  
A new app connector for Zendesk is available in public preview. You can now connect Microsoft Cloud App Security to Zendesk to monitor and protect users and activities. For more information, see [Connect Zendesk](./connect-zendesk.md).

- **New Cloud Discovery parser for Wandera**  
Cloud Discovery in Cloud App Security analyzes a wide range of traffic logs to rank and score apps. Now, Cloud Discovery includes a built-in log parser to support the Wandera format. For a list of supported log parsers, see [Supported firewalls and proxies](set-up-cloud-discovery.md#supported-firewalls-and-proxies).


### Cloud App Security release 204

June 27, 2021

- **Slack and OneLogin app connectors available in public preview**  
New app connectors are now available for Slack and OneLogin in public preview. You can now connect Microsoft Cloud App Security to Slack and to OneLogin to monitor and protect users and activities. For more information, see [Connect Slack](./connect-slack.md) and [Connect OneLogin](./connect-okta.md).

### Cloud App Security release 203

June 13, 2021

- **Expose verified publisher indicating in O365 OAuth apps**  
Cloud App Security now surfaces whether a publisher of an Microsoft 365 OAuth app has been verified by Microsoft to enable higher app trust. This feature is in a gradual rollout. For more information, see [Working with the OAuth app page](manage-app-permissions.md#working-with-the-oauth-apps-page).

- **Azure Active Directory Cloud App Security admin**  
A Cloud App Security admin role has been added to Azure Active Directory (Azure AD), allowing the assignment of global admin capabilities to Cloud App Security alone via Azure AD. For more information, see [Microsoft 365 and Azure AD roles with access to Cloud App Security](manage-admins.md#office-365-and-azure-ad-roles-with-access-to-cloud-app-security).

- **Export custom tag and app domains per discovered app**  
  **Export to CSV** in the discovered apps page now include the application's custom app tags and associated web domains. For more information, see [Working with discovered apps](discovered-apps.md).

  >[!IMPORTANT]
  >**Enhanced proxy URL for access controls (gradual rollout)**  
  Starting in early July 2021, we will change our access endpoint from `<mcas-dc-id>.access-control.cas.ms` to `access.mcas.ms`. Make sure you update your network appliance rules before the end of June, as this can lead to access issues. For more information, see [Access and session controls](network-requirements.md#access-and-session-controls)


### Cloud App Security release 200, 201, and 202

May 30, 2021

- **Authentication Context (Step-Up Authentication) in public preview**  
We've added the ability to protect users working with proprietary and privileged assets by requiring Azure AD Conditional Access policies to be reassessed in the session. For example, if a change in IP address is detected because an employee in a highly sensitive session has moved from the office to the coffee shop downstairs, step-up can be configured to reauthenticate that user. For more information, see [Require step-up authentication (authentication context) upon risky action](tutorial-step-up-authentication.md).


### Cloud App Security release 199

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
We've expanded the available events in Cloud App Security. Microsoft 365 Defender Advanced Hunting now includes telemetry from Microsoft OneDrive, SharePoint Online, Microsoft 365, Dynamics 365, Dropbox, Power BI, Yammer, Skype for Business, and Power Automate, in addition to Exchange Online and Teams, which were available until now. For more information, see [Apps and services covered](/microsoft-365/security/defender/advanced-hunting-cloudappevents-table#apps-and-services-covered).

### Cloud App Security release 198

Released April 4, 2021

- **Exclusion of Azure Active Directory groups entities from discovery**  
We've added the ability to exclude discovered entities based on imported Azure Active Directory groups. Excluding Azure AD groups will hide all discovery-related data for any users in these groups. For more information, see [Exclude entities](discovered-apps.md#exclude-entities).

- **API connector support for ServiceNow Orlando and Paris versions**  
We have added support for the ServiceNow API connector to the Orlando and Paris versions. For more information, see [Connect ServiceNow to Microsoft Cloud App Security](./connect-servicenow.md).

- **Always apply the selected action even if data cannot be scanned**  
  We've added a new checkbox to [Session policies](session-policy-aad.md) that treats any data that can't be scanned as a match for the policy.

  >[!NOTE]
  >Deprecation notice: this feature replaces both **Treat encrypted as match**, and **Treat files that cannot be scanned as match**, in addition to adding new functionality. New policies will contain the new checkbox by default, deselected by default. Pre-existing policies will be migrated to the new checkbox on May 30. Policies with either or both options selected will have the new option selected by default; all other policies will have it deselected.


### Cloud App Security release 197

Released March 21, 2021

- **Status page deprecation notice**  
On April 29, Cloud App Security will deprecate the service health status page, replacing it with the [Service Health Dashboard](https://admin.microsoft.com/Adminportal/Home?ref=/servicehealth) within the Microsoft 365 Admin portal. The change aligns Cloud App Security with other Microsoft services and provides an enhanced service overview.

  >[!NOTE]
  >Only users with **Monitor service health** permissions can access the dashboard. For more information, see [About admin roles](/microsoft-365/admin/add-users/about-admin-roles).  
  >
  >In the dashboard, you can configure notifications, allowing relevant users to stay updated with the current Cloud App Security status. To learn how to configure email notifications and additional information regarding dashboard, see [How to check Microsoft 365 service health](/microsoft-365/enterprise/view-service-health).

- **OAuth app consents link**  
We've added the ability to scope activity investigations to specific OAuth app's consent activities directly from the OAuth app view. For more information, see [How to investigate suspicious OAuth apps](investigate-risky-oauth.md#how-to-investigate-suspicious-oauth-apps).

### Cloud App Security release 195 and 196

Released March 7, 2021

- **Enhanced Shadow IT discovery with Microsoft Defender for Endpoint**  
We've further improved our Defender for Endpoint integration by leveraging enhanced signals for the Defender agent, providing more accurate app discovery and organizational user context.

  To benefit from the latest enhancements, make sure your organizational endpoints are updated with the latest Windows 10 updates:

  - [KB4601383](https://support.microsoft.com/topic/february-16-2021-kb4601383-os-build-17763-1790-preview-9535653c-8012-47f0-0f90-44cdd57cdc36): Windows 10, version 1809
  - [KB4601380](https://support.microsoft.com/topic/february-16-2021-kb4601380-os-build-18363-1411-preview-2e3c38e1-a947-1033-8006-a30f3806da18): Windows 10, version 1909
  - [KB4601382](https://support.microsoft.com/topic/february-24-2021-kb4601382-os-builds-19041-844-and-19042-844-preview-1a7ed2b4-017d-2644-a1e8-dd6bf14cba76): Windows 10, version 20H2, version [21H1 Insider](https://blogs.windows.com/windows-insider/2021/02/17/announcing-windows-10-insider-preview-build-19043-844-21h1/)

- **Configurable session lifetime**  
We're enabling customers to configure a shorter session lifetime for Conditional Access App Control. By default, sessions proxied by Cloud App Security have a maximum lifetime of 14 days. For more information about shortening session lifetimes, contact us at mcaspreview@microsoft.com.


### Cloud App Security release 192, 193, and 194

Released February 7, 2021

- **Updates to Policies page**  
We've updated the **Policies** page, adding a tab for every policy category. We also added an **All policies** tab to give you a complete list of all your policies. For more information about the policy categorization, see [Policy types](control-cloud-apps-with-policies.md#policy-types).

- **Enhanced Microsoft 365 OAuth apps export**  
We've enhanced the Microsoft 365 OAuth apps activities export to CSV file with the *Redirect URL* of the OAuth apps. For more information about exporting OAuth app activities, see [OAuth app auditing](manage-app-permissions.md#oauth-app-auditing).

- **Updates to the portal interface**  
In the coming months, Cloud App Security will be updating its User Interface to provide a more consistent experience across Microsoft 365 security portals. [Learn more](https://techcommunity.microsoft.com/t5/security-compliance-and-identity/microsoft-cloud-app-security-user-interface-updates/ba-p/2083113)


### Cloud App Security release 189, 190, and 191

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

## Updates made in 2020

### Cloud App Security release 187 and 188

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

### Cloud App Security release 184, 185, and 186

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
  - Microsoft Microsoft 365 Admin Center has been renamed to Office Portal

- **Terminology update**  
We've updated the term **machine** to **device** as part of the general Microsoft effort to align terminology across products.


### Cloud App Security release 182 and 183

Released September 6, 2020

- **Access and session controls for Azure portal GA**  
Conditional Access App Control for the Azure portal is now generally available. For information about configuring these controls, see the [Deployment guide](proxy-deployment-aad.md).


### Cloud App Security release 181

Released August 9, 2020

- **New Cloud Discovery Menlo Security log parser**  
Cloud App Security Cloud Discovery analyzes a wide range of traffic logs to rank and score apps. Now Cloud Discovery includes a built-in log parser to support the Menlo Security CEF format. For a list of supported log parsers, see [Supported firewalls and proxies](set-up-cloud-discovery.md#supported-firewalls-and-proxies).

- **Azure Active Directory (AD) Cloud App Discovery name displays in portal**  
For Azure AD P1 and P2 licenses, we've updated the product name in the portal to **Cloud App Discovery**. Learn more about [Cloud App Discovery](editions-cloud-app-security-aad.md).


### Cloud App Security release 179 and 180

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


### Cloud App Security release 178

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

### Cloud App Security release 177

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


### Cloud App Security release 176

Released May 31, 2020

- **New activity privacy feature**  
We've enhanced your ability to granularly determine which users you want to monitor with the ability to make activities private. This new feature enables you to specify users based on group membership whose activities will be hidden by default. Only authorized admins have the option to choose to view these private activities, with each instance being audited in the governance log. For more information, see [Activity privacy](activity-privacy.md).

- **New integration with Azure Active Directory (Azure AD) Gallery**  
We've leveraged our native integration with Azure AD to give you the ability to navigate directly from an app in the Cloud App Catalog to its corresponding Azure AD Gallery app, and manage it in the gallery. For more information, see [Manage apps with Azure AD Gallery](tutorial-shadow-it.md).

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

### Cloud App Security release 175

Released May 17, 2020

- **New Shadow IT Discovery integration with Corrata (preview)**  
We've added native integration with Corrata providing you with Shadow IT visibility into app use and control over app access. For more information, see [Integrate Cloud App Security with Corrata](corrata-integration.md).

- **New Cloud Discovery log parsers**  
Cloud App Security Cloud Discovery analyzes a wide range of traffic logs to rank and score apps. Now Cloud Discovery includes a built-in log parser to support Corrata and Cisco ASA with FirePOWER 6.4 log formats. For a list of supported log parsers, see [Supported firewalls and proxies](set-up-cloud-discovery.md#supported-firewalls-and-proxies).

- **Enhanced dashboard (gradual rollout)**
As part of our ongoing improvements to the portal design, we are now gradually rolling out the improved Cloud App Security dashboard. The dashboard has been modernized based on your feedback and offers an enhanced user experience with updated content and data. For more information, see [Gradual deployment of our enhanced dashboard](classic-daily-activities-to-protect-your-cloud-environment.md).

- **Enhanced governance: Confirm User Compromised for anomaly detections**  
We've expanded our current governance actions for anomaly policies to include **Confirm User Compromised** allowing you to proactively protect your environment from suspicious user activity. For more information, see [Activity governance actions](governance-actions.md#activity-governance-actions).


### Cloud App Security release 173 and 174

Released April 26, 2020

- **New SIEM agent CEF format for alerts**  
  As part of our effort to enrich the alert information provided in the CEF files used by generic SIEM servers, we've extended the format to include the following client fields:
  - IPv4 address
  - IPv6 address
  - IP address location

    For more information, see [CEF file format](siem.md#sample-cloud-app-security-alerts-in-cef-format).
- **Enhanced detection logic: Impossible travel**  
We've updated the detection logic for impossible travel to provide improved accuracy and reduced alert volume. For more information about this anomaly detection policy, see [Impossible travel](anomaly-detection-policy.md#impossible-travel).

#### Cloud App Security release 172

Released April 5, 2020

- **Enhanced access and session controls with any IdP (preview)**  
Access and session controls now support SAML apps configured with any identity provider. The public preview of this new feature is now gradually rolling out. To configure these controls, see the [Deployment guide](proxy-deployment-aad.md).

- **New bulk deanonymization of users and machines**  
We've expanded and simplified the process of deanonymizing one or more users and machines under investigation. For more information about bulk deanonymization, see [How data anonymization works](cloud-discovery-anonymizer.md#how-data-anonymization-works).


#### Cloud App Security release 170 and 171

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

#### Cloud App Security release 169

Released March 1, 2020

- **New detection for Workday**  
We've expanded our current anomalous behavior alerts for Workday. The new alerts include the following user geolocation detections:
  - [Activity from anonymous IP addresses](anomaly-detection-policy.md#activity-from-anonymous-ip-addresses)
  - [Activity from infrequent country/region](anomaly-detection-policy.md#activity-from-infrequent-country)
  - [Activity from suspicious IP addresses](anomaly-detection-policy.md#activity-from-suspicious-ip-addresses)
  - [Impossible travel](anomaly-detection-policy.md#impossible-travel)

- **Enhanced Salesforce log collection**  
Cloud App Security now supports Salesforce's hourly event log. Hourly event logs give you accelerated, near real-time monitoring of user activities. For more information, see [Connect Salesforce](./connect-salesforce.md).

- **Support for AWS security configuration using a master account**  
Cloud App Security now supports using a master account. Connecting your master account allows you to receive security recommendations for all member accounts across all regions. For more information about connecting with a master account, see [How to connect AWS security configuration to Defender for Cloud Apps](connect-aws.md).

- **Session controls support for modern browsers**  
Cloud App Security session controls now includes support for the new Microsoft Edge browser based on Chromium. While we'll continue supporting the most recent versions of Internet Explorer and the legacy version of Microsoft Edge, the support will be limited and we recommend using the new Microsoft Edge browser.


#### Cloud App Security release 165, 166, 167, and 168

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

## Updates made in 2019

### Cloud App Security release 162, 163, and 164

Released December 8, 2019

- **Change to SIEM activities and alerts in CEF format**  
The [portal URL format (CS1)](siem.md#sample-cloud-app-security-alerts-in-cef-format) for activity and alert information sent by Cloud App Security to SIEMs has changed to `https://<tenant_name>.portal.cloudappsecurity.com` and no longer contains the data center location. Customers using pattern matching for the portal URL should update the pattern to reflect this change.

### Cloud App Security release 160 and 161

Released November 3, 2019

- **Discovery data in Azure Sentinel (preview)**  
Cloud App Security now integrates with Azure Sentinel. Sharing alert and discovery data with Azure Sentinel provides the following benefits:

  - Enable correlation of discovery data with other data sources for deeper analysis.

  - View data in Power BI with out-of-the-box dashboards or build your own visualizations.

  - Enjoy longer retention periods with Log Analytics.

  For more information, see [Azure Sentinel integration](siem-sentinel.md).

- **Google Cloud Platform connector (preview)**  
Cloud App Security is extending its IaaS monitoring capabilities beyond Amazon Web Services and Azure and now supports Google Cloud Platform. This enables you to seamlessly connect and monitor all your GCP workloads with Cloud App Security. The connection provides you with a powerful set of tools to protect your GCP environment, including:

  - Visibility into all activities performed through the admin console and API calls.

  - Ability to create custom policies and use predefined templates to alert on risky events.

  - All GCP activities are covered by our anomaly detection engine and will automatically alert on any suspicious behavior, such as impossible travel, suspicious mass activities, and activity from a new country/region.

  For more information, see [Connect Google Cloud Platform to Microsoft Cloud App Security](./connect-google-gcp.md).

- **New policy templates**  
Cloud App Security now includes new built-in Activity policy templates for Google Cloud Platform security best practices.

- **Enhanced Cloud Discovery log parser**  
Cloud App Security Cloud Discovery analyzes a wide range of traffic logs to rank and score apps. Now Cloud Discovery's built-in log parser supports the Ironport WSA 10.5.1 log format.

- **Customizable user landing page for session controls**  
We've launched the ability for admins to personalize the landing page that your users see when navigating to a app that a Session policy is applied to. You can now display your organization's logo and customize the message shown. To start customizing, go to the **Settings** page, and under **Cloud Access App Control**, select **User monitoring**.

- **New detections**  

  - **Suspicious AWS logging service changes (preview)**: Alerts you when a user makes changes to the CloudTrail logging service. For example, attackers often turn off auditing in CloudTrail to hide the footprints of their attack.

  - **Multiple VM creation activities**: Alerts you when a user performs an unusual number of VM creation activities, compared to the learned baseline. Now applies to AWS.

### Cloud App Security release 159

Released October 6, 2019

- **New Cloud Discovery ContentKeeper log parser**  
Cloud App Security Cloud Discovery analyzes a wide range of traffic logs to rank and score apps. Now Cloud Discovery includes a built-in log parser to support ContentKeeper log formats. For a list of supported log parsers, see [Supported firewalls and proxies](set-up-cloud-discovery.md#supported-firewalls-and-proxies).

- **New Detections**  
The following new anomaly detection policies are available out-of-the-box and automatically enabled:

  - **Suspicious email deletion activity (preview)**  
    Alerts you when a user performs unusual email deletion activities. This policy can help you detect user mailboxes that may be compromised by potential attack vectors such as command-and-control communication (C&C/C2) over email.

  - **Multiple Power BI report sharing (preview)**  
    Alerts you when a user performs an unusual number of Power BI report sharing activities, compared to the learned baseline.

  - **Multiple VM creation activities (preview)**  
    Alerts you when a user performs an unusual number of VM creation activities, compared to the learned baseline. Currently applies to Azure.

  - **Multiple storage deletion activities (preview)**  
    Alerts you when a user performs an unusual number of storage deletion activities, compared to the learned baseline. Currently applies to Azure.

### Cloud App Security release 158

Released September 15, 2019

- **Customize Cloud Discovery executive report name**  
The Cloud Discovery executive report provides you with an overview of Shadow IT use across your organization. You now have the option to customize the report name before generating it. For more information, see [Generate Cloud Discovery executive report](discovered-apps.md#generate-cloud-discovery-executive-report).

- **New policies overview report**  
Cloud App Security detects policy matches and, where defined, logs alerts that you can use to understand your cloud environment more deeply. Now you can export a policies overview report showing aggregated alert metrics per policy to help you monitor, understand, and customize your policies to better protect your organization. For more information about exporting the report, see [Policies overview report](control-cloud-apps-with-policies.md#policies-overview-report).

### Cloud App Security release 157

Released September 1, 2019

- **Reminder: End of support for TLS 1.0 and 1.1 on September 8**  
Microsoft is moving all its online services to Transport Layer Security (TLS) 1.2+ to provide best-in-class encryption. Therefore, as of September 8, 2019 Cloud App Security will no longer support TLS 1.0 and 1.1 and connections using these protocols will not be supported. For more information about how the change affects you, see [our blog post](https://techcommunity.microsoft.com/t5/security-compliance-and-identity/end-of-support-for-tls-1-0-and-1-1-in-microsoft-cloud-app/ba-p/770507).

- **New detection – Suspicious Microsoft Power BI sharing (preview)**  
The new suspicious Power BI report sharing policy is now available out-of-the-box and automatically enabled to alert you when a potentially sensitive Power BI report is suspiciously shared outside of your organization.

- **New export feature for OAuth app auditing**  
Cloud App Security audits all OAuth authorization activities to provide you with comprehensive monitoring and investigation of activities performed. Now you can also export the details of users that authorized a specific OAuth app, providing you with additional information on the users, which you can then use for further analysis.

- **Enhanced Okta event auditing**  
Cloud App Security now supports the new System Log API released by Okta. For more information about connecting Okta, see [Connect Okta](./connect-okta.md).

- **Workday connector (preview)**  
A new app connector is now available for Workday. You can now connect Workday to Cloud App Security to monitor activities and protect its users and activities. For more information, see [Connect Workday](./connect-workday.md).

- **Enhanced assessment for the "Password policy" risk factor**  
The Cloud App Catalog now provides granular assessment for the **Password policy** risk factor. By hovering over its information icon, you can see a breakdown of the specific policies that are enforced by the app.

### Cloud App Security release 156

Released August 18, 2019

- **New Cloud Discovery log parsers**  
Cloud App Security Cloud Discovery analyzes a wide range of traffic logs to rank and score apps. Now Cloud Discovery includes a built-in log parser to support Stormshield and Forcepoint LEEF log formats.

- **Activity log enhancements**  
Cloud App Security now provides you with greater visibility into unclassified activities performed by apps in your environment. These activities are available in the Activity log and also in Activity policies. To see unclassified activities, in the **Type** filter select **Unspecified**. For more information about activity filters, see [Activity filters and queries](activity-filters-queries.md).

- **Risky user investigation enhancement**  
Cloud App Security provides the ability to identify risky users on the **Users and accounts** page by specific groups, apps, and even roles. Now you can also investigate the users in your organization by their **Investigation priority** score. For more information, see [Understand the investigation priority score](tutorial-ueba.md#risk-score).

- **Activity policy enhancements**  
You can now create activity policy alerts based on activity objects. For example, this capability allows you to create alerts on changes to Azure Active Directory administrative roles. For more information about activity objects, see [Activity filters](activity-filters-queries.md#activity-filters).

### Cloud App Security release 155

Released August 4, 2019

- **New policy templates**  
Cloud App Security now includes new built-in Activity policy templates for AWS security best practices.

- **Notice: End of support for TLS 1.0 and 1.1 on September 8**  
Microsoft is moving all its online services to Transport Layer Security (TLS) 1.2+ to provide best-in-class encryption. Therefore, as of September 8, 2019 Cloud App Security will no longer support TLS 1.0 and 1.1 and connections using these protocols will not be supported. For more information about how the change affects you, see [our blog post](https://techcommunity.microsoft.com/t5/security-compliance-and-identity/end-of-support-for-tls-1-0-and-1-1-in-microsoft-cloud-app/ba-p/770507).

- **Enhanced logic for interactive sign-in activities (gradual rollout)**  
We are gradually rolling out new logic to identify if an Azure Active Directory sign-in activity is interactive. The new logic enhances Cloud App Security's ability to only surface sign-in activities that are initiated by a user.

### Cloud App Security release 154

Released July 21, 2019

- **Onboard and deploy Conditional Access App Control for any app is now GA**  
Since previewing Conditional Access App Control for any app last month, we've received tremendous feedback and are excited to announce GA. This new capability allows you to deploy any web app to work with session and access policies, enabling powerful real-time monitoring and control.

- **Security configuration assessment for AWS**  
Cloud App Security is gradually rolling out the ability to get a security configuration assessment of your Amazon Web Services environment for CIS compliance, and provides recommendations for missing configurations and security controls. This ability provides organizations with a single view for monitoring the compliance status for all connected AWS accounts.

- **OAuth app anomaly detections**  
We've expanded our current capability to detect suspicious OAuth apps. Four new detections are now available out-of-the-box that profile the metadata of OAuth apps authorized in your organization to identify ones that are potentially malicious.

### Cloud App Security release 153

Released July 7, 2019

- **Enhanced Dropbox support**  
Cloud App Security now supports the **Trash** governance action for Dropbox – This governance action can be used manually or automatically as part of a file policy.
- **New featured apps for Cloud Access App Control**  
Conditional Access App Control for the following featured apps is now generally available:

  - OneDrive for Business
  - SharePoint Online
  - Azure DevOps
  - Exchange Online
  - Power BI

- **Authorize files identified as malware**  
Cloud App Security scans files from your connected apps for DLP exposure and malware. You can now authorize files that have been identified as malware but were confirmed safe following an investigation. Authorizing a file removes it from the malware detection report and suppresses future matches on this file. For more information about malware detection, see [Cloud App Security anomaly detection](anomaly-detection-policy.md).

### Cloud App Security release 152

Released June 23, 2019

- **Deploy Conditional Access App Control for any app (preview)**  
We are excited to announce that we've expanded our support for Conditional Access App Control to any web app, in addition to the rich support we already offer for [our featured applications](proxy-intro-aad.md). This new capability allows you to deploy any web app to work with session and access policies, enabling powerful real-time monitoring and control. For example, you can protect downloads with Azure Information Protection labels, block upload of sensitive documents, providing auditing, among many others.
- **Portal activity auditing**  
Cloud App Security audits all admin activity in the portal to provide you with comprehensive monitoring and investigation of activities performed. Now you can also export up to 90 days of activities for further investigation and analysis, for example, auditing of an admin investigating a specific user or viewing specific alerts. To export the log, go to the **Manage admin access** settings page.
- **Custom session sign out from Cloud App Security portal**  
You can now configure automatic sign out of admin sessions to the portal that are idle for longer than a specified period.

### Cloud App Security release 151

Released June 9, 2019

- **Hybrid UEBA - Native integration with Azure ATP (preview)**  
Cloud App Security now natively integrates with Azure ATP to provide a single view of identity activities in both cloud apps and your on-premises network. For more information, see [Azure Advanced Threat Protection integration](mdi-integration.md).
- **UEBA enhancements**  
To help you identify threats that fall below the radar, Cloud App Security now uses unique profiling to provide risk scores for individual activities and alerts. The risk scores can be used to identify activities that aren't suspicious enough on their own to trigger alerts. However, by aggregating the risk scores to a user's **Investigation priority score**, Cloud App Security helps you identify risky behavior and focus your investigation. These new capabilities are now available on our redesigned user page.
- **New risk factor added to Cloud App Catalog**  
The Cloud App Catalog now includes the Disaster Recovery Plan risk factor to enable you to assess the apps in the Cloud App Catalog for business continuity support.
- **Microsoft Flow connector GA**  
Since previewing Microsoft Cloud App Security's support for the Microsoft Flow connector last year, the connector is now generally available.
- **Automated governance enhancement for File policies**  
Cloud App Security now supports configuring the **Trash** governance action for File policies – This governance action provides you with the ability to automatically move files to the trash folder.
- **Enhanced Google Drive support**  
Cloud App Security now supports the **Trash** governance action for Google Drive – This governance action provides you with the ability to move Google Drive files to the trash folder.
- **New permission for App admin and Group admin roles**  
*App/instance admin* and *User group admin* roles now support read-only access.
- **Legacy authentication sign-in activities (gradual rollout)**  
Cloud App Security now surfaces Azure Active Directory sign-in activities that use legacy protocols such as ActiveSync. These sign-in activities can be viewed in the activity log and can be used when configuring policies.

### Cloud App Security release 150

Released May 26, 2019

- **Alerts export improvement**  
When you export alerts to CSV from the **Alerts** page, the results will now include the date of the alert resolution or dismissal.

### Cloud App Security release 148 and 149

Released May 12, 2019

- **Webex app connector available**  
A new app connector is now available for Cisco Webex Teams in Public Preview. You can now connect Microsoft Cloud App Security to Cisco Webex Teams to monitor and protect its users, activities, and files. For more information, see [Connect Webex](./connect-webex.md)

- **Microsoft Data Classification Service new locations**  
[Microsoft Data Classification Service](dcs-inspection.md) is now available in four new locations - Australia, India, Canada, and Japan. If your Office tenant is located in these locations, you can now utilize Microsoft Data Classification Service as the content inspection method in Microsoft Cloud App Security file policies.

- **Discovery of Shadow PaaS and IaaS**  
Microsoft Cloud App Security has extended its Cloud Discovery capabilities and is now also providing Shadow IT for resources that are hosted on IaaS and PaaS solutions such as Microsoft Azure, Amazon Web Services, and Google Cloud Platform. Cloud Discovery now provides you with visibility into which custom apps run on top of your IaaS and PaaS, storage accounts that are being created, and more. Use this new capability in order to discover what resources exist, who accesses each of them, and how much traffic is transmitted.

- **App attestation**  
Microsoft Cloud App Security compliance and risk assessment now allows cloud providers to attest their app to be up to date in Cloud App Catalog. This pilot allows cloud providers to fill out a self-attestation questionnaire based on the Cloud App Catalog's risk attributes to make sure that their risk assessment in Cloud App Security is accurate and up-to-date. Users can then get an indication as to which risk attributes were attested by the provider (rather than assessed by the Cloud App Security team) and when each attribute was submitted by the provider. For more information, see [Attest your app](attest-your-app.md).

- **Microsoft 365 workload granularity**  
When connecting Microsoft 365 to Microsoft Cloud App Security, you now have control over which workloads you want to connect. For example, customers only interested in connecting Microsoft 365 for activity monitoring can now do so during the connection process, or by editing an existing Microsoft 365 connector. As part of this change, OneDrive and SharePoint will no longer be shown as separate connectors but will be included in the Microsoft 365 connector as the *Microsoft 365 files* workload. Customers with an existing Microsoft 365 connector are not impacted by this change.

- **Enhanced Teams support**  
You can now monitor and block message sending in the Teams web app in real time, by configuring a Session policy based on sensitive content.

### Cloud App Security release 147

Released April 14, 2019

- **New Cloud Discovery log parser**  
Cloud App Security Cloud Discovery now includes a built-in log parser to support the Palo Alto LEEF log format.

- **Session policies updates**  
  - **Additional content inspection method for session policies**:  When setting a session policy, you now have the option to choose Data Classification Service as a content inspection method for files. Data Classification Service offers the user a wide range of built-in sensitive types to use to identify sensitive information.
  - **Enhanced file permissions control in session policies**:  When you're creating a session policy to control downloads using Cloud App Security, you can now automatically apply permissions per user, such as read-only, to the documents upon download from your cloud apps. This provides a much greater level of flexibility and the ability to protect information beyond your pre-configured corporate labels.
  - **Large file download control**:  When content inspection is enabled in session policies, you can now control what happens when a user tries to download a very large file. If the file is too big to scan on download, you can choose whether it will be blocked or allowed.

### Cloud App Security release 146

Released March 31, 2019

- **Impossible travel enhancement**  
Impossible travel detection was enhanced with dedicated support for neighboring countries/regions.
- **Additional attribute support for the generic CEF parser**  
The Cloud Discovery log parser support for generic CEF format was enhanced to support additional attributes.
- **Scoped access to Cloud Discovery reports**  
In addition to the Discovery Admin role, you can now scope access to specific Discovery reports. This enhancement enables you to configure privileges to data of specific sites and business units.
- **New role support: Global reader**  
Microsoft Cloud App Security now supports the Azure AD Global Reader role. The Global reader has full read-only access to all aspects of Microsoft Cloud App Security, but cannot change any settings or take any actions.

### Cloud App Security release 145

Released March 17, 2019

- **Microsoft Defender ATP integration is now GA**  
Last year we announced [integration with Windows Defender Advanced Threat Protection](https://techcommunity.microsoft.com/t5/security-compliance-and-identity/microsoft-cloud-app-security-and-windows-defender-atp-better/ba-p/263265) that enhances the Discovery of Shadow IT in your organization, and extends it beyond the corporate network. [Enabled with a single click](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RWtNmG), we are excited to announce that this unique integration is now generally available.
- **Dynamics 365 CRM support**  
Cloud App Security added real-time monitoring and control for Dynamics 365 CRM, to enable you to protect your business applications and the sensitive content stored within these apps. For more information about what can be done with Dynamics 365 CRM, see [this article](proxy-intro-aad.md#how-it-works).

### Cloud App Security release 144

Released March 3, 2019

- **Unified SecOps Investigation for Hybrid Environments**  
Because many organizations have hybrid environments, attacks start in the cloud and then pivot to on-premises, meaning SecOps teams need to investigate these attacks from multiple places. By combining signals from cloud and on-premises sources including Microsoft Cloud App Security, Azure ATP, and Azure AD Identity Protection, Microsoft empowers security analysts by providing unified identity and user information, in a single console, ending the need to toggle between security solutions. This gives your SecOps teams more time and the right information to make better decisions, and actively remediate the real identity threats and risks. For more information, see [Unified SecOps Investigation for Hybrid Environments](https://techcommunity.microsoft.com/t5/security-compliance-and-identity/unified-secops-investigation-for-hybrid-environments/ba-p/360850)

- **Sandboxing capabilities for malware detection** (gradual rollout)  
Cloud App Security's malware detection capabilities are being expanded to include the ability to identify zero-day malware through advanced Sandboxing technology.  
As part of this capability, Cloud App Security automatically identifies suspicious files and detonates them to look for suspicious file behavior and indicators that the file has malicious intent (malware).
As part of this change, malware detection policies now include a Detection type field that enables you to filter by threat intelligence as well as sandboxing.

- **Conditional Access updates**  
Conditional Access App Control added the ability to monitor and block the following activities:
  - File uploads in any app - enabling scenarios such as preventing upload of known malware extensions, and ensuring users protect files with Azure Information Protection prior to upload.
  - Copy and paste in any app - rounding out robust controls of data exfiltration that already included controlling download, print, and custom activities such as share.
  - Send message - ensuring that personal data such as passwords is not shared in popular collaboration tools such as Slack, Salesforce, and Workplace by Facebook.
  - Session Policies now include built-in templates to enable your organization to effortlessly enable popular real-time monitoring and control over your sanctioned apps, such as **Block upload based on real-time content inspection**.

### Cloud App Security release 143

Released February 17, 2019

- **Scope deployment for app instances**  
Scoped deployment can now be configured at the app instance level, allowing for greater granularity and control.
- **Role enhancements**  
  - The data admin and security operator Microsoft 365 roles are now supported in Cloud App Security. The data admin role enables users to manage everything file related, as well as view the Cloud Discovery reports. Security operators have permission to manage alerts and view policy configuration.
  - The security reader role now has the ability to configure the SIEM agent, allowing better permission scoping.

- **Microsoft Flow support**  
Cloud App Security now monitors user activities in Microsoft Flow. The activities supported are the activities reported by Flow to the Microsoft 365 audit log.

- **Alert entity grouping**  
The **Alert** page now groups related entities that were involved in an alert to aid in your investigation.

### Cloud App Security release 142

Released February 3, 2019

- **Session policy configuration in Azure AD**  
You can now configure session policies to monitor users or block downloads in real-time, directly in Azure AD conditional access. You can still configure advanced session policies directly in Cloud App Security. To walk through this deployment, see [Deploy Conditional Access App Control for Azure AD apps](proxy-deployment-aad.md).

- **Suggested and Saved queries for OAuth apps**  
Suggested queries have been added to the OAuth apps page provide out-of-the-box investigation templates to filter your OAuth apps. Suggested queries include custom filters to identify risky apps such as apps authorized by administrators. Saved queries enable you to save custom queries for future use, similar to saved queries available today in the Activity log and Discovery pages.

- **Microsoft 365 auditing default configuration**  
If you want to enable monitoring of Microsoft 365 activities in Cloud App Security, you are now required to enable auditing in the [Office Security and Compliance Center](/microsoft-365/compliance/turn-audit-log-search-on-or-off#turn-on-audit-log-search), this is a result of a [change to Microsoft 365 auditing](/office/office-365-management-api/troubleshooting-the-office-365-management-activity-api#frequently-asked-questions-about-the-office-365-management-activity-api). This change only needs to be performed if you haven't already enabled monitoring of Microsoft 365 activities in Cloud App Security.

- **Enhanced Box support**  
Cloud App Security now supports two new governance actions for Box:

  - **Expire shared link** – This governance action provides you with the ability to set an expiration date for a shared link after which it will no longer be active.

  - **Change sharing link access level** – This governance action provides you with the ability to change the access level of the shared link between company only, collaborators only, and public.

- **Multi-location support in OneDrive**  
Cloud App Security now provides full visibility into OneDrive files, even if they are dispersed across multiple geographic locations. Protection is now available for files located in the additional locations as well as the main location.

- **Portal navigation enhancement**  
The Cloud App Security portal was enhanced to provide better navigation and better align Cloud App Security with Microsoft's other security services, for streamlined ease-of-use.

### Cloud App Security release 141

Released January 20, 2019

- **Cloud risk assessment enhancements**  
  - Cloud app risk assessment was enhanced with two new experiences.
    - A new **Data type** attribute assesses what kind of content users can upload to the app. You can use this attribute to assess an app according to the sensitivity of each data type in your organization.
    - To get a more comprehensive risk overview of an app, you can now easily pivot from the app's risk assessment to the risk assessment of hosting company by clicking on the **Hosting company** attribute.

- **Enhanced file context for anomaly detection alert investigation**  
  - Anomaly detection investigation was enhanced to enable you to see additional insight associated with the files that are involved in an alert. When alerts are triggered for file-related unusual activity alerts (Download, Share, Delete), this drill-down is available. For example, if most of the affected files are from the same folder or share the same file extension, you will see these insights in the Additional risk section of the alert.

- **Queries for file investigation**  
  - Cloud App Security's ability to create and save custom queries was extended to the **Files** page. Queries in the **File** page enable you to create query templates that can be reused for deep-dive investigation.

### Cloud App Security release 139, 140

Released January 6, 2019

- **Change in file detection**  
Files shared with everyone in SharePoint and One Drive are now considered **internal** [due to changes made to SharePoint and One Drive](/office365/troubleshoot/access-management/grant-everyone-claim-to-external-users). So if a file is detected that is shared with everyone, it will now be treated as an internal file – this affects how the file is handled by policies and shown in the files page.

- **Change in file monitoring**  
The default file monitoring behavior changed for new and idle customers. You will now need to turn on file monitoring to enable the feature, via **Settings** > **Files**. Existing active customers will not be affected by this change.

- **Advanced tuning for anomaly detection policies**  
You can now affect the anomaly detection engine to suppress or surface alerts according to your preferences.
  - In the Impossible Travel policy, you can set the sensitivity slider to determine the level of anomalous behavior needed before an alert is triggered.
  - You can also configure whether the alerts for Activity from infrequent country/region, anonymous IP addresses, suspicious IP addresses, and  impossible travel should analyze both failed and successful logins or just successful logins.

- **Support for multiple trust chains**  
Conditional Access App Control now supports adding and using multiple trusted root or intermediate certificates as a form of device management.

- **New Cloud Discovery role** (gradual rollout)  
Cloud App Security now provides a new admin role for Cloud Discovery users. This role can be used in order to scope the access of an admin user to only Cloud Discovery settings and data within the Cloud App Security portal.

- **Support for Microsoft Purview Information Protection unified labels** (gradual rollout)  
Cloud App Security now supports Microsoft Purview Information Protection unified labels. For customers that already [migrated their classification labels for the Microsoft 365 Security and Compliance Center](/azure/information-protection/configure-policy-migrate-labels), Cloud App Security will identify and work with these labels as described in [Integrating with Azure Information Protection](azip-integration.md).

**Support for PDF file labeling** (gradual rollout)  
For customers using unified labels, Cloud App Security now supports autolabeling for PDF files.

## Updates made in 2018

### Cloud App Security release 138

Released December 9, 2018

- **Automatic log upload using Docker on Windows**  
Cloud App Security now supports automatic log upload for Windows 10 (fall creators update) and Windows Server, version 1709 and later using a Docker for Windows. For more information and instructions on how this can be configured, see [Docker on Windows on-premises](discovery-docker-windows.md).

- Cloud App Security integrates with [Microsoft Flow](/power-automate/getting-started) to provide custom alert automation and orchestration playbooks. For more information and integration instructions, see [Integrating with Microsoft Flow](flow-integration.md).

### Cloud App Security release 137

Released November 25, 2018

- **Added support for Dynamics**  
Cloud App Security now includes support for the Microsoft Dynamics activities that are supported in the Microsoft 365 audit log.

- **Scanning encrypted content (preview)**  
Cloud App Security now enables you to scan content that is protected by Azure Information Protection protection labels. This will allow you to find sensitive content, even in files that have already been encrypted by Azure Information Protection.

- **Heads up – new terminology!**  
The name of the App permissions capabilities was changed for clarity – it is now called **OAuth apps**.

### Cloud App Security release 136

Released November 11, 2018

- **Cloud Discovery updates**  
The custom log parser was enhanced to support additional and more complex web traffic logs formats. As part of these enhancements users can now input custom headers for headerless CSV log files, use special delimiters for key-value files, process Syslog file format, and more.

- **New anomaly detection policies**  
Suspicious inbox manipulation rules: This policy profiles your environment and triggers alerts when suspicious rules that delete or move messages or folders are set on a user's inbox. This may indicate that the user's account is compromised, that messages are being intentionally hidden, and that the mailbox is being used to distribute spam or malware in your organization.

- **Support for groups in app permission policies**  
Cloud App Security now gives you the ability to define app permission policies more granularly, based on the group memberships of the users who authorized the apps. For example, an admin can decide to set a policy that revokes uncommon apps if they ask for high permissions, only if the user who authorized the permissions is a member of the administrators group.

- **Conditional Access App Control now integrates with your on-prem apps via Azure Active Directory Application Proxy**  
  - The [Azure AD Application Proxy](/azure/active-directory/app-proxy/application-proxy) provides single sign-on and secure remote access for your web apps hosted on-prem.
  - These on-prem web apps can now be routed to Microsoft Cloud App Security via Azure AD conditional access to provide real-time monitoring and controls, via [access](access-policy-aad.md) and [session](session-policy-aad.md) policies.

### Cloud App Security release 133, 134, 135

Released October, 2018

- **New anomaly detection policies being gradually rolled out**  
  - The new Data exfiltration to unsanctioned apps policy is automatically enabled to alert you when a user or IP address uses an app that is not sanctioned to perform an activity that resembles an attempt to exfiltrate information from your organization.
    - The new Multiple delete VM activities policy profiles your environment and triggers alerts when users delete multiple VMs in a single session, relative to the baseline in your organization.

- **Data classification service available for APAC**  
  - Data classification service content inspection is now available for APAC customers. For a list of full regional support, see [Microsoft Data Classification Services integration](dcs-inspection.md).

- **Cloud Discovery support for i-Filter**  
  - The Cloud App Security Cloud Discovery feature now has enhanced support for the i-Filter syslog parser.

### Cloud App Security release 132

Released September 25, 2018

- **Conditional Access App Control for Microsoft 365 is now in Public Preview**  
  - Conditional Access App Control now also supports Microsoft 365 and any app that is configured with Open ID Connect.
  - Provide feedback from within a session: This new tool enables you to provide feedback to the Cloud App Security team about the performance of an application under session control, directly from within the session.

- **Native integration with Microsoft Defender ATP for Shadow IT Discovery beyond your corp**  
  - Microsoft Cloud App Security now natively integrates with Windows Defender Advanced Threat Protection (ATP) to provide deploymentless Shadow IT discovery capabilities for on and off corporate network use of cloud apps.  This enables you to perform Cloud Discovery on machines, even when they are not within your corporate network. It also enables machine-based investigation: after you identify a risky user, you can then check all the machines the user accessed to detect potential risks; if you identify a risky machine, you can check all the users who used it to investigate potential risks. For more information, see  Windows Defender Advanced Threat Protection integration with [Microsoft Cloud App Security](mde-integration.md).

- **Content inspection for encrypted files**  
  - Cloud App Security now supports content inspection of protected files that are encrypted that were protected using Azure Information Protection. You can now inspect these encrypted files for reclassification proposes and identify additional DLP exposure and security policy violations.

### Cloud App Security release 131

Released September 2, 2018

- **Automatically revoke permissions on risky OAuth apps**  
You can now control which OAuth apps your users have access to, by revoking app permission for OAuth apps on Office, Google, or Salesforce. When creating an **App permission policy**, you can now set the policy to revoke an app's permission.

- **Cloud Discovery additional built-in parser supported**  
Cloud Discovery now supports the Forcepoint Web Security Cloud log format.

### Cloud App Security release 130

Released August 22, 2018

- **New menu bar**  
To provide a more consistent admin experience across Microsoft 365 products and enable you to more easily pivot between Microsoft security solutions, the Cloud App Security portal menu bar moved to the left side of the screen. This consistent navigation experience helps you orient yourself when moving from one Microsoft security portal to another.

- **Impact OAuth app score**  
You can now send the Cloud App Security team feedback to let us know if there's an OAuth app discovered in your organization that seems malicious. This new feature enables you to be part of our security community and enhance OAuth app risk score and analysis. For more information, see [Manage app permiOAuth appsssions](manage-app-permissions.md).

- **New Cloud Discovery parsers**  
The Cloud Discovery parsers now support iboss Secure Cloud Gateway and Sophos XG.

### Cloud App Security release 129

Released August 5, 2018

- **New anomaly detection policies - suspicious email rules**  
New anomaly detection policies were added that detect suspicious email forwarding rules, for example, if a user created an inbox rule that forwards a copy of all emails to an external address.

- This release includes fixes and improvements for multiple issues.

### Cloud App Security release 128

Released July 22, 2018

- **OAuth apps actions across multiple apps**  
For OAuth apps that have been granted app permissions, you can now ban or approve multiple apps in a single action. For example, you can review all the apps that have been granted permission by users in your organization, select all the apps you want to ban, and then click ban apps to revoke all consent granted and will no longer allow users to grant permission to those apps.  For more information, see [Manage OAuth apps](manage-app-permissions.md).

- **Enhanced support for Azure applications**  
For Azure, we are now gradually rolling out the ability to detect applications as user account activities performed by the Azure applications (both internal and external). This enables you to create policies that will alert you if an application performs unexpected and unauthorized activities. For more information, see [Connect Azure to Microsoft Cloud App Security](./connect-azure.md).

- **Data Classification Engine updated with new GDPR sensitive types**  
The [Cloud App Security Data Classification Service](dcs-inspection.md) added new GDPR sensitive types to our Data Classification Engine to enable you to detect GDPR related content in your files.

- **Updates to the Cloud App Catalog**  
The Cloud App Catalog now includes a legal risk category (in addition to General, Security and Compliance) to help you manage data privacy and ownership compliance, including GDPR readiness.
To help with assessing the GDPR readiness of each cloud app, the new risk category contains the GDPR readiness statement of the cloud service and status of each GDPR framework control.
Note that as part of this improvement, the following risk attributes were moved from other risk category to the Legal category:
  - DMCA
  - Data ownership
  - Data retention policy

  In addition, the new risk category is scored separately so you can configure the score weighting according to your preferences and priorities. For more information, see [Risk score](risk-score.md).

- **New suggested query: GDPR ready**  
There is a new suggested query to enable you to identify discovered apps that are GDPR ready. Because GDPR recently became a top priority for security admins, this query helps you easily identify apps that are GDPR ready and mitigate threat by assessing the risk of those that aren't.

### Cloud App Security release 127

Released July 8, 2018

- You now have the ability to see generic activities for Microsoft 365. In the **Activity log** and in **Activity policies** you can now filter the Microsoft 365 activities for **Unspecified** activities. Reviewing these activities enables you to investigate information about activities performed that aren't yet classified by type in Cloud App Security, and you can use these activities to send requests to the Cloud App Security team to create new activity types based on these activities.

### Cloud App Security release 126

Released June 24, 2018

- **Conditional Access App Control GA**  
Microsoft Cloud App Security's Conditional Access App Control (reverse proxy) is now generally available for any SAML applications. Conditional Access App Control integrates directly with your Azure AD conditional access policies to **monitor and control your users' sessions in real time**, while enabling them to be productive. Since first previewing the feature, many features and improvements have been made, including:
  - The ability to create an [access policy](access-policy-aad.md) to manage access to the same apps from native clients, in addition to creating a session policy for browser traffic.
  - The app onboarding process was streamlined to support custom SAML applications in your organization.
  - As part of the Azure worldwide network, the integration and interface have been improved for a seamless experience for users located anywhere in the world.

- **Content inspection with Microsoft Data Classification Service GA**  
Microsoft Cloud App Security integration with Microsoft Data Classification Services is now generally available. This integration enables you to utilize the Microsoft Data Classification Service natively, to classify the files in your cloud apps. For more information, see [Microsoft Data Classification Services integration](dcs-inspection.md). This feature is currently only available in the US and Europe (excluding France).

- **Cloud Discovery executive report**  
Microsoft Cloud App Security is gradually rolling out the ability to generate a Cloud Discovery executive PDF report. This report provides an overview of the Shadow IT use that was identified in your organization, highlighting the top apps and users in use overall and in leading categories, and focuses on the risk that Shadow IT poses in your organization. In addition, the report provides a list of recommendations for how to improve visibility into, and control over, Shadow IT in your organization. Use this report to make sure that potential risks and threats are removed and that your organization remains safe and secure.

- **Malware detection**  
The malware detection capability is being gradually rolled out that **automatically detects malicious files in your cloud storage**, regardless of the file type. Microsoft Cloud App Security uses Microsoft's threat intelligence to recognize whether certain files are associated with known malware attacks or are potentially malicious. For more information, see [Anomaly detection policies](anomaly-detection-policy.md).

- **Automated remediation for suspicious activities**  
You can now set automatic remediation actions for suspicious session triggered by the anomaly detection policies. This enhancement enables you to be alerted instantly when a breach occurs and **apply governance actions automatically**, such as suspend user. For more information, see [Anomaly detection policies](anomaly-detection-policy.md#enable-automated-governance).

- **Security configuration assessment for Azure**  
Microsoft Cloud App Security is gradually rolling out the ability to get a security configuration assessment of your Azure environment, and provides recommendations for missing configuration and security control. For example, it will let you know if you are missing MFA for administrative users. For more information, see [Cloud Security Posture Management integration](security-config.md).

- **Automated detection of risky OAuth Apps**  
In addition to the existing investigation of OAuth apps connected to your environment, Microsoft Cloud App Security is now gradually rolling out the ability to set automated notifications to let you know when an OAuth app meets certain criteria. For example, you can automatically be alerted when there are apps that require a high permission level and were authorized by more than 50 users. For more information, see [App permission policies](app-permission-policy.md).

- **Managed Security Service Provider management (MSSP) support**  
Microsoft Cloud App Security now provides a better management experience for MSSPs. External users can now be configured as administrators and assigned any of the [roles currently available in Microsoft Cloud App Security](manage-admins.md). In addition, to enable MSSPs to provide services across multiple customer tenants, Administrators who have access rights to more than one tenant can now easily switch tenants within the portal. For information about managing admins, see [Manage admins](manage-admins.md).

- **Integration with external DLP GA**  
Microsoft Cloud App Security allows you to [leverage existing investments in third-party classification systems](icap-stunnel.md) such as Data Loss Prevention (DLP) solutions, and enables you to scan the contents of cloud applications using existing deployments running in your environment. For more information, see [External DLP integration](icap-stunnel.md).

### Cloud App Security release 125

Released June 10, 2018

- **New investigation capability by top users:**  
Microsoft Cloud App Security added a new investigation card to the dashboard that shows top users by the number of open threat detection alerts. This investigation card enables you to focus your threat investigation on users with the highest number of suspicious sessions.

- **Support for AWS S3 buckets:**  
Microsoft Cloud App Security can now detect AWS S3 buckets and their sharing levels. This provides alerts and visibility into publicly accessible AWS buckets. This also enables you to create policies based on buckets and apply automatic governance. In addition, there is a new policy template available called **Publicly accessible S3 buckets (AWS)** that you can use to easily create a policy to govern your AWS storage. In order to enable these new capabilities, make sure you update your AWS connected apps by adding the new permissions described in [Connect AWS](./connect-aws.md).

- **Admin privileges based on user groups**:  
You can now set administrative permissions to Microsoft Cloud App Security admins per user group. For example, you can set a specific user as an administrator for only users in Germany. This would enable the user to view and modify information in Microsoft Cloud App Security only for the user group "Germany - all users." For more information, see [Managing admin access](manage-admins.md).

### Cloud App Security release 124

Released May 27, 2018

- **GDPR risk assessment added to Cloud App Catalog**  
13 new risk factors were added to Microsoft Cloud App Security. These risk factors follow the checklist of the GDPR framework to enable you to assess the apps in the Cloud App Catalog according to the GDPR regulations.

- **Integrate with Microsoft Data Classification Service**  
Microsoft Cloud App Security now enables you to utilize the Microsoft Data Classification Service natively, to classify the files in your cloud apps.
The Microsoft Data Classification Service provides a unified information protection experience across Microsoft 365, Azure Information Protection, and Microsoft Cloud App Security. It allows you to extend the same data classification framework to the third-party cloud apps that are protected by Microsoft Cloud App Security, leveraging the decisions you already made across an even greater number of apps.

- **Connect to Microsoft Azure** (gradual rollout)  
Microsoft Cloud App Security is extending its IaaS monitoring capabilities beyond Amazon Web Services and now supports Microsoft Azure. This enables you to seamlessly connect and monitor all your Azure subscriptions with Cloud App Security. This connection provides you with a powerful set of tools to protect your Azure environment, including:

  - Visibility into all activities performed through the portal

  - Ability to create custom policies to alert on unwanted behavior, as well as the ability to automatically protect possible risky users by suspending, or forcing them to sign in again.

  - All Azure activities are covered by our anomaly detection engine and will automatically alert on any suspicious behavior in the Azure portal, such as impossible travel, suspicious mass activities, and activity from a new country/region.  

  For more information, see [Connect Azure to Microsoft Cloud App Security](./connect-azure.md).

- **Scoped deployments** (gradual rollout)  
Microsoft Cloud App Security provides enterprises with the ability to granularly determine which users they want to monitor and protect based on group membership. This feature enables you to select users whose activities will not show up for any of the protected applications. The scoped monitoring capability is especially useful for:
  - Compliance – If your compliance regulations necessitate that you refrain from monitoring users from certain countries/regions due to local regulations.
  - Licensing – If you want to monitor fewer users to stay within the limits of your Microsoft Cloud App Security licenses.
  For more information, see [Scoped deployment](scoped-deployment.md).

- **Breached app alert for discovered apps**  
 We now have a built-in alert to notify you when any of a tenant's discovered apps is breached. The alert will provide information about the time and date of the breach, which users used the app, and will link to publicly available sources that provide information about the breach.

- **New mail server**  
 Cloud App Security's mail server changed and uses different IP address ranges. To make sure you can get notifications, add the new IP addresses to your anti-spam allow list. For users who customize their notifications, Microsoft Cloud App Security enables this for you using MailChimp&reg;, a third-party email service. For the list of mail server IP addresses, and instructions for enabling work with MailChimp, see [Network requirements](network-requirements.md#mail-server) and [Mail settings](mail-settings.md).

### Cloud App Security release 123

Released May 13, 2018

- **Anomaly detection policy scoping**:  
The anomaly detection policies can now be scoped. This enables you to set each anomaly detection policy to include only specific users or groups, and to exclude specific users or groups. For example, you can set the Activity from infrequent county detection to ignore a specific user who travels frequently.

### Cloud App Security release 122

Released April 29, 2018

- Gradual rollout: You can now **set administrative permissions to Microsoft Cloud App Security admins per app**. For example, you can set a specific user as an administrator for only G Suite. This would enable the user to view and modify information in Microsoft Cloud App Security only when it relates exclusively to G Suite. For more information, see [Managing admin access](manage-admins.md).

- Gradual rollout: **Okta admin roles are now visible** in Microsoft Cloud App Security and are available for each role as a tag under **Settings** > **User groups**.

### Cloud App Security release 121

Released April 22, 2018

- The public preview of **Conditional Access App Control (formerly known as Cloud App Security Proxy)** has been enhanced with capabilities that facilitate deeper visibility into, and control over various applications. You can now create a Session Policy with an *Activity type* filter, to monitor, and block a variety of app-specific activities. This new filter augments the existing file download control features, to provide you with comprehensive control of the applications in your organization and works hand-in-hand with Azure Active Directory conditional access, to provide real-time visibility and control of risky user sessions — for example, sessions with B2B collaboration users or users coming from an unmanaged device. For more information, see [Session policies](session-policy-aad.md).

- Gradual rollout: Cloud App Security's **anomaly detection policies have been improved** to include two new types of threat detection: Ransomware activity and Terminated user activity. Cloud App Security extended its ransomware detection capabilities with anomaly detection to ensure a more comprehensive coverage against sophisticated Ransomware attacks. Using our security research expertise to identify behavioral patterns that reflect ransomware activity, Cloud App Security ensures holistic and robust protection. Terminated user activity enables you to monitor the accounts of terminated users, who may have been de-provisioned from corporate apps, but in many cases they still retain access to certain corporate resources. For more information, see [Get instantaneous behavioral analytics and anomaly detection](anomaly-detection-policy.md).

### Cloud App Security release 120

Released April 8, 2018

- For Microsoft 365 and Azure AD, we are now gradually rolling out the ability to detect internal applications as user account activities performed by the Microsoft 365 and Azure AD applications (both internal and external). This enables you to create policies that will alert you if an application performs unexpected and unauthorized activities.

- When exporting an app permissions list to csv, additional fields such as publisher, permissions level, and community usage are included to assist with the compliance and investigation process.

- The ServiceNow connected app was improved so that internal service activities no longer register as having been performed by "Guest" and no longer trigger false positive alerts. These activities are now represented as N/A like all other connected apps.

### Cloud App Security release 119

Released March 18, 2018

- The IP address ranges page includes built-in IP addresses that are discovered by Cloud App Security. This includes IP addresses for identified cloud services, like Azure and Microsoft 365, as well as the Threat intelligence feed that automatically enriches IP addresses with information about known risky IP addresses.

- When Cloud App Security attempts to run a governance action on a file but fails because the file is locked, it will now automatically retry the governance action.

### Cloud App Security release 118

Released March 4, 2018

- You can now take advantage of Microsoft Cloud App Security's shadow IT discovery and monitoring capabilities on your own proprietary custom apps. The new ability to add custom apps to Cloud Discovery enables you to monitor app usage and get alerted on changes in the usage pattern. For more information, see [Protecting your custom apps](cloud-discovery-custom-apps.md). This feature is being rolled out gradually.

- The Cloud App Security portal **Settings** pages were redesigned. The new design consolidates all the settings pages, provides search functionality, and an improved design.

- Cloud Discovery now supports Barracuda F-Series Firewalls and Barracuda F-Series Firewall Web Log Streaming.

- The search functionality in the User and IP address pages now enables auto complete to make it easier for you to find what you're looking for.

- You can now perform bulk actions in the Exclude entities and Exclude IP address settings pages. This makes it easier for you to select multiple users or IP addresses and exclude them from being monitored as part of the Cloud Discovery in your organization.

### Cloud App Security release 117

Released February 20, 2018

- Cloud App Security deepened integration with Azure Information Protection now enables you to protect files in G Suite. This public preview feature enables you to scan and classify files in G Suite, and automatically apply Azure Information protection labels for protection. For more information, see [Azure Information Protection integration](azip-integration.md).

- Cloud Discovery now supports [Digital Arts i-FILTER](https://www.daj.jp/en/products/if/).

- The SIEM agents table now includes more detail for easier management.

### Cloud App Security release 116

Released February 4, 2018

- Cloud App Security's anomaly detection policy was enhanced with new **scenario-based detections** including impossible travel, activity from a suspicious IP address, and multiple failed login attempts. The new policies are automatically enabled, providing out-of-the-box threat detection across your cloud environment. In addition, the new policies expose more data from the Cloud App Security detection engine, to help you speed up the investigation process and contain ongoing threats. For more information, see [Get instantaneous behavioral analytics and anomaly detection](anomaly-detection-policy.md).

- Gradual rollout: Cloud App Security now correlates between users and their accounts across SaaS apps. This enables you to easily investigate all the activities for a user, across all their various correlated SaaS apps, no matter which app or account they used.

- Gradual rollout: Cloud App Security now supports multiple instances of the same connected app. If you have multiple instances of, for example, Salesforce (one for sales, one for marketing) you will be able to connect them both to Cloud App Security and manage them from the same console to create granular policies and deeper investigation.

- The Cloud Discovery parsers now support two additional Checkpoint formats, XML, and KPC.

### Cloud App Security release 115

Released January 21, 2018

- This release provides an improved experience when selecting specific folders in file policies. You can now easily view and select multiple folders to include in a policy.
- In the **Discovered apps** page:
  - The bulk tagging feature enables you to apply custom tags (in addition to sanctioned and unsanctioned tags).
  - When you **Generate an IP addresses report**, or **Generate a users report** the exported reports now include the information about whether the traffic was from sanctioned or unsanctioned apps.
- You can now request a new API App connector from the Microsoft Cloud App Security team directly in the portal, from the **Connect an app** page.

### Cloud App Security release 114

Released January 7, 2018

- Beginning in version 114, we are gradually rolling out the ability to create and save custom queries in the Activity log and Discovered apps pages. Custom queries enable you to create filter templates that can be reused for deep-dive investigation. In addition, **Suggested queries** have been added to provide out-of-the-box investigation templates to filter your activities and discovered apps. The **Suggested queries** include custom filters to identify risks such as impersonation activities, administrator activities, risky non-compliant cloud storage apps, enterprise apps with weak encryption, and security risks. You can use the **Suggested queries** as a starting point, modify them as you see fit, and then save them as a new query. For more information, see [Activity filters and queries](activity-filters-queries.md) and [Discovered app filters and queries](discovered-app-queries.md).

- You can now check the current Cloud App Security service status by going [status.cloudappsecurity.com](https://status.cloudappsecurity.com) or directly from within the portal by clicking on **Help**>**System status**.

## Updates made in 2017

### Cloud App Security release 113

Released December 25, 2017

- We're excited to announce that Cloud App Security now supports deepened integration with Azure Information Protection. This public preview feature enables you to scan and classify files in cloud apps, and automatically apply Azure Information protection labels for protection. This feature is available for Box, SharePoint, and OneDrive. For more information, see [Azure Information Protection integration](azip-integration.md).

- Cloud Discovery log parsers now support for generic formats: LEEF, CEF, and W3C.

### Cloud App Security release 112

Released December 10, 2017

- You can now access the relevant insight drawer by clicking on a username or IP address in the Activity log.
- When investigating activities, you can now easily view all activities within the same time period from within the insight drawer by clicking on the clock icon. The clock icon enables you to view all activities done within 48 hours of the activity you're viewing.
- Improvements were made to the Cloud Discovery log parser for Juniper SRX.
- For activities monitored by the proxy, the **Activity object** was expanded to include information relevant to DLP scans. Matched policies were expanded to include DLP violations if they exist.

### Cloud App Security release 111

Released November 26, 2017

- Discovery policies now support app tags as a condition and as a governance action. This addition enables you to automatically tag newly discovered apps with custom tags such as **Trending apps**. You can also use the app tag as a filter. For example, "Alert me when an app in the 'Watchlist' has more than 100 users in a single day".

- The **Time** filter was improved to make it more user-friendly.

- Content inspection now enables you to distinguish between content, metadata, and filename, enabling you to select which you want to inspect.

- A new governance action was added for G Suite. You can now **Reduce public access** to shared files. This action enables you to set publicly available files to be available only with a shared link.

- All OKTA logon activities to other applications will now show up in Cloud App Security as originating from OKTA. You can view and filter based on the target application to which the login was performed in the activity's **Activity objects** field.

### Cloud App Security release 110

Released November 12, 2017

- Now generally available: We're starting to roll out a new deployment mode for the log collector. In addition to the current virtual-appliance based deployment, the new Docker (container) based log collector can be installed as a package on [Ubuntu machines](discovery-docker.md) both on-premises and in Azure. When using the Docker, the hosting machine is owned by the customer, who can freely patch and monitor it.

- Using the new blue question mark in the corner, you can now access the relevant Cloud App Security documentation page from within the pages of the portal. Each link is context-sensitive, taking you to the information you need based on the page you're on.
- You can now send feedback from every page of the Cloud App Security portal. Feedback enables you to report bugs, request new features and share your experience directly with the Cloud App Security team.
- Improvements were made to the Cloud Discovery ability to recognize subdomains for deep-dive investigations into your organization's cloud usage. For more information, see [Working with discovered apps](discovered-apps.md).

### Cloud App Security release 109

Released October 29, 2017

- Microsoft Cloud App Security proxy feature rollout has started. The Microsoft Cloud App Security proxy gives you the tools you need to have real-time visibility and control over access to your cloud environment, and activities within it. For example:

  - Avoid data leaks by blocking downloads before they happen.
  - Set rules that force data stored in and downloaded from the cloud to be protected with encryption.
  - Gain visibility into unprotected endpoints so you can monitor what's being done on unmanaged devices.
  - Control access from non-corporate networks or risky IP addresses.

  For more information, see [Protect apps with Conditional Access App Control](proxy-intro-aad.md).

- We're gradually rolling out the ability to filter according to specific service activity names. This new Activity Type filter is more granular, to enable you to monitor specific app activities, as opposed to more general activity types. For example, previously, you could filter for the **Run command**, and now you can filter for specific EXO cmdlets. The activity name can also be seen in the Activity drawer under **Type (in app)**. This capability will eventually replace the Activity type filter.

- Cloud Discovery now supports Cisco ASA with FirePOWER.

- Performance enhancements were made to the Discovery User and IP pages to improve user experience.

### Cloud App Security releases 105, 106, 107, 108

Released September/October 2017

- Cloud App Security now includes a data center located in the EU. In addition to our US data center, the EU data center will enable Cloud App Security customers to be in complete compliance with new and upcoming European standardization and certifications.
- New filters were added to the **App connectors** page that provide you with simpler filtering and additional insight.
- Cloud Discovery on log files that have only destination IP information was improved.

### Cloud App Security release 104

Released August 27, 2017

- You can now add IP ranges in bulk by creating a script using the **IP address ranges API**. The API can be found from the Cloud App Security portal menu bar by clicking the question mark and then **API documentation**.
- Cloud Discovery now provides better visibility for blocked transactions, by presenting both the total transactions as well as the blocked transactions.
- You can now filter cloud applications based on whether they're certified with **ISO 27017**. This new Cloud App Catalog risk factor determines whether the application provider has this certification. ISO 27017 establishes commonly accepted controls and guidelines for processing and protecting user information in a public cloud computing environment.
- To enable you to prepare for GDPR compliance, we gathered the GDPR readiness statements from the cloud apps in the Cloud App Catalog. It doesn't yet affect the app risk score, but provides a link for you to the app publisher's GDPR readiness page, when provided. Microsoft hasn't verified this content and isn't responsible for its validity.

### Cloud App Security release 103

Released August 13, 2017

- Cloud App Security added Azure Information Protection native protection support for the following Office files .docm, .docx, .dotm, .dotx, .xlam, .xlsb, .xlsm, .xlsx, .xltx, .xps, .potm, .potx, .ppsx, .ppsm, .pptm, .pptx, .thmx, .vsdx, .vsdm, .vssx, .vssm, .vstx, .vstm (in place of generic protection).

- Any Azure Active Directory Compliance administrator will automatically be granted similar permissions in Cloud App Security. Permissions include the ability to read only and manage alerts, create and modify file policies, allow file governance actions, and view all the built-in reports under Data Management.

- We extended the DLP violation context from 40 to 100 characters to help you better understand the context of the violation.

- Detailed error messages to the Cloud Discovery Custom Log uploader to enable you to easily troubleshoot errors in log upload.

- The Cloud Discovery block script was extended to support Zscaler format.

- New Cloud App Catalog risk factor: data retention after account termination. This enables you to make sure that your data is completely removed after you terminate an account within a cloud app.

### Cloud App Security release 102

Released July 30, 2017

- Because IP address information is crucial for almost all investigations, you can now view detailed information about IP addresses in the Activity Drawer. From within a specific activity, you can now click on the IP address tab to view consolidated data about the IP address. The data includes the number of open alerts for the specific IP address, a trend graph of recent activity and a location map. This feature enables easy drill down. For example, when investigating impossible travel alerts, you can easily understand where the IP address was used and if it was involved in suspicious activities or not. You can perform actions directly in the IP address drawer that enable you to tag an IP address as risky, VPN, or corporate to ease future investigation and policy creation. For more information, see [IP address insights](activity-filters.md#ip-address-insights)

- In Cloud Discovery, you can now use [custom log formats](custom-log-parser.md)  for [automated log uploads](discovery-docker.md). Custom log formats enable you to easily automate log upload from your SIEMs such as Splunk servers or any other unsupported format.

- The new user investigation actions enable an added level of drill-down to user investigations. From the **Investigation** pages, you can now right-click on an activity, user, or account and apply one of the following new filters for advanced investigation and filtration: **View related activity**, **View related governance**, **View related alerts**, **View owned files**, **View files shared with this user**.

- The Cloud App Catalog now contains a new field for data retention after account termination. This risk factor enables you to make sure that your data is completely removed after you terminate an account within a cloud app.

- Cloud App Security now has enhanced visibility into activities regarding Salesforce objects. Objects include leads, accounts, campaigns, opportunities, profiles, and cases. For example, visibility into access of account pages enables you to configure a policy that alert you if a user views an unusually large number of account pages. This is available through the Salesforce App Connector, when you have enabled Salesforce Event Monitoring in Salesforce (part of Salesforce Shield).

- Do not track is now available for private preview customers! You can now control which users' activity data is processed. This feature enables you to set specific groups in Cloud App Security as "Do not track". For example, you can now decide not to process any activity data for users located in Germany or any country/region that is not bound by a specific compliance law. This can be implemented across all apps in Cloud App Security, for a specific app, or even for a specific subapp. Additionally, this feature can be used to facilitate gradual roll out of Cloud App Security. For more information or to join the private preview for this feature, contact support or your account representative.

### Cloud App Security release 100

Released July 3, 2017

**New features**

- **Security extensions:** Security extensions is a new dashboard for centralized management of all security extensions to Cloud App Security.  Extensions include API token management, SIEM agents, and External DLP connectors. The new dashboard is available in Cloud App Security under "Settings".

  - API tokens – generate and manage your own [API tokens](api-authentication.md)  to integrate Cloud App Security with third-party software using our RESTful APIs.
  - SIEM agents – [SIEM integration](siem.md) was previously located directly under "Settings", now available as a tab in Security Extensions.
  - External DLP (Preview) – Cloud App Security allows you to [leverage existing investments in third-party classification systems](icap-stunnel.md) such as Data Loss Prevention (DLP) solutions, and enables you to scan the contents of cloud applications using existing deployments running in your environment. Contact your account manager to join the preview.

- **Automatically sanction/unsanction:** New App detection policies give Cloud Discovery the ability to automatically set apps with Sanctioned/Unsanctioned label. This gives you the ability to automatically identify apps that are in violation of your organization's policy and regulations and add them to the generated blocking script.
- **Cloud App Security file labels:** You can now apply Cloud App Security file labels to now provide more insight into the files it scans. For each file scanned by Cloud App Security DLP, you can now know if the files were blocked from being inspected because they were encrypted or corrupted. For instance, you can set up policies to alert and quarantine password protected files that are shared externally. This feature is available for files scanned after July 3, 2017.

    You can filter for these files by using the filter **Classification labels** > **Cloud App Security**:

  - **Azure RMS encrypted** – files whose content wasn't inspected because they have Azure RMS encryption set.
  - **Password encrypted** – files whose content wasn't inspected because they're password protected by the user.
  - **Corrupt file** – files whose content wasn't inspected because their content couldn't be read.

- **User insights**: The investigation experience was upgraded to enable out-of-the-box insights about the acting user. With a single click, you can now see a comprehensive overview of the users from the Activity drawer, Insights include which location they connected from, how many open alerts are they're involved with, and their metadata information.
- **App connector insights:** Under **App Connectors**, each connected app now includes an app drawer in the table for easier drill-down into its status. Details that are provided include when the App connector was connected and last health check on the connector. You can also monitor the status of DLP scanning on each app: the total number of files inspected by DLP and the status of the real-time scans (requested scans vs. actual scans). You'll be able to tell if the rate of files scanned by Cloud App Security in real time is lower than the requested number, and whether your tenant might be exceeding its capacity and experiencing a delay in the DLP results.

- **Cloud App Catalog customization:**

  - **App tags**: You can now create custom tags for apps. These tags can be used as filters for diving deeper into specific types of apps that you want to investigate. For example, custom watch list, assignment to a specific business unit, or custom approvals, such as "approved by legal".
  - **Custom notes**: As you review and assess the different applications that were discovered across your environment, you can now save your conclusions and insights in the Notes.
  - **Custom risk score**: You can now override the risk score of an app. For example, if the risk score of an app is 8 and it's a sanctioned app in your organization, you can change the risk score to 10 for your organization. You can also add notes to make the justification of the change clear when anyone reviews the app.

- **New log collector deployment mode:** We're starting to roll out a new deployment mode is now available for the log collector. In addition to the current virtual-appliance based deployment, the new Docker (container) based log collector can be installed as a package on Windows and Ubuntu machines both on-premises and in Azure. When using the Docker, the hosting machine is owned by the customer, who can freely patch and monitor it.

**Announcements:**

- The Cloud App Catalog now supports over 15,000 discoverable apps
- Compliance: Cloud App Security is officially SOC1/2/3 certified by Azure. For the full list of certifications, see [Compliance offerings](https://www.microsoft.com/trustcenter/compliance/complianceofferings) and filter the results for Cloud App Security.

**Other improvements:**

- **Improved parsing:** Improvements were made in the Cloud Discovery log parsing mechanism. Internal errors are significantly less likely to occur.
- **Expected log formats:** The expected log format for Cloud Discovery logs now provides examples for both Syslog format and FTP format.
- **Log collector upload status:** You can now see the log collector status in the portal and troubleshoot errors faster using the in-portal status notifications and the system alerts.

### Cloud App Security release 99

Released June 18, 2017

**New Features**

- You can now require users to sign in again to all Microsoft 365 and Azure AD apps. Require sign in again as a quick and effective remediation for suspicious user activity alerts and compromised accounts. You can find the new governance in the policy settings and the alert pages, next to the Suspend user option.
- You can now filter for **Add impersonation role assignment** activities in the Activity log. This activity enables you to detect when an admin has granted an **Application Impersonation** role to any user or system account, using the cmdlet **New-ManagementRoleAssignment**. This role allows the impersonator to perform operations by using the permissions associated with the impersonated account, instead of the permissions associated with the impersonator's account.

**Cloud Discovery Improvements:**

- Cloud Discovery data can now be enriched with Azure Active Directory username data. When you enable this feature, the username received in the discovery traffic logs will be matched and replaced by the Azure AD username. Enriching enables the following new features:
  - You can investigate Shadow IT usage by Azure Active Directory user.
  - You can correlate the discovered cloud app use with the API collected activities.
  - You can then create custom logs based on Azure AD user groups. For example, a Shadow IT report for a specific Marketing department.
- Improvements were made to the Juniper syslog parser. It now supports the welf and sd-syslog formats.
- Improvements were made to the Palo Alto parser for better application discovery.
- To verify that logs are being successfully uploaded, you can now see the status of your log collectors in the Cloud App Security portal.

**General improvements:**

- Built-in IP address tags and custom IP tags are now considered hierarchically, with custom IP tags taking precedence over built-in IP tags. For instance, if an IP address is tagged as **Risky** based on threat intelligence, but there's a custom IP tag that identifies it as **Corporate**, the custom category and tags will take precedence.

### Cloud App Security release 98

Released June 4, 2017

**Cloud Discovery updates:**

- Users can now perform advanced filtering on discovered apps. Filtering enables you to perform deep investigation. For example, filtering apps based on usage. Wow much upload traffic from discovered apps of certain types? How many users used certain categories of discovered apps? You can also perform multi-selection in the left panel to select multiple categories.
- Started roll out of new templates for Cloud Discovery that are based on popular searches such as "non-compliant cloud storage app". These basic filters can be used as templates to perform analysis on your discovered apps.
- For ease of use, you can now do actions such as sanction and unsanction across multiple apps in one action.
- We're now rolling out the ability to create custom discovery reports based on Azure Active Directory user groups. For example, if you want to see the cloud use of your marketing department, you can import the marketing group using the import user group feature, then create a custom report for this group.

**New features:**

- RBAC for Security Readers completed roll out. This feature enables you to manage the permissions you grant to your admins inside the Cloud App Security console. By default, all Azure Active Directory admins, Microsoft 365 Global admins, and Security admins have full permissions in the portal. All Security readers in Azure Active Directory and Microsoft 365 have read-only access in Cloud App Security. You can add additional admins or override permissions using the "Manage Access" option. For more information, see [Managing admin permissions](manage-admins.md).
- We're now rolling out detailed threat intelligence reports for risky IP addresses detected by Microsoft intelligent security graph. When an activity is performed by a botnet, you'll see the name of the botnet (if available) with a link to a detailed report about the specific botnet.

### Cloud App Security release 97

Released May 24, 2017

**New features:**

- Investigate files and policy violations: You can now see all policy matches in the Files page. Additionally, the File Alert page has been improved to now include a separate tab for History of the specific file. The improvement enables you to drill down into the violation history across all policies for the specific file. Every History event includes a snapshot of the file at the time of the alert. It will include an indication of whether the file was deleted or quarantined.
- [Admin quarantine](use-case-admin-quarantine.md) is now available in private preview for Microsoft 365 SharePoint and OneDrive for Business files. This feature enables you to quarantine files that match policies or set an automated action to quarantine them. Quarantining removes the files from the user's SharePoint directory and copies the originals to the admin quarantine location you choose.

**Cloud Discovery improvements:**

- Cloud Discovery support for Cisco Meraki logs has been improved.
- The option to suggest an improvement to Cloud Discovery now enables you to suggest new risk factor.
- The custom log parser was improved to support log formats by separating the setting of time and date and to give you the option to set timestamp.
- Starting to roll out the ability to create custom discovery reports based on Azure Active Directory user groups. For example, if you want to see the cloud use of your marketing department, import the marketing group using the import user group feature, and then create a custom report for this group.

**Other updates:**

- Cloud App Security now includes support for the Microsoft Power BI activities that are supported in the Microsoft 365 audit log. This feature is being rolled out gradually. You need to enable [this functionality in the Power BI portal](/power-bi/admin/service-admin-auditing).
- In activity policies, you can now set notify and suspend actions to be taken on the user across all connected apps. For example, you can set a policy to always notify the user's manager and suspend the user immediately whenever the user has multiple failed logins in any connected app.

### OOB release

- In a speedy reaction to the ransomware sweeping the globe, on Sunday, the Cloud App Security team added a new [Potential ransomware activity detection policy](use-case-ransomware.md) template to the portal that includes the signature extension of WannaCrypt. We advise you to the set this policy today.

### Cloud App Security release 96

Released May 8, 2017

**New features:**

- Continuing the gradual roll out of the Security Reader permission, which enables you to manage the permissions you grant to your admins inside the Cloud App Security console. By default, all Azure Active Directory and Microsoft 365 Global admins and Security admins have full permissions in the portal. All Security readers in Azure Active Directory and Microsoft 365 will have read-only access in Cloud App Security. For more information, see [Managing admin permissions](manage-admins.md).
- Completed roll out of Cloud Discovery support for user-defined log parsers for CSV-based logs. Cloud App Security enables you to configure a parser for your previously unsupported appliances by providing you with the tools to delineate which columns correlate to specific data. For more information, see [Custom log parser](custom-log-parser.md).

**Improvements:**

- Cloud Discovery now supports Juniper SSG appliances.
- Cloud Discovery support for Cisco ASA logs has been improved for better visibility.
- You can now more easily run bulk actions and select multiple records in Cloud App Security portal tables: the page length has been increased to improve bulk operations.
- The **Outbound sharing by domain**, and **Owners of shared files** built-in reports can now be run for Salesforce data.
- We're starting rollout of additional Salesforce activities enabling you to track interesting information that was extracted from the activity data. These activities include viewing and editing accounts, leads, opportunities, and various other interesting Salesforce objects.
- New activities were added for Exchange to enable you to monitor which permissions were granted for user mailboxes or mailbox folders. These activities include:
  - Add recipient permissions
  - Remove recipient permissions
  - Add mailbox folder permissions
  - Remove mailbox folder permissions
  - Set mailbox folder permissions

   For example, you can now monitor users who were granted **SendAs** permissions to other users' mailboxes and as a result can now send emails in their name.

### Cloud App Security release 95

Released April 24, 2017

**Updates:**

- The **Accounts** page has been updated with improvements that make detecting risks easier. You can now more easily filter for internal and external accounts. See at a glance whether a user has admin permissions. You can perform actions on each account per-app such as remove permissions, remove user's collaborations, suspend user. Additionally, imported [user groups](user-groups.md) for each account will be displayed.

- For Microsoft work accounts (Microsoft 365 and Azure Active Directory), Cloud App Security groups different user identifiers such as proxy addresses, aliases, SID, and more under a single account. All aliases related to an account will appear under the primary email address. Based on the list of user identifiers, for activities whose actor is a user identifier, the actor will be displayed as the primary user name UPN (User Principal Name). Based on the UPN, groups will be assigned and policies applied. This change will improve investigation of activities and fuse all related activities to the same session for anomalies and group-based policies. This feature will be gradually rolled out over the next month.

- The Robot tag was added as a possible risk factor in the Browser Use built-in report. Now, in addition to browser use being tagged as outdated, you can see when browser use was performed by a robot.
- When creating a content inspection file policy, you can now set the filter to include only files with at least 50 matches.

### Cloud App Security release 94

Released April 2, 2017

**New features:**

- Cloud App Security is now integrated with Azure RMS. You can protect files in Microsoft 365 OneDrive and Sharepoint Online with Microsoft Rights Management directly from the Cloud App Security portal. Protection can be accomplished from the **Files** page. For more information, see [Integrating with Azure Information Protection](azip-integration.md). Support for additional applications will be available in future versions.
- Up until now, when robot and crawler activities take place on your network, it was especially hard to identify because the activities are not performed by a user on your network. Without your knowledge, bots and crawlers can run malicious tools on your computers. Now, Cloud App Security gives you the tools to see when robots and crawlers are performing activities on your network. You can use the new user agent tag to filter activities in the activity log. The user agent tag enables you to filter all activities performed by robots and you can use it to create a policy that alerts you each time this type of activity is detected. You'll be updated when future releases will include this risky activity as embedded into the anomaly detection alerts.
- The new unified app permissions page enables you to more easily investigate the permissions your users have given to third-party apps. By clicking on **Investigate** > **App permissions**, you can now view a list of all the permissions your users gave to third-party apps. A page of app permissions per connected app enables you to better compare between the various apps and the permissions granted. For more information, see [Manage app permissions](manage-app-permissions.md).
- You can filter data right from the table drawer for easier investigation.
In the **Activity log**, the **Files** table and **App permissions** pages are now enhanced with new contextual actions that makes pivoting in the investigation process a lot easier. We also added quick links to configuration pages and the ability to copy data with a single click. For more information, see the information about [working with the file and activity drawers](file-filters.md).
- Support for Microsoft Teams to Microsoft 365 Activity logs and alerts rollout was completed.

### Cloud App Security release 93

Released March 20, 2017

**New features:**

- You can now apply policies to include or exclude imported user groups.
- Cloud App Security Anonymization now enables you to configure a custom encryption key. For more information, see [Cloud Discovery anonymization](cloud-discovery-anonymizer.md).
- In order to have more control over user and account management, you now have direct access to Azure AD account settings for each user and account from within the **Account** page. Just click the cog next to each user. This change enables easier access to advanced user management features group management, configuration of MFA, details about user sign-ins, and the ability to block sign-in.
- You can now export a blocking script for unsanctioned apps via the Cloud App Security API. Learn about our APIs in the Cloud App Security portal by clicking the question mark in the menu bar, followed by **API documentation**.
- The Cloud App Security app connector for ServiceNow was expanded to include support for OAuth tokens (as introduced in Geneva, Helsinki, Istanbul). This change provides a more robust API connection to ServiceNow that doesn't rely on the deploying user. For more information, see [Connect ServiceNow to Microsoft Cloud App Security](./connect-servicenow.md). Existing customers can update their settings in the ServiceNow App connector page.
- If you configured additional third-party DLP scanners, DLP scan status will now show the status of each connector independently to improve visibility.
- Cloud App Security now includes support for the Microsoft Teams activities that are supported in the Microsoft 365 audit log. This feature is being rolled out gradually.
- For Exchange Online impersonation events, you can now filter by the permission level used - delegated, admin, or delegated admin. You can search for events displaying the impersonation level that interests you in the **Activity log** by searching for **Activity objects** > **Item**.
- In the app drawer on the **App Permissions** tab of Microsoft 365 apps, you can now see the **Publisher** of each app. You can also use the Publisher as a filter for investigation of additional apps from the same publisher.
- Risky IP addresses now show up as an independent risk factor rather than weighted under the general **Location** risk factor.
- When Azure Information Protection labels are disabled on a file, the disabled labels will appear as disabled in Cloud App Security. Deleted labels won't be displayed.

**Additional Salesforce support:**

- You can now suspend and unsuspend Salesforce users in Cloud App Security. This action can be accomplished in the **Accounts** tab of the Salesforce Connector. Click the cog at the end of the row of a specific user and select**Suspend** or **Unsuspend**. Suspend and unsuspend can also be applied as a governance action as part of a policy. All suspend and unsuspend activities taken in Cloud App Security will be logged in the [Governance log](governance-actions.md).
- Improved visibility to Salesforce content sharing: You can now see which files were shared with whom, including publicly shared files, files shared with groups, and files shared with the entire Salesforce domain. Improved visibility will be rolled out retroactively to new and current connected Salesforce apps, it may take a while for this information to update the first time.
- We improved coverage for the following Salesforce events, and separated them out of the **Manage users** activity:
  - Edit permissions
  - Create user
  - Change role
  - Reset password

### Cloud App Security release 90, 91, 92

Released February  2017

**Special announcement:**

Cloud App Security is now officially certified with Microsoft Compliance for ISO, HIPAA, CSA STAR, EU model clauses, and more. See the full list of certifications in the [Microsoft Compliance Offerings](https://www.microsoft.com/trustcenter/compliance/complianceofferings) article by selecting Cloud App Security.

**New features:**

- **Import user groups (preview)**   When you connect apps using API connectors, Cloud App Security now enables you to import user groups, from Microsoft 365 and Azure Active Directory. Typical scenarios that leverage imported user groups include: investigating which docs the HR people look at, or you can check if there's something unusual happening in the executive group, or if someone from the admin group performed an activity outside the US. For details and instructions, see [Importing user groups](user-groups.md).

- In the Activity log, you can now filter users and users in groups to show which activities were performed by a specific user, and which were performed on a specific user. For example, you can investigate activities in which the user impersonated others, and activities in which others impersonated this user. For more information, see [Activities](activity-filters.md).

- When investigating a file in the **Files** page, if you drill down into the **Collaborators** of a specific file, you can now see more information about the collaborators. This information includes if they're Internal or External, Writers or Readers (file permissions), and when a file is shared with a group you can now see all users who are members of the group. Seeing all users enables you to see if the group members are external users.

- IPv6 support is now available for all appliances.

- Cloud Discovery now supports Barracuda appliances.

- Cloud App Security system alerts now cover SIEM connectivity errors. For more information, see [SIEM integration](siem.md).

- Cloud App Security now includes support for the following activities:

  - **Microsoft 365, SharePoint/OneDrive**: Update application configuration, Remove owner from group, Delete site, Create folder

  - **Dropbox**: Add member to group, Remove member from group, Create group, Rename group, Change team member name

  - **Box**: Remove item from group, Update item share, Add user to group, Remove user from group

### Cloud App Security release 89

Released January 22, 2017

**New features:**

- We're starting to roll out the ability to view Microsoft 365 Security and Compliance Center DLP events in Cloud App Security. If you configured DLP policies in the Microsoft 365 Security and Compliance Center, when policy matches are detected, you'll see them in the Cloud App Security Activity log. The information in the Activity log will include the file or email that triggered the match as and the policy or alert that it matched. The **Security event** activity allows you to view Microsoft 365 DLP policy matches in the Cloud App Security activity log. Using this feature, you can:
  - See all DLP matches coming from the Microsoft 365 DLP engine.
  - Alert on Microsoft 365 DLP policy matches for a specific file, SharePoint site, or policy.
  - Investigate DLP matches with a broader context, for example- external users who accessed or downloaded a file that triggered a DLP policy match.

- The activity descriptions have been improved for clarity and consistency. Each activity now provides a feedback button. If there are some things you don't understand or have a question about, you can let us know.

**Improvements:**

- A new governance action was added for Microsoft 365 that enables you to remove all external users of a file. For instance, this action enables you to implement policies that **remove external shares from files with internal only classification**.
- Improved identification of external users in SharePoint online. When filtering for the "external users" group, app@"sharepoint" system account won't show up.

### Cloud App Security release 88

Released January 8, 2017

**New features:**

- Connect your SIEM to Cloud App Security. You can now send alerts and activities automatically to your SIEM of choice by configuring SIEM Agents. Now available as a public preview.  For full documentation and details, take a look at Integrating with SIEM.
- Cloud Discovery now supports IPv6. We rolled out support for Palo Alto and Juniper, and more appliances will be rolled out in future releases.

**Improvements:**

- There's a new risk factor in the Cloud App Catalog. You can now rate an app based on whether it Requires user authentication. Apps that enforce authentication and don't allow anonymous use will receive a healthier risk score.
- We're rolling out new activity descriptions to be more usable and consistent. Searching for activities will not be affected by this change.
- We included improved user-device identification, enabling Cloud App Security to enrich a larger number of events with device information.

## Updates made in 2016

### Cloud App Security release 87

Released December 25, 2016

**New features:**

- We're in the process of rolling out [data anonymization](cloud-discovery-anonymizer.md) so that you can enjoy Cloud Discovery while protecting user privacy. The data anonymization is performed by encrypting username information.
- We are in the process of rolling out the ability to export a blocking script from Cloud App Security to additional appliances. The script will allow you to easily reduce shadow IT by blocking traffic to unsanctioned apps. This option is now available for:
  - BlueCoat ProxySG
  - Cisco ASA
  - Fortinet
  - Juniper SRX
  - Palo Alto
  - Websense
- A new File governance action was added that enables you to force a file to Inherit permissions from parent, deleting any unique permissions that were set for the file or folder. This file governance action enables you to change your file or folder's permissions to be inherited from the parent folder.
- A new user group was added called External. This group is a default user group that is pre-configured by Cloud App Security to include all users who aren't part of your internal domains. You can use this user group as a filter. For example, you can find activities performed by external users.
- The Cloud Discovery feature now supports Sophos Cyberoam appliances.

**Bug fixes:**

- SharePoint online and One Drive for Business files were displayed in the File policy report and in the Files page as Internal instead of Private. This bug was fixed.

### Cloud App Security release 86

Released December 13, 2016

**New features:**

- All Cloud App Security standalone licenses provide you with the ability to enable Azure Information Protection scanning from the general settings (without the need to create a policy).

**Improvements:**

- You can now use "or" in the file filter for the file name and in the MIME type filter for files and policies. This change enables scenarios such as entering the word "passport" OR "driver" when creating a policy for personal data. The filter will match any file that has "passport" or "driver" in the filename.
- By default, when a DLP content inspection policy runs, the data in the resulting violations is masked. You can now unmask the last four characters of the violation.

**Minor improvements:**

- New Microsoft 365 (Exchange) mailbox-related events having to do with forwarding rules and adding and removing delegate mailbox permissions.
- New event that audits the granting of consent to new apps in Azure Active Directory.

### Cloud App Security release 85

Released November 27, 2016

**New features:**

- A distinction was made between sanctioned apps and connected apps. Sanctioning and unsanctioning is now a tag that can be applied to discovered apps and any app in the app catalog. Connected apps are apps that you connected using the API connector for deeper visibility and control. You can now tag apps as sanctioned or unsanctioned or connect them using the app connector, where available.
- As part of this change, the Sanctioned apps page was replaced with a redesigned **Connected apps** page that externalizes status data about the connectors.
- The log collectors are more easily accessible in their own line in the **Settings** menu under **Sources**.
- When creating an activity policy filter, you can reduce false positives by choosing to ignore repeated activities when they're performed on the same target object by the same user. For example, multiple attempts to download the same file by the same person won't trigger an alert.
- Improvements were made to the activity drawer. Now, when you click on an activity object in the activity drawer, you can drill down for more information.

**Improvements:**

- Improvements were made to the anomaly detection engine, including the impossible travel alerts, for which IP information is now available in the alert description.
- Improvements were made to the complex filters to enable adding the same filter more than once for fine-tuning of filtered results.
- File and folder activities in Dropbox were separated for better visibility.

**Bug fixes:**

- A bug in the system alerts mechanism that created false positives was fixed.

### Cloud App Security release 84

Released November 13, 2016

**New features:**

- Cloud App Security now supports for Microsoft Azure Information Protection including enhanced integration and autoprovisioning. You can filter your Files and set File policies using the Tag Secure Classification and then set the classification label you want to view. The labels also indicate whether the classification was set by someone in your organization or by people from another tenant (External). You can also set activity policies, based on the Azure Information Protection classification labels and enable automatic scan for classification labels in Microsoft 365. For more information on how to take advantage of this great new feature, see [Integrating with Azure Information Protection](azip-integration.md).

**Improvements:**

- Improvements were made to the Cloud App Security activity log:
  - Microsoft 365 events from the Security and Compliance Center are now integrated with Cloud App Security and are visible in the **Activity log**.
  - All Cloud App Security activity is registered in the Cloud App Security activity log as administrative activity.
- To help you investigate file-related alerts, in each alert that results from a file policy, you can now view the list of activities that were performed on the matched file.
- The impossible travel algorithm in the anomaly detection engine was improved to provide better support for small tenants.

**Minor improvements:**

- The **Activity export limit** was raised to 10,000.
- When creating a **Snapshot report** in the Cloud Discovery manual log upload process, you now receive an accurate estimate for how long the log processing will take.
- In a file policy, the **Remove collaborator** governance action now works on groups.
- Minor improvements were made in the **App permissions** page.
- When more than 10,000 users have granted permissions to an app that connects to Microsoft 365, the list loaded slowly. This slowness has been fixed.
- Additional attributes were added to the **App catalog** regarding the payment card industry.

### Cloud App Security release 83

Released October 30, 2016

**New features:**

- To simplify filtering in the [activity log](activity-filters.md) and [file log](file-filters.md), similar filters have been consolidated. Use the activity filters: Activity object, IP address, and User. Use the file filter Collaborators to find exactly what you need.
- From the activity log drawer, under **Source**, you can click the link for **View raw data**. This action downloads the raw data used to generate the activity log for greater drill down into app events.
- Added support for additional login activities in Okta. [Private preview]
- Added support for additional login activities in Salesforce.

**Improvements:**

- Improved usability for Cloud Discovery snapshot reports and troubleshooting.
- Improved visibility in the alerts list for alerts on multiple apps.
- Improved usability when creating new Cloud Discovery continuous reports.
- Improved usability in the Governance log.

### Cloud App Security release 82

Released October 9, 2016

**Improvements:**

- The activities **Change email** and **Change password** are now independent from the generic **Manage users** activity in Salesforce.
- Added a clarification for the SMS daily alert limit. A maximum of 10 messages are sent per phone number, per day (UTC).
- A new certificate was added to the Cloud Discovery attributes for Privacy Shield, which replaced Safe Harbor (relevant for US vendors only).
- Troubleshooting has been added to the API connector failure messages to make it easier to remediate problems.
- Improvement in the update frequency of Microsoft 365 third-party app scan.
- Improvements in the Cloud Discovery dashboard.
- The Checkpoint Syslog parser was improved.
- Improvements in the Governance Log for banning and unbanning third-party apps.

**Bug fixes:**

- Improved process for uploading a logo.

### Cloud App Security release 81

Released September 18, 2016

**Improvements:**

- Cloud App Security is now a first-party app in Microsoft 365! From now on, you can connect Microsoft 365 to Cloud App Security in a single click.

- New look to the Governance log- it was now upgraded to the same clear a useful look as the Activity log and Files table. Use the new filters to easily find what you need and monitor your governance actions.
- Improvements were made to the anomaly detection engine for multiple failed logins and additional risk factors.
- Improvements were made to the Cloud Discovery snapshot reports.
- Improvements were made to administrative activities in the activity log; Change password, Update user, Reset password now indicate whether the activity was performed as an administrative activity.
- The alert filters for system alerts were improved.
- The label for a policy within an alert now links back to the policy report.
- If there's no owner specified for a Dropbox file, notification email messages are sent to the recipient you set.
- Cloud App Security supports an additional 24 languages extending our support to a total of 41 languages.

### Cloud App Security release 80

Released September 4, 2016

**Improvements:**

- When the DLP scan fails, you're now provided with an explanation of why Cloud App Security couldn't scan the file. For more information, see [Content Inspection](content-inspection.md).
- Improvements were made to the anomaly detection engines, including improvements in the impossible travel alerts.
- Improvements were made to the dismiss alert experience. You can also add feedback so that you can let the Cloud App Security team know whether the alert was interesting and why. Your feedback will be used to improve the Cloud App Security detections.
- The Cisco ASA Cloud Discovery parsers were improved.
- You now receive an email notification when your Cloud Discovery log manual upload completes.

### Cloud App Security release 79

Released August 21, 2016

**New features:**

- **New Cloud Discovery Dashboard** - A brand new Cloud Discovery dashboard is available, designed to give you more insight into how cloud apps are being used in your organization. It provides an at-a-glance overview of what kinds of apps are being used, your open alerts and the risk levels of apps in your organization. It also lets you know who the top app users are in your organization and provides an App Headquarter location map. The new Dashboard has more options for filtering the data, to allow you to generate specific views, depending on what you're most interested in, and easy-to-understand graphics to give you the full picture at a glance.

- **New Cloud Discovery reports** - To view Cloud Discovery results, you can now generate two types of reports, Snapshot reports and Continuous reports. Snapshot reports provide ad-hoc visibility on a set of traffic logs you manually upload from your firewalls and proxies. Continuous reports show the results of all logs that are forwarded from your network using Cloud App Security's log collectors. These new reports provide improved visibility over all data, automatic identification of anomalous use as identified by the Cloud App Security machine learning anomaly detection engine, and identification of anomalous use as defined by you using the robust and granular policy engine. For more information, see [Set up Cloud Discovery](set-up-cloud-discovery.md).

**Improvements:**

- General usability improvements in the following pages: Policy pages, General settings, Mail settings.
- In the Alerts table, it's now easier to distinguish between read and unread alerts. The read alerts have a blue line to the left and are grayed out to indicate that you already read them.
- The Activity policy **Repeated activity** parameters were updated.
- In the Accounts page, a user **Type** column was added so you can now see what type of user account each user has. The user types are app-specific.
- Near real-time support was added for file-related activities in OneDrive and SharePoint. When a file changes, Cloud App Security triggers a scan almost immediately.

### Cloud App Security release 78

Released August 7, 2016

**Improvements:**

- From a specific file, you can now right-click and **Find related**. From the Activity log, you can use the Target object filter then select the specific file.

- Improved Cloud Discovery Log file parsers, including the addition of Juniper and Cisco ASA.
- Cloud App Security now enables you to provide feedback for the improvement of alerts, when you dismiss an alert. You can help improve the quality of the Cloud App Security alert feature by letting us know why you're dismissing the alert. For example, it's not interesting, you received too many similar alerts, the actual severity should be lower, the alert isn't accurate.
- In the File policy view, or when viewing a file, when you open the file drawer, the new link to Matched policies was added. When you click on it, you can view all the matches and you're now enabled to dismiss all.
- The organizational unit a user belongs to is now added to all relevant alerts.
- An email notification is now sent to let you know when processing completes for your manually uploaded logs.

### Cloud App Security release 77

Released July 24, 2016

**Improvements:**

- The Cloud Discovery Export button icon was improved for usability.
- When investigating an activity, if the user agent wasn't parsed, you can now see the raw data.
- Two new risk factors were added to the Anomaly Detection engine:
  - Cloud App Security now uses the IP address tags that are associated with a botnet and anonymous IP addresses as part of the calculation of Risk.
  - Microsoft 365 activity is now monitored for high-download rates. If the Microsoft 365 download rate is much higher than your organization's, or a specific user's, normal download rate, an Anomaly Detection alert is triggered.
- Cloud App Security is now compatible with the new Dropbox [Secure Sharing functionality](https://blog.dropbox.com/topics/product/new-dropbox-productivity-tools) API.
- Improvements were made to add details to the Discovery log parsing errors, including: No cloud-related transactions, All events are outdated, Corrupted file, Log format doesn't match.
- The Activity log date filter was improved; it now includes the ability to filter by time.
- The IP address ranges page was improved for usability.
- Cloud App Security now includes support for Microsoft Azure Information Protection (Preview version). You can filter your Files and set File policies using the Tag Secure Classification. Then, set the level of the classification label you want to view. The labels also indicate whether the classification was set by someone in your organization or by people from another tenant (External).

### Cloud App Security release 76

Released: July 10, 2016

**Improvements:**

- Lists of users in built-in Reports can now be exported.
- Improved usability for aggregated activity policy.
- Improved support for the TMG W3C firewall log message parser.
- Improved usability for the file governance action drop-down, which is now separated into collaboration, security and investigation actions.
- Improved Impossible Travel detection for Exchange Online activity of: Send mail.
- A new list of titles (breadcrumbs) was added to the top of the Alerts and Policy pages to make navigation easier.

**Bug fixes:**

- The preset expression for Credit Card in the DLP setting for File Policies was changed to All: Finance: Credit Card.

### Cloud App Security release 75

Released: June 27, 2016

**New features:**

- New additions were added to our growing list of supported Salesforce events.  Events include providing insights into reports, shared links, content distribution, impersonated login and more.
- The connected app icons on the Cloud App Security dashboard were aligned with the status of the apps as displayed on the dashboard to reflect the last 30 days.
- Support for full-width screens.

**Bug fixes:**

- SMS alert phone numbers are now validated upon insertion.

### Cloud App Security release 74

Released: June 13, 2016

- The Alert screen was updated to provide you with more information at a glance. Updates include the ability to see all user activities at a glance, a map of activities, related user governance logs, a description of the reason the alert is triggered, and additional graphs and maps from the user page.
- Events generated by Cloud App Security now include the event type, format, policy groups, related objects, and a description.
- New IP address tags were added for Microsoft 365 Apps for enterprise, OneNote, Office Online, and Exchange Online Protection.
- You now have an option to upload logs from the main discovery menu.
- The IP address category filter was improved. The IP address category null is now called uncategorized. A new category called No value was added to include all activities that have no IP address data.
- Security groups in Cloud App Security are now called user groups to avoid confusion with Active Directory security groups.
- It's now possible to filter per IP address, and filter out events without an IP address.
- Changes were made to the settings for notification emails sent when matches are detected in Activity Policies and File Policies. You can now add email addresses for recipients you want to CC with the notification.

### Cloud App Security release 73

Released: May 29, 2016

- Updated alert capabilities: You can now set alerts per policy to be sent via email or sent as a text message.
- Alerts page: Improved design to better enable advanced resolution options and incident management.
- Adjust policy: Alerts now enable you to move from alert resolution options directly to the policy settings page to enable easier fine-tuning based on alerts.
- Improvements to anomaly detection risk score calculation and reduced false-positive rate based on customer feedback.
- Activity log export now includes Event ID, Event Category, and Event Type Name.
- Improved appearance and usability of policy creation Governance Actions.
- Simplified investigation and control for Microsoft 365 - Selection of Microsoft 365 automatically selects all apps that are part of the Microsoft 365 Suite.
- Notifications are now sent to the email address as configured in the connected app.
- Upon connection error, a detailed description of the error is now provided by the cloud app.
- When a file matches a policy, a URL to access the file is now provided in the file drawer.
- When an alert is triggered by an activity policy or an anomaly detection policy, a new detailed notification is sent that provides information about the match.
- An automated system alert is triggered when an app connector is disconnected.
- You can now dismiss and resolve a single alert or a bulk selection of alerts from within the alerts page.

### Cloud App Security release 72

Released: May 15, 2016

- General appearance and infrastructure improvements, including:

  - New diagram to provide more assistance with the Cloud Discovery manual log upload process.
  - Improved process for updating unrecognized ("Other") log files. This process includes a pop-up that lets you know that the file requires additional review. You'll be notified when the data is available.
  - More activity and file violations are highlighted when investigating an activity and file log for outdated browsers and operating systems.

- Improved Cloud Discovery Log file parsers, including the addition of Cisco ASA, Cisco FWSM, Cisco Meraki, and W3C.
- Cloud Discovery known issue improvements.
- New activity filters added for owner's domain and internal/external affiliation.
- A new filter was added that enables you to search for any Microsoft 365 object (files, folders, URLs).
- The ability was added to configure a minimal risk score for Anomaly detection policies.
- When you set an alert to be sent when a policy is violated, you can now set a minimum severity level for which you want to be alerted. You can choose to use your organization's default setting for this and you can set a specific alert setting as the default for your organization.

[!INCLUDE [Open support ticket](includes/support.md)]
