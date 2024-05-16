---
title: Classic portal -  Connect Zoom
description: Classic portal -  This article provides information about how to connect your Zoom environment  to Defender for Cloud Apps using the API connector for visibility and control over use.
ms.date: 04/24/2023
ms.topic: how-to
ROBOTS: NOINDEX
---
# Classic portal: Connect Zoom to Microsoft Defender for Cloud Apps

[!INCLUDE [Banner for top of topics](includes/classic-banner.md)]

This article provides instructions for connecting Microsoft Defender for Cloud Apps to your existing Zoom environment using the app connector API. This connection gives you visibility into and control over Zoom use.


## Prerequisites

Before connecting Zoom to Defender for Cloud Apps, make sure that you have the following prerequisites:

- A Zoom PRO plan or higher
- Access to Zoom as an account owner or admin, which is required to access the Zoom API.

    The admin account is used only for initial consent while connecting Zoom to Defender for Cloud Apps. Defender for Cloud Apps uses an OAuth app for daily transactions.

## How to connect Zoom to Defender for Cloud Apps

1. Sign into Zoom as an account owner or admin.

1. In the [Defender for Cloud Apps portal](https://portal.cloudappsecurity.com/), select **Investigate** and then **Connected apps**.

1. In the **App connectors** page, select the plus button followed by **Zoom**.

1. In the pop-up, give the connector a descriptive name, and select **Connect in Zoom**.

    You're redirected to the Zoom page, where you're prompted to allow the connection.

1. Allow the connection in Zoom.

1. Watch for the updates to appear on the Microsoft 365 **Secure score** page. For more information, see the [Microsoft Secure Score documentation](/microsoft-365/security/defender/microsoft-secure-score).

   > [!NOTE]
   >
   > - The first connection can take up to 4 hours to get all users and their activities.
   > - The activities that will show are the activities that were generated in the last 7 days before the connection.
   > - After the connector's **Status** is marked as **Connected**, the connector is live and works.

## Rate limits

- **Pro accounts**: 30 requests per second
- **Business accounts**: 80 requests per second

## Next steps

> [!div class="nextstepaction"]
> [Control cloud apps with policies](control-cloud-apps-with-policies.md)

[!INCLUDE [Open support ticket](includes/classic-support.md)]
