---
title: Classic portal -  Security configuration for Google Cloud Platform
description: Classic portal -  This article provides information about how to get security configuration recommendations in Defender for Cloud Apps by integrating with Google Cloud Platform.
ms.date: 01/19/2023
ms.topic: how-to
ROBOTS: NOINDEX
---
# Classic portal: Security configuration for Google Cloud Platform

[!INCLUDE [Banner for top of topics](includes/banner.md)]

[!INCLUDE [CSPM banner](includes/cspm-banner.md)]

Microsoft Defender for Cloud Apps provides you with a security configuration assessment of your Google Cloud Platform (GCP) environment. This assessment provides fundamental security recommendations based on the [Center for Internet Security (CIS) benchmark for GCP](https://www.cisecurity.org/benchmark/google_cloud_computing_platform/), version 1.1.0.

This assessment provides an organizational view of security configuration recommendations of all GCP projects and enables security admins to investigate of security configuration gaps and initiate remediation by the resource owners.

## Prerequisites

- You must set up GCP Security Command Center with Security Health Analytics for all your GCP projects in your organization. For more information, see [Setting up GCP Security Command Center](https://cloud.google.com/security-command-center/docs/quickstart-security-command-center) and [Enable Security Health Analytics](https://cloud.google.com/security-command-center/docs/how-to-use-security-health-analytics).
- Your GCP projects must be connected to Defender for Cloud Apps. For more information, see [Connect GCP to Microsoft Defender for Cloud Apps](./connect-google-gcp.md).

## How to view GCP security recommendations

1. In Defender for Cloud Apps, browse to **Investigate** > **Security configuration**, and then select the **Google Cloud Platform** tab.

    > [!NOTE]
    > It might take up to 15 minutes before your changes take effect.

    ![security configuration menu.](media/classic-security-configuration-menu.png)

1. You can filter the recommendations by type, by resource, and by subscription. Additionally, you can click on the security configuration icon ![GCP Security Command Center icon.](media/classic-asc-icon.png) to open the recommendation in GCP Security Command Center for more information and to deep dive into the recommendation.

    > [!NOTE]
    > To make investigation even simpler, you can create custom queries and save them for later use. After you've finished building your query, click the **Save as** button in the top right corner of the filters. In the **Save query** pop-up, name your query.

    ![security configuration.](media/classic-security-configuration-gcp.png)

1. Select a recommendation to view additional information about the recommendation including a description and detailed remediation guidelines.

    ![security configuration recommendation.](media/classic-security-configuration-gcp-details.png)

## Next steps

> [!div class="nextstepaction"]
> [Control cloud apps with policies](control-cloud-apps-with-policies.md)

[!INCLUDE [Open support ticket](includes/support.md)]
