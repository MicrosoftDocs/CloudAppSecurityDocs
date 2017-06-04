---
# required metadata

title: Cloud App Security release notes & versions | Microsoft Docs
description: This topic is updated frequently to let you know what's new in the latest release of Cloud App Security.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 6/4/2017
ms.topic: article
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: d418ef3d-76ee-45d5-b5ae-21346e5239a3

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Release notes

## Cloud App Security release 98 
Released June 4, 2017
 
Cloud Discovery updates:
-	Users can now perform advanced filtering on discovered apps, to enable you to perform deep investigation such as filtering apps based on usage - how much upload traffic from discovered apps of certain types, how many users used certain categories of discovered apps. You can also perform multi-selection in the left panel to select multiple categories. 
-	Started roll out of new templates for Cloud Discovery which are based on popular searches, for example "non-compliant cloud storage app". These basic filters can be used as templates to perform analysis on your discovered apps.
-	For ease of use, you can now perform actions such as sanction and unsanction across multiple apps in one action.
-	We are now rolling out the ability to create custom discovery reports based on Azure Active Directory user groups. For example, if you want to see the cloud use of your marketing department, you can import the marketing group using the import user group feature, and then create a custom report for this group.

New features:
-	RBAC for Security Readers completed roll out. This feature enables you to manage the permissions you grant to your admins inside the Cloud App Security console. By default, all Azure Active Directory and Office 365 Global admins and Security admins have full permissions in the portal, and all Security readers in Azure Active Directory and Office 365 have read-only access in Cloud App Security. You can add additional admins or override permissions using the “Manage Access” option. For more information see [Managing admin permissions](manage-admins.md).
-	Detailed threat intelligence reports are now available for risky IP addresses detected by Microsoft intelligent security graph: when an activity is performed by a botnet, you will see the name of the botnet (if available) with a link to a detailed report about the specific botnet.
 
## Cloud App Security release 97
Released May 24, 2017

### New features
-	Investigate files and policy violations: You can now see all policy matches in the Files page. In addition, you the File Alert page has been improved to now include a separate tab for History of the specific file enabling you to drill down into the violation history across all policies for the specific file. Every History event includes a snapshot of the file at the time of the alert. It will include an indication of whether the file was deleted or quarantined.
-	[Admin quarantine](use-case-admin-quarantine.md) is now available for Office 365 SharePoint and OneDrive for Business files, in private preview. This feature enables you to quarantine files that match policies, or set an automated action to quarantine them, removing them from the user’s SharePoint directory and copying the original file to the admin quarantine location of your choice.
        
### Cloud Discovery improvements

