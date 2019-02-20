---
# required metadata

title: Working with Cloud App Security activity filters and queries
description: This article provides a list of Cloud App Security activity filters and queries and explains how to work with them.
keywords:
author: rkarlin
ms.author: rkarlin
manager: barbkess
ms.date: 12/10/2018
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: 9ba5c7d3-c733-4048-9b99-bf41a0f46695


# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: seodec18

---
# Activity filters and queries

*Applies to: Microsoft Cloud App Security*

This article provides descriptions and instructions for Cloud App Security activity filters and queries.

## Activity filters

Below is a list of the activity filters that can be applied. Most filters support multiple values as well as NOT to provide you with a powerful tool for policy creation.  
  
- Activity ID - Search only for specific activities by their ID. This filter is useful when you connect Microsoft Cloud App Security to your SIEM (using the SIEM agent), and you want to further investigate alerts within the Cloud App Security portal.  
  
- Activity objects – Search for the objects the activity was done on. This filter applies to file, folder, user, or app objects. 
  - Activity object ID - the ID of the object (file, folder, user, or app ID).
  <!-- - File, folder or site URL - Enables you to select files, folders and URLs that start with a specific string.-->
  <!-- - Target object (file/folder) - Enables you to select a specific file or folder. -->
  - Item - Enables you to search by the name or ID of any activity object (for example: user names, files, parameters, sites). For the **Activity object Item** filter, you can select whether you want to filter for items that **Contain**, **Equal**, or **Starts with** the specific item.
    
- Activity type - Search for the app activity.

- Administrative activity – Search only for administrative activities.  
  
- Alert ID - Search by alert ID.

- App – Search only for activities within specific apps.  
  
- Applied action - Search by governance action applied: Blocked, Bypass proxy, Decrypted, Encrypted, Encryption failed, No action.

- Date – The date when the activity occurred. Filter supports before/after dates and a date range.  
  
<!--- Description – Specific keyword in the activity description, for example, all activities that include the string **user** in their description.  -->
  
- Device tag - Search by compliant, managed or verified device.

- Device type - Search only for activities that were done using a specific device type. For example, search all activities from mobile devices, PCs, or Tablets.  

- Files and folders - Search for files and folders the activity was performed on.
    - File ID - Enables you to search by the File ID the activity was performed on. 
    - Name - Filters on the name of files or folders. You can select if the name  **ends with**, **equals**, or **starts with** your search value.
    - Specific files or folders - Allows you to include or exclude specific files or folders. When selecting files or folders, you can filter the list by **App**, **Owner**, or partial **File Name**. 
  
