---
title: Classic portal -  Integrate with Corrata
description: Classic portal -  This article describes how to integrate Microsoft Defender for Cloud Apps with Corrata for seamless Cloud Discovery and automated block of unsanctioned apps.
ms.date: 01/19/2023
ms.topic: how-to
ROBOTS: NOINDEX
---
# Classic portal: Integrate Defender for Cloud Apps with Corrata

[!INCLUDE [Banner for top of topics](includes/classic-banner.md)]

If you work with both Defender for Cloud Apps and Corrata, you can integrate the two products to enhance your security Cloud Discovery experience for mobile app use. Corrata, as a local Mobile gateway, monitors your organization's traffic from mobile devices enabling you to set policies for blocking transactions. Together, Defender for Cloud Apps and Corrata provide the following capabilities:

- Seamless deployment of Cloud Discovery - Use Corrata to collect your mobile device traffic and send it to Defender for Cloud Apps. This eliminates the need for installation of log collectors on your network endpoints to enable Cloud Discovery.
- Corrata's block capabilities are automatically applied on apps you set as unsanctioned in Defender for Cloud Apps.
- Enhance your Corrata portal with the Defender for Cloud Apps risk assessment for leading cloud apps, which can be viewed directly in the Corrata portal.

## Prerequisites

- A valid license for Microsoft Defender for Cloud Apps
- A valid license for Corrata Cloud

## Deployment

1. In the Corrata portal, integrate Corrata into Defender for Cloud Apps. For instructions, see [Integrating Corrata with Microsoft Defender for Cloud Apps](https://corrata.com/microsoft-mcas-onboarding/).
2. In the [Defender for Cloud Apps portal](https://portal.cloudappsecurity.com/), do the following integration steps:
    1. Select the settings cog and then select **Cloud Discovery Settings**.
    2. Select the **Automatic log upload** tab and then select **Add data source**.
    3. In the **Add data source** page, enter the following settings:

        - Name = Corrata
        - Source = Corrata
        - Receiver type = FTP

        ![data source Corrata.](media/classic-data-source-corrata.png)

    4.Select **View sample of expected log file**. Then select **Download sample log** to view a sample discovery log, and make sure it matches your logs.

3. Investigate cloud apps discovered on your network. For more information and investigation steps, see [Working with Cloud Discovery](working-with-cloud-discovery-data.md).

4. Any app that you set as unsanctioned in Defender for Cloud Apps will be pinged by Corrata, and then automatically blocked by Corrata. For more information about unsanctioning apps, see [Sanctioning/unsanctioning an app](governance-discovery.md#sanctioningunsanctioning-an-app).

## Next steps

> [!div class="nextstepaction"]
> [Control cloud apps with policies](control-cloud-apps-with-policies.md)

[!INCLUDE [Open support ticket](includes/classic-support.md)]
