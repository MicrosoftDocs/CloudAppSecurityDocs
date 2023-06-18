---
title: Connect Okta
description: This article provides information about how to connect your Okta to Defender for Cloud Apps using the API connector for visibility and control over use.
ms.date: 04/03/2023
ms.topic: how-to
---
# Connect Okta to Microsoft Defender for Cloud Apps

[!INCLUDE [Banner for top of topics](includes/banner.md)]

This article provides instructions for connecting Microsoft Defender for Cloud Apps to your existing Okta account using the connector APIs. This connection gives you visibility into and control over Okta use. For information about how Defender for Cloud Apps protects Okta, see [Protect Okta](protect-okta.md).

[!INCLUDE [security-posture-management-connector](includes/security-posture-management-connector.md)]


## How to connect Okta to Defender for Cloud Apps

1. It's recommended that you create an admin Service Account in Okta for Defender for Cloud Apps.

    Make sure you use an account with Super Admin permissions.

    Make sure your Okta account is verified.

1. In the Okta console, select **Admin**.

    - Select **Security** and then **API**.

         ![Okta api.](media/okta-api.png "Okta api")

    - Select **Create Token**.

         ![Okta create token.](media/okta-createtoken.png "Okta create token")

    - In the **Create Token** pop-up, name your Defender for Cloud Apps token, and select **Create Token**.

         ![Okta token pop-up.](media/okta-token-pop-up.png)

    - In the **Token created successfully** pop-up, copy the **Token value**.

         ![Okta token value.](media/okta-token-value.png "Okta token value")

1. In the Microsoft 365 Defender portal, select **Settings**. Then choose **Cloud Apps**. Under **Connected apps**, select **App Connectors**.

1. In the **App connectors page**, select **+Connect an app**, and then **Okta**.

    ![Connect Okta.](media/connect-okta.png "Connect Okta")

1. In the next window, give your connection a name and select **Next**.
1. In the **Enter details** window, in the **Domain** field, enter your Okta domain and paste your Token into the **Token** field.

1. Select **Submit** to create the token for Okta in Defender for Cloud Apps.

1. In the Microsoft 365 Defender portal, select **Settings**. Then choose **Cloud Apps**. Under **Connected apps**, select **App Connectors**. Make sure the status of the connected App Connector is **Connected**.

After connecting Okta, you'll receive events for 60 days prior to connection.

If you have any problems connecting the app, see [Troubleshooting App Connectors](troubleshooting-api-connectors-using-error-messages.md).

## Next steps

> [!div class="nextstepaction"]
> [Control cloud apps with policies](control-cloud-apps-with-policies.md)

[!INCLUDE [Open support ticket](includes/support.md)]
