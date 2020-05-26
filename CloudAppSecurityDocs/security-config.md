---
# required metadata

title: Get security configuration recommendations for Azure - Cloud App Security
description: This article provides information about how to Get security configuration recommendations in Cloud App Security by integrating with Azure Security Center.
keywords:
author: shsagir
ms.author: shsagir
manager: shsagir
ms.date: 06/23/2020
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.prod:
ms.service: cloud-app-security
ms.technology:

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: seodec18

---
# Security configuration for Azure

*Applies to: Microsoft Cloud App Security*

Microsoft Cloud App Security provides you with security configuration assessments of your public cloud platforms, including Azure, Amazon Web Services (AWS), and Google Cloud Platform (GCP).

The assessments are based on the native cloud platform tools:

- [Azure recommendations](security-config-azure.md) are sourced from Azure Security Center surfacing Azure best practices security recommendations
- [AWS recommendations](security-config-aws.md) are sourced from AWS Security Hub surfacing security recommendations based on the Center for Internet Security (CIS) benchmark for AWS, version 1.2.0.
- [GCP recommendations](security-config-gcp.md) are sourced from Google Security Command Center and Security Health Analytics surfacing security recommendations based on the Center for Internet Security (CIS) benchmark for GCP, version 1.1.0.

This organization-level view of all public cloud platform security configuration recommendations enables security admins to investigate security configuration gaps in one central location. Recommendations cover all Azure subscriptions of the Azure tenant, AWS accounts within the organization including member accounts, and all GCP projects within the organization.

## Next steps

> [!div class="nextstepaction"]
> [Control cloud apps with policies](control-cloud-apps-with-policies.md)

[!INCLUDE [Open support ticket](includes/support.md)]
