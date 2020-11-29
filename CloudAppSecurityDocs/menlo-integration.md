---
title: Integrate Cloud App Security with Menlo Security
description: This article describes how to integrate Microsoft Cloud App Security with Menlo Security for seamless Cloud Discovery and automated block of unsanctioned apps.
ms.date: 11/09/2020
ms.topic: how-to
---
# Integrate Cloud App Security with Menlo Security

[!INCLUDE [Banner for top of topics](includes/banner.md)]

If you work with both Cloud App Security and Menlo Security, you can integrate the two products to enhance your security Cloud Discovery experience. Menlo Security, as a standalone Secure Web Gateway, monitors your organization's traffic enabling you to set policies for blocking transactions. Together, Cloud App Security and Menlo Security provide the following capabilities:

- Seamless deployment of Cloud Discovery - Use Menlo Security to proxy your traffic and send it to Cloud App Security. This eliminates the need for installation of log collectors on your network endpoints to enable Cloud Discovery.
- Menlo Security's block capabilities are automatically applied on apps you set as unsanctioned in Cloud App Security.

## Prerequisites

- A valid license for Microsoft Cloud App Security, or a valid license for Azure Active Directory Premium P1
- A valid license for Menlo Security

## Deployment

1. Log into you Menlo Admin portal and use the [Menlo Security Integration with Microsoft Cloud Access Security Setup Guide](https://admin.menlosecurity.com/docs/guides/web_admin_settings_casb.html?highlight=microsoft) to integrate the products.

1. Investigate cloud apps discovered on your network. For more information and investigation steps, see [Working with Cloud Discovery](working-with-cloud-discovery-data.md).
1. Any app that you set as unsanctioned in Cloud App Security will be pinged by Menlo Security every two hours, and then automatically blocked by Menlo Security. For more information about unsanctioning apps, see [Sanctioning/unsanctioning an app](governance-discovery.md#BKMK_SanctionApp).

## Next steps

> [!div class="nextstepaction"]
> [Control cloud apps with policies](control-cloud-apps-with-policies.md)

[!INCLUDE [Open support ticket](includes/support.md)]