- IP address – The raw IP address, category, or tag from which the activity was performed.  
  - Raw IP address - Enables you to search for activities that were performed on or by raw IP addresses. The raw IPs can equal, don't equal, start with, or don't start with a particular sequence. 
  - IP category - The category of the IP address from which the activity was performed, for example, all activities from administrative IP address range. The categories need to be configured to include the relevant IP addresses, except for the "Risky" category, which is pre-configured and includes two IP tags - Anonymous proxy and Tor. To learn how to configure the IP categories, see [Organize the data according to your needs](ip-tags.md).  
  - IP tag - The tag of the IP address from which the activity was performed, for example, all activities from anonymous proxy IP addresses. Cloud App Security creates a set of built-in IP tags that aren't configurable. Additionally, you can configure your own IP tags. For more information about configuring your own IP tags, see [Organize the data according to your needs](ip-tags.md).
  The built-in IP tags include:
  - Microsoft apps (14 of them)
  - Anonymous proxy
  - Botnet (you'll see that the activity was performed by a botnet with a link to learn more about the specific botnet)
  - Darknet scanning IP
  - Malware C&C server
  - Remote Connectivity Analyzer
  - Satellite providers
  - Smart proxy and access proxy (left out on purpose)
  - Tor exit nodes
  - Zscaler


- Impersonated activity – Search only for activities that were performed in the name of another user.  

- Instance - The app instance where the activity was or wasn't performed.

- Location – The country from which the activity was performed.  

- Matched policy – Search for activities that matched on a specific policy that was set in the portal.  

- Registered ISP – The ISP from which the activity was performed.

- Source - Search by the source from which the activity was detected. Source can be any of the following:
  -	App connector - logs coming directly from the app’s API connector.
  -	App connector analysis - Cloud App Security enrichments based on information scan by the API connector.
  

- User – The user who performed the activity, which can be filtered into domain, group, name, or organization. In order to filter activities with no specific user, you can use the ‘is not set’ operator.  
  - User domain - Search for a specific user domain.
  - User organization – The organizational unit of the user who performed the activity, for example, all activities performed by EMEA_marketing users.  
  - User group – Specific user groups that you can import from connected apps, for example, Office 365 administrators.  
  - User name - Search for a specific username. To see a list of users in a specific user group, in the **Activity drawer**, click on the name of the user group. Clicking will take you to the Accounts page that lists all the users in the group. From there, you can drill down into the details of the accounts of specific users in the group.
    -  The **User group** and **User name** filters can be further filtered by using the **As** filter, and selecting the role of the user, which can be any of the following:
        - Activity object only - meaning that the user or user group selected didn't perform the activity in question, they were the object of the activity.
        - Actor only - meaning that the user or user group performed the activity.
        - Any role - Meaning that the user or user group were involved in the activity, either as the person who performed the activity or as the object of the activity.

- User agent – The user agent of from with the activity was performed.  
  
- User agent tag – Built-in user agent tag, for example, all activities from an outdated browser or outdated operating systems.  

<!--
>[!NOTE]
> If at any point you want to clear the filters, you can do so by clicking the clear filters icon ![clear filters icon](./media/clear-filters.png). -->


## Activity queries

To make investigation even simpler, you can now create custom queries and save them for later use. 

1. In the **Activity log** page, use the filters as described above to drill down into your apps as necessary. 

2. After you've finished building your query, click the **Save as** button in the top right corner of the filters. 

3. In the **Save query** popup, name your query.

   ![new query](./media/new-activity-query.png)

4. To use this query again in the future, under **Queries**, scroll down to **Saved queries** and select your query. 

   ![open query](./media/select-activity-query.png)


Cloud App Security also provides you with **Suggested queries**. Suggested queries provide you with recommended avenues of investigation that filter your activities. You can edit these queries and save the as custom queries. The following are optional suggested queries:

 - Admin activities - filters all your activities to display only those activities that involved admins.

 - Download activities - filters all your activities to display only those activities that were download activities, including download user list as a .csv vile, downloading of shared content and downloading a folder.

 - Failed log in - filters all your activities to display only failed log ons and failed sign in via SSO 

 - File and folder activities - filters all your activities to display only those activities that involved files and folders. The filter includes upload, download, and accessing folders, along with creating, deleting, uploading, downloading, quarantining, and accessing files, and transferring content. 

 - Impersonation activities - filters all your activities to display only impersonation activities.

 - Mailbox activities - filters all your activities to display only Microsoft Exchange Online activities such as create item, purge messages from mailbox, update message and send message using Send As permissions (impersonation).

 - Password changes and reset requests - filters all your activities to display only those activities that involving password reset, change password, and force user to change password on next sign-in.

 - Security risks - filters all your activities to display only those activities that match DLP policies.

 - Sharing activities - filters all your activities to display only those activities that involve sharing folders and files, including creating a company link, creating an anonymous link and granting read/write permissions.

 - Successful log in - filters all your activities to display only those activities that involve successful log ins, including impersonate action, impersonate log on, single sign-on log-on, and log on from new device.

![query activities](./media/queries-activity.png)
 
Additionally, you can use the suggested queries as a starting point for a new query. First, select one of the suggested queries. Then, make changes as needed and finally click **Save as** to create a new **Saved query**.


## Next steps 
[Daily activities to protect your cloud environment](daily-activities-to-protect-your-cloud-environment.md)   

  
  
