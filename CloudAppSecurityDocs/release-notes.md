---
title: What's new in Cloud App Security
description: This article is updated frequently to let you know what's new in the latest release of Cloud App Security.
ms.date: 02/7/2021
ms.topic: overview
---
# What's new with Microsoft Cloud App Security

*Applies to: Microsoft Cloud App Security*

This article is updated frequently to let you know what's new in the latest release of Cloud App Security.

RSS feed: Get notified when this page is updated by copying and pasting the following URL into your feed reader: `https://docs.microsoft.com/api/search/rss?search=%22This+article+is+updated+frequently+to+let+you+know+what%27s+new+in+the+latest+release+of+Cloud+App+Security%22&locale=en-us`

> [!IMPORTANT]
>
> Threat protection product names from Microsoft are changing. Read more about this and other updates [here](https://www.microsoft.com/security/blog/?p=91813). We'll be using the new names in future releases.

## Cloud App Security release 192, 193, and 194

Released February 7, 2021

- **Updated: Policies page grouped by categories**  
We've updated the **Policies** page, adding a tab for every policy category. We also added an **All policies** tab to give you a complete list of all your policies. For more information about the categorization, see [Policy types](control-cloud-apps-with-policies.md#policy-types).

- **Enhanced Office 365 OAuth apps export**  
We've enhanced the Office 365 OAuth apps activities export to CSV file with the *Redirect URL* of the OAuth apps. For more information about exporting OAuth app activities, see [OAuth app auditing](manage-app-permissions.md#oauth-app-auditing).

- **Updates to the portal interface**  
In the coming months, Cloud App Security will be updating its User Interface to provide a more consistent experience across Microsoft 365 security portals. [Learn more](https://techcommunity.microsoft.com/t5/microsoft-security-and/microsoft-cloud-app-security-user-interface-updates/ba-p/2083113)

## Cloud App Security release 189, 190, and 191

Released January 10, 2021

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
On June 7, 2020, we started gradually rolling out our enhanced proxy session controls to use one unified suffix that doesn't include named regions. For example, users will see `<AppName>.mcas.ms` suffix instead of `<AppName>.<Region>.cas.ms`. If you routinely block domains in your network appliances or gateways, make sure you allow list all the domains listed under [Access and session controls](network-requirements.md#access-and-session-controls).

## Cloud App Security release 184, 185, and 186

Released October 25, 2020

- **New enhanced alert monitoring and management experience**  
As part of our ongoing improvements to monitoring and managing alerts, the Cloud App Security Alerts page has been improved based on your feedback. In the enhanced experience, the **Resolved** and **Dismissed** statuses are replaced by the **Closed** status with a resolution type. [Learn more](monitor-alerts.md#deployment-of-our-enhanced-alert-monitoring-and-management-experience)

- **New global severity setting for signals sent to Microsoft Defender for Endpoints**  
We've added the ability to set the global severity setting for signals sent to Microsoft Defender for Endpoint. For more information, see [How to integrate Microsoft Defender for Endpoint with Cloud App Security](mde-integration.md#how-to-integrate-microsoft-defender-for-endpoint-with-cloud-app-security).

- **New security recommendations report**  
Cloud App Security provides you with security configuration assessments for your Azure, Amazon Web Services (AWS), and Google Cloud Platform (GCP) giving you insights into security configuration gaps in your multi-cloud environment. Now you can export detailed security recommendation reports to help you monitor, understand, and customize your cloud environments to better protect your organization. For more information about exporting the report, see [Security recommendations report](security-config.md#security-recommendations-report).

- **Enhanced proxy URL suffix for session controls (gradual rollout)**  
On June 7, 2020, we started gradually rolling out our enhanced proxy session controls to use one unified suffix that doesn't include named regions. For example, users will see `<AppName>.mcas.ms` suffix instead of `<AppName>.<Region>.cas.ms`. If you routinely block domains in your network appliances or gateways, make sure you allow list all the domains listed under [Access and session controls](network-requirements.md#access-and-session-controls).

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
We've made additional performance improvements to our session controls, by improving our content caching mechanisms. The improved service is even more streamlined and provides increased responsiveness when using session controls. Note that session controls do not cache private content, aligning with the appropriate standards to only cache shared (public) content. For more information, see [How session control works](proxy-intro-aad.md#how-session-control-works).

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
Cloud App Security provides the ability to identify risky machines as part of your shadow IT discovery investigation. Now, we've added the Microsoft Defender Advanced Threat Protection **Machine risk level** to the **machines** page giving analysts more context when investigating machines in your organization. For more information, see [Investigate devices in Cloud App Security](mde-integration.md#investigate-devices-in-cloud-app-security).

- **New feature: Self-service disable app connector (gradual rollout)**  
We've added the ability to disable app connectors directly in Cloud App Security. For more information, see [Disable app connectors](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md#disable-app-connectors).

## Cloud App Security release 177

Released June 14, 2020

- **New real-time malware detection (preview, gradual rollout)**  
We've expanded our session controls to detect potential malware using Microsoft Threat Intelligence upon file uploads or downloads. The new detection is now available out-of-the-box and can be configured to automatically block files identified as potential malware. For more information, see [Block malware on upload](session-policy-aad.md#block-malware-on-upload).

- **New access token support for access and session controls**  
We've added the ability to treat access token and code requests as logins when onboarding apps to access and session controls. To use tokens, click the settings cog icon, select **Conditional Access App Control**, edit the relevant app (three dots menu > **Edit app**), select **Treat access token and code requests as app logins**, and then click **Save**. For more information about onboarding apps, see [Onboard and deploy any app](proxy-deployment-any-app.md) and [Deploy featured apps](proxy-deployment-aad.md).

- **Enhanced proxy URL suffix for session controls (gradual rollout)**  
On June 7, 2020, we started gradually rolling out our enhanced proxy session controls to use one unified suffix that doesn't include named regions. For example, users will see `<AppName>.mcas.ms` suffix instead of `<AppName>.<Region>.cas.ms`. If you routinely block domains in your network appliances or gateways, make sure you allow list all the domains listed under [Access and session controls](network-requirements.md#access-and-session-controls).

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
Starting June 7, 2020, we are gradually rolling out our enhanced proxy session controls to use one unified suffix that doesn't include named regions. For example, users will see `<AppName>.mcas.ms` suffix instead of `<AppName>.<Region>.cas.ms`. If you routinely block list domains in your network appliances or gateways, make sure you allow list all the domains listed under [Access and session controls](network-requirements.md#access-and-session-controls).

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
Cloud App Security now supports Salesforce's hourly event log. Hourly event logs give you accelerated, near real-time monitoring of user activities. For more information, see [Connect Salesforce](connect-salesforce-to-microsoft-cloud-app-security.md).

- **Support for AWS security configuration using a master account**  
Cloud App Security now supports using a master account. Connecting your master account allows you to receive security recommendations for all member accounts across all regions. For more information about connecting with a master account, see [How to connect AWS Security configuration to Cloud App Security](connect-aws-to-microsoft-cloud-app-security.md#how-to-connect-aws-security-configuration-to-cloud-app-security).

- **Session controls support for modern browsers**  
Cloud App Security session controls now includes support for the new Microsoft Edge browser based on Chromium. Whilst we'll continue supporting the most recent versions of Internet Explorer and the legacy version of Microsoft Edge, the support will be limited and we recommend using the new Microsoft Edge browser.

## Cloud App Security release 165, 166, 167, and 168

Released February 16, 2020

- **New block unsanctioned apps with Microsoft Defender ATP**  
Cloud App Security has extended its native integration with Microsoft Defender Advanced Threat Protection (ATP). You can now block access to apps marked as unsanctioned using Microsoft Defender ATP's network protection capability. For more information, see [Block access to unsanctioned cloud apps](mde-integration.md#block-access-to-unsanctioned-cloud-apps).

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
Cloud App Security now supports the latest version (New York) of ServiceNow. To learn about securing ServiceNow, see [Connect ServiceNow to Microsoft Cloud App Security](connect-servicenow-to-microsoft-cloud-app-security.md).

- **Enhanced detection logic: Impossible travel**  
We've updated the detection logic for impossible travel to provide enhanced coverage and better accuracy. As part of this update, we also updated the detection logic for [impossible travel from corporate networks](anomaly-detection-policy.md#impossible-travel).

- **New threshold for activity policies**  
We've added a threshold for [activity policies](user-activity-policies.md) to help you manage the volume of alerts. Policies that trigger a large volume of matches for several days are automatically disabled. If you receive a system alert about this, you should try refining policies by adding additional filters or, if you are using policies for reporting purposes, consider saving them as queries instead.

## See Also

For a description of releases prior to those listed here, see [Past releases of Microsoft Cloud App Security](release-note-archive.md).

[!INCLUDE [Open support ticket](includes/support.md)]