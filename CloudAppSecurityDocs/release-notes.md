---
# required metadata

title: What's new in Cloud App Security
description: This article is updated frequently to let you know what's new in the latest release of Cloud App Security.
author: shsagir
ms.author: shsagir
manager: shsagir
ms.date: 05/17/2020
ms.topic: overview
ms.service: cloud-app-security

# optional metadata

#ROBOTS:
ms.collection: M365-security-compliance
ms.reviewer: reutam
ms.suite: ems
ms.custom: seodec18

---
# What's new with Microsoft Cloud App Security

*Applies to: Microsoft Cloud App Security*

This article is updated frequently to let you know what's new in the latest release of Cloud App Security.

RSS feed: Get notified when this page is updated by copying and pasting the following URL into your feed reader: `https://docs.microsoft.com/api/search/rss?search=%22This+article+is+updated+frequently+to+let+you+know+what%27s+new+in+the+latest+release+of+Cloud+App+Security%22&locale=en-us`

## Cloud App Security release 175

Released May 17, 2020

- **New Shadow IT Discovery integration with Corrata (Preview)**  
We've added native integration with Corrata providing you with Shadow IT visibility into app use and control over app access. For more information, see [Integrate Cloud App Security with Corrata](corrata-integration.md).

- **New Cloud Discovery log parsers**  
Cloud App Security Cloud Discovery analyzes a wide range of traffic logs to rank and score apps. Now Cloud Discovery includes a built-in log parser to support Corrata and Cisco ASA with FirePOWER 6.4 log formats. For a list of supported log parsers, see [Supported firewalls and proxies](set-up-cloud-discovery.md#supported-firewalls-and-proxies).

- **Enhanced dashboard (gradual rollout)**
As part of our ongoing improvements to the portal design, we are now gradually rolling out the improved Cloud App Security dashboard. The dashboard has been modernized based on your feedback and offers an enhanced user experience with updated content and data. For more information, see [Gradual deployment of our enhanced dashboard](daily-activities-to-protect-your-cloud-environment.md#gradual-deployment-of-our-enhanced-dashboard).

## Cloud App Security release 173 and 174

Released April 26, 2020

- **New SIEM agent CEF format for alerts**  
As part of our effort to enrich the alert information provided in the CEF files used by generic SIEM servers, we have extended the format to include the following client fields:
  - IPv4 address
  - IPv6 address
  - IP address location

    For more information, see [CEF file format](siem.md#sample-cloud-app-security-alerts-in-cef-format).
- **Enhanced detection logic: Impossible travel**  
We've updated the detection logic for impossible travel to provide improved accuracy and reduced alert volume. For more information about this anomaly detection policy, see [Impossible travel](anomaly-detection-policy.md#impossible-travel).

## Cloud App Security release 172

Released April 5, 2020

- **Enhanced access and session controls with any IdP (Preview)**  
Access and session controls now support SAML apps configured with any identity provider. The public preview of this new feature is now gradually rolling out. To configure these controls, see the [Deployment guide](proxy-deployment-aad.md).
- **New bulk deanonymization of users and machines**  
We have expanded and simplified the process of deanonymizing one or more users and machines under investigation. For more information about bulk deanonymization, see [How data anonymization works](cloud-discovery-anonymizer.md#how-data-anonymization-works).

## Cloud App Security release 170 and 171

Released March 22, 2020

- **New anomaly detection: Unusual region for cloud resource (Preview)**  
We have expanded our current capability to detect anomalous behavior for AWS. The new detection is now available out-of-the-box and automatically enabled to alert you when a resource is created in an AWS region where the activity is not normally performed. Attackers often leverage an organization's AWS credits to perform malicious activities such as crypto-mining. Detecting such anomalous behavior can help mitigate an attack.

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
We have expanded our current anomalous behavior alerts for Workday. The new alerts include the following user geo-location detections:
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
Cloud App Security has extended its native integration with Microsoft Defender Advanced Threat Protection (ATP). You can now block access to apps marked as unsanctioned using Microsoft Defender ATP's network protection capability. For more information, see [Block access to unsanctioned cloud apps](wdatp-integration.md#block-access-to-unsanctioned-cloud-apps).

- **New OAuth app anomaly detection**  
We have expanded our current capability to detect malicious OAuth app consent. The new detection is now available out-of-the-box and automatically enabled to alert you when a potentially malicious OAuth app is authorized in your environment. This detection leverages Microsoft security research and threat intelligence expertise to identify malicious apps.

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

## Cloud App Security release 162, 163, and 164

Released December 8, 2019

- **Change to SIEM activities and alerts in CEF format**  
The [portal URL format (CS1)](siem.md#sample-cloud-app-security-alerts-in-cef-format) for activity and alert information sent by Cloud App Security to SIEMs has changed to `https://<tenant_name>.portal.cloudappsecurity.com` and no longer contains the data center location. Customers using pattern matching for the portal URL should update the pattern to reflect this change.

## Cloud App Security release 160 and 161

Released November 3, 2019

- **Discovery data in Azure Sentinel (Preview)**  
Cloud App Security now integrates with Azure Sentinel. Sharing alert and discovery data with Azure Sentinel provides the following benefits:

  - Enable correlation of discovery data with other data sources for deeper analysis.

  - View data in Power BI with out-of-the-box dashboards or build your own visualizations.

  - Enjoy longer retention periods with Log Analytics.

  For more information, see [Azure Sentinel integration](siem-sentinel.md).

- **Google Cloud Platform connector (Preview)**  
Cloud App Security is extending its IaaS monitoring capabilities beyond Amazon Web Services and Azure and now supports Google Cloud Platform. This enables you to seamlessly connect and monitor all your GCP workloads with Cloud App Security. The connection provides you with a powerful set of tools to protect your GCP environment, including:

  - Visibility into all activities performed through the admin console and API calls.

  - Ability to create custom policies and use predefined templates to alert on risky events.

  - All GCP activities are covered by our anomaly detection engine and will automatically alert on any suspicious behavior, such as impossible travel, suspicious mass activities, and activity from a new country.

  For more information, see [Connect Google Cloud Platform to Microsoft Cloud App Security](connect-google-gcp-to-microsoft-cloud-app-security.md).

- **New policy templates**  
Cloud App Security now includes new built-in Activity policy templates for Google Cloud Platform security best practices.

- **Enhanced Cloud Discovery log parser**  
Cloud App Security Cloud Discovery analyzes a wide range of traffic logs to rank and score apps. Now Cloud Discovery's built-in log parser supports the Ironport WSA 10.5.1 log format.

- **Customizable user landing page for session controls**  
We've launched the ability for admins to personalize the landing page that your users see when navigating to a app that a Session policy is applied to. You can now display your organization's logo and customize the message shown. To start customizing, go to the **Settings** page, and under **Cloud Access App Control**, select **User monitoring**.

- **New detections**  

  - **Suspicious AWS logging service changes (Preview)**: Alerts you when a user makes changes to the CloudTrail logging service. For example, attackers often turn off auditing in CloudTrail to hide the footprints of their attack.

  - **Multiple VM creation activities**: Alerts you when a user performs an unusual number of VM creation activities, compared to the learned baseline. Now applies to AWS.

## Cloud App Security release 159

Released October 6, 2019

- **New Cloud Discovery ContentKeeper log parser**  
Cloud App Security Cloud Discovery analyzes a wide range of traffic logs to rank and score apps. Now Cloud Discovery includes a built-in log parser to support ContentKeeper log formats. For a list of supported log parsers, see [Supported firewalls and proxies](set-up-cloud-discovery.md#supported-firewalls-and-proxies).

- **New Detections**  
The following new anomaly detection policies are available out-of-the-box and automatically enabled:

  - **Suspicious email deletion activity (Preview)**  
    Alerts you when a user performs unusual email deletion activities. This policy can help you detect user mailboxes that may be compromised by potential attack vectors such as command-and-control communication (C&C/C2) over email.

  - **Multiple Power BI report sharing (Preview)**  
    Alerts you when a user performs an unusual number of Power BI report sharing activities, compared to the learned baseline.

  - **Multiple VM creation activities (Preview)**  
    Alerts you when a user performs an unusual number of VM creation activities, compared to the learned baseline. Currently applies to Azure.

  - **Multiple storage deletion activities (Preview)**  
    Alerts you when a user performs an unusual number of storage deletion activities, compared to the learned baseline. Currently applies to Azure.

## Cloud App Security release 158

Released September 15, 2019

- **Customize Cloud Discovery executive report name**  
The Cloud Discovery executive report provides you with an overview of Shadow IT use across your organization. You now have the option to customize the report name before generating it. For more information, see [Generate Cloud Discovery executive report](discovered-apps.md#generate-cloud-discovery-executive-report).

- **New policies overview report**  
Cloud App Security detects policy matches and, where defined, logs alerts that you can use to understand your cloud environment more deeply. Now you can export a policies overview report showing aggregated alert metrics per policy to help you monitor, understand, and customize your policies to better protect your organization. For more information about exporting the report, see [Policies overview report](control-cloud-apps-with-policies.md#policies-overview-report).

## Cloud App Security release 157

Released September 1, 2019

- **Reminder: End of support for TLS 1.0 and 1.1 on September 8**  
Microsoft is moving all its online services to Transport Layer Security (TLS) 1.2+ to provide best-in-class encryption. Therefore, as of September 8, 2019 Cloud App Security will no longer support TLS 1.0 and 1.1 and connections using these protocols will not be supported. For more information about how the change affects you, see [our blog post](https://techcommunity.microsoft.com/t5/Enterprise-Mobility-Security/End-of-support-for-TLS-1-0-and-1-1-in-Microsoft-Cloud-App/ba-p/770507).

- **New detection – Suspicious Microsoft Power BI sharing (Preview)**  
The new suspicious Power BI report sharing policy is now available out-of-the-box and automatically enabled to alert you when a potentially sensitive Power BI report is suspiciously shared outside of your organization.

- **New export feature for OAuth app auditing**  
Cloud App Security audits all OAuth authorization activities to provide you with comprehensive monitoring and investigation of activities performed. Now you can also export the details of users that authorized a specific OAuth app, providing you with additional information on the users, which you can then use for further analysis.

- **Enhanced Okta event auditing**  
Cloud App Security now supports the new System Log API released by Okta. For more information about connecting Okta, see [Connect Okta](connect-okta-to-microsoft-cloud-app-security.md).

- **Workday connector (Preview)**  
A new app connector is now available for Workday. You can now connect Workday to Cloud App Security to monitor activities and protect its users and activities. For more information, see [Connect Workday](connect-workday-to-microsoft-cloud-app-security.md).

- **Enhanced assessment for the "Password policy" risk factor**  
The Cloud App Catalog now provides granular assessment for the **Password policy** risk factor. By hovering over its information icon, you can see a breakdown of the specific policies that are enforced by the app.

## Cloud App Security release 156

Released August 18, 2019

- **New Cloud Discovery log parsers**  
Cloud App Security Cloud Discovery analyzes a wide range of traffic logs to rank and score apps. Now Cloud Discovery includes a built-in log parser to support Stormshield and Forcepoint LEEF log formats.

- **Activity log enhancements**  
Cloud App Security now provides you with greater visibility into unclassified activities performed by apps in your environment. These activities are available in the Activity log and also in Activity policies. To see unclassified activities, in the **Type** filter select **Unspecified**. For more information about activity filters, see [Activity filters and queries](activity-filters-queries.md).

- **Risky user investigation enhancement**  
Cloud App Security provides the ability to identify risky users on the **Users and accounts** page by specific groups, apps, and even roles. Now you can also investigate the users in your organization by their **Investigation priority** score. For more information, see [Understand the investigation priority score](tutorial-ueba.md#risk-score).

- **Activity policy enhancements**  
You can now create activity policy alerts based on activity objects. For example, this capability allows you to create alerts on changes to Azure Active Directory administrative roles. For more information about activity objects, see [Activity filters](activity-filters-queries.md#activity-filters).

## Cloud App Security release 155

Released August 4, 2019

- **New policy templates**  
Cloud App Security now includes new built-in Activity policy templates for AWS security best practices.

- **Notice: End of support for TLS 1.0 and 1.1 on September 8**  
Microsoft is moving all its online services to Transport Layer Security (TLS) 1.2+ to provide best-in-class encryption. Therefore, as of September 8, 2019 Cloud App Security will no longer support TLS 1.0 and 1.1 and connections using these protocols will not be supported. For more information about how the change affects you, see [our blog post](https://techcommunity.microsoft.com/t5/Enterprise-Mobility-Security/End-of-support-for-TLS-1-0-and-1-1-in-Microsoft-Cloud-App/ba-p/770507).

- **Enhanced logic for interactive sign-in activities (gradual rollout)**  
We are gradually rolling out new logic to identify if an Azure Active Directory sign-in activity is interactive. The new logic enhances Cloud App Security's ability to only surface sign-in activities that are initiated by a user.

## Cloud App Security release 154

Released July 21, 2019

- **Onboard and deploy Conditional Access App Control for any app is now GA**  
Since previewing Conditional Access App Control for any app last month, we've received tremendous feedback and are excited to announce GA. This new capability allows you to deploy any web app to work with session and access policies, enabling powerful real-time monitoring and control.

- **Security configuration assessment for AWS**  
Cloud App Security is gradually rolling out the ability to get a security configuration assessment of your Amazon Web Services environment for CIS compliance, and provides recommendations for missing configurations and security controls. This ability provides organizations with a single view for monitoring the compliance status for all connected AWS accounts.

- **OAuth app anomaly detections**  
We have expanded our current capability to detect suspicious OAuth apps. Four new detections are now available out-of-the-box that profile the metadata of OAuth apps authorized in your organization to identify ones that are potentially malicious.

## Cloud App Security release 153

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

## Cloud App Security release 152

Released June 23, 2019

- **Deploy Conditional Access App Control for any app (Preview)**  
We are excited to announce that we have expanded our support for Conditional Access App Control to any web app, in addition to the rich support we already offer for [our featured applications](proxy-intro-aad.md). This new capability allows you to deploy any web app to work with session and access policies, enabling powerful real-time monitoring and control. For example, you can protect downloads with Azure Information Protection labels, block upload of sensitive documents, providing auditing, among many others.
- **Portal activity auditing**  
Cloud App Security audits all admin activity in the portal to provide you with comprehensive monitoring and investigation of activities performed. Now you can also export up to 90 days of activities for further investigation and analysis, for example, auditing of an admin investigating a specific user or viewing specific alerts. To export the log, go to the **Manage admin access** settings page.
- **Custom session sign out from Cloud App Security portal**  
You can now configure automatic sign out of admin sessions to the portal that are idle for longer than a specified period.

## Cloud App Security release 151

Released June 9, 2019

- **Hybrid UEBA - Native integration with Azure ATP (Preview)**  
Cloud App Security now natively integrates with Azure ATP to provide a single view of identity activities in both cloud apps and your on-premises network. For more information, see [Azure Advanced Threat Protection integration](aatp-integration.md).
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

## Cloud App Security release 150

Released May 26, 2019

- **Alerts export improvement**  
When you export alerts to CSV from the **Alerts** page, the results will now include the date of the alert resolution or dismissal.

## Cloud App Security release 148 and 149

Released May 12, 2019

- **Webex app connector available**  
A new app connector is now available for Cisco Webex Teams in Public Preview. You can now connect Microsoft Cloud App Security to Cisco Webex Teams to monitor and protect its users, activities, and files. For more information, see [Connect Webex](connect-webex-to-microsoft-cloud-app-security.md)

- **Microsoft Data Classification Service new locations**  
[Microsoft Data Classification Service](dcs-inspection.md) is now available in four new locations - Australia, India, Canada, and Japan. If your Office tenant is located in these locations, you can now utilize Microsoft Data Classification Service as the content inspection method in Microsoft Cloud App Security file policies.

- **Discovery of Shadow PaaS and IaaS**  
Microsoft Cloud App Security has extended its Cloud Discovery capabilities and is now also providing Shadow IT for resources that are hosted on IaaS and PaaS solutions such as Microsoft Azure, Amazon Web Services, and Google Cloud Platform. Cloud Discovery now provides you with visibility into which custom apps run on top of your IaaS and PaaS, storage accounts that are being created, and more. Use this new capability in order to discover what resources exist, who accesses each of them, and how much traffic is transmitted.

- **App attestation**  
Microsoft Cloud App Security compliance and risk assessment now allows cloud providers to attest their app to be up to date in Cloud App Catalog. This pilot allows cloud providers to fill out a self-attestation questionnaire based on the Cloud App Catalog's risk attributes to make sure that their risk assessment in Cloud App Security is accurate and up-to-date. Users can then get an indication as to which risk attributes were attested by the provider (rather than assessed by the Cloud App Security team) and when each attribute was submitted by the provider. For more information, see [Attest your app](attest-your-app.md).

- **Office 365 workload granularity**  
When connecting Office 365 to Microsoft Cloud App Security, you now have control over which workloads you want to connect. For example, customers only interested in connecting Office 365 for activity monitoring can now do so during the connection process, or by editing an existing Office 365 connector. As part of this change, OneDrive and SharePoint Online will no longer be shown as separate connectors but will be included in the Office 365 connector as the _Office 365 files_ workload. Customers with an existing Office 365 connector are not impacted by this change.

- **Enhanced Teams support**  
You can now monitor and block message sending in the Teams web app in real time, by configuring a Session policy based on sensitive content.

## Cloud App Security release 147

Released April 14, 2019

- **New Cloud Discovery log parser**  
Cloud App Security Cloud Discovery now includes a built-in log parser to support the Palo Alto LEEF log format.

- **Session policies updates**  
  - **Additional content inspection method for session policies**:  When setting a session policy, you now have the option to choose Data Classification Service as a content inspection method for files. Data Classification Service offers the user a wide range of built-in sensitive types to use to identify sensitive information.
  - **Enhanced file permissions control in session policies**:  When you're creating a session policy to control downloads using Cloud App Security, you can now automatically apply permissions per user, such as read-only, to the documents upon download from your cloud apps. This provides a much greater level of flexibility and the ability to protect information beyond your pre-configured corporate labels.
  - **Large file download control**:  When content inspection is enabled in session policies, you can now control what happens when a user tries to download a very large file. If the file is too big to scan on download, you can choose whether it will be blocked or allowed.

## Cloud App Security release 146

Released March 31, 2019

- **Impossible travel enhancement**  
Impossible travel detection was enhanced with dedicated support for neighboring countries.
- **Additional attribute support for the generic CEF parser**  
The Cloud Discovery log parser support for generic CEF format was enhanced to support additional attributes.
- **Scoped access to Cloud Discovery reports**  
In addition to the Discovery Admin role, you can now scope access to specific Discovery reports. This enhancement enables you to configure privileges to data of specific sites and business units.
- **New role support: Global reader**  
Microsoft Cloud App Security now supports the Azure AD Global Reader role. The Global reader has full read-only access to all aspects of Microsoft Cloud App Security, but cannot change any settings or take any actions.

## Cloud App Security release 145

Released March 17, 2019

- **Microsoft Defender ATP integration is now GA**  
Last year we announced [integration with Windows Defender Advanced Threat Protection](https://techcommunity.microsoft.com/t5/Enterprise-Mobility-Security/Microsoft-Cloud-App-Security-and-Windows-Defender-ATP-better/ba-p/263265) that enhances the Discovery of Shadow IT in your organization, and extends it beyond the corporate network. [Enabled with a single click](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RWtNmG), we are excited to announce that this unique integration is now generally available.
- **Dynamics 365 CRM support**  
Cloud App Security added real-time monitoring and control for Dynamics 365 CRM, to enable you to protect your business applications and the sensitive content stored within these apps. For more information about what can be done with Dynamics 365 CRM, see [this article](proxy-intro-aad.md#how-it-works).

## Cloud App Security release 144

Released March 3, 2019

- **Unified SecOps Investigation for Hybrid Environments**  
Because many organizations have hybrid environments, attacks start in the cloud and then pivot to on-premises, meaning SecOps teams need to investigate these attacks from multiple places. By combining signals from cloud and on-premises sources including Microsoft Cloud App Security, Azure ATP, and Azure AD Identity Protection, Microsoft empowers security analysts by providing unified identity and user information, in a single console, ending the need to toggle between security solutions. This gives your SecOps teams more time and the right information to make better decisions, and actively remediate the real identity threats and risks. For more information, see [Unified SecOps Investigation for Hybrid Environments](https://techcommunity.microsoft.com/t5/Enterprise-Mobility-Security/Unified-SecOps-Investigation-for-Hybrid-Environments/ba-p/360850)

- **Sandboxing capabilities for malware detection** (gradual rollout)  
Cloud App Security's malware detection capabilities are being expanded to include the ability to identify zero-day malware through advanced Sandboxing technology.  
As part of this capability, Cloud App Security automatically identifies suspicious files and detonates them to look for suspicious file behavior and indicators that the file has malicious intent (malware).
As part of this change, malware detection policies now include a Detection type field that enables you to filter by threat intelligence as well as sandboxing.

- **Conditional Access updates**  
Conditional Access App Control added the ability to monitor and block the following activities:
  - File uploads in any app - enabling scenarios such as preventing upload of known malware extensions, and ensuring users protect files with AIP prior to upload.
  - Copy and paste in any app - rounding out robust controls of data exfiltration that already included controlling download, print, and custom activities such as share.
  - Send message - ensuring that PII data such as passwords is not shared in popular collaboration tools such as Slack, Salesforce, and Workplace by Facebook.
  - Session Policies now include built-in templates to enable your organization to effortlessly enable popular real-time monitoring and control over your sanctioned apps, such as **Block upload based on real-time content inspection**.

## Cloud App Security release 143

Released February 17, 2019

- **Scope deployment for app instances**  
Scoped deployment can now be configured at the app instance level, allowing for greater granularity and control.
- **Role enhancements**  
  - The data admin and security operator Office 365 roles are now supported in Cloud App Security. The data admin role enables users to manage everything file related, as well as view the Cloud Discovery reports. Security operators have permission to manage alerts and view policy configuration.
  - The security reader role now has the ability to configure the SIEM agent, allowing better permission scoping.

- **Microsoft Flow support**  
Cloud App Security now monitors user activities in Microsoft Flow. The activities supported are the activities reported by Flow to the Office 365 audit log.

- **Alert entity grouping**  
The **Alert** page now groups related entities that were involved in an alert to aid in your investigation.

## Cloud App Security release 142

Released February 3, 2019

- **Session policy configuration in Azure AD**  
You can now configure session policies to monitor users or block downloads in real-time, directly in Azure AD conditional access. You can still configure advanced session policies directly in Cloud App Security. To walk through this deployment, see [Deploy Conditional Access App Control for Azure AD apps](proxy-deployment-aad.md).

- **Suggested and Saved queries for OAuth apps**  
Suggested queries have been added to the OAuth apps page provide out-of-the-box investigation templates to filter your OAuth apps. Suggested queries include custom filters to identify risky apps such as apps authorized by administrators. Saved queries enable you to save custom queries for future use, similar to saved queries available today in the Activity log and Discovery pages.

- **Office 365 auditing default configuration**  
If you want to enable monitoring of Office 365 activities in Cloud App Security, you are now required to enable auditing in the [Office Security and Compliance Center](/office365/securitycompliance/turn-audit-log-search-on-or-off#turn-on-audit-log-search), this is a result of a [change to Office 365 auditing](/office/office-365-management-api/office-365-management-activity-api-faq#what-happens-if-i-disable-auditing-for-my-office-365-organization-will-i-still-get-events-via-the-management-activity-api). This change only needs to be performed if you haven't already enabled monitoring of Office 365 activities in Cloud App Security.

- **Enhanced Box support**  
Cloud App Security now supports two new governance actions for Box:

  - **Expire shared link** – This governance action provides you with the ability to set an expiration date for a shared link after which it will no longer be active.

  - **Change sharing link access level** – This governance action provides you with the ability to change the access level of the shared link between company only, collaborators only, and public.

- **Multi-location support in OneDrive**  
Cloud App Security now provides full visibility into OneDrive files, even if they are dispersed across multiple geographic locations. Protection is now available for files located in the additional locations as well as the main location.

- **Portal navigation enhancement**  
The Cloud App Security portal was enhanced to provide better navigation and better align Cloud App Security with Microsoft's other security services, for streamlined ease-of-use.

## Cloud App Security release 141

Released January 20, 2019

- **Cloud risk assessment enhancements**  
  - Cloud app risk assessment was enhanced with two new experiences.
    - A new **Data type** attribute assesses what kind of content users can upload to the app. You can use this attribute to assess an app according to the sensitivity of each data type in your organization.
    - To get a more comprehensive risk overview of an app, you can now easily pivot from the app's risk assessment to the risk assessment of hosting company by clicking on the **Hosting company** attribute.

- **Enhanced file context for anomaly detection alert investigation**  
  - Anomaly detection investigation was enhanced to enable you to see additional insight associated with the files that are involved in an alert. When alerts are triggered for file-related unusual activity alerts (Download, Share, Delete), this drill-down is available. For example, if most of the affected files are from the same folder or share the same file extension, you will see these insights in the Additional risk section of the alert.

- **Queries for file investigation**  
  - Cloud App Security's ability to create and save custom queries was extended to the **Files** page. Queries in the **File** page enable you to create query templates that can be reused for deep-dive investigation.

## Cloud App Security release 139, 140

Released January 6, 2019

- **Change in file detection**  
Files shared with everyone in SharePoint and One Drive are now considered **internal** [due to changes made to SharePoint and One Drive](https://support.microsoft.com/help/4089534/how-to-grant-the-everyone-claim-to-external-users-in-office-365). So if a file is detected that is shared with everyone, it will now be treated as an internal file – this affects how the file is handled by policies and shown in the files page.

- **Change in file monitoring**  
The default file monitoring behavior changed for new and idle customers. You will now need to turn on file monitoring to enable the feature, via **Settings** > **Files**. Existing active customers will not be affected by this change.

- **Advanced tuning for anomaly detection policies**  
You can now affect the anomaly detection engine to suppress or surface alerts according to your preferences.
  - In the Impossible Travel policy, you can set the sensitivity slider to determine the level of anomalous behavior needed before an alert is triggered.
  - You can also configure whether the alerts for Activity from infrequent country, anonymous IP addresses, suspicious IP addresses, and  impossible travel should analyze both failed and successful logins or just successful logins.

- **Support for multiple trust chains**  
Conditional Access App Control now supports adding and using multiple trusted root or intermediate certificates as a form of device management.

- **New Cloud Discovery role** (gradual roll out)  
Cloud App Security now provides a new admin role for Cloud Discovery users. This role can be used in order to scope the access of an admin user to only Cloud Discovery settings and data within the Cloud App Security portal.

- **Support for Microsoft Information Protection unified labels** (gradual roll out)  
Cloud App Security now supports Microsoft Information Protection unified labels. For customers that already [migrated their classification labels for the Office 365 Security and Compliance Center](/azure/information-protection/configure-policy-migrate-labels), Cloud App Security will identify and work with these labels as described in [Integrating with Azure Information Protection](azip-integration.md).

**Support for PDF file labeling** (gradual roll out)  
For customers using unified labels, Cloud App Security now supports autolabeling for PDF files.

## Cloud App Security release 138

Released December 9, 2018

- **Automatic log upload using Docker on Windows**  
Cloud App Security now supports automatic log upload for Windows 10 (fall creators update) and Windows Server, version 1709 and later using a Docker for Windows. For more information and instructions on how this can be configured, see [Docker on Windows on-premises](discovery-docker-windows.md).

- Cloud App Security integrates with [Microsoft Flow](/flow/getting-started) to provide custom alert automation and orchestration playbooks. For more information and integration instructions, see [Integrating with Microsoft Flow](flow-integration.md).

## Cloud App Security release 137

Released November 25, 2018

- **Added support for Dynamics**  
Cloud App Security now includes support for the Microsoft Dynamics activities that are supported in the Office 365 audit log.

- **Scanning encrypted content (Preview)**  
Cloud App Security now enables you to scan content that is protected by Azure Information Protection protection labels. This will allow you to find sensitive content, even in files that have already been encrypted by Azure Information Protection.

- **Heads up – new terminology!**  
The name of the App permissions capabilities was changed for clarity – it is now called **OAuth apps**.

## Cloud App Security release 136

Released November 11, 2018

- **Cloud Discovery updates**  
The custom log parser was enhanced to support additional and more complex web traffic logs formats. As part of these enhancements users can now input custom headers for headerless CSV log files, use special delimiters for key-value files, process Syslog file format, and more.

- **New anomaly detection policies**  
Suspicious inbox manipulation rules: This policy profiles your environment and triggers alerts when suspicious rules that delete or move messages or folders are set on a user's inbox. This may indicate that the user's account is compromised, that messages are being intentionally hidden, and that the mailbox is being used to distribute spam or malware in your organization.

- **Support for groups in app permission policies**  
Cloud App Security now gives you the ability to define app permission policies more granularly, based on the group memberships of the users who authorized the apps. For example, an admin can decide to set a policy that revokes uncommon apps if they ask for high permissions, only if the user who authorized the permissions is a member of the administrators group.

- **Conditional Access App Control now integrates with your on-prem apps via Azure Active Directory Application Proxy**  
  - The [Azure AD Application Proxy](/azure/active-directory/manage-apps/application-proxy) provides single sign-on and secure remote access for your web apps hosted on-prem.
  - These on-prem web apps can now be routed to Microsoft Cloud App Security via Azure AD conditional access to provide real-time monitoring and controls, via [access](access-policy-aad.md) and [session](session-policy-aad.md) policies.

## Cloud App Security release 133, 134, 135

Released October, 2018

- **New anomaly detection policies being gradually rolled out**  
  - The new Data exfiltration to unsanctioned apps policy is automatically enabled to alert you when a user or IP address uses an app that is not sanctioned to perform an activity that resembles an attempt to exfiltrate information from your organization.
    - The new Multiple delete VM activities policy profiles your environment and triggers alerts when users delete multiple VMs in a single session, relative to the baseline in your organization.

- **Data classification service available for APAC**  
  - Data classification service content inspection is now available for APAC customers. For a list of full regional support, see [Microsoft Data Classification Services integration](dcs-inspection.md).

- **Cloud Discovery support for i-Filter**  
  - The Cloud App Security Cloud Discovery feature now has enhanced support for the i-Filter syslog parser.

## Cloud App Security release 132

Released September 25, 2018

- **Conditional Access App Control for Office 365 is now in Public Preview**  
  - Conditional Access App Control now also supports Office 365 and any app that is configured with Open ID Connect.
  - Provide feedback from within a session: This new tool enables you to provide feedback to the Cloud App Security team about the performance of an application under session control, directly from within the session.

- **Native integration with Microsoft Defender ATP for Shadow IT Discovery beyond your corp**  
  - Microsoft Cloud App Security now natively integrates with Windows Defender Advanced Threat Protection (ATP) to provide deploymentless Shadow IT discovery capabilities for on and off corporate network use of cloud apps.  This enables you to perform Cloud Discovery on machines, even when they are not within your corporate network. It also enables machine-based investigation: after you identify a risky user, you can then check all the machines the user accessed to detect potential risks; if you identify a risky machine, you can check all the users who used it to investigate potential risks. For more information, see  Windows Defender Advanced Threat Protection integration with [Microsoft Cloud App Security](wdatp-integration.md).

- **Content inspection for encrypted files**  
  - Cloud App Security now supports content inspection of protected files that are encrypted that were protected using Azure Information Protection. You can now inspect these encrypted files for reclassification proposes and identify additional DLP exposure and security policy violations.

## Cloud App Security release 131

Released September 2, 2018

- **Automatically revoke permissions on risky OAuth apps**  
You can now control which OAuth apps your users have access to, by revoking app permission for OAuth apps on Office, Google, or Salesforce. When creating an **App permission policy**, you can now set the policy to revoke an app's permission.

- **Cloud Discovery additional built-in parser supported**  
Cloud Discovery now supports the Forcepoint Web Security Cloud log format.

## Cloud App Security release 130

Released August 22, 2018

- **New menu bar**  
To provide a more consistent admin experience across Microsoft 365 products and enable you to more easily pivot between Microsoft security solutions, the Cloud App Security portal menu bar moved to the left side of the screen. This consistent navigation experience helps you orient yourself when moving from one Microsoft security portal to another.

- **Impact OAuth app score**  
You can now send the Cloud App Security team feedback to let us know if there's an OAuth app discovered in your organization that seems malicious. This new feature enables you to be part of our security community and enhance OAuth app risk score and analysis. For more information, see [Manage app permiOAuth appsssions](manage-app-permissions.md).

- **New Cloud Discovery parsers**  
The Cloud Discovery parsers now support iboss Secure Cloud Gateway and Sophos XG.

## Cloud App Security release 129

Released August 5, 2018

- **New anomaly detection policies - suspicious email rules**  
New anomaly detection policies were added that detect suspicious email forwarding rules, for example, if a user created an inbox rule that forwards a copy of all emails to an external address.

- This release includes fixes and improvements for multiple issues.

## Cloud App Security release 128

Released July 22, 2018

- **OAuth apps actions across multiple apps**  
For OAuth apps that have been granted app permissions, you can now ban or approve multiple apps in a single action. For example, you can review all the apps that have been granted permission by users in your organization, select all the apps you want to ban, and then click ban apps to revoke all consent granted and will no longer allow users to grant permission to those apps.  For more information, see [Manage OAuth apps](manage-app-permissions.md).

- **Enhanced support for Azure applications**  
For Azure, we are now gradually rolling out the ability to detect applications as user account activities performed by the Azure applications (both internal and external). This enables you to create policies that will alert you if an application performs unexpected and unauthorized activities. For more information, see [Connect Azure to Microsoft Cloud App Security](connect-azure-to-microsoft-cloud-app-security.md).

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

## Cloud App Security release 127

Released July 8, 2018

- You now have the ability to see generic activities for Office 365. In the **Activity log** and in **Activity policies** you can now filter the Office 365 activities for **Unspecified** activities. Reviewing these activities enables you to investigate information about activities performed that aren't yet classified by type in Cloud App Security, and you can use these activities to send requests to the Cloud App Security team to create new activity types based on these activities.

## Cloud App Security release 126

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
You can now set automatic remediation actions for suspicious session triggered by the anomaly detection policies. This enhancement enables you to be alerted instantly when a breach occurs and **apply governance actions automatically**, such as suspend user. For more information, see [Anomaly detection policies](anomaly-detection-policy.md#adp-automated-gov).

- **Security configuration assessment for Azure**  
Microsoft Cloud App Security is gradually rolling out the ability to get a security configuration assessment of your Azure environment, and provides recommendations for missing configuration and security control. For example, it will let you know if you are missing MFA for administrative users. For more information, see [Cloud Security Posture Management integration](security-config.md).

- **Automated detection of risky OAuth Apps**  
In addition to the existing investigation of OAuth apps connected to your environment, Microsoft Cloud App Security is now gradually rolling out the ability to set automated notifications to let you know when an OAuth app meets certain criteria. For example, you can automatically be alerted when there are apps that require a high permission level and were authorized by more than 50 users. For more information, see [App permission policies](app-permission-policy.md).

- **Managed Security Service Provider management (MSSP) support**  
Microsoft Cloud App Security now provides a better management experience for MSSPs. External users can now be configured as administrators and assigned any of the [roles currently available in Microsoft Cloud App Security](manage-admins.md). In addition, to enable MSSPs to provide services across multiple customer tenants, Administrators who have access rights to more than one tenant can now easily switch tenants within the portal. For information about managing admins, see [Manage admins](manage-admins.md).

- **Integration with external DLP GA**  
Microsoft Cloud App Security allows you to [leverage existing investments in third-party classification systems](icap-stunnel.md) such as Data Loss Prevention (DLP) solutions, and enables you to scan the contents of cloud applications using existing deployments running in your environment. For more information, see [External DLP integration](icap-stunnel.md).

## Cloud App Security release 125

Released June 10, 2018

- **New investigation capability by top users:**  
Microsoft Cloud App Security added a new investigation widget to the dashboard that shows top users by the number of open threat detection alerts. This investigation widget enables you to focus your threat investigation on users with the highest number of suspicious sessions.

- **Support for AWS S3 buckets:**  
Microsoft Cloud App Security can now detect AWS S3 buckets and their sharing levels. This provides alerts and visibility into publicly accessible AWS buckets. This also enables you to create policies based on buckets and apply automatic governance. In addition, there is a new policy template available called **Publicly accessible S3 buckets (AWS)** that you can use to easily create a policy to govern your AWS storage. In order to enable these new capabilities, make sure you update your AWS connected apps by adding the new permissions described in [Connect AWS](connect-aws-to-microsoft-cloud-app-security.md).

- **Admin privileges based on user groups**:  
You can now set administrative permissions to Microsoft Cloud App Security admins per user group. For example, you can set a specific user as an administrator for only users in Germany. This would enable the user to view and modify information in Microsoft Cloud App Security only for the user group "Germany - all users." For more information, see [Managing admin access](manage-admins.md).

## Cloud App Security release 124

Released May 27, 2018

- **GDPR risk assessment added to Cloud App Catalog**  
13 new risk factors were added to Microsoft Cloud App Security. These risk factors follow the checklist of the GDPR framework to enable you to assess the apps in the Cloud App Catalog according to the GDPR regulations.

- **Integrate with Microsoft Data Classification Service**  
Microsoft Cloud App Security now enables you to utilize the Microsoft Data Classification Service natively, to classify the files in your cloud apps.   
The Microsoft Data Classification Service provides a unified information protection experience across Office 365, Azure Information Protection, and Microsoft Cloud App Security. It allows you to extend the same data classification framework to the third-party cloud apps that are protected by Microsoft Cloud App Security, leveraging the decisions you already made across an even greater number of apps.

- **Connect to Microsoft Azure** (gradual rollout)  
Microsoft Cloud App Security is extending its IaaS monitoring capabilities beyond Amazon Web Services and now supports Microsoft Azure. This enables you to seamlessly connect and monitor all your Azure subscriptions with Cloud App Security. This connection provides you with a powerful set of tools to protect your Azure environment, including:

  - Visibility into all activities performed through the portal

  - Ability to create custom policies to alert on unwanted behavior, as well as the ability to automatically protect possible risky users by suspending, or forcing them to sign in again.

  - All Azure activities are covered by our anomaly detection engine and will automatically alert on any suspicious behavior in the Azure portal, such as impossible travel, suspicious mass activities, and activity from a new country.  

  For more information, see [Connect Azure to Microsoft Cloud App Security](connect-azure-to-microsoft-cloud-app-security.md).

- **Scoped deployments** (gradual rollout)  
Microsoft Cloud App Security provides enterprises with the ability to granularly determine which users they want to monitor and protect based on group membership. This feature enables you to select users whose activities will not show up for any of the protected applications. The scoped monitoring capability is especially useful for:
  - Compliance – If your compliance regulations necessitate that you refrain from monitoring users from certain countries due to local regulations.
  - Licensing – If you want to monitor fewer users to stay within the limits of your Microsoft Cloud App Security licenses.
  For more information, see [Scoped deployment](scoped-deployment.md).

- **Breached app alert for discovered apps**  
 We now have a built-in alert to notify you when any of a tenant's discovered apps is breached. The alert will provide information about the time and date of the breach, which users used the app, and will link to publicly available sources that provide information about the breach.

- **New mail server**  
 Cloud App Security's mail server changed and uses different IP address ranges. To make sure you can get notifications, add the new IP addresses to your anti-spam whitelist. For users who customize their notifications, Microsoft Cloud App Security enables this for you using MailChimp&reg;, a third-party email service. For the list of mail server IP addresses, and instructions for enabling work with MailChimp, see [Network requirements](network-requirements.md#mail-server) and [Mail settings](mail-settings.md).

## Cloud App Security release 123

Released May 13, 2018

- **Anomaly detection policy scoping**:  
The anomaly detection policies can now be scoped. This enables you to set each anomaly detection policy to include only specific users or groups, and to exclude specific users or groups. For example, you can set the Activity from infrequent county detection to ignore a specific user who travels frequently.

## Cloud App Security release 122

Released April 29, 2018

- Gradual rollout: You can now **set administrative permissions to Microsoft Cloud App Security admins per app**. For example, you can set a specific user as an administrator for only G Suite. This would enable the user to view and modify information in Microsoft Cloud App Security only when it relates exclusively to G Suite. For more information, see [Managing admin access](manage-admins.md).

- Gradual rollout: **Okta admin roles are now visible** in Microsoft Cloud App Security and are available for each role as a tag under **Settings** > **User groups**.

## Cloud App Security release 121

Released April 22, 2018

- The public preview of **Conditional Access App Control (formerly known as Cloud App Security Proxy)** has been enhanced with capabilities that facilitate deeper visibility into, and control over various applications. You can now create a Session Policy with an *Activity type* filter, to monitor, and block a variety of app-specific activities. This new filter augments the existing file download control features, to provide you with comprehensive control of the applications in your organization and works hand-in-hand with Azure Active Directory conditional access, to provide real-time visibility and control of risky user sessions — for example, sessions with B2B collaboration users or users coming from an unmanaged device. For more information, see [Session policies](session-policy-aad.md).

- Gradual roll out: Cloud App Security's **anomaly detection policies have been improved** to include two new types of threat detection: Ransomware activity and Terminated user activity. Cloud App Security extended its ransomware detection capabilities with anomaly detection to ensure a more comprehensive coverage against sophisticated Ransomware attacks. Using our security research expertise to identify behavioral patterns that reflect ransomware activity, Cloud App Security ensures holistic and robust protection. Terminated user activity enables you to monitor the accounts of terminated users, who may have been de-provisioned from corporate apps, but in many cases they still retain access to certain corporate resources. For more information, see [Get instantaneous behavioral analytics and anomaly detection](anomaly-detection-policy.md).

## Cloud App Security release 120

Released April 8, 2018

- For Office 365 and Azure AD, we are now gradually rolling out the ability to detect internal applications as user account activities performed by the Office 365 and Azure AD applications (both internal and external). This enables you to create policies that will alert you if an application performs unexpected and unauthorized activities.

- When exporting an app permissions list to csv, additional fields such as publisher, permissions level, and community usage are included to assist with the compliance and investigation process.

- The ServiceNow connected app was improved so that internal service activities no longer register as having been performed by "Guest" and no longer trigger false positive alerts. These activities are now represented as N/A like all other connected apps.

## Cloud App Security release 119

Released March 18, 2018

- The IP address ranges page includes built-in IP addresses that are discovered by Cloud App Security. This includes IP addresses for identified cloud services, like Azure and Office 365, as well as the Threat intelligence feed that automatically enriches IP addresses with information about known risky IP addresses.

- When Cloud App Security attempts to run a governance action on a file but fails because the file is locked, it will now automatically retry the governance action.

## Cloud App Security release 118

Released March 4, 2018

- You can now take advantage of Microsoft Cloud App Security's shadow IT discovery and monitoring capabilities on your own proprietary custom apps. The new ability to add custom apps to Cloud Discovery enables you to monitor app usage and get alerted on changes in the usage pattern. For more information, see [Protecting your custom apps](cloud-discovery-custom-apps.md). This feature is being rolled out gradually.

- The Cloud App Security portal **Settings** pages were redesigned. The new design consolidates all the settings pages, provides search functionality, and an improved design.

- Cloud Discovery now supports Barracuda F-Series Firewalls and Barracuda F-Series Firewall Web Log Streaming.

- The search functionality in the User and IP address pages now enables auto complete to make it easier for you to find what you're looking for.

- You can now perform bulk actions in the Exclude entities and Exclude IP address settings pages. This makes it easier for you to select multiple users and groups or IP addresses and exclude them from being monitored as part of the Cloud Discovery in your organization.

## Cloud App Security release 117

Released February 20, 2018

- Cloud App Security deepened integration with Azure Information Protection now enables you to protect files in G Suite. This public preview feature enables you to scan and classify files in G Suite, and automatically apply Azure Information protection labels for protection. For more information, see [Azure Information Protection integration](azip-integration.md).

- Cloud Discovery now supports [Digital Arts i-FILTER](https://www.daj.jp/en/products/if/).

- The SIEM agents table now includes more detail for easier management.

## Cloud App Security release 116

Released February 4, 2018

- Cloud App Security's anomaly detection policy was enhanced with new **scenario-based detections** including impossible travel, activity from a suspicious IP address, and multiple failed login attempts. The new policies are automatically enabled, providing out-of-the-box threat detection across your cloud environment. In addition, the new policies expose more data from the Cloud App Security detection engine, to help you speed up the investigation process and contain ongoing threats. For more information, see [Get instantaneous behavioral analytics and anomaly detection](/cloud-app-security/anomaly-detection-policy).

- Gradual roll out: Cloud App Security now correlates between users and their accounts across SaaS apps. This enables you to easily investigate all the activities for a user, across all their various correlated SaaS apps, no matter which app or account they used.

- Gradual roll out: Cloud App Security now supports multiple instances of the same connected app. If you have multiple instances of, for example, Salesforce (one for sales, one for marketing) you will be able to connect them both to Cloud App Security and manage them from the same console to create granular policies and deeper investigation.

- The Cloud Discovery parsers now support two additional Checkpoint formats, XML, and KPC.

## Cloud App Security release 115

Released January 21, 2018

- This release provides an improved experience when selecting specific folders in file policies. You can now easily view and select multiple folders to include in a policy.
- In the **Discovered apps** page:
  - The bulk tagging feature enables you to apply custom tags (in addition to sanctioned and unsanctioned tags).
  - When you **Generate an IP addresses report**, or **Generate a users report** the exported reports now include the information about whether the traffic was from sanctioned or unsanctioned apps.
- You can now request a new API App connector from the Microsoft Cloud App Security team directly in the portal, from the **Connect an app** page.

## Cloud App Security release 114

Released January 7, 2018

- Beginning in version 114, we are gradually rolling out the ability to create and save custom queries in the Activity log and Discovered apps pages. Custom queries enable you to create filter templates that can be reused for deep-dive investigation. In addition, **Suggested queries** have been added to provide out-of-the-box investigation templates to filter your activities and discovered apps. The **Suggested queries** include custom filters to identify risks such as impersonation activities, administrator activities, risky non-compliant cloud storage apps, enterprise apps with weak encryption, and security risks. You can use the **Suggested queries** as a starting point, modify them as you see fit, and then save them as a new query. For more information, see [Activity filters and queries](activity-filters-queries.md) and [Discovered app filters and queries](discovered-app-queries.md).

- You can now check the current Cloud App Security service status by going [status.cloudappsecurity.com](https://status.cloudappsecurity.com) or directly from within the portal by clicking on **Help**>**System status**.

## See Also

For a description of releases prior to those listed here, see [Past releases of Microsoft Cloud App Security](release-note-archive.md).

[!INCLUDE [Open support ticket](includes/support.md)]
