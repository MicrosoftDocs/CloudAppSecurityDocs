---
title: Connect Egnyte
description: This article describes how to connect Microsoft Defender for Cloud Apps to your existing Egnyte via the App Connector APIs. 
ms.date: 04/03/2023
ms.topic: how-to
---
# Connect Egnyte to Microsoft Defender for Cloud Apps

[!INCLUDE [Banner for top of topics](includes/banner.md)]

This article describes how to connect Microsoft Defender for Cloud Apps to your existing Egnyte via the App Connector APIs. The resulting connection gives you visibility into and control over your organization's use of Egnyte.

## Prerequisites

- The authorizing user must be one of the following:
  - Power user with **can run reports** role
  - Administrator
- Audit reporting must be available in Egnyte's plan

## How to connect Egnyte to Defender for Cloud Apps

### Configure Defender for Cloud Apps

1. In the Microsoft 365 Defender portal, select **Settings**. Then choose **Cloud Apps**. Under **Connected apps**, select **App Connectors**.

1. In the **App connectors** page, select **+Connect an app**, and then select **Egnyte**.

1. In the window that appears, give the connector a descriptive name, and then select **Next**.

1. In the **Enter details** page, in **Application URL**, insert your Egnyte URL by using the following format: `https://<domain_name>.egnyte.com`
1. Select **Next**.
1. Select **Connect Egnyte**.
1. In the redirected page, select **Allow**.
1. In the Microsoft 365 Defender portal, select **Settings**. Then choose **Cloud Apps**. Under **Connected apps**, select **App Connectors**. Make sure the status of the connected App Connector is **Connected**.

>[!NOTE]
>Microsoft recommends using a short lived access token. Egnyte doesn't currently support short lived tokens. We recommend our customers to refresh the access token every 6 months as a security best practice.
>To refresh the access token, revoke the old token by following [Revoking an oAuth token](https://developers.egnyte.com/docs/read/Public_API_Authentication#Revoking-an-OAuth-Token).
>Once the old token is revoked, reconnect the Egnyte connector by following the process documented above.

## Next steps

> [!div class="nextstepaction"]
> [Control cloud apps by using policies](control-cloud-apps-with-policies.md)

[!INCLUDE [Open support ticket](includes/support.md)]
