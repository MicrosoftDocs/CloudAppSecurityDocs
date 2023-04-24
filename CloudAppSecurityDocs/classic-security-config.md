---
title: Classic portal -  Security configuration overview for public cloud platforms
description: Classic portal -  This article provides information about how to get security configuration recommendations in Defender for Cloud Apps for your organization's public cloud platforms.
ms.date: 01/19/2023
ms.topic: how-to
ROBOTS: NOINDEX
---
# Classic portal: Security configuration overview for public cloud platforms

[!INCLUDE [Banner for top of topics](includes/banner.md)]

[!INCLUDE [CSPM banner](includes/cspm-banner.md)]

Microsoft Defender for Cloud Apps provides you with security configuration assessments for your Azure, Amazon Web Services (AWS), Google Cloud Platform (GCP) and other SaaS applications. Recommendations cover all Azure subscriptions, AWS accounts including member accounts, and all GCP projects that are connected to your organization. This multi-cloud view of all cloud platform security configuration recommendations enables security admins to investigate all security configuration gaps in Defender for Cloud Apps.

Use the following links to get more details about the different assessment types.

- **[Azure recommendations](security-config-azure.md)**: Azure best practices security recommendations consumed from Microsoft Defender for Cloud.
- **[AWS recommendations](security-config-aws.md)**: Security recommendations based on the Center for Internet Security (CIS) benchmark for AWS, version 1.2.0, consumed from AWS Security Hub.
- **[GCP recommendations](security-config-gcp.md)**: Security recommendations based on the CIS benchmark for GCP, version 1.1.0, consumed from Google Security Command Center and Security Health Analytics.
- **[SaaS applications](security-saas.md)**: Security recommendations for different SaaS applications based on Microsoft benchmarks.

## Security recommendations report

Defender for Cloud Apps lets you export a details list of security recommendations to help you monitor, understand, and customize your cloud environments to better protect your organization.

To export a security recommendations list, perform the following steps:

1. In Defender for Cloud Apps, browse to **Investigate** > **Security configuration**.

1. Select the security recommendations tab for the relevant cloud.
1. On the top-right of the recommendations table, select **Export**.

## Next steps

> [!div class="nextstepaction"]
> [Control cloud apps with policies](control-cloud-apps-with-policies.md)

[!INCLUDE [Open support ticket](includes/support.md)]
