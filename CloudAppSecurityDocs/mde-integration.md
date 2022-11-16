---
title: Integrate Microsoft Defender for Endpoint with Defender for Cloud Apps
description: This article describes how to integrate Microsoft Defender for Endpoint with Defender for Cloud Apps for enhanced visibility into Shadow IT and risk management.
ms.date: 11/09/2021
ms.topic: how-to
---
# Microsoft Defender for Endpoint integration with Microsoft Defender for Cloud Apps

[!INCLUDE [Banner for top of topics](includes/banner.md)]

Microsoft Defender for Cloud Apps integrates with Microsoft Defender for Endpoint natively. The integration simplifies roll out of Cloud Discovery, extends Cloud Discovery capabilities beyond your corporate network, and enables device-based investigation. [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint) is a security platform for intelligent protection, detection, investigation, and response. Defender for Endpoint protects endpoints from cyber threats, detects advanced attacks and data breaches, automates security incidents, and improves security posture.

Defender for Cloud Apps uses the traffic information collected by Defender for Endpoint about the cloud apps and services being accessed from IT-managed Windows 10 devices. The native integration enables you to run Cloud Discovery on any device in the corporate network, using public Wi-Fi, while roaming, and over remote access. It also enables device-based investigation.

The integration doesn't require any additional deployment and works out of the box. You don't need to route or mirror traffic from your endpoints or do complex integration steps. Logs from your endpoints sent to Defender for Cloud Apps provide user information for traffic activities. Defender for Endpoint network activity provides device context. Pairing device context with the username provides a full picture across your network enabling you to determine which user did which activity from which device.

Additionally, when you identify a risky user, you can check all the devices the user accessed to detect potential risks. If you identify a risky device, check all the users who used it to detect further potential risks.

Once traffic information is collected, you're ready to [deep dive into cloud app use](discovered-apps.md#deep-dive-into-discovered-apps) in your organization. Defender for Cloud Apps takes advantage of Defender for Endpoint Network Protection capabilities to block endpoint device access to cloud apps. You can block apps by [tagging them as **Unsanctioned**](governance-discovery.md#BKMK_SanctionApp) in the portal. Based on the comprehensive usage and risk assessment of each unsanctioned app, the app's domains are used to create [domain indicators](/microsoft-365/security/defender-endpoint/manage-indicators) in the Defender for Endpoint portal. Microsoft Defender Antivirus, running on endpoint devices, uses the domain indicators to block access to these apps.

> [!NOTE]
> Want to experience Microsoft Defender for Endpoint? [Sign up for a free trial](https://www.microsoft.com/windows/business?ocid=docs-wdatp-assignaccess-abovefoldlink).

## Prerequisites

- Microsoft Defender for Cloud Apps license
- Microsoft Defender for Endpoint [Plan 2 license](/microsoft-365/security/defender-endpoint/defender-endpoint-plan-1-2)
- Windows 10 version 1709 (OS Build 16299.1085 with KB4493441), Windows 10 version 1803 (OS Build 17134.704 with KB4493464), Windows 10 version 1809 (OS Build 17763.379 with KB4489899) or later Windows 10 and Windows 11 versions
- Microsoft Defender Antivirus
  - [Real-time protection enabled](/microsoft-365/security/defender-endpoint/configure-real-time-protection-microsoft-defender-antivirus)
  - [Cloud-delivered protection enabled](/microsoft-365/security/defender-endpoint/enable-cloud-protection-microsoft-defender-antivirus)
  - [Network protection enabled and configured to block mode](/microsoft-365/security/defender-endpoint/enable-network-protection)

> [!NOTE]
The ability to perform Cloud Disocvery when Defender for Endpoint is deployed behind a proxy is in public preview. To do so, please make sure Defender for Endpoint is in **Active** mode (see here how to check it: [Microsoft Defender Antivirus in Windows | Microsoft Docs](https://learn.microsoft.com/en-us/microsoft-365/security/defender-endpoint/microsoft-defender-antivirus-windows?view=o365-worldwide#comparing-active-mode-passive-mode-and-disabled-mode)).

## How it works

On its own, Defender for Cloud Apps collects logs from your endpoints using either [logs you upload](create-snapshot-cloud-discovery-reports.md) or by [configuring automatic log upload](discovery-docker.md). Native integration enables you to take advantage of the logs Defender for Endpoint's agent creates when it runs on Windows and monitors network transactions. Use this information for Shadow IT discovery across the Windows devices on your network.

To enable you to perform Cloud Discovery across other platforms, it's best to use both the Defender for Cloud Apps [log collector](discovery-docker.md), along with Defender for Endpoint integration to monitor your Windows 10 and Windows 11 devices.

[Watch our videos](#related-videos) showing the benefits of using Defender for Endpoint with Defender for Cloud Apps.

<a name="how-to-integrate-microsoft-defender-for-endpoint-with-cloud-app-security"></a>

## How to integrate Microsoft Defender for Endpoint with Defender for Cloud Apps

To enable Defender for Endpoint integration with Defender for Cloud Apps:

1. In [Microsoft 365 Defender](https://security.microsoft.com), from the navigation pane, select **Settings**.
1. Select **Endpoints**.
1. Under **General**, select **Advanced features**.
1. Toggle the **Microsoft Defender for Cloud Apps** to **On**.
1. Select **Apply**.

    >[!NOTE]
    > It takes up to two hours after you enable the integration for the data to show up in Defender for Cloud Apps.
    >

    ![Defender for Endpoint settings.](media/mde-settings.png)

To configure the severity for alerts sent to Microsoft Defender for Endpoint:

1. In Defender for Cloud Apps, select the **Settings** icon, and then select **Microsoft Defender for Endpoint**.
1. Under **Alerts**, select the global severity level for alerts.
1. Select **Save**.

    ![Defender for Endpoint alert settings.](media/mde-alert-severity-settings.png)

## Next steps

> [!div class="nextstepaction"]
> [Investigate apps discovered by Microsoft Defender for Endpoint](mde-investigation.md)

> [!div class="nextstepaction"]
> [Govern apps discovered by Microsoft Defender for Endpoint](mde-govern.md)

## Related videos

> [!div class="nextstepaction"]
> [Discover and block Shadow IT using Defender for Endpoint](https://www.youtube.com/watch?v=MsHkTOoqSQo)

> [!div class="nextstepaction"]
> [Shadow IT discovery beyond the corporate network](https://www.youtube.com/watch?v=f8hbvbY1Hnc)

[!INCLUDE [Open support ticket](includes/support.md)]
