---
title: Working with Defender for Cloud Apps activity filters and queries
description: This article provides a list of Defender for Cloud Apps activity filters and queries and explains how to work with them.
ms.date: 11/09/2021
ms.topic: how-to
---
# Activity filters and queries

[!INCLUDE [Banner for top of topics](includes/banner.md)]

This article provides descriptions and instructions for Defender for Cloud Apps activity filters and queries.

## Activity filters

Below is a list of the activity filters that can be applied. Most filters support multiple values as well as NOT to provide you with a powerful tool for policy creation.

- Activity ID - Search only for specific activities by their ID. This filter is useful when you connect Microsoft Defender for Cloud Apps to your SIEM (using the SIEM agent) and you want to further investigate alerts within the Defender for Cloud Apps portal.

- Activity objects – Search for the objects the activity was done on. This filter applies to files, folders, users, or app objects.
  - Activity object ID - the ID of the object (file, folder, user, or app ID).
  <!-- - File, folder, or site URL - This enables you to select files, folders, and URLs that start with a specific string.-->
  <!-- - Target object (file/folder) - Enables you to select a specific file or folder. -->
  - Item - Enables you to search by the name or ID of any activity object (for example, user names, files, parameters, sites). For the **Activity object Item** filter, you can select whether to filter for items that **Contain**, **Equal**, or **Starts with** the specific item.

- Activity type - Search for the app activity.

- Activity type - Search for a more specific action in an app.

- Administrative activity – Search only for administrative activities.

  >[!NOTE]
  >Defender for Cloud Apps can't mark Google Cloud Platform (GCP) administrative activities as administrative activities.

- Alert ID - Search by alert ID.

- App – Search only for activities within specific apps.

- Applied action - Search by governance action applied: Blocked, Bypass proxy, Decrypted, Encrypted, Encryption failed, No action.

- Date – The date when the activity occurred. Filter supports before/after dates and a date range.

<!--- Description – Specific keyword in the activity description, for example, all activities with the string **user** in their description.  -->

- Device tag - Search by **Intune compliant**, **Hybrid Azure AD joined** or **Valid client certificate**.

- Device type - Search only for activities that were done using a specific device type. For example, search all activities from mobile devices, PCs, or Tablets.

- Files and folders - Search for files and folders the activity was performed on.
  - File ID - Enables you to search by the File ID the activity was performed on.
  - Name - Filters on the name of files or folders. You can select if the name  **ends with**, **equals**, or **starts with** your search value.
  - Specific files or folders - You can include or exclude specific files or folders. You can filter the list by **App**, **Owner**, or partial **File Name**when selecting files or folders.

- IP address – The raw IP address, category, or tag from which the activity was performed.
  - Raw IP address - Enables you to search for activities that were performed on or by raw IP addresses. The raw IPs can equal, don't equal, start with, or don't start with a particular sequence.
  - IP category - The category of the IP address from which the activity was performed, for example, all activities from the administrative IP address range. The categories need to be configured to include the relevant IP addresses, except for the "Risky" type, which is pre-configured and includes two IP tags - Anonymous proxy and Tor. To learn how to configure the IP categories, see [Organize the data according to your needs](ip-tags.md).
  - IP tag - The tag of the IP address from which the activity was performed, for example, all activities from anonymous proxy IP addresses. Defender for Cloud Apps creates a set of built-in IP tags that aren't configurable. Additionally, you can configure your IP tags. For more information about configuring your IP tags, see [Organize the data according to your needs](ip-tags.md).
  The built-in IP tags include the following:
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

- Location – The country/region from which the activity was performed.

- Matched Policy – Search for activities that matched a specific policy that was set in the portal.

- Registered ISP – The ISP from which the activity was performed.

- Source - Search by the source from which the activity was detected. The source can be any of the following:
  - App connector - logs coming directly from the app's API connector.
  - App connector analysis - Defender for Cloud Apps enrichments based on information scanned by the API connector.

