---
title: Classic portal -  Import user groups from connected apps
description: Classic portal -  This article provides instructions for importing your user groups from connected apps into Defender for Cloud Apps.
ms.date: 01/19/2023
ms.topic: how-to
ROBOTS: NOINDEX
---
# Classic portal: Import user groups from connected apps

[!INCLUDE [Banner for top of topics](includes/banner.md)]

When you connect apps using API connectors, Microsoft Defender for Cloud Apps enables you to import user groups, for example from Microsoft 365 and Azure Active Directory. There are two types of user groups:

- **Automatic groups:** Automatic groups are created by default by Microsoft Defender for Cloud Apps. For example, there's an automatic user group called **External** that combines all users from all apps who are external to your organization and have access to files or were in user activities in your tenant. The following automatic groups exist in Defender for Cloud Apps:

  - External
  - Dropbox administrator
  - Microsoft 365 administrator
  - Google Workspace administrator
  - Box administrator
  - All Salesforce standard and custom profiles, for example, Salesforce System Administrator. See the full list [here](https://help.salesforce.com/s/articleView?id=sf.standard_profiles.htm).

- **Imported groups:** You can import any group from your connected apps. For example, you can import user groups from Microsoft 365 (Active Directory) and other connected apps. These groups enable you to look for threats in your org, not by looking at the whole org or at a specific user, but by looking at a specific group.

  Typical scenarios that use imported user groups include:

  - Investigating which docs the HR people look at.
  - Check if there's something unusual happening in the executive group.
  - Find if someone from the admin group performed an activity outside the US.

## How to import user groups

1. In the menu bar, select the settings icon ![settings icon.](media/classic-settings-icon.png "settings icon") and select **User groups**.
1. Select **Import user group**.

    ![Import user groups.](media/classic-user-groups-add.png)

1. Select the app from which to import the user group. The list of apps will depend on which App Connectors you deployed.
1. Select the group to import. The list of available groups will be a list of all the existing user groups in the app itself. If you want to add a new group, you have to do it directly in the app itself. Then, when the group appears in the list here, select it.
1. You can select the option to be notified by email when the import process is complete.
1. Select **Import**. After you import a group, Defender for Cloud Apps automatically syncs the group members, just like Active Directory Connect.
1. After the import is complete, from the **User groups** page you can select a specific group to view a list of all the members of the group. Select any member of the group to further drill down into the details of a specific account. You can view which apps they use and a summary of the account including graphs of the user and their activity.

Importing groups enables you to select those groups as filters when investigating in the **Activity log** and when creating policies.

> [!NOTE]
>
> - The maximum number of imported user groups is 500.
> - Only active users will be imported as part of the imported group. Any suspended, deleted, or disabled users will be ignored.
> - There may be a short delay until imported user groups are available in filters.
> - Only activities performed after importing a user group will be tagged as having been performed by a member of the user group.
> - After the initial sync, groups are usually updated every hour. However, due to various factors there could be times where this might take several hours.

For more information on using the User group filters, see [Activities](activity-filters.md).

## Next steps

> [!div class="nextstepaction"]
> [Set up Cloud Discovery](set-up-cloud-discovery.md)

[!INCLUDE [Open support ticket](includes/support.md)]
