---
title: Get security configuration recommendations for your public cloud platforms
description: This article provides information about how to get security configuration recommendations in Cloud App Security for your organization's public cloud platforms.
ms.date: 06/28/2020
ms.topic: how-to
---
# Security configuration overview

[!INCLUDE [Banner for top of topics](includes/banner.md)]

Microsoft Cloud App Security provides you with security configuration assessments for your Azure, Amazon Web Services (AWS), and Google Cloud Platform (GCP). Recommendations cover all Azure subscriptions, AWS accounts including member accounts, and all GCP projects that are connected to your organization. This multi-cloud view of all cloud platform security configuration recommendations enables security admins to investigate all security configuration gaps in Cloud App Security.

Use the following links to get more details about the different assessment types.

- **[Azure recommendations](security-config-azure.md)**: Azure best practices security recommendations consumed from Azure Security Center.
- **[AWS recommendations](security-config-aws.md)**: Security recommendations based on the Center for Internet Security (CIS) benchmark for AWS, version 1.2.0, consumed from AWS Security Hub.
- **[GCP recommendations](security-config-gcp.md)**: Security recommendations based on the CIS benchmark for GCP, version 1.1.0, consumed from Google Security Command Center and Security Health Analytics.

## Security recommendations report

Cloud App Security lets you export a details list of security recommendations to help you monitor, understand, and customize your cloud environments to better protect your organization.

To export a security recommendations list, perform the following steps:

1. In Cloud App Security, browse to **Investigate** > **Security configuration**.

1. Select the security recommendations tab for the relevant cloud.
1. On the top-right of the recommendations table, click **Export**.

## Next steps

> [!div class="nextstepaction"]
> [Control cloud apps with policies](control-cloud-apps-with-policies.md)

[!INCLUDE [Open support ticket](includes/support.md)]
