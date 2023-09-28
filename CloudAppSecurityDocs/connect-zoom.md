---
title: Connect Zoom
description: This article provides information about how to connect your Zoom environment  to Defender for Cloud Apps using the API connector for visibility and control over use.
ms.date: 06/18/2023
ms.topic: how-to
---

# Connect Zoom to Microsoft Defender for Cloud Apps

[!INCLUDE [Banner for top of topics](includes/banner.md)]

This article provides instructions for connecting Microsoft Defender for Cloud Apps to your existing Zoom environment using the app connector API. This connection gives you visibility into and control over Zoom use.

[!INCLUDE [security-posture-management-connector](includes/security-posture-management-connector.md)]


## Prerequisites

Before connecting Zoom to Defender for Cloud Apps, make sure that you have the following prerequisites:

- A Zoom PRO plan or higher
- Access to Zoom as an account owner or admin, which is required to access the Zoom API.

    The admin account is used only for initial consent while connecting Zoom to Defender for Cloud Apps. Defender for Cloud Apps uses an OAuth app for daily transactions.

## How to connect Zoom to Defender for Cloud Apps

1. Sign into Zoom as an account owner or admin.

1. In the Microsoft 365 Defender portal, select **Settings**. Then choose **Cloud Apps**. Under **Connected apps**, select **App Connectors**.

1. In the **App connectors** page, select **+ Connect an app**, and then **Zoom**.
    :::image type="content" source="media/connect-zoom.png" alt-text="Screenshot of the App Connectors > Zoom pop-up.":::

1. In the **Instance name** page of the pop-up, give the connector a descriptive name, and select **Next**.

1. In the **External link** page, select **Connect Zoom**.  You're redirected to the Zoom page, where you're prompted to allow the connection.

1. In Zoom, select to allow the connection. 

    In Microsoft 365 Defender, the **External link** page of the pop-up is updated to confirm that you're connected. For example:

    :::image type="content" source="media/connect-zoom-success.png" alt-text="Screenshot of the success message in Microsoft 365 Defender.":::

1. In the Microsoft 365 Defender pop-up, select **Done**.

   > [!NOTE]
   > After the connector's **Status** is marked as **Connected**, the connector is live and works.

## Rate limits

- **Pro accounts**: 30 requests per second
- **Business accounts**: 80 requests per second

## Next steps

> [!div class="nextstepaction"]
> [Control cloud apps with policies](control-cloud-apps-with-policies.md)

[!INCLUDE [Open support ticket](includes/support.md)]
