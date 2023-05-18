---
title: Connect Dropbox
description: This article provides information about how to connect your Dropbox app to Defender for Cloud Apps using the API connector  for visibility and control over use.
ms.date: 01/29/2023
ms.topic: how-to
---
# Connect Dropbox to Microsoft Defender for Cloud Apps

[!INCLUDE [Banner for top of topics](includes/banner.md)]

This article provides instructions for connecting Microsoft Defender for Cloud Apps to your existing Dropbox account using the connector APIs. This connection gives you visibility into and control over Dropbox use. For information about how Defender for Cloud Apps protects Dropbox, see [Protect Dropbox](protect-dropbox.md).

Because Dropbox enables access to files from shared links without signing in, Defender for Cloud Apps registers these users as Unauthenticated users. If you see unauthenticated Dropbox users, it may indicate users who aren't from your organization, or they might be recognized users from within your organization who didn't sign in.

## How to connect Dropbox to Defender for Cloud Apps

1. In the Microsoft 365 Defender portal, select **Settings**. Then choose **Cloud Apps**. Under **Connected apps**, select **App Connectors**.

1. In the **App connectors** page, select **+Connect an app**, followed by **Dropbox**.

    ![connect dropbox.](media/connect-dropbox.png "connect dropbox")

1. In the next window, give the connector a name and select **Next**.

1. In the **Enter details** window, enter the admin account email address.

1. In the **Follow the link** window, select **Connect Dropbox**.

    The Dropbox sign in page opens. Enter your credentials to allow Defender for Cloud Apps access to your team's Dropbox instance.

1. Dropbox asks you if you want to allow Defender for Cloud Apps access to your team information, activity log, and perform activities as a team member. To proceed, select **Allow**.

1. Back in the Defender for Cloud Apps console, you should receive a message that Dropbox was successfully connected.

1. In the Microsoft 365 Defender portal, select **Settings**. Then choose **Cloud Apps**. Under **Connected apps**, select **App Connectors**. Make sure the status of the connected App Connector is **Connected**.

> [!NOTE]
> Any Dropbox events for adding a file are displayed in Defender for Cloud Apps as Upload file to align to all other apps connected to Defender for Cloud Apps.

If you have any problems connecting the app, see [Troubleshooting App Connectors](troubleshooting-api-connectors-using-error-messages.md).

## Next steps

> [!div class="nextstepaction"]
> [Control cloud apps with policies](control-cloud-apps-with-policies.md)

[!INCLUDE [Open support ticket](includes/support.md)]
