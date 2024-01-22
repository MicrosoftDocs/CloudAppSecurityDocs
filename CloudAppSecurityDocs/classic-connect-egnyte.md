---
title: Classic portal -  Connect Egnyte
description: Classic portal -  This article describes how to connect Microsoft Defender for Cloud Apps to your existing Egnyte via the App Connector APIs. 
ms.date: 01/19/2023
ms.topic: how-to
ROBOTS: NOINDEX
---
# Classic portal: Connect Egnyte to Microsoft Defender for Cloud Apps

[!INCLUDE [Banner for top of topics](includes/classic-banner.md)]

This article describes how to connect Microsoft Defender for Cloud Apps to your existing Egnyte via the App Connector APIs. The resulting connection gives you visibility into and control over your organization's use of Egnyte.

## Prerequisites

- The authorizing user must be one of the following:
  - Power user with **can run reports** role
  - Administrator
- Audit reporting must be available in Egnyte's plan

## How to connect Egnyte to Defender for Cloud Apps

### Configure Defender for Cloud Apps

1. In the [Defender for Cloud Apps portal](https://portal.cloudappsecurity.com/), select **Investigate** and then **Connected apps**.

1. On the **App connectors** tab, select the plus sign, and then select **Egnyte**.

1. In the window that appears, give the connector a descriptive name, and then select **Connect Egnyte**:

    - In the **Application URL**, insert your Egnyte URL by using the following format: `https://<domain_name>.egnyte.com`

1. Select **Connect in Egnyte**.
1. In the redirected page, select **Allow**.
1. Make sure the connection succeeded by selecting **Test now**. The test might take a few minutes. After you see a success notice, select **Close**.
1. The first connection can take up to four hours to get all users and their activities in the seven days before the connection.
1. After the connector's **Status** is marked as **Connected**, the connector is live and works.

>[!NOTE]
>Microsoft recommends using a short lived access token. Egnyte doesn't currently support short lived tokens. We recommend our customers to refresh the access token every 6 months as a security best practice.
>To refresh the access token, revoke the old token by following [Revoking an oAuth token](https://developers.egnyte.com/docs/read/Public_API_Authentication#Revoking-an-OAuth-Token).
>Once the old token is revoked, reconnect the Egnyte connector by following the process documented above.

## Next steps

> [!div class="nextstepaction"]
> [Control cloud apps by using policies](control-cloud-apps-with-policies.md)

[!INCLUDE [Open support ticket](includes/classic-support.md)]
