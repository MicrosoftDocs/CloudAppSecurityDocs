---
title: Monthly operational guide - Microsoft Defender for Cloud Apps
description: This article provides monthly operational recommendations to help security operations teams to plan and run security activities.
ms.date: 11/28/2023
ms.topic: reference
---

# Monthly operational guide - Microsoft Defender for Cloud Apps

This article lists monthly operational activities that we recommend you perform with Defender for Cloud Apps.

Monthly activities can be performed more frequently or as needed, depending on your environment 
and needs.

## Review Microsoft service health

If you are experiencing problems with a cloud service, please check the service 
health to determine whether this is a known issue with a resolution in progress before you call 
support or spend time troubleshooting.
**Where**: M365 admin center > Health > Service health
Microsoft 365 Service health status (office365.com)
Twitter: @MSFT365status

## Run advanced hunting queries

Similar to reviewing activity logs, Advanced Hunting can be used as a scheduled 
activity, ability to create custom detections or ad-hoc to proactively hunt for threats. Advanced 
Hunting is a unified tool that allows you to hunt for threats across M365D. It’s a good practice to save 
frequently used queries for faster manual threat hunting and remediation. Heare are a couple of 
examples of AH queries for MDA: 
**Persona**: SOC analysts 
**Where**: In the Microsoft Defender XDR Portal, select Hunting > Advanced hunting
Office - FileDownloaded Events
CloudAppEvents
| where ActionType == "FileDownloaded"
| extend FileName = RawEventData.SourceFileName, Site = RawEventData.SiteUrl, 
FileLabel = RawEventData.SensitivityLabelId, SiteLabel = 
RawEventData.SiteSensitivityLabelId
| project 
Timestamp,AccountObjectId,ActionType,Application,FileName,Site,FileLabel,SiteL
abel
Office - MailItemsAccessed Details
CloudAppEvents
| where ActionType == "MailItemsAccessed" //Defines the action type we want to 
filter on
16
| extend Folders = RawEventData.Folders[0] //Set variable and then use the 
index to trim the [] to data can be accessed
| extend MailboxPath = Folders.Path //set a variable for the path
| mv-expand Folders.FolderItems //expand the list of items because some 
entries might contain multiple items which were accessed
| extend MessageIDs = tostring(Folders_FolderItems.InternetMessageId) //extend 
and then convert to string so table can be joined
| join EmailEvents on $left.MessageIDs == $right.InternetMessageId //join the 
email events table to access subject and mailbox information
| project 
Timestamp,AccountType,AccountDisplayName,AccountObjectId,UserAgent,IPAddress,C
ountryCode,City,ISP,NetworkMessageId,MailboxPath,Subject,SenderFromAddress,Rec
ipientEmailAddress
| sort by Timestamp desc
Extract activity objects
CloudAppEvents
| take 100
| mv-expand(ActivityObjects)
| evaluate bag_unpack(ActivityObjects)
AAD - Add to Role
CloudAppEvents
| where ActionType in ("Add member to role.") 
| extend FirstElement = ActivityObjects[0], SecondElement = 
ActivityObjects[1], ThirdElement = ActivityObjects[2]
| extend Type = FirstElement.ServiceObjectType, 
RoleName = FirstElement.Name, 
UserAddedName = SecondElement.Name, 
UserAddedId = SecondElement.Id
| project 
Timestamp,Type,ActionType,RoleName,UserAddedName,UserAddedId,AccountId,Account
DisplayName
AAD - Group Adds
CloudAppEvents
| where ActionType in ("Add member to group.") and AccountType == "Regular"
| extend SecondElement = RawEventData.ModifiedProperties[1]
| extend UserAddedId = RawEventData.ObjectId, GroupName = 
SecondElement.NewValue
| project Timestamp, ActionType,UserAddedId,PerformedBy = 
AccountDisplayName,GroupName

## Review file quarantines

Microsoft Defender for Cloud Apps can be used to detect unwanted files stored in 
your cloud that leave you vulnerable, and take immediate action to stop them in their tracks and lock 
down the files that pose a threat by using Admin quarantine to protect your files in the cloud, 
remediate problems, and prevent future leaks from occurring. Files in Admin quarantine can be 
reviewed as part of alert investigation. For governance and compliance reasons you may be required 
to manage quarantined files.
**Where**: In the Microsoft Defender XDR Portal, select Cloud apps > Files
Query: Quarantined is True
**Persona**: Compliance administrator
More information: Understand how quarantine works

## Review app risk scores

The Cloud app catalog rates risk for your cloud apps based on regulatory 
certification, industry standards, and best practices. It’s recommended to review the score for each 
of the application in your environment to make sure it’s aligned with your company regulations. You 
may submit a request to change an app risk score. You can also customize the risk score in Cloud 
Discovery > Score metrics. 
**Persona**: Compliance administrator
**Where**: In the Microsoft Defender XDR Portal, select Cloud apps > Cloud app catalog
More information: Working with the risk score

## Delete cloud discovery data

There are a number of reasons why you may want to delete your Cloud Discovery 
data. We recommend deleting it in the following cases:
• If you manually uploaded log files and a long time passed before you updated the system 
with new log files and you don't want old data affecting your results.
• When you set a new custom data view, it will apply only to new data from that point 
forward. So, you may want to erase old data and then upload your log files again to enable 
the custom data view to pick up events in the log file data.
• If many users or IP addresses recently started working again after being offline for some 
time, their activity will be identified as anomalous and may give you false positive violations.
18
**Persona**: Compliance administrator
**Where**: In the Microsoft Defender XDR Portal, select Settings > Cloud apps > Cloud Discovery > Delete Data 
More information: Deleting Cloud Discovery data


## Generate a cloud discovery executive report

The best way to get an overview of Shadow IT use across your organization is by 
generating a Cloud Discovery executive report. This report identifies the top potential risks and helps 
you plan a workflow to mitigate and manage risks until they're resolved.
**Where**: In the Microsoft Defender XDR Portal, select Cloud apps > Cloud discovery > Dashboard > Actions
**Persona**: Compliance administrator
More information: Generate Cloud Discovery executive report

## Generate a cloud discovery snapshot report

If you don't have a log yet and you want to see an example of what your log should 
look like, download a sample log file.
**Where**: In the Microsoft Defender XDR Portal, select Cloud apps > Cloud discovery > Dashboard > Actions
**Persona**: Security and Compliance administrators
More information: Create snapshot Cloud Discovery report

## Related content

[Microsoft Defender for Cloud Apps operational guide](mda-ops-guide.md)

