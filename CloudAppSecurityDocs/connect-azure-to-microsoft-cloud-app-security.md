---
title: Connect Azure to Cloud App Security
description: This article provides information about how to connect Azure to Cloud App Security using the API connector for visibility and control over use.
ms.date: 12/27/2020
ms.topic: how-to
---
# Connect Azure to Microsoft Cloud App Security

[!INCLUDE [Banner for top of topics](includes/banner.md)]

This article provides instructions for connecting Microsoft Cloud App Security to your existing Azure account using the app connector API. This connection gives you visibility into and control over Azure use. For information about how Cloud App Security protects Azure, see [Protect Azure](protect-azure.md).

## How to connect Azure to Cloud App Security

> [!NOTE]
>
> - User must be a Global or Security administrator in Azure AD to connect Azure to Microsoft Cloud App Security.
> - Cloud App Security displays activities from **all** subscriptions.
> - User account information is populated in Cloud App Security as users perform activities in Azure.
> - Currently, Cloud App Security monitors only ARM activities.

1. In the **Connected apps** page, click the plus button and select **Microsoft Azure**.

    ![connect Azure menu item](media/connect-azure-menu.png)

2. In the Azure pop-up, click **Connect Microsoft Azure**.

    ![connect Azure](media/connect-azure.png)

> [!NOTE]
> After connecting Azure, data will be pulled. You will see data from then onwards.

If you have any problems connecting the app, see [Troubleshooting App Connectors](troubleshooting-api-connectors-using-error-messages.md).

## Next steps

> [!div class="nextstepaction"]
> [Control cloud apps with policies](control-cloud-apps-with-policies.md)

[!INCLUDE [Open support ticket](includes/support.md)]
