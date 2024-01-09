---
title: Classic portal -  Connect Dropbox
description: Classic portal -  This article provides information about how to connect your Dropbox app to Defender for Cloud Apps using the API connector  for visibility and control over use.
ms.date: 01/19/2023
ms.topic: how-to
ROBOTS: NOINDEX
---
# Classic portal: Connect Dropbox to Microsoft Defender for Cloud Apps

[!INCLUDE [Banner for top of topics](includes/classic-banner.md)]

This article provides instructions for connecting Microsoft Defender for Cloud Apps to your existing Dropbox account using the connector APIs. This connection gives you visibility into and control over Dropbox use. For information about how Defender for Cloud Apps protects Dropbox, see [Protect Dropbox](protect-dropbox.md).

Because Dropbox enables access to files from shared links without signing in, Defender for Cloud Apps registers these users as Unauthenticated users. If you see unauthenticated Dropbox users, it may indicate users who aren't from your organization, or they might be recognized users from within your organization who didn't sign in.

## How to connect Dropbox to Defender for Cloud Apps

1. In the Defender for Cloud Apps console, select **Investigate** and then **Connected apps**.

1. In the **App connectors** page, select the plus button followed by **Dropbox**.

    ![connect dropbox.](media/classic-connect-dropbox.png "connect dropbox")

1. In the pop-up, enter the admin account email address.

1. Select **Generate link**.

1. Select **Follow this link**.

    The Dropbox sign in page opens. Enter your credentials to allow Defender for Cloud Apps access to your team's Dropbox instance.

1. Dropbox asks you if you want to allow Defender for Cloud Apps access to your team information, activity log, and perform activities as a team member. To proceed, select **Allow**.

1. Back in the Defender for Cloud Apps console, you should receive a message that Dropbox was successfully connected.

1. Make sure the connection succeeded by selecting **Test API**.

    Testing may take a couple of minutes. After you receive a success notice, select **Close**.

After connecting Dropbox, you'll receive events for 60 days prior to connection.

> [!NOTE]
> Any Dropbox events for adding a file are displayed in Defender for Cloud Apps as Upload file to align to all other apps connected to Defender for Cloud Apps.

If you have any problems connecting the app, see [Troubleshooting App Connectors](troubleshooting-api-connectors-using-error-messages.md).

## Next steps

> [!div class="nextstepaction"]
> [Control cloud apps with policies](control-cloud-apps-with-policies.md)

[!INCLUDE [Open support ticket](includes/classic-support.md)]
