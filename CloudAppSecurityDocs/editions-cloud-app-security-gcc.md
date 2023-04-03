---
title: US Government offerings
description: This article describes the features differences between Microsoft Defender for Cloud Apps for US Government offerings and the commercial offering.
ms.date: 02/28/2023
ms.topic: overview
---
# Microsoft Defender for Cloud Apps for US Government offerings

[!INCLUDE [Banner for top of topics](includes/banner.md)]

The Microsoft Defender for Cloud Apps GCC High and Department of Defense (DoD) offerings is built on the Microsoft Azure Government Cloud and is designed to inter-operate with Microsoft 365 GCC High and DoD. The GCC High and DoD offerings utilizes the same underlying technologies and capabilities as the commercial instance of Microsoft Defender for Cloud Apps. Therefore, the commercial offering's public documentation should be used as a starting point for deploying and operating the service.

The Microsoft Defender for Cloud Apps US Government Service Description is designed to serve as an overview of the service offering in the GCC High and DoD environments and will cover feature variations from the commercial offering.  For more information about government offerings, see [US Government service description](/enterprise-mobility-security/solutions/ems-govt-service-description).

>[!NOTE]
> Defender for Cloud Apps customers who are using GCC should use this URL to log on to the service:  <https://portal.cloudappsecuritygov.com>

## Getting started with Microsoft Defender for Cloud Apps for US Government offerings

The Microsoft Defender for Cloud Apps offerings for GCC High and DoD customers are built on the Microsoft Azure Government Cloud and are designed to inter-operate with Microsoft 365 GCC High and DoD environments. Full details on the services and how to use them can be found in the [Microsoft Defender for Cloud Apps public documentation](/defender-cloud-apps/). The public documentation should be used as a starting point for deploying and operating the service and the following Service Description details and changes from functionality or features in the GCC High or DoD environments.

To get started, use the [Basic Setup](general-setup.md) page for access to the Microsoft Defender for Cloud Apps GCC High or DoD portals, and ensure your [Network requirements](network-requirements.md) are configured. To configure Defender for Cloud Apps to use your own key to encrypt the data it collects while it's at rest, see [Encrypt Defender for Cloud Apps data at rest with your own key (BYOK)](ems-cloud-app-security-govt-service-byok.md). Follow the additional steps in the How-to guides for other detailed instructions.

> [!NOTE]
> Data encryption is currently only available for specific Microsoft Defender for Cloud Apps government offerings.

## Feature variations in Microsoft Defender for Cloud Apps US Government offerings

Unless otherwise specified, new feature releases, including preview features, documented in [What's new with Microsoft Defender for Cloud Apps](release-notes.md), will be available in GCC High and DoD environments within three months of release in the Microsoft Defender for Cloud Apps commercial environment, unless otherwise noted.

## Feature support

Microsoft Defender for Cloud Apps for US Government offers parity with the Microsoft Defender for Cloud Apps commercial environment, with the following exceptions:

| Feature Name                           | Description                                                  | GCC     | GCC High | DoD     |
| -------------------------------------- | ------------------------------------------------------------ | ------- | -------- | ------- |
| **Microsoft Secure Score integration** | Surfacing Microsoft Defender for Cloud Apps controls in Microsoft Secure Score | Roadmap | Roadmap  | Roadmap |
|**App governance add-on to Microsoft Defender for Cloud Apps** | App governance delivers full visibility, remediation, and governance into how Azure-connected apps and their users access, use, and share your sensitive data stored in Microsoft 365 through actionable insights and automated policy alerts and actions. | Roadmap | Roadmap  | Roadmap |

## Next steps

- [Microsoft Defender for Cloud Apps overview](what-is-defender-for-cloud-apps.md)
