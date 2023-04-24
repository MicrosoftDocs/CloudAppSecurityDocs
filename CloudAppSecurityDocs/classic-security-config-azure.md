---
title: Classic portal -  Security configuration for Azure
description: Classic portal -  This article provides information about how to get security configuration recommendations in Defender for Cloud Apps by integrating with Microsoft Defender for Cloud.
ms.date: 01/19/2023
ms.topic: how-to
ROBOTS: NOINDEX
---
# Classic portal: Security configuration for Azure

[!INCLUDE [Banner for top of topics](includes/banner.md)]

[!INCLUDE [CSPM banner](includes/cspm-banner.md)]

Microsoft Defender for Cloud Apps provides you with a security configuration assessment of your Azure environment. The assessment, powered by Microsoft Defender for Cloud, provides recommendations for missing configuration and security controls.

## Prerequisites

Your organization must have Microsoft Defender for Cloud licenses for all subscriptions that you want to provide Azure security configuration assessments.

## How to enable Azure security recommendations

To enable security configuration recommendations in Defender for Cloud Apps, activate your Microsoft Defender for Cloud subscription by navigating to the <a href="https://ms.portal.azure.com/#blade/Microsoft_Azure_Security/SecurityMenuBlade/0" target="_blank">portal</a>.

## How to view Azure security recommendations

1. In Defender for Cloud Apps, browse to **Investigate** > **Security configuration**, and then select the **Azure** tab.

    > [!NOTE]
    > It might take up to 15 minutes before your changes take effect.

    ![security configuration menu.](media/classic-security-configuration-menu.png)

1. You can filter the recommendations by type, by resource, and by subscription. Additionally, you can select the security configuration icon ![Defender for Cloud icon.](media/classic-asc-icon.png) to open the recommendation in Microsoft Defender for Cloud for more information and to deep dive into the recommendation.

    > [!NOTE]
    > To make investigation even simpler, you can create custom queries and save them for later use. After you've finished building your query, select the **Save as** button in the top right corner of the filters.  In the **Save query** pop-up, name your query.

    ![security configuration.](media/classic-security-configuration-azure.png)

For information about how to implement security recommendations, see [Managing security recommendations in Microsoft Defender for Cloud](/azure/security-center/security-center-recommendations).

## Next steps

> [!div class="nextstepaction"]
> [Control cloud apps with policies](control-cloud-apps-with-policies.md)

[!INCLUDE [Open support ticket](includes/support.md)]
