---
# required metadata

title: Release notes | Microsoft Docs
description: This topic is updated frequently to let you know what's new in the latest release of Cloud App Security.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 12/28/2016
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
-	SPO and OD4B files were displayed in the File policy report and in the Files page as Internal instead of Private. This was corrected.
 


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
  
  