-	Cloud Discovery support for Cisco Meraki logs has been improved.
-	The option to suggest an improvement to Cloud Discovery now enables you to suggest new risk factor.
-	The custom log parser was improved to support log formats by separating the setting of time and date and to give you the option to set timestamp.
-	Starting to roll out the ability to create custom discovery reports based on Azure Active Directory user groups. For example, if you want to see the cloud use of your marketing department, you can import the marketing group using the import user group feature, and then create a custom report for this group.
Other updates
-	Cloud App Security now includes support for the Microsoft Power BI activities that are supported in the Office 365 audit log. This feature is being rolled out gradually. Note that you need to enable [this functionality in the Power BI portal](https://powerbi.microsoft.com/documentation/powerbi-admin-auditing/).
-	In activity policies, you can now set notify and suspend actions to be taken on the user across all connected apps. For example, you can set a policy to always notify the user's manager and suspend the user immediately whenever the user has multiple failed logins in any connected app.
 
## OOB release
-	In a speedy reaction to the ransomware sweeping the globe, on Sunday, the Cloud App Security team added a new [Potential ransomware activity detection policy](use-case-ransomware.md) template to the portal that includes the signature extension of WannaCrypt. We advise you to the set this policy today.

## Cloud App Security release 96
Released May 8, 2017

New features:

-	Continuing the gradual roll out of the Security Reader permission which enables you to manage the permissions you grant to your admins inside the Cloud App Security console. By default, all Azure Active Directory and Office 365 Global admins and Security admins have full permissions in the portal, and all Security readers in Azure Active Directory and Office 365 will have read-only access in Cloud App Security. For more information see [Managing admin permissions](manage-admins.md).
-	Completed roll out of Cloud Discovery support for user-defined log parsers for CSV-based logs. Cloud App Security enables you to configure a parser for your previously unsupported appliances by providing you with the tools to delineate which columns correlate to specific data. For more information see [Custom log parser](custom-log-parser.md).

Improvements:

-	Cloud Discovery now supports Juniper SSG appliances.
-	Cloud Discovery support for Cisco ASA logs has been improved for better visibility.
-	You can now more easily run bulk actions and select multiple records in Cloud App Security portal tables: the page length has been increased to improve bulk operations.
-	The **Outbound sharing by domain**, and **Owners of shared files** built-in reports can now be run for Salesforce data.
-	We are starting rollout of additional Salesforce activities enabling you to track interesting information that was extracted from the activity data. These activities include viewing and editing accounts, leads, opportunities and various other interesting Salesforce objects.
-	New activities were added for Exchange to enable you to monitor which permissions were granted for user mailboxes or mailbox folders. These activities include:
    -	Add recipient permissions
    -	Remove recipient permissions
    -	Add mailbox folder permissions
    -	Remove mailbox folder permissions
    -	Set mailbox folder permissions

    For example, you can now monitor users who were granted **SendAs** permissions to other users’ mailboxes and as a result can now send emails in their name.


## Cloud App Security release 95 (in roll out)
Released April 24, 2017

**Updates**
- The **Accounts** page has been updated with improvements that make detecting risks easier. You can now more easily filter for internal and external accounts, see at a glance whether a user has admin permissions and you can perform actions on each account per-app simply (such as remove permissions, remove user’s collaborations, suspend user). In addition, imported [user groups](user-groups.md) for each account will be displayed. 

- For Microsoft work accounts (Office 365 and Azure Active Directory), Cloud App Security groups different user identifiers such as proxy addresses, aliases, SID and more under a single account. All aliases related to an account will appear under the primary email address. Based on the list of user identifiers, for activities whose actor is a user identifier, the actor will be displayed as the primary user name UPN (User Principal Name). Based on the UPN, groups will be assigned and policies applied. This will improve investigation of activities and fuse all related activities to the same session for anomalies and group based policies. This feature will be gradually rolled out over the next month.

- The Robot tag was added as a possible risk factor in the Browser Use built-in report. Now, in addition to browser use being tagged as outdated, you can see when browser use was performed by a robot. Learn more about the [built-in reports](built-in-report-reference.md).

- When creating a content inspection file policy, you can now set the filter to include only files with at least 50 matches.



## Cloud App Security release 94
Released April 2, 2017

**New features:**
-	Cloud App Security is now integrated with Azure RMS. You can protect files in Office 365 OneDrive and Sharepoint Online with Microsoft Rights Management directly from the Cloud App Security portal. This can be accomplished from the **Files** page. For more information see [Integrating with Azure Information Protection](azip-integration.md). Support for additional applications will be available in future versions.
-	Up until now, when robot and crawler activities take place on your network, it was especially hard to identify because the activities are not performed by a user on your network. Without your knowledge, bots and crawlers can run malicious tools on your computers. Now, Cloud App Security gives you the tools to see when robots and crawlers are performing activities on your network. You can use the new user agent tag to filter activities in the activity log. The user agent tag enables you to filter all activities performed by robots and you can use it to create a policy that alerts you each time this type of activity is detected. You will be updated when future releases will include this risky activity as embedded into the anomaly detection alerts. 
-	The new unified app permissions page enables you to more easily investigate the permissions your users have given to third party apps. By clicking on **Investigate** > **App permissions**, you can now view a list of all the permissions your users gave to third-party apps with a page of app permissions per connected app that enables you to better compare between the various apps and the permissions granted.  For more information, see [Manage app permissions](manage-app-permissions.md).
-	You can filter data right from the table drawer for easier investigation.
In the **Activity log**, the **Files** table and **App permissions** pages are now enhanced with new contextual actions that makes pivoting in the investigation process a lot easier. We also added quick links to configuration pages and the ability to copy data with a single click. For more information see the information about [working with the file and activity drawers](file-filters.md).
-	Support for Microsoft Teams to Office 365 Activity logs and alerts roll out was completed.
 



## Cloud App Security release 93
Released March 20, 2017

**New features:**
-   You can now apply policies to include or exclude imported user groups. 
-	Cloud App Security Anonymization now enables you to configure a custom encryption key. For more information, see [Cloud Discovery anonymization](cloud-discovery-anonymizer.md).
-	In order to have more control over user and account management, you now have direct access to Azure AD account settings for each user and account from within the **Account** page by clicking the cog next to each user. This enables easier access to advanced user management features group management, configuration of MFA, details about user sign-ins and the ability to block sign-in. 
-	You can now export a blocking script for unsanctioned apps via the Cloud App Security API. Read more about our APIs in the Cloud App Security portal by clicking the question mark in the menu bar, followed by **API documentation**.
-	The Cloud App Security app connector for ServiceNow was expanded to include support for OAuth tokens (as introduced in Geneva, Helsinki, Istanbul). This provides a more robust API connection to ServiceNow which does not rely on the deploying user. For more information see [Connect ServiceNow to Microsoft Cloud App Security](connect-servicenow-to-microsoft-cloud-app-security.md). Existing customers can update their settings in the ServiceNow App connector page.
-	If you configured additional third-party DLP scanners, DLP scan status will now show the status of each connector independently to improve visibility.
-	Cloud App Security now includes support for the Microsoft Teams activities that are supported in the Office 365 audit log. This feature is being rolled out gradually.
-	For Exchange Online impersonation events, you can now filter by the permission level used - delegated, admin or delegated admin. You can search for events displaying the impersonation level that interests you in the **Activity log** by searching for **Activity objects** > **Item**.
-	In the app drawer on the App Permissions tab you can now see the **Publisher** of each app. You can also use the Publisher as a filter for investigation of additional apps from the same publisher.
-	Risky IP addresses now show up as an independent risk factor rather than weighted under the general **Location** risk factor. 
-	When Azure Information Protection labels are disabled on a file, the disabled labels will appear as disabled in Cloud App Security. Deleted labels will not be displayed.
 
**Additional Salesforce support:**
-	You can now suspend and unsuspend Salesforce users in Cloud App Security. This can be accomplished in the **Accounts** tab of the Salesforce Connector by clicking the cog at the end of the row of a specific user, and selecting **Suspend** or **Unsuspend** and can also be applied as a governance action as part of a policy. All suspend and unsuspend activities taken in Cloud App Security will be logged in the [Governance log](governance-actions.md). 
-	Improved visibility to Salesforce content sharing: You can now see which files were shared with whom, including publicly shared files, files shared with groups and files shared with the entire Salesforce domain. Improved visibility will be rolled out retroactively to new and current connected Salesforce apps, it may take a while for this to update the first time.
-	We improved coverage for the following Salesforce events, and separated them out of the **Manage users** activity: 
    - Edit permissions
    - Create user
    - Change role
    - Reset password

## Cloud App Security release 90, 91, 92
Released February, 2017

**Special announcement**

Cloud App Security is now officially certified with Microsoft Compliance for ISO, HIPAA, CSA STAR, EU model clauses and more. Please see the full list of certifications go to [Microsoft Compliance Offerings](https://www.microsoft.com/trustcenter/compliance/complianceofferings) and select Cloud App Security.

**New features**

-  **Import user groups (preview)**   When you connect apps using API connectors, Cloud App Security now enables you to import user groups, from Office 365 and Azure Active Directory. Typical scenarios that leverage imported user groups include: investigating which docs the HR people look at, or you can check if there's something unusual happening in the executive group, or if someone from the admin group performed an activity outside the US. For details and instructions, see [Importing user groups](user-groups.md).

-  In the Activity log, you can now filter users and users in groups to show which activities were performed by a specific user, and which were performed on a specific user. For example, you can investigate activities in which the user impersonated others, and activities in which others impersonated this user. For more information, see [Activities](activity-filters.md).

- When investigating a file in the **Files** page, if you drill down into the **Collaborators** of a specific file, you can now see more information about the collaborators, including whether or not they are Internal or External, Writers or Readers (file permissions), and when a file is shared with a group, you can now see all users who are members of the group. This enables you to see if the group members are external users.

-  IPv6 support is now available for all appliances.

-	Cloud Discovery now supports Baracuda appliances.

-	Cloud App Security system alerts now cover SIEM connectivity errors. For more information see [SIEM integration](siem.md).

-	Cloud App Security now includes support for the following activities:

     **Office 365, SharePoint/OneDrive**: Update application configuration, Remove owner from group, Delete site, Create folder

     **Dropbox**: Add member to group, Remove member from group, Create group, Rename group, Change team member name

     **Box**: Remove item from group, Update item share, Add user to group, Remove user from group


## Cloud App Security release 89
Released January 22, 2017

**New features**
-	We are starting to roll out the ability to view Office 365 Security and Compliance Center DLP events in Cloud App Security. If you configured DLP policies in the Office 365 Security and Compliance Center, when policy matches are detected, you will be able to see them in the Cloud App Security Activity log. The information in the Activity log will include the file or email that triggered the match as and the policy or alert that it matched. The **Security event** activity allows you to view Office 365 DLP policy matches in the Cloud App Security activity log. Using this feature, you can:
    -	See all DLP matches coming from the Office 365 DLP engine.
    -	Alert on Office 365 DLP policy matches for a specific file, SharePoint site, or policy.
    -	Investigate DLP matches with a broader context, for example- external users who accessed or downloaded a file that triggered a DLP policy match.
 
-	The activity descriptions have been improved for clarity and consistency. Each activity now provides a feedback button, so if there are some that you don’t understand or have a question about, you can let us know. 
 
**Improvements**  
-	A new governance action was added for Office 365 that enables you to remove all external users of a file. For instance, this enables you to implement policies that **remove external shares from files with internal only classification**.
-	Improved identification of external users in SharePoint online. When filtering for the “external users” group, app@sharepoint system account will not show up.



## Cloud App Security release 88
Released January 8, 2017
 
**New features**
- Connect your SIEM to Cloud App Security. You can now send alerts and activities automatically to your SIEM of choice by configuring SIEM Agents. Now available as a public preview.  For full documentation and details, take a look at Integrating with SIEM.
- Cloud Discovery now supports IPv6. We rolled out support for Palo Alto and Juniper, and more appliances will be rolled out in future releases.
 
**Improvements**
- There is a new risk factor in the Cloud App Catalog. You can now rate an app based on whether it Requires user authentication. Apps that enforce authentication and do not allow anonymous use will receive a healthier risk score.
- We are rolling out new activity descriptions to be more usable and consistent. Searching for activities will not be affected by this.
- We included improved user-device identification, enabling Cloud App Security to enrich a larger number of events with device information.
 
## Cloud App Security release 87
Released December 25, 2016

**New features**
-	We are in the process of rolling out [data anonymization](cloud-discovery-anonymizer.md) so that you can enjoy Cloud Discovery while protecting user privacy. The data anonymization is performed by encrypting username information.
-	We are in the process of rolling out the ability to export a blocking script from Cloud App Security to additional appliances. The script will allow you to easily reduce shadow IT by blocking traffic to unsanctioned apps. This option is now available for: 
    -	BlueCoat ProxySG
    -	Cisco ASA
    -	Fortinet
    -	Juniper SRX
    -	Palo Alto
    -	Websense
-	A new File governance action was added that enables you to force a file to Inherit permissions from parent, deleting any unique permissions that were set for the file or folder. This file governance action enables you to change your file or folder’s permissions to be inherited from the parent folder. 
-	A new user group was added called External. This is a default user group that is pre-configured by Cloud App Security to include all users who are not part of your internal domains. You can use this user group as a filter, for example you can find activities performed by external users.
-	The Cloud Discovery feature now supports Sophos Cyberoam appliances.
 
**Bug fixes**
-	SharePoint online and One Drive for Business files were displayed in the File policy report and in the Files page as Internal instead of Private. This was corrected.
 


## Cloud App Security release 86
Released December 13, 2016

**New features**
- All Cloud App Security standalone licenses provide you with the ability to enable Azure Information Protection scanning from the general settings (without the need to create a policy). 
 
**Improvements**
- You can now use “or” in the file filter for the file name and in the MIME type filter for files and policies. This enables scenarios such as entering the word “passport” OR “driver” when creating a policy with PII, and it will match any file that has “passport” or “driver” in the filename. 
- By default, when a DLP content inspection policy runs, the data in the resulting violations is masked. You can now unmask the last 4 characters of the violation. 

**Minor improvements**
- New Office 365 (Exchange) mailbox related events having to do with forwarding rules and adding and removing delegate mailbox permissions.
- New event that audits the granting of consent to new apps in Azure Active Directory. 




## Cloud App Security release 85
Released November 27, 2016

**New features**
- A distinction was made between sanctioned apps and connected apps. Sanctioning and unsanctioning is now a tag that can be applied to discovered apps and any app in the app catalog. Connected apps are apps that you connected using the API connector for deeper visibility and control. You can now tag apps as sanctioned or unsanctioned or connect them using the app connector, where available. 
 
- As part of this change, the Sanctioned apps page was replaced with a redesigned **Connected apps** page that externalizes status data about the connectors. 
 
- The log collectors are more easily accessible in their own line in the **Settings** menu under **Sources**. 
- When creating an activity policy filter, you can reduce false positives by choosing to ignore repeated activities when they are performed on the same target object by the same user, for example, multiple attempts to download the same file by the same person will not trigger an alert. 
- Improvements were made to the activity drawer. Now, when you click on an activity object in the activity drawer, you can drill down for more information.

**Improvements**
- Improvements were made to the anomaly detection engine, including the impossible travel alerts, for which IP information is now available in the alert description.
- Improvements were made to the complex filters to enable adding the same filter more than once for finetuning of filtered results. 
- File and folder activities in Dropbox were separated for better visibility. 
  
**Bug fixes**
- A bug in the system alerts mechanism that created false positives was fixed.

## Cloud App Security release 84
Released November 13, 2016

**New features**
-	Cloud App Security now supports for Microsoft Azure Information Protection including enhanced integration and auto-provisioning. You can filter your Files and set File policies using the Tag Secure Classification and then set the classification label you want to view. The labels also indicate whether the classification was set by someone in your organization or by people from another tenant (External). You can also set activity policies, based on the Azure Information Protection classification labels and enable automatic scan for classification labels in Office 365. For more information on how to take advantage of this great new feature, see [Integrating with Azure Information Protection](azip-integration.md).
 
**Improvements**
-	Improvements were made to the Cloud App Security activity log: 
   -	Office 365 events from the Security and Compliance Center are now integrated with Cloud App Security and are visible in the **Activity log**.
   -	All Cloud App Security activity is registered in the Cloud App Security activity log as administrative activity.
-	To help you investigate file-related alerts, in each alert that results from a file policy, you can now view the list of activities that were performed on the matched file.
-	The impossible travel algorithm in the anomaly detection engine was improved to provide better support for small tenants. 
 
**Minor improvements**
-	The **Activity export limit** was raised to 10,000. 
-	When creating a **Snapshot report** in the Cloud Discovery manual log upload process, you now receive an accurate estimate for how long the log processing will take. 
-	In a file policy, the **Remove collaborator** governance action now works on groups.
-	Minor improvements were made in the **App permissions** page. 
-	When more than 10,000 users have granted permissions to an app that connects to Office 365, the list loaded slowly. This has been fixed.
-	Additional attributes were added to the **App catalog** regarding the payment card industry.


## Cloud App Security release 83
Released October 30, 2016

**New features**
-	To simplify filtering in the [activity log](activity-filters.md) and [file log](file-filters.md), similar filters have been consolidated. Use the activity filters: Activity object, IP address and User. Use the file filter Collaborators to find exactly what you need.
-	From the activity log drawer, under **Source**, you can click the link for **View raw data** to download the raw data used to generate the activity log, for greater drill down into app events. 
-	Added support for additional login activities in Okta. [Private preview]
-	Added support for additional login activities in Salesforce. 

**Improvements**
-	Improved usability for Cloud Discovery snapshot reports and troubleshooting.
-	Improved visibility in the alerts list for alerts on multiple apps.
-	Improved usability when creating new Cloud Discovery continuous reports.
-	Improved usability in the Governance log.



## Cloud App Security release 82
Released October 9, 2016

**Improvements**

- The activities **Change email** and **Change password** are now independent from the generic **Manage users** activity in Salesforce.
- Added a clarification for the SMS daily alert limit. A maximum of 10 messages are sent per phone number, per day (UTC).
- A new certificate was added to the Cloud Discovery attributes for Privacy Shield which replaced Safe Harbor (relevant for US vendors only).
- Troubleshooting has been added to the API connector failure messages to make it easier to remediate problems.
- Improvement in the update frequency of Office 365 third-party app scan.
- Improvements in the Cloud Discovery dashboard.
- The Checkpoint Syslog parser was improved.
- Improvements in the Governance Log for banning and unbanning third-party apps.
 
**Bug fixes**
 
- Improved process for uploading a logo.
 
## Cloud App Security release 81
Released September 18, 2016

**Improvements**
- Cloud App Security is now a first-party app in Office 365! From now on, you can connect Office 365 to Cloud App Security in a single click.

- New look to the Governance log- it was now upgraded to the same clear a useful look as the Activity log and Files table. Use the new filters to easily find what you need and monitor your governance actions. 
- Improvements were made to the anomaly detection engine for multiple failed logins and additional risk factors.
- Improvements were made to the Cloud Discovery snapshot reports.
- Improvements were made to administrative activities in the activity log; Change password, Update user, Reset password now indicate whether the activity was performed as an administrative activity.
- The alert filters for system alerts were improved. 
- The label for a policy within an alert now links back to the policy report.
- If there is no owner specified for a Dropbox file, notification email messages are sent to the recipient you set. 
- Cloud App Security supports an additional 24 languages extending our support to a total of 41 languages.  


## Cloud App Security release 80
Released September 4, 2016 

**Improvements**
- When the DLP scan fails, you are now provided with an explanation of why Cloud App Security could not scan the file. For more information, see [Content Inspection](https://aka.ms/aka.ms/cas-contentinspection).
- Improvements were made to the anomaly detection engines, including improvements in the impossible travel alerts.
- Improvements were made to the dismiss alert experience, you can also add feedback so that you can let the Cloud App Security team know whether the alert was interesting and why so that your feedback can be used to improve the Cloud App Security detections.
- The Cisco ASA Cloud Discovery parsers were improved.
- You now receive an email notification when your Cloud Discovery log manual upload completes.
   



## Cloud App Security release 79
Released August 21, 2016 

**New features**

- **New Cloud Discovery Dashboard**  
A brand new Cloud Discovery dashboard is available, designed to give you more insight into how cloud apps are being used in your organization. It provides an at-a-glance overview of what kinds of apps are being used,  your open alerts and the risk levels of apps in your organization. It also lets you know who the top app users are in your organization and provides an App Headquarter location map.
The new Dashboard has more options for filtering the data, to allow you to generate specific views, depending on what you're most interested in, and easy-to-understand graphics to give you the full picture at a glance.

- **New Cloud Discovery reports** 
To view Cloud Discovery results, you can now generate two types of reports, Snapshot reports and Continuous reports.
Snapshot reports provide ad-hoc visibility on a set of traffic logs you manually upload from your firewalls and proxies. Continuous reports show the results of all logs that are forwarded from your network using Cloud App Security’s log collectors. These new reports provide improved visibility over all data, automatic identification of anomalous use as identified by the Cloud App Security machine learning anomaly detection engine and identification of anomalous use as defined by you using the robust and granular policy engine. For more information see [Set up Cloud Discovery](set-up-cloud-discovery.md).
 
**Improvements**
- General usability improvements in the following pages: Policy pages, General settings, Mail settings.
- In the Alerts table, it is now easier to distinguish between read and unread alerts. The read alerts have a blue line to the left and are grayed out to indicate that you already read them.
- The Activity policy **Repeated activity** parameters were updated. 
- In the Accounts page, a user **Type** column was added so you can now see what type of user account each user has. The user types are app-specific. 
- Near real-time support was added for file-related activities in OneDrive and SharePoint. When a file changes, Cloud App Security triggers a scan almost immediately.


## Cloud App Security release 78
Released August 7, 2016

**Improvements**
- From a specific file, you can now right-click and **Find related**. From the Activity log, you can use the Target object filter then select the specific file.

- Improved Cloud Discovery Log file parsers, including the addition of Juniper and Cisco ASA.
- Cloud App Security now enables you to provide feedback for the improvement of alerts, when you dismiss an alert. You can help improve the quality of the Cloud App Security alert feature by letting us know why you are dismissing the alert, for example, it's not interesting, you received too many similar alerts, the actual severity should be lower, the alert isn't accurate.
-In the File policy view, or when viewing a file, when you open the file drawer, the new link to Matched policies was added. When you click on it, you can view all the matches and you are now enabled to dismiss all. 
- The organizational unit a user belongs to is now added to all relevant alerts.
- An email notification is now sent to let you know when processing completes for your manually uploaded logs.


## Cloud App Security release 77
Released July 24, 2016

**Improvements:**
- The Cloud Discovery Export button icon was improved for usability.
- When investigating an activity, if the user agent was not parsed, you can now see the raw data.
- Two new risk factors were added to the Anomaly Detection engine: 
    - Cloud App Security now uses the IP address tags that are associated with a botnet and anonymous IP addresses as part of the calculation of Risk. 
    - Office 365 activity is now monitored for high-download rates. If the Office 365 download rate is much higher than your organization's, or a specific user's, normal download rate, an Anomaly Detection alert will be triggered. 
- Cloud App Security is now compatible with the new Dropbox [Secure Sharing functionality](https://blogs.dropbox.com/dropbox/2016/06/new-dropbox-productivity-tools/) API. 
- Improvements were made to add details to the Discovery log parsing errors, including: No cloud related transactions, All events are outdated, Corrupted file, Log format does not match.
- The Activity log date filter was improved; it now includes the ability to filter by time.
- The IP address ranges page was improved for usability.
- Cloud App Security now includes support for Microsoft Azure Information Protection (Preview version). You can filter your Files and set File policies using the Tag Secure Classification and then set the level of the classification label you want to view. The labels will also indicate whether the classification was set by someone in your organization or by people from another tenant (External). 



## Cloud App Security release 76
Released: July 10, 2016

**Improvements:**

- Lists of users in built-in Reports can now be exported.
- Improved usability for aggregated activity policy.
- Improved support for the TMG W3C firewall log message parser.
- Improved usability for the file governance action drop down, which is now separated into collaboration, security and investigation actions.
- Improved Impossible Travel detection for Exchange Online activity of: Send mail.
- A new list of titles (breadcrumbs) was added to the top of the Alerts and Policy pages to make navigation easier.

**Bug fixes:**
- The preset expression for Credit Card in the DLP setting for File Policies was changed to All: Finance: Credit Card.


## Cloud App Security release 75
Released: June 27, 2016


**New features:**
* New additions were added to our growing list of supported Salesforce events, including events providing insights into reports, shared links, content distribution, impersonated login and more.
* The connected app icons on the Cloud App Security dashboard were aligned with the status of the apps as displayed on the dashboard to reflect the last 30 days.
* Support for full-width screens.


**Bug fixes:**
* SMS alert phone numbers are now validated upon insertion.

## Cloud App Security release 74
Released: June 13, 2016
* The Alert screen was updated to provide you with more information at a glance, including the ability to see all user activities at a glance, a map of activities, related user governance logs, a description of the reason the alert is triggered and additional graphs and maps from the user page. 
* Events generated by Cloud App Security now include the event type, format, policy groups, related objects and a description.
* New IP address tags were added for Office 365 ProPlus, OneNote, Office Online and Exchange Online Protection.
* You now have the option to upload logs from the main discovery menu.
* The IP address category filter was improved. The IP address category null is now called uncategorized and a new category called No value was added to include all activities that have no IP address data.
* Security groups in Cloud App Security are now called user groups to avoid confusion with Active Directory security groups.
* It is now possible to filter per IP address, and filter out events without an IP address. 
* Changes were made to the settings for notification emails sent when matches are detected in Activity Policies and File Policies. You can now add email addresses for recipients you want to CC with the notification.


## Cloud App Security release 73
Released: May 29, 2016

* Updated alert capabilities:
You can now set alerts per policy to be sent via email or sent as a text message.
* Alerts page:
Improved design to better enable advanced resolution options and incident management.
* Adjust policy: Alerts now enable you to move from alert resolution options directly to the policy settings page to enable easier fine-tuning based on alerts.
* Improvements to anomaly detection risk score calculation and reduced false-positive rate based on customer feedback.
* Activity log export now includes Event ID, Event Category and Event Type Name.
* Improved appearance and usability of policy creation Governance Actions.
* Simplified investigation and control for Office 365 - Selection of Office 365 automatically selects all apps that are part of the Office 365 Suite.
* Notifications are now sent to the email address as configured in the connected app. 
* Upon connection error a detailed description of the error is now provided by the cloud app.
* When a file matches a policy, a URL to access the file is now provided in the file drawer.
* When an alert is triggered by an activity policy or an anomaly detection policy, a new detailed notification is sent that provides information about the match. 
* An automated system alert is triggered when an app connector is disconnected.
* You can now dismiss and resolve a single alert or a bulk selection of alerts from within the alerts page.

## Cloud App Security release 72
Released: May 15, 2016

*  General appearance and infrastructure improvements, including:
    * New diagram to provide more assistance with the Cloud Discovery manual log upload process.
    * Improved process for updating unrecognized ("Other") log files, including a pop-up that let's you know that the file requires additional review and you will be notified when the data is available.
    * More activity and file violations are highlighted when investigating an activity and file log for outdated browsers and operating systems.
* Improved Cloud Discovery Log file parsers, including the addition of Cisco ASA, Cisco FWSM, Cisco Meraki, and W3C.
* Cloud Discovery known issue improvements.
* New activity filters added for owner's domain and internal/external affiliation.
* A new filter was added that enables you to search for any Office 365 object (files, folders, URLs).
* The ability was added to configure a minimal risk score for Anomaly detection policies.
* When you set an alert to be sent when a policy is violated, you can now set a minimum severity level for which you want to be alerted. You can choose to use your organization's default setting for this and you can set a specific alert setting as the default for your organization.

## See Also  
[For technical support, please visit the Cloud App Security assisted support page.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  