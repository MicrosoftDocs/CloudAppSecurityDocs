---
title: Classic portal -  Security configuration for Amazon Web Services
description: Classic portal -  This article provides information about how to get security configuration recommendations in Defender for Cloud Apps by integrating with Amazon Web Services.
ms.date: 01/19/2023
ms.topic: how-to
ROBOTS: NOINDEX
---
# Classic portal: Security configuration for Amazon Web Services

[!INCLUDE [Banner for top of topics](includes/banner.md)]

[!INCLUDE [CSPM banner](includes/cspm-banner.md)]

Microsoft Defender for Cloud Apps provides you with a security configuration assessment of your Amazon Web Services environment. This assessment provides fundamental security recommendations based on the Center for Internet Security (CIS) benchmark for AWS.

## Prerequisites

- AWS Security Hub must be set up for all your AWS account regions. For more information, see [Setting Up AWS Security Hub](https://go.microsoft.com/fwlink/?linkid=2100208).
    > [!NOTE]
    > If this is the first time you're enabling Security Hub, it can take several hours for the initial data to become available.
- Your Amazon Web Services must be connected to Defender for Cloud Apps. For more information, see [Connect AWS to Microsoft Defender for Cloud Apps](./connect-aws.md).

## How to view AWS security recommendations

1. In Defender for Cloud Apps, browse to **Investigate** > **Security configuration**, and then select the **Amazon Web Services** tab.

    > [!NOTE]
    > It might take up to 15 minutes before your changes take effect.

    ![security configuration menu.](media/classic-security-configuration-menu.png)

1. You can filter the recommendations by type, by resource, and by accounts. Additionally, you can click on the security configuration icon ![Amazon Security Hub icon.](media/classic-asc-icon.png) to open the recommendation in Amazon Security Hub for more information and to deep dive into the recommendation.

    > [!NOTE]
    > To make investigation even simpler, you can create custom queries and save them for later use. After you've finished building your query, click the **Save as** button in the top right corner of the filters. In the **Save query** pop-up, name your query.

    ![security configuration.](media/classic-security-configuration-aws.png)

## Next steps

> [!div class="nextstepaction"]
> [Control cloud apps with policies](control-cloud-apps-with-policies.md)

[!INCLUDE [Open support ticket](includes/support.md)]