- User – The user who performed the activity, which can be filtered into domain, group, name, or organization. In order to filter activities with no specific user, you can use the 'is not set' operator.
  - User domain - Search for a specific user domain.
  - User organization – The organizational unit of the user who performed the activity, for example, all activities performed by EMEA_marketing users. This is only relevant for connected Google Workspace instances using organizational units.
  - User group – Specific user groups that you can import from connected apps, for example, Office 365 administrators.
  - User name - Search for a specific username. To see a list of users in a specific user group, in the **Activity drawer**, select the name of the user group. Clicking will take you to the Accounts page, which lists all the users in the group. From there, you can drill down into the details of the accounts of specific users in the group.
  - The **User group** and **User name** filters can be further filtered by using the **As** filter and selecting the role of the user, which can be any of the following:
    - Activity object only - meaning that the user or user group selected didn't perform the activity in question; they were the object of the activity.
    - Actor only - meaning that the user or user group performed the activity.
    - Any role - Meaning that the user or user group was involved in the activity, either as the person who performed the activity or as the object of the activity.

- User-agent – The user agent of from with the activity was performed.

- User-agent tag – Built-in user agent tag, for example, all activities from outdated operating systems or outdated browsers.

>[!NOTE]
>Defender for Cloud Apps considers *outdated* as two major versions older than the current version. For example, if the current version of Edge is 90, then version 88 and earlier are outdated.

<!--
>[!NOTE]
> If at any point you want to clear the filters, you can do so by clicking the clear filters icon ![clear filters icon.](media/clear-filters.png). -->

## Activity queries

To make investigation even simpler, you can now create custom queries and save them for later use.

1. In the **Activity log** page, use the filters as described above to drill down into your apps as necessary.

2. After you've finished building your query, select the **Save as** button in the top-right corner of the filters.

3. In the **Save query** pop-up, name your query.

   ![new query.](media/new-activity-query.png)

4. To use this query again in the future, under **Queries**, scroll down to **Saved queries** and select your query.

   ![open query.](media/select-activity-query.png)

Defender for Cloud Apps also provides you with **Suggested queries**. Suggested queries provide you with recommended avenues of investigation that filter your activities. You can edit these queries and save them as custom queries. The following are optional suggested queries:

- Admin activities - filters all your activities to display only those activities that involve admins.

- Download activities - filters all your activities to display only those activities that were download activities, including downloading user list as a .csv file, downloading shared content, and downloading a folder.

- Failed log-in - filters all your activities to display only failed log-ins and failed sign-ins via SSO

- File and folder activities - filters all your activities to display only those involving files and folders. The filter includes uploading, download, and accessing folders, along with creating, deleting, uploading, downloading, quarantining, and accessing files and transferring content.

- Impersonation activities - filters all your activities to display only impersonation activities.

- Mailbox activities - filters all your activities to display only Microsoft Exchange Online activities such as creating items, purging mailbox messages, updating messages, and sending messages using Send As permissions (impersonation).

- Password changes and reset requests - filters all your activities to display only those activities that involve password reset, change password, and force a user to change the password on the next sign-in.

- Security risks - filters all your activities to display only those activities that match DLP policies.

- Sharing activities - filters all your activities to display only those activities that involve sharing folders and files, including creating a company link, creating an anonymous link, and granting read/write permissions.

- Successful log-in - filters all your activities to display only those activities that involve successful log-ins, including impersonate action, impersonate log-on, single sign-on logon, and log-on from a new device.

![query activities.](media/queries-activity.png)

Additionally, you can use the suggested queries as a starting point for a new query. First, select one of the suggested queries. Then, make changes as needed and finally select **Save as** to create a new **Saved query**.

## Next steps

> [!div class="nextstepaction"]
> [Daily activities to protect your cloud environment](daily-activities-to-protect-your-cloud-environment.md)
