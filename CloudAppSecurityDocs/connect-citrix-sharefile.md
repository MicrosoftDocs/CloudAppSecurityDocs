---
title: Connect Citrix ShareFile
description: This article provides information about how to connect your Citrix ShareFile app to Defender for Cloud Apps using the API connector for visibility and control over use.
ms.date: 04/03/2023
ms.topic: how-to
---
# Connect Citrix ShareFile to Microsoft Defender for Cloud Apps

[!INCLUDE [Banner for top of topics](includes/banner.md)]

This article provides instructions for connecting Microsoft Defender for Cloud Apps to your existing Citrix ShareFile account using the App Connector APIs. This connection gives you visibility into and control over Citrix ShareFile use.

[!INCLUDE [security-posture-management-connector](includes/security-posture-management-connector.md)]

## Prerequisites

The Citrix Share file user used for logging into Citrix Share file must have Access Company account permissions.

## Create API keys

1. Go to [ShareFile API Documentation](https://api.sharefile.com/), and sign in to your organization account.

    ![connect Citrix ShareFile login.](media/connect-citrix-sharefile-login.png "connect Citrix ShareFile login")

1. Select **Get an API Key**.

    ![connect Citrix ShareFile API key.](media/connect-citrix-sharefile-api-key.png "connect Citrix ShareFile API key")

1. To generate API keys (*Client ID* and *Client Secret*), go to **Create New**.

    ![connect Citrix ShareFile create new key.](media/connect-citrix-sharefile-create-new.png "connect Citrix ShareFile create new key")

1. Fill out the following fields:

    - Application name: Microsoft Defender for Cloud Apps (you can also choose another name).
    - Redirect URL:  `https://portal.cloudappsecurity.com/api/oauth/saga` (change to your domain).

1. Select **Generate API Key**.

1. Copy the *Client ID* and *Client Secret*.

## Configure Defender for Cloud Apps

1. In the Microsoft 365 Defender portal, select **Settings**. Then choose **Cloud Apps**. Under **Connected apps**, select **App Connectors**.

1. In the **App connectors** page, select **+Connect an app**, followed by **Citrix ShareFile**.

    ![connect Citrix ShareFile app connectors.](media/connect-citrix-sharefile-app-connectors.png "connect Citrix ShareFile app connectors")

1. In the pop-up, give the connector a descriptive name, and select **Connect Citrix ShareFile**.  

    ![connect Citrix ShareFile instance name.](media/connect-citrix-sharefile-instance-name.png "connect Citrix ShareFile instance name")

1. In the next screen, enter the following fields:

    - The **Client ID** and **Client Secret** that you created in the Citrix ShareFile API portal.
    - **Client Subdomain**: Enter your account's subdomain. For example, if your account's URL is "mycompany.sharefile.com", you would enter "mycompany".

1. Select **Connect** in Citrix ShareFile.

1. In the Microsoft 365 Defender portal, select **Settings**. Then choose **Cloud Apps**. Under **Connected apps**, select **App Connectors**. Make sure the status of the connected App Connector is **Connected**.

## Rate limits

The default rate limit is 420 requests per minute.  

## Next steps

> [!div class="nextstepaction"]
> [Control cloud apps with policies](control-cloud-apps-with-policies.md)

[!INCLUDE [Open support ticket](includes/support.md)]
