---
# required metadata

title: Set up your organization's settings in Cloud App Security
description: This article explains how to provide information about your organization in Cloud App Security.
keywords:
author: shsagir
ms.author: shsagir
manager: shsagir
ms.date: 11/01/2019
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
# Basic setup for Cloud App Security

*Applies to: Microsoft Cloud App Security*

The following procedure gives you instructions for customizing the Microsoft Cloud App Security portal.

## Prerequisites

For portal access, it's necessary to add the following IP addresses to your Firewall's allow list to provide access for the Cloud App Security portal:

* 104.42.231.28

For US Government GCC High customers, it's also necessary to add the following IP addresses to your Firewall’s allow list to provide access for the Cloud App Security GCC High portal:

* 52.227.143.223
* 13.72.19.4

> [!NOTE]
> To get updates when URLs and IP addresses are changed, subscribe to the RSS as explained in: [Office 365 URLs and IP address ranges](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2).

## Set up the portal

1. In the Cloud App Security portal, in the menu bar, click the settings cog ![settings icon](media/settings-icon.png "settings icon") and select **Settings** to configure your organization's details.

1. Under **Organization details**, it's important that you provide an **Organization display name** for your organization. It's displayed on emails and web pages sent from the system.

1. Provide an **Environment name** (tenant). This information is especially important if you manage more than one tenant.

1. It's also possible to provide a **Logo** that is displayed in email notifications and web pages sent from the system. The logo should be a png file with a maximum size of 150 x 50 pixels on a transparent background.

1. Make sure you add a list of your **Managed domains**. Adding managed domains is a crucial step. Cloud App Security uses the managed domains to determine which users are internal, external, and where files should and shouldn't be shared. This information is used for reports and alerts.

    * Users in domains that aren't configured as internal are marked as external. External users aren't scanned for activities or files.

1. Under **Auto sign out**, specify the amount of time a session can remain inactive before the session is automatically signed out.

1. If you're integrating with Azure Information Protection integration, see [Azure Information Protection Integration](azip-integration.md) for information.

    * To work with Azure Information Protection integration, you must enable the [App connector for Office 365](connect-office-365-to-microsoft-cloud-app-security.md).

1. If you're integrating with Azure Advanced Threat Protection integration, see [Azure Advanced Threat Protection Integration](azip-integration.md) for information.

1. If at any point you want to back up your portal settings, this screen enables you to do that. Click **Export portal settings** to create a json file of all your portal settings, including policy rules, user groups, and IP address ranges.

> [!NOTE]
> If you use ExpressRoute, Cloud App Security is deployed in Azure and fully integrated with [ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-introduction/). All interactions with the Cloud App Security apps and traffic sent to Cloud App Security, including upload of discovery logs, is routed via ExpressRoute **public peering** for improved latency, performance, and security. There are no configuration steps required from the customer side.
>
> For more information about  Public Peering, see [ExpressRoute circuits and routing domains](https://azure.microsoft.com/documentation/articles/expressroute-circuit-peerings/).

## Next steps

> [!div class="nextstepaction"]
> [Set up Cloud Discovery](set-up-cloud-discovery.md)

[!INCLUDE [Open support ticket](includes/support.md)]
