---
title: Archive of past updates 
description: This article is an archive that describes updates made in past releases of Defender for Cloud Apps.
ms.date: 01/29/2023
ms.topic: conceptual
---
# Archive of past updates for Microsoft Defender for Cloud Apps

[!INCLUDE [Banner for top of topics](includes/banner.md)]

This article is an archive that describes updates made in past releases of Defender for Cloud Apps. To see the latest what's new list, see [What's new in Defender for Cloud Apps](release-notes.md).

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

  - All GCP activities are covered by our anomaly detection engine and will automatically alert on any suspicious behavior, such as impossible travel, suspicious mass activities, and activity from a new country.

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

- **Office 365 workload granularity**  
When connecting Office 365 to Microsoft Cloud App Security, you now have control over which workloads you want to connect. For example, customers only interested in connecting Office 365 for activity monitoring can now do so during the connection process, or by editing an existing Office 365 connector. As part of this change, OneDrive and SharePoint will no longer be shown as separate connectors but will be included in the Office 365 connector as the *Office 365 files* workload. Customers with an existing Office 365 connector are not impacted by this change.

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
  - The data admin and security operator Office 365 roles are now supported in Cloud App Security. The data admin role enables users to manage everything file related, as well as view the Cloud Discovery reports. Security operators have permission to manage alerts and view policy configuration.
  - The security reader role now has the ability to configure the SIEM agent, allowing better permission scoping.

- **Microsoft Flow support**  
Cloud App Security now monitors user activities in Microsoft Flow. The activities supported are the activities reported by Flow to the Office 365 audit log.

- **Alert entity grouping**  
The **Alert** page now groups related entities that were involved in an alert to aid in your investigation.

### Cloud App Security release 142

Released February 3, 2019

- **Session policy configuration in Azure AD**  
You can now configure session policies to monitor users or block downloads in real-time, directly in Azure AD conditional access. You can still configure advanced session policies directly in Cloud App Security. To walk through this deployment, see [Deploy Conditional Access App Control for Azure AD apps](proxy-deployment-aad.md).

- **Suggested and Saved queries for OAuth apps**  
Suggested queries have been added to the OAuth apps page provide out-of-the-box investigation templates to filter your OAuth apps. Suggested queries include custom filters to identify risky apps such as apps authorized by administrators. Saved queries enable you to save custom queries for future use, similar to saved queries available today in the Activity log and Discovery pages.

