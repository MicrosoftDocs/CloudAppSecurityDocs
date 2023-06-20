---
title: Set admin preferences 
description: This article provides instructions for setting admin preferences in Defender for Cloud Apps.
ms.date: 11/09/2021
ms.topic: how-to
---
# Admin user settings 

[!INCLUDE [Banner for top of topics](includes/banner.md)]

Microsoft Defender for Cloud Apps allows you to customize your admin user settings. The notification settings allow admins to specify if they would like to receive email or text notifications for alerts.

## Customize your admin settings

To set up your preferences as an admin of Microsoft Defender for Cloud Apps, click your name in the portal menu bar, and select **User settings** to set the following settings:

1. Click **Language**. Here you can choose the language to use in the Defender for Cloud Apps portal.

    ![custom user settings.](media/custom-language-settings.png)

2. Click **Notifications** and set email and text notification preferences for emails you receive from the system. You can set the severity that determines which alerts and violations you want to receive emails. The severity is set per policy. When violations are triggered, you receive email notification depending on the setting here and the Severity setting in the policy that was violated. Emails are sent to the alias associated with the administrator user account you used to sign in to Defender for Cloud Apps. Enter a phone number to enable Defender for Cloud Apps to send you text messages when alerts and notifications are sent, and set the severity level for which you want to receive notifications via text message.

    > [!NOTE]
    >
    > - The maximum number of alerts that are sent via text message is 10 per phone number per day. The day is calculated according to the UTC timezone.
    > - Notifications are not sent for Azure Active Directory IPC events.

    ![notification settings.](media/notification-settings.png)

3. When you're done, click **Save**.

## Next steps

> [!div class="nextstepaction"]
> [Set up Cloud Discovery](set-up-cloud-discovery.md)

[!INCLUDE [Open support ticket](includes/support.md)]
