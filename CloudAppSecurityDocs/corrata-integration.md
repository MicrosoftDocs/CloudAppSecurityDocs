---
# required metadata

title: Integrate Cloud App Security with Corrata
description: This article describes how to integrate Microsoft Cloud App Security with Corrata for seamless Cloud Discovery and automated block of unsanctioned apps.
keywords:
author: shsagir
ms.author: shsagir
manager: shsagir
ms.date: 05/17/2020
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.prod:
ms.service: cloud-app-security
ms.technology:

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: borisk
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: seodec18

---
# Integrate Cloud App Security with Corrata

*Applies to: Microsoft Cloud App Security*

If you work with both Cloud App Security and Corrata, you can integrate the two products to enhance your security Cloud Discovery experience for mobile app use. Corrata, as a local Mobile gateway, monitors your organization's traffic from mobile devices enabling you to set policies for blocking transactions. Together, Cloud App Security and Corrata provide the following capabilities:

- Seamless deployment of Cloud Discovery - Use Corrata to collect your mobile device traffic and send it to Cloud App Security. This eliminates the need for installation of log collectors on your network endpoints to enable Cloud Discovery.
- Corrata's block capabilities are automatically applied on apps you set as unsanctioned in Cloud App Security.
- Enhance your Corrata portal with Cloud App Security's risk assessment for leading cloud apps, which can be viewed directly in the Corrata portal.

## Prerequisites

- A valid license for Microsoft Cloud App Security
- A valid license for Corrata Cloud

## Deployment

1. In the Corrata portal, do the steps to complete the [Corrata partner integration with Microsoft Cloud App Security](https://corrata.com/microsoft-mcas-onboarding).
2. In the Cloud App Security portal, do the following integration steps:
    1. Click on the settings cog and select **Cloud Discovery Settings**.
    2. Click on the **Automatic log upload** tab and then click **Add data source**.
    3. In the **Add data source** page, enter the following settings:

        - Name = Corrata
        - Source = Corrata
        - Receiver type = FTP

        ![data source Corrata](media/data-source-Corrata.png)

    4. Click **View sample of expected log file**. Then click **Download sample log** to view a sample discovery log, and make sure it matches your logs.

3. Investigate cloud apps discovered on your network. For more information and investigation steps, see [Working with Cloud Discovery](working-with-cloud-discovery-data.md).

4. Any app that you set as unsanctioned in Cloud App Security will be pinged by Corrata, and then automatically blocked by Corrata. For more information about unsanctioning apps, see [Sanctioning/unsanctioning an app](governance-discovery.md#BKMK_SanctionApp).

## Next steps

> [!div class="nextstepaction"]
> [Control cloud apps with policies](control-cloud-apps-with-policies.md)

[!INCLUDE [Open support ticket](includes/support.md)]
