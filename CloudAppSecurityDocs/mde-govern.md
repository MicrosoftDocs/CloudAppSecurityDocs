---
title: Govern discovered apps using Microsoft Defender for Endpoint
description: This article describes how to govern Microsoft Defender for Endpoint discovered apps.
ms.date: 02/16/2023
ms.topic: how-to
---

# Govern discovered apps using Microsoft Defender for Endpoint

[!INCLUDE [Banner for top of topics](includes/banner.md)]

The Microsoft Defender for Cloud Apps [integration with Microsoft Defender for Endpoint](mde-integration.md) provides a seamless Shadow IT visibility and control solution. Our integration enables Defender for Cloud Apps administrators to block access of end users to cloud apps, by natively integrating Defender for Cloud Apps app governance controls with Microsoft Defender for Endpoint's network protection. Alternatively, administrators can take a gentler approach of warning users when they access risky cloud apps.

## Prerequisites

- Microsoft Defender for Cloud Apps license
- Microsoft Defender for Endpoint [Plan 2 license](/microsoft-365/security/defender-endpoint/defender-endpoint-plan-1-2)
- Supported operating systems are listed below in the [Prerequisites for blocking apps](#prerequisites-for-blocking-apps-with-defender-for-endpoint) section
- Microsoft Defender Antivirus
  - [Real-time protection enabled](/microsoft-365/security/defender-endpoint/configure-real-time-protection-microsoft-defender-antivirus)
  - [Cloud-delivered protection enabled](/microsoft-365/security/defender-endpoint/enable-cloud-protection-microsoft-defender-antivirus)
  - [Network protection enabled and configured to block mode](/microsoft-365/security/defender-endpoint/enable-network-protection)

## Block access to unsanctioned cloud apps

Defender for Cloud Apps uses the built-in [**Unsanctioned**](governance-discovery.md#sanctioningunsanctioning-an-app) app tag to mark cloud apps as prohibited for use, available in both the Cloud Discovery and Cloud app catalog pages. By enabling the integration with Defender for Endpoint, you can seamlessly block access to unsanctioned apps with a single click in the Defender for Cloud Apps portal.

### How blocking works

Apps marked as **Unsanctioned** in Defender for Cloud Apps are automatically synced to Defender for Endpoint. More specifically, the domains used by these unsanctioned apps are propagated to endpoint devices to be blocked by Microsoft Defender Antivirus within the Network Protection SLA.

> [!NOTE]
> The time latency to block an app via Defender for Endpoint is up to three hours from the moment you mark the app as unsanctioned in Defender for Cloud Apps to the moment the app is blocked in the device. This is due to up to one hour of synchronization of Defender for Cloud Apps sanctioned/unsanctioned apps to Defender for Endpoint, and up to two hours to push the policy to the devices in order to block the app once the indicator was created in Defender for Endpoint.

### How to enable cloud app blocking with Defender for Endpoint

Use the following steps to enable access control for cloud apps:

1. In the Microsoft 365 Defender portal, select **Settings**. Then choose **Cloud Apps**. Under **Cloud Discovery**, select **Microsoft Defender for Endpoint**, and then select **Enforce app access**.

    ![Screenshot showing how to enable blocking with Defender for Endpoint.](media/mde-integration.png)

    > [!NOTE]
    > It can take up to 30 minutes for this setting to take effect.

1. In Microsoft 365 Defender, go to **Settings** > **Endpoints** > **Advanced features**, and then select **Custom network indicators**. For information about network indicators, see [Create indicators for IPs and URLs/domains](/microsoft-365/security/defender-endpoint/indicator-ip-domain).

    This allows you to leverage Microsoft Defender Antivirus network protection capabilities to block access to a predefined set of URLs using Defender for Cloud Apps, either by manually assigning [app tags](governance-discovery.md#sanctioningunsanctioning-an-app) to specific apps or automatically using an [app discovery policy](cloud-discovery-policies.md#creating-an-app-discovery-policy).

    ![Screenshot showing how to enable custom network indicators in Defender for Endpoint.](media/mde-custom-network-indicators.png)

### Prerequisites for blocking apps with Defender for Endpoint

1. One of the following licenses:

   - Defender for Cloud Apps (E5, AAD-P1m CAS-D) and Microsoft Defender for Endpoint [Plan 2](/microsoft-365/security/defender-endpoint/defender-endpoint-plan-1-2)
   - Microsoft 365 E5
1. Supported Operating Systems:
   - Windows: Windows 10 version 18.09 (RS5), OS Build 1776.3 or later.
   - Android: minimum version 8.0: For more information see: [Microsoft Defender for Endpoint on Android](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint-android#system-requirements)
   - iOS: minimum version 14.0: For more information see: [Microsoft Defender for Endpoint on iOS](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint-ios#prerequisites)
   - MacOS: minimum version 11: For more information see:  [Network protection for macOS](/microsoft-365/security/defender-endpoint/network-protection-macos)
   - [Linux system requirements](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint-linux): For more information see: [Network protection for Linux](/microsoft-365/security/defender-endpoint/network-protection-linux)

1. [Onboard Defender for Cloud Apps with Defender for Endpoint](mde-integration.md#how-to-integrate-microsoft-defender-for-endpoint-with-defender-for-cloud-apps).
1. Enable [cloud app blocking with Defender for Endpoint](mde-govern.md#how-to-enable-cloud-app-blocking-with-defender-for-endpoint).

### Blocking apps

To block usage for specific device groups, do the following steps:

1. In the Microsoft 365 Defender portal, select **Settings**. Then choose **Cloud Apps**.  Then under **Cloud discovery**, select **Apps tags** and go to the **Scoped profiles** tab.

1. Select **Add profile**. The profile sets the entities scoped for blocking/unblocking apps.

1. Provide a descriptive profile name and description.

1. Choose whether the profile should be an **Include** or **Exclude** profile.

    - **Include**: only the included set of entities will be affected by the access enforcement. For example, the profile *myContoso* has **Include** for device groups A and B. Blocking app Y with the profile *myContoso* will block app access only for groups A and B.

    - **Exclude**: The excluded set of entities won't be affected by the access enforcement. For example, the profile *myContoso* has **Exclude** for device groups A and B. Blocking app Y with the profile *myContoso* will block app access for the entire organization except for groups A and B.

1. Select the relevant device groups for the profile.

1. Select **Save**.

    ![Scoped profiles.](media/scoped-profiles.png)

To block an app, do the following steps:

1. In the Microsoft 365 Defender portal, under **Cloud Apps**, go to **Cloud Discovery** and go to the **Discovered apps** tab.

1. Select the app that should be blocked.

1. Tag the app as **Unsanctioned**.

    ![Unsanction an app.](media/unsanctioned-app.png)

1. To block all the devices in your organization, select **Save**. To block specific device groups in your organizations, select **Select a profile to include or exclude groups from being blocked**. Then choose the profile for which the app will be blocked, and select **Save**.

    ![Choose a profile to unsanction an app with.](media/choosing-unsanctioned-app-profile.png)

> [!NOTE]
>
> - The enforcement ability is based on Defender for Endpoint’s custom URL indicators.
> - Any organizational scoping that was set manually on indicators that were created by Defender for Cloud Apps before the release of this feature will be overridden by Defender for Cloud Apps. The required scoping should be set from the Defender for Cloud Apps experience using the scoped profiles experience.
> - To remove a selected scoping profile from an unsanctioned app, remove the unsanctioned tag and then tag the app again with the required scoped profile.
> - It can take up to two hours for app domains to propagate and be updated in the endpoint devices once they're marked with the relevant tag or/and scoping.

## Educate users when accessing risky apps

Admins have the option to warn users when they access risky apps. Rather than blocking users, they're prompted with a message providing a custom redirect link to a company page listing apps approved for use. The prompt provides options for users to bypass the warning and continue to the app. Admins are also able to monitor the number of users that bypass the warning message.

### Prerequisites for warning with Defender for Endpoint

Same as [Prerequisites for blocking apps with Defender for Endpoint](/defender-cloud-apps/mde-govern), but doesn't support mobile (Android and iOS).

### How does it work

Defender for Cloud Apps uses the built-in **Monitored** app tag to mark cloud apps as risky for use. The tag is available on both the Cloud Discovery and Cloud App Catalog pages. By enabling the integration with Defender for Endpoint, you can seamlessly warn users on access to monitored apps with a single click in the Defender for Cloud Apps portal.

Apps marked as **Monitored** are automatically synced to Defender for Endpoint's custom URL indicators, usually within a few minutes. More specifically, the domains used by monitored apps are propagated to endpoint devices to provide a warning message by Microsoft Defender Antivirus within the Network Protection SLA.

### Setting up the custom redirect URL for the warn message

Use the following steps to configure a custom URL pointing to a company web page where you can educate employees on why they've been warned and provide a list of alternative approved apps that adhere to your organization's risk acceptance or are already managed by the organization.

1. In the Microsoft 365 Defender portal, select **Settings**. Then choose **Cloud Apps**. Under **Cloud Discovery**, select **Microsoft Defender for Endpoint**.
1. In the **Notification URL** box, enter your URL.

    ![Screenshot showing how to configure notification URL.](media/mde-educate-config-notification-url.png)

### Setting up user bypass duration

Since users can bypass the warning message, you can use the following steps to configure the duration of the bypass apply. Once the duration has elapsed, users are prompted with the warning message the next time they access the monitored app.

1. In the Microsoft 365 Defender portal, select **Settings**. Then choose **Cloud Apps**. Under **Cloud Discovery**, select **Microsoft Defender for Endpoint**.
1. In the **Bypass duration** box, enter the duration (hours) of the user bypass.

    ![Screenshot showing how to configure bypass duration.](media/mde-educate-config-bypass-duration.png)

### Monitor applied app controls

Once controls are applied, you can monitor app usage patterns by the applied controls (access, block, bypass) using the following steps.

1. In the Microsoft 365 Defender portal, under **Cloud Apps**, go to **Cloud Discovery** and then go to the **Discovered apps** tab. Use the [filters](discovered-app-queries.md) to find the relevant monitored app.
1. Select the app's name to view applied app controls on the app's overview page.

## Next steps

> [!div class="nextstepaction"]
> [Investigate apps discovered by Microsoft Defender for Endpoint](mde-investigation.md)

> [!div class="nextstepaction"]
> [Control cloud apps with policies](control-cloud-apps-with-policies.md)

## Related videos

> [!div class="nextstepaction"]
> [Discover and block Shadow IT using Defender for Endpoint](https://www.youtube.com/watch?v=MsHkTOoqSQo)

> [!div class="nextstepaction"]
> [Shadow IT discovery beyond the corporate network](https://www.youtube.com/watch?v=f8hbvbY1Hnc)

[!INCLUDE [Open support ticket](includes/support.md)]