- **Office 365 auditing default configuration**  
If you want to enable monitoring of Office 365 activities in Cloud App Security, you are now required to enable auditing in the [Office Security and Compliance Center](/microsoft-365/compliance/turn-audit-log-search-on-or-off#turn-on-audit-log-search), this is a result of a [change to Office 365 auditing](/office/office-365-management-api/troubleshooting-the-office-365-management-activity-api#frequently-asked-questions-about-the-office-365-management-activity-api). This change only needs to be performed if you haven't already enabled monitoring of Office 365 activities in Cloud App Security.

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
  - You can also configure whether the alerts for Activity from infrequent country, anonymous IP addresses, suspicious IP addresses, and  impossible travel should analyze both failed and successful logins or just successful logins.

- **Support for multiple trust chains**  
Conditional Access App Control now supports adding and using multiple trusted root or intermediate certificates as a form of device management.

- **New Cloud Discovery role** (gradual rollout)  
Cloud App Security now provides a new admin role for Cloud Discovery users. This role can be used in order to scope the access of an admin user to only Cloud Discovery settings and data within the Cloud App Security portal.

- **Support for Microsoft Purview Information Protection unified labels** (gradual rollout)  
Cloud App Security now supports Microsoft Purview Information Protection unified labels. For customers that already [migrated their classification labels for the Office 365 Security and Compliance Center](/azure/information-protection/configure-policy-migrate-labels), Cloud App Security will identify and work with these labels as described in [Integrating with Azure Information Protection](azip-integration.md).

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
Cloud App Security now includes support for the Microsoft Dynamics activities that are supported in the Office 365 audit log.

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

- **Conditional Access App Control for Office 365 is now in Public Preview**  
  - Conditional Access App Control now also supports Office 365 and any app that is configured with Open ID Connect.
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
To provide a more consistent admin experience across Office 365 products and enable you to more easily pivot between Microsoft security solutions, the Cloud App Security portal menu bar moved to the left side of the screen. This consistent navigation experience helps you orient yourself when moving from one Microsoft security portal to another.

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

- You now have the ability to see generic activities for Office 365. In the **Activity log** and in **Activity policies** you can now filter the Office 365 activities for **Unspecified** activities. Reviewing these activities enables you to investigate information about activities performed that aren't yet classified by type in Cloud App Security, and you can use these activities to send requests to the Cloud App Security team to create new activity types based on these activities.

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
Microsoft Cloud App Security added a new investigation widget to the dashboard that shows top users by the number of open threat detection alerts. This investigation widget enables you to focus your threat investigation on users with the highest number of suspicious sessions.

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
The Microsoft Data Classification Service provides a unified information protection experience across Office 365, Azure Information Protection, and Microsoft Cloud App Security. It allows you to extend the same data classification framework to the third-party cloud apps that are protected by Microsoft Cloud App Security, leveraging the decisions you already made across an even greater number of apps.

- **Connect to Microsoft Azure** (gradual rollout)  
Microsoft Cloud App Security is extending its IaaS monitoring capabilities beyond Amazon Web Services and now supports Microsoft Azure. This enables you to seamlessly connect and monitor all your Azure subscriptions with Cloud App Security. This connection provides you with a powerful set of tools to protect your Azure environment, including:

  - Visibility into all activities performed through the portal

  - Ability to create custom policies to alert on unwanted behavior, as well as the ability to automatically protect possible risky users by suspending, or forcing them to sign in again.

  - All Azure activities are covered by our anomaly detection engine and will automatically alert on any suspicious behavior in the Azure portal, such as impossible travel, suspicious mass activities, and activity from a new country.  

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

- For Office 365 and Azure AD, we are now gradually rolling out the ability to detect internal applications as user account activities performed by the Office 365 and Azure AD applications (both internal and external). This enables you to create policies that will alert you if an application performs unexpected and unauthorized activities.

- When exporting an app permissions list to csv, additional fields such as publisher, permissions level, and community usage are included to assist with the compliance and investigation process.

- The ServiceNow connected app was improved so that internal service activities no longer register as having been performed by "Guest" and no longer trigger false positive alerts. These activities are now represented as N/A like all other connected apps.

### Cloud App Security release 119

Released March 18, 2018

- The IP address ranges page includes built-in IP addresses that are discovered by Cloud App Security. This includes IP addresses for identified cloud services, like Azure and Office 365, as well as the Threat intelligence feed that automatically enriches IP addresses with information about known risky IP addresses.

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

- Do not track is now available for private preview customers! You can now control which users' activity data is processed. This feature enables you to set specific groups in Cloud App Security as "Do not track". For example, you can now decide not to process any activity data for users located in Germany or any country that is not bound by a specific compliance law. This can be implemented across all apps in Cloud App Security, for a specific app, or even for a specific subapp. Additionally, this feature can be used to facilitate gradual roll out of Cloud App Security. For more information or to join the private preview for this feature, contact support or your account representative.

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

- You can now require users to sign in again to all Office 365 and Azure AD apps. Require sign in again as a quick and effective remediation for suspicious user activity alerts and compromised accounts. You can find the new governance in the policy settings and the alert pages, next to the Suspend user option.
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

- RBAC for Security Readers completed roll out. This feature enables you to manage the permissions you grant to your admins inside the Cloud App Security console. By default, all Azure Active Directory admins, Office 365 Global admins, and Security admins have full permissions in the portal. All Security readers in Azure Active Directory and Office 365 have read-only access in Cloud App Security. You can add additional admins or override permissions using the "Manage Access" option. For more information, see [Managing admin permissions](manage-admins.md).
- We're now rolling out detailed threat intelligence reports for risky IP addresses detected by Microsoft intelligent security graph. When an activity is performed by a botnet, you'll see the name of the botnet (if available) with a link to a detailed report about the specific botnet.

### Cloud App Security release 97

Released May 24, 2017

**New features:**

- Investigate files and policy violations: You can now see all policy matches in the Files page. Additionally, the File Alert page has been improved to now include a separate tab for History of the specific file. The improvement enables you to drill down into the violation history across all policies for the specific file. Every History event includes a snapshot of the file at the time of the alert. It will include an indication of whether the file was deleted or quarantined.
- [Admin quarantine](use-case-admin-quarantine.md) is now available in private preview for Office 365 SharePoint and OneDrive for Business files. This feature enables you to quarantine files that match policies or set an automated action to quarantine them. Quarantining removes the files from the user's SharePoint directory and copies the originals to the admin quarantine location you choose.

**Cloud Discovery improvements:**

- Cloud Discovery support for Cisco Meraki logs has been improved.
- The option to suggest an improvement to Cloud Discovery now enables you to suggest new risk factor.
- The custom log parser was improved to support log formats by separating the setting of time and date and to give you the option to set timestamp.
- Starting to roll out the ability to create custom discovery reports based on Azure Active Directory user groups. For example, if you want to see the cloud use of your marketing department, import the marketing group using the import user group feature, and then create a custom report for this group.

**Other updates:**

- Cloud App Security now includes support for the Microsoft Power BI activities that are supported in the Office 365 audit log. This feature is being rolled out gradually. You need to enable [this functionality in the Power BI portal](/power-bi/admin/service-admin-auditing).
- In activity policies, you can now set notify and suspend actions to be taken on the user across all connected apps. For example, you can set a policy to always notify the user's manager and suspend the user immediately whenever the user has multiple failed logins in any connected app.

### OOB release

- In a speedy reaction to the ransomware sweeping the globe, on Sunday, the Cloud App Security team added a new [Potential ransomware activity detection policy](use-case-ransomware.md) template to the portal that includes the signature extension of WannaCrypt. We advise you to the set this policy today.

### Cloud App Security release 96

Released May 8, 2017

**New features:**

- Continuing the gradual roll out of the Security Reader permission, which enables you to manage the permissions you grant to your admins inside the Cloud App Security console. By default, all Azure Active Directory and Office 365 Global admins and Security admins have full permissions in the portal. All Security readers in Azure Active Directory and Office 365 will have read-only access in Cloud App Security. For more information, see [Managing admin permissions](manage-admins.md).
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

- For Microsoft work accounts (Office 365 and Azure Active Directory), Cloud App Security groups different user identifiers such as proxy addresses, aliases, SID, and more under a single account. All aliases related to an account will appear under the primary email address. Based on the list of user identifiers, for activities whose actor is a user identifier, the actor will be displayed as the primary user name UPN (User Principal Name). Based on the UPN, groups will be assigned and policies applied. This change will improve investigation of activities and fuse all related activities to the same session for anomalies and group-based policies. This feature will be gradually rolled out over the next month.

- The Robot tag was added as a possible risk factor in the Browser Use built-in report. Now, in addition to browser use being tagged as outdated, you can see when browser use was performed by a robot.
- When creating a content inspection file policy, you can now set the filter to include only files with at least 50 matches.

### Cloud App Security release 94

Released April 2, 2017

**New features:**

- Cloud App Security is now integrated with Azure RMS. You can protect files in Office 365 OneDrive and Sharepoint Online with Microsoft Rights Management directly from the Cloud App Security portal. Protection can be accomplished from the **Files** page. For more information, see [Integrating with Azure Information Protection](azip-integration.md). Support for additional applications will be available in future versions.
- Up until now, when robot and crawler activities take place on your network, it was especially hard to identify because the activities are not performed by a user on your network. Without your knowledge, bots and crawlers can run malicious tools on your computers. Now, Cloud App Security gives you the tools to see when robots and crawlers are performing activities on your network. You can use the new user agent tag to filter activities in the activity log. The user agent tag enables you to filter all activities performed by robots and you can use it to create a policy that alerts you each time this type of activity is detected. You'll be updated when future releases will include this risky activity as embedded into the anomaly detection alerts.
- The new unified app permissions page enables you to more easily investigate the permissions your users have given to third-party apps. By clicking on **Investigate** > **App permissions**, you can now view a list of all the permissions your users gave to third-party apps. A page of app permissions per connected app enables you to better compare between the various apps and the permissions granted. For more information, see [Manage app permissions](manage-app-permissions.md).
- You can filter data right from the table drawer for easier investigation.
In the **Activity log**, the **Files** table and **App permissions** pages are now enhanced with new contextual actions that makes pivoting in the investigation process a lot easier. We also added quick links to configuration pages and the ability to copy data with a single click. For more information, see the information about [working with the file and activity drawers](file-filters.md).
- Support for Microsoft Teams to Office 365 Activity logs and alerts rollout was completed.

### Cloud App Security release 93

Released March 20, 2017

**New features:**

- You can now apply policies to include or exclude imported user groups.
- Cloud App Security Anonymization now enables you to configure a custom encryption key. For more information, see [Cloud Discovery anonymization](cloud-discovery-anonymizer.md).
- In order to have more control over user and account management, you now have direct access to Azure AD account settings for each user and account from within the **Account** page. Just click the cog next to each user. This change enables easier access to advanced user management features group management, configuration of MFA, details about user sign-ins, and the ability to block sign-in.
- You can now export a blocking script for unsanctioned apps via the Cloud App Security API. Learn about our APIs in the Cloud App Security portal by clicking the question mark in the menu bar, followed by **API documentation**.
- The Cloud App Security app connector for ServiceNow was expanded to include support for OAuth tokens (as introduced in Geneva, Helsinki, Istanbul). This change provides a more robust API connection to ServiceNow that doesn't rely on the deploying user. For more information, see [Connect ServiceNow to Microsoft Cloud App Security](./connect-servicenow.md). Existing customers can update their settings in the ServiceNow App connector page.
- If you configured additional third-party DLP scanners, DLP scan status will now show the status of each connector independently to improve visibility.
- Cloud App Security now includes support for the Microsoft Teams activities that are supported in the Office 365 audit log. This feature is being rolled out gradually.
- For Exchange Online impersonation events, you can now filter by the permission level used - delegated, admin, or delegated admin. You can search for events displaying the impersonation level that interests you in the **Activity log** by searching for **Activity objects** > **Item**.
- In the app drawer on the **App Permissions** tab of Office 365 apps, you can now see the **Publisher** of each app. You can also use the Publisher as a filter for investigation of additional apps from the same publisher.
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

- **Import user groups (preview)**   When you connect apps using API connectors, Cloud App Security now enables you to import user groups, from Office 365 and Azure Active Directory. Typical scenarios that leverage imported user groups include: investigating which docs the HR people look at, or you can check if there's something unusual happening in the executive group, or if someone from the admin group performed an activity outside the US. For details and instructions, see [Importing user groups](user-groups.md).

- In the Activity log, you can now filter users and users in groups to show which activities were performed by a specific user, and which were performed on a specific user. For example, you can investigate activities in which the user impersonated others, and activities in which others impersonated this user. For more information, see [Activities](activity-filters.md).

- When investigating a file in the **Files** page, if you drill down into the **Collaborators** of a specific file, you can now see more information about the collaborators. This information includes if they're Internal or External, Writers or Readers (file permissions), and when a file is shared with a group you can now see all users who are members of the group. Seeing all users enables you to see if the group members are external users.

- IPv6 support is now available for all appliances.

- Cloud Discovery now supports Barracuda appliances.

- Cloud App Security system alerts now cover SIEM connectivity errors. For more information, see [SIEM integration](siem.md).

- Cloud App Security now includes support for the following activities:

  - **Office 365, SharePoint/OneDrive**: Update application configuration, Remove owner from group, Delete site, Create folder

  - **Dropbox**: Add member to group, Remove member from group, Create group, Rename group, Change team member name

  - **Box**: Remove item from group, Update item share, Add user to group, Remove user from group

### Cloud App Security release 89

Released January 22, 2017

**New features:**

- We're starting to roll out the ability to view Office 365 Security and Compliance Center DLP events in Cloud App Security. If you configured DLP policies in the Office 365 Security and Compliance Center, when policy matches are detected, you'll see them in the Cloud App Security Activity log. The information in the Activity log will include the file or email that triggered the match as and the policy or alert that it matched. The **Security event** activity allows you to view Office 365 DLP policy matches in the Cloud App Security activity log. Using this feature, you can:
  - See all DLP matches coming from the Office 365 DLP engine.
  - Alert on Office 365 DLP policy matches for a specific file, SharePoint site, or policy.
  - Investigate DLP matches with a broader context, for example- external users who accessed or downloaded a file that triggered a DLP policy match.

- The activity descriptions have been improved for clarity and consistency. Each activity now provides a feedback button. If there are some things you don't understand or have a question about, you can let us know.

**Improvements:**

- A new governance action was added for Office 365 that enables you to remove all external users of a file. For instance, this action enables you to implement policies that **remove external shares from files with internal only classification**.
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

- New Office 365 (Exchange) mailbox-related events having to do with forwarding rules and adding and removing delegate mailbox permissions.
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

- Cloud App Security now supports for Microsoft Azure Information Protection including enhanced integration and autoprovisioning. You can filter your Files and set File policies using the Tag Secure Classification and then set the classification label you want to view. The labels also indicate whether the classification was set by someone in your organization or by people from another tenant (External). You can also set activity policies, based on the Azure Information Protection classification labels and enable automatic scan for classification labels in Office 365. For more information on how to take advantage of this great new feature, see [Integrating with Azure Information Protection](azip-integration.md).

**Improvements:**

- Improvements were made to the Cloud App Security activity log:
  - Office 365 events from the Security and Compliance Center are now integrated with Cloud App Security and are visible in the **Activity log**.
  - All Cloud App Security activity is registered in the Cloud App Security activity log as administrative activity.
- To help you investigate file-related alerts, in each alert that results from a file policy, you can now view the list of activities that were performed on the matched file.
- The impossible travel algorithm in the anomaly detection engine was improved to provide better support for small tenants.

**Minor improvements:**

- The **Activity export limit** was raised to 10,000.
- When creating a **Snapshot report** in the Cloud Discovery manual log upload process, you now receive an accurate estimate for how long the log processing will take.
- In a file policy, the **Remove collaborator** governance action now works on groups.
- Minor improvements were made in the **App permissions** page.
- When more than 10,000 users have granted permissions to an app that connects to Office 365, the list loaded slowly. This slowness has been fixed.
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
- Improvement in the update frequency of Office 365 third-party app scan.
- Improvements in the Cloud Discovery dashboard.
- The Checkpoint Syslog parser was improved.
- Improvements in the Governance Log for banning and unbanning third-party apps.

**Bug fixes:**

- Improved process for uploading a logo.

### Cloud App Security release 81

Released September 18, 2016

**Improvements:**

- Cloud App Security is now a first-party app in Office 365! From now on, you can connect Office 365 to Cloud App Security in a single click.

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
  - Office 365 activity is now monitored for high-download rates. If the Office 365 download rate is much higher than your organization's, or a specific user's, normal download rate, an Anomaly Detection alert is triggered.
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
- New IP address tags were added for Office 365 Apps for enterprise, OneNote, Office Online, and Exchange Online Protection.
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
- Simplified investigation and control for Office 365 - Selection of Office 365 automatically selects all apps that are part of the Office 365 Suite.
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
- A new filter was added that enables you to search for any Office 365 object (files, folders, URLs).
- The ability was added to configure a minimal risk score for Anomaly detection policies.
- When you set an alert to be sent when a policy is violated, you can now set a minimum severity level for which you want to be alerted. You can choose to use your organization's default setting for this and you can set a specific alert setting as the default for your organization.

[!INCLUDE [Open support ticket](includes/support.md)]
