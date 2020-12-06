---
title: Integrate Microsoft Defender for Endpoint with Cloud App Security
description: This article describes how to integrate Microsoft Defender for Endpoint with Cloud App Security for enhanced visibility into Shadow IT and risk management.
ms.date: 10/29/2020
ms.topic: how-to
---
# Microsoft Defender for Endpoint integration with Microsoft Cloud App Security

[!INCLUDE [Banner for top of topics](includes/banner.md)]

Microsoft Cloud App Security's integration with Microsoft Defender for Endpoint provides a seamless Shadow IT visibility and control solution. We already allow Cloud App Security administrators to block access of end users to cloud apps, by natively integrating Cloud App Security app governance controls with Microsoft Defender for Endpoints' network protection.

## Block access to unsanctioned cloud apps

Cloud App Security uses the built-in [**Unsanctioned**](governance-discovery.md#BKMK_SanctionApp) app tag to mark cloud apps as prohibited for use, available in both the Cloud Discovery and Cloud app catalog pages. By enabling the integration with Defender for Endpoint, you can seamlessly block access to unsanctioned apps with a single click in the Cloud App Security portal.

### How blocking works

Apps marked as **Unsanctioned** in Cloud App Security are automatically synced to Defender for Endpoint, usually within a few minutes. More specifically, the domains used by these unsanctioned apps are propagated to endpoint devices to be blocked by Microsoft Defender Antivirus within the Network Protection SLA.

### How to enable cloud app blocking with Defender for Endpoint

Use the following steps to enable access control for cloud apps:

1. In Cloud App Security, under the settings cog, select **Settings**, under **Cloud Discovery** select **Microsoft Defender for Endpoint**, and then select **Block unsanctioned apps**.

    ![Screenshot showing how to enable blocking with Defender for Endpoint](media/mde-integration.png)

1. In Microsoft Defender Security Center, go to **Settings** > **Advanced features**, and then select **Custom network indicators**. For information about network indicators, see [Create indicators for IPs and URLs/domains](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators#create-indicators-for-ips-and-urlsdomains-preview).

    This allows you to leverage Microsoft Defender Antivirus network protection capabilities to block access to a predefined set of URLs using Cloud App Security, either by manually assigning [app tags](governance-discovery.md#BKMK_SanctionApp) to specific apps or automatically using an [app discovery policy](cloud-discovery-policies.md#creating-an-app-discovery-policy).

    ![Screenshot showing how to enable custom network indicators in Defender for Endpoint](media/mde-custom-network-indicators.png)

## Warn and educate on access to monitored apps

Monitoring apps and warning users on access allow Cloud App Security administrators to take a "softer" action on end users access to risky cloud apps. Admins now have the option to enable a warning prompt to be displayed to the user when attempting to access and provide a redirect URL to a company web page pointing to the allowed apps for use, rather than fully blocking them – also, allowing the user to bypass the warning and continue using the app. The Admin, would then be able to monitor how many users bypassed the warning message.

### Warn on access to monitored cloud apps

Cloud App Security uses the built-in Monitored app tag to mark cloud apps as risky for use, available in both the Cloud Discovery and Cloud app catalog pages. By enabling the integration with Defender for Endpoint, you can seamlessly warn on access to unsanctioned apps with a single click in the Cloud App Security portal.

### How warning works

Apps marked as Monitored in Cloud App Security are automatically synced to Defender for Endpoint's custom url indicators, usually within a few minutes. More specifically, the domains used by these monitored apps are propagated to endpoint devices to provide a warning message by Microsoft Defender Antivirus within the Network Protection SLA.

{Link to Defender's docs explaining how Warn indicators behave on the endpoint – Edge Vs Other – toast message}

Pre-requisites
{Same as for Block}

### Setting up custom redirect URL for the warn message

An Admin can set a custom URL pointing to a company web page where he could potentially educate employees on why they have been warned and what other alternative apps they could use which fall into the organization's risk acceptance or are already managed by the organization.

- Go to Defender for Endpoints settings
- Enter your company's URL

### Setting up user bypass duration

As users are able to bypass the warning message, Admin can set for how long does that bypass apply until users are prompted with the warning message once again upon accessing the monitored app.

- Go to Defender for Endpoints settings
- Enter the bypass duration (hours)

### Monitor app access / block / bypass

Once discovering and applying controls, an Admin can monitor usage patterns based on each of the applied controls.

## Next steps

> [!div class="nextstepaction"]
> [Control cloud apps with policies](control-cloud-apps-with-policies.md)

## Related videos

> [!div class="nextstepaction"]
> [Discover and block Shadow IT using Defender for Endpoint](https://www.youtube.com/watch?v=MsHkTOoqSQo)

> [!div class="nextstepaction"]
> [Shadow IT discovery beyond the corporate network](https://www.youtube.com/watch?v=f8hbvbY1Hnc)

[!INCLUDE [Open support ticket](includes/support.md)]
