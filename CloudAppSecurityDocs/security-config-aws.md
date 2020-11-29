---
title: Get security configuration recommendations for AWS
description: This article provides information about how to get security configuration recommendations in Cloud App Security by integrating with Amazon Web Services.
ms.date: 06/28/2020
ms.topic: how-to
---
# Security configuration for AWS

[!INCLUDE [Banner for top of topics](includes/banner.md)]

Microsoft Cloud App Security provides you with a security configuration assessment of your Amazon Web Services environment. This assessment provides fundamental security recommendations based on the Center for Internet Security (CIS) benchmark for AWS.

## Prerequisites

- AWS Security Hub must be set up for all your AWS account regions. For more information, see [Setting Up AWS Security Hub](https://go.microsoft.com/fwlink/?linkid=2100208).
    > [!NOTE]
    > If this is the first time you're enabling Security Hub, it can take several hours for the initial data to become available.
- Your Amazon Web Services must be connected to Cloud App Security. For more information, see [Connect AWS to Microsoft Cloud App Security](connect-aws-to-microsoft-cloud-app-security.md).

## How to view AWS security recommendations

1. In Cloud App Security, browse to **Investigate** > **Security configuration**, and then select the **Amazon Web Services** tab.

    > [!NOTE]
    > It might take up to 15 minutes before your changes take effect.

    ![security configuration menu](media/security-configuration-menu.png)

1. You can filter the recommendations by type, by resource, and by accounts. Additionally, you can click on the security configuration icon ![ASC icon](media/asc-icon.png) to open the recommendation in Amazon Security Hub for more information and to deep dive into the recommendation.

    > [!NOTE]
    > To make investigation even simpler, you can create custom queries and save them for later use. After you've finished building your query, click the **Save as** button in the top right corner of the filters. In the **Save query** pop-up, name your query.

    ![security configuration](media/security-configuration-aws.png)

## Next steps

> [!div class="nextstepaction"]
> [Control cloud apps with policies](control-cloud-apps-with-policies.md)

[!INCLUDE [Open support ticket](includes/support.md)]
