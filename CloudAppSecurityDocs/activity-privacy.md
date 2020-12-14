---
title: Activity privacy
description: This article provides information about how to configure your activity monitoring to comply with your user privacy policy.
ms.date: 05/27/2020
ms.topic: how-to
---
# Activity privacy

[!INCLUDE [Banner for top of topics](includes/banner.md)]

Microsoft Cloud App Security provides enterprises with the ability to granularly determine which users they want to monitor based on group membership. Activity privacy adds the ability to follow your organization's compliance regulations without compromising user privacy. This is achieved by enabling you to monitor users whilst maintaining their privacy by hiding their activities in the activity log. Only authorized admins have the option to choose to view these private activities, with each instance being audited in the governance log.

## Configure activity privacy user groups

You may have users in Cloud App Security that you want to monitor but, due to compliance regulations, you need to limit the people who can do so. Activity privacy allows you to define a user group for which the activities will be hidden by default.

To configure your user privacy groups, you must first [import user groups](user-groups.md) to Cloud App Security. By default, you'll see the following groups:

- **Application** user group -  A built-in group that enables you to see activities performed by Office 365 and Azure AD applications.

- **External users** group - All users who aren't members of any of the managed domains you configured for your organization.

1. In the menu bar, click the settings cog and select **Scoped deployment and privacy**.

    ![settings icon](media/settings-icon.png)

1. To set specific groups to be monitored by Cloud App Security, in the **Activity privacy** tab, click the plus icon.
    ![icon](media/plus-icon.png)

1. In the **Add user groups** dialog, under **Select user groups**, select all the groups you want to make private in Cloud App Security, and then click **Add**.

    ![Screenshot showing the add user groups dialog box](media/activity-privacy-add-user-groups.png)

    > [!NOTE]
    > Once a user group is added, all the activities performed by users of the group will be made private from then on. Existing activities are not affected.

## Assign admins permission to view private activities

1. In the menu bar, click the settings cog and select **Manage admin access**.

    ![settings icon](media/settings-icon.png)

1. To give specific admins permission to view private activities, in the **Activity privacy permissions** tab, click the plus icon.
    ![icon](media/plus-icon.png)

1. In the **Add admin permission** dialog, enter the admin's UPN or email address, and then click **Add permission**.

    ![Screenshot showing the add admin permission dialog box](media/activity-privacy-add-admin-permission.png)

    > [!NOTE]
    > Only admins can be assigned permission to view private activities.

## Viewing private activities

Once an admin has been granted the appropriate permission to view private activities, they have the option to choose to see these activities in the activity log.

### To view private activities

1. In the **Activity log** page, to the right of the activity table, click the settings icon, and then select **Show private activities**.

    ![Screenshot showing the activity log settings icon](media/activity-privacy-view-settings-icon.png)

1. In the **Show private activities** dialog, click **OK** to confirm that you understand that the action is being audited. Once confirmed, the private activities are shown in the activity log and the action is recorded in the governance log.

[!INCLUDE [Open support ticket](includes/support.md)]
