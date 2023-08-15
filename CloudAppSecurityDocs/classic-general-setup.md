---
title: Classic portal -  Basic setup
description: Classic portal -  This article explains how to provide information about your organization in Defender for Cloud Apps.
ms.date: 01/19/2023
ms.topic: how-to
ROBOTS: NOINDEX
---
# Classic portal: Basic setup for Defender for Cloud Apps

[!INCLUDE [Banner for top of topics](includes/banner.md)]

The following procedure gives you instructions for customizing the Microsoft Defender for Cloud Apps portal.

## Prerequisites

For portal access, it's necessary to add the following IP addresses to your Firewall's allow list to provide access for the Defender for Cloud Apps portal:

* 104.42.231.28

For US Government GCC High customers, it's also necessary to add the following IP addresses to your Firewall's allow list to provide access for the Defender for Cloud Apps GCC High portal:

* 52.227.143.223
* 13.72.19.4

> [!NOTE]
> To get updates when URLs and IP addresses are changed, subscribe to the RSS as explained in: [Microsoft 365 URLs and IP address ranges](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2).

## Set up the portal

1. In the [Defender for Cloud Apps portal](https://portal.cloudappsecurity.com/), in the menu bar, select the settings cog ![settings icon.](media/classic-settings-icon.png "settings icon") and select **Settings** to configure your organization's details.

1. Under **Organization details**, it's important that you provide an **Organization display name** for your organization. It's displayed on emails and web pages sent from the system.

1. Provide an **Environment name** (tenant). This information is especially important if you manage more than one tenant.

1. It's also possible to provide a **Logo** that is displayed in email notifications and web pages sent from the system. The logo should be a png file with a maximum size of 150 x 50 pixels on a transparent background.

1. Make sure you add a list of your **Managed domains** to identify internal users. Adding managed domains is a crucial step. Defender for Cloud Apps uses the managed domains to determine which users are internal, external, and where files should and shouldn't be shared. This information is used for reports and alerts.

    * Users in domains that aren't configured as internal are marked as external. External users aren't scanned for activities or files.

1. Under **Auto sign out**, specify the amount of time a session can remain inactive before the session is automatically signed out. Note that Defender for Cloud Apps also uses Azure Active Directory to determine the user's directory level inactivity timeout setting. If a user is configured in Azure Active Directory to never sign out when inactive, the same setting will apply in Defender for Cloud Apps as well.

1. If you're integrating with Microsoft Purview Information Protection, see [Microsoft Purview Information Protection Integration](azip-integration.md) for information.

    * To work with Microsoft Purview Information Protection integration, you must enable the [App connector for Microsoft 365](./connect-office-365.md).

1. If you're integrating with Microsoft Defender for Identity integration, see [Microsoft Defender for Identity Integration](mdi-integration.md) for information.

1. If at any point you want to back up your portal settings, this screen enables you to do that. Select **Export portal settings** to create a json file of all your portal settings, including policy rules, user groups, and IP address ranges.

> [!NOTE]
> If you use ExpressRoute, Defender for Cloud Apps is deployed in Azure and fully integrated with [ExpressRoute](/azure/expressroute/expressroute-introduction). All interactions with the Defender for Cloud Apps apps and traffic sent to Defender for Cloud Apps, including upload of discovery logs, is routed via ExpressRoute for improved latency, performance, and security.
>
> For more information about Microsoft Peering, see [ExpressRoute circuits and routing domains](/azure/expressroute/expressroute-circuit-peerings).

## Next steps

> [!div class="nextstepaction"]
> [Set up Cloud Discovery](set-up-cloud-discovery.md)

[!INCLUDE [Open support ticket](includes/support.md)]
