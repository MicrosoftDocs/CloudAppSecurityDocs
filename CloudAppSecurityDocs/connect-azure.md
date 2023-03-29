---
title: Connect Azure 
description: This article provides information about how to connect Azure to Defender for Cloud Apps using the API connector for visibility and control over use.
ms.date: 01/29/2023
ms.topic: how-to
---
# Connect Azure to Microsoft Defender for Cloud Apps

[!INCLUDE [Banner for top of topics](includes/banner.md)]

This article provides instructions for connecting Microsoft Defender for Cloud Apps to your existing Azure account using the app connector API. This connection gives you visibility into and control over Azure use. For information about how Defender for Cloud Apps protects Azure, see [Protect Azure](protect-azure.md).

## How to connect Azure to Defender for Cloud Apps

> [!NOTE]
>
> - User must be a Global or Security administrator in Azure AD to connect Azure to Microsoft Defender for Cloud Apps.
> - Defender for Cloud Apps displays activities from **all** subscriptions.
> - User account information is populated in Defender for Cloud Apps as users perform activities in Azure.
> - Currently, Defender for Cloud Apps monitors only ARM activities.

1. In the **Connected apps** page, select the plus button and then select **Microsoft Azure**.

    ![connect Azure menu item.](media/connect-azure-menu.png)

2. In the Azure pop-up, select **Connect Microsoft Azure**.

    ![connect Azure.](media/connect-azure.png)

> [!NOTE]
> After connecting Azure, data will be pulled. You will see data from then onwards.

If you have any problems connecting the app, see [Troubleshooting App Connectors](troubleshooting-api-connectors-using-error-messages.md).

## Next steps

> [!div class="nextstepaction"]
> [Control cloud apps with policies](control-cloud-apps-with-policies.md)

[!INCLUDE [Open support ticket](includes/support.md)]
