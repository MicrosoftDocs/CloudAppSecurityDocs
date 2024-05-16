---
title: Classic portal -  Integrate with Microsoft Defender for Identity 
description: Classic portal -  This article provides information about how to leverage Microsoft Defender for Identity insights in Defender for Cloud Apps for hybrid risk detection.
ms.date: 01/19/2023
ms.topic: how-to
ROBOTS: NOINDEX
---
# Classic portal: Integrate Microsoft Defender for Identity with Microsoft Defender for Cloud Apps

[!INCLUDE [Banner for top of topics](includes/classic-banner.md)]

Microsoft Defender for Cloud Apps integrates with Microsoft Defender for Identity to provide user entity behavioral analytics (UEBA) across a hybrid environment - both cloud app and on-premises, for more information, see [Tutorial: Investigate risky users](tutorial-ueba.md). For more information about the machine learning and behavioral analytics provided by Defender for Identity, see [What is Defender for Identity?](/defender-for-identity/what-is)

> [!NOTE]
>
> - Defender for Cloud Apps does not send email notifications for Defender for Identity alerts. However, you can configure email notifications for them in the Defender for Identity portal.
>
> - Defender for Identity Alerts will be reflected in the Defender for Cloud Apps portal, but the alert's status won't be updated from external sources.

## Prerequisites

For complete user investigation across a hybrid environment, you must have:

- A valid license for Microsoft Defender for Identity connected to your Active Directory instance
- You must be a Microsoft Entra global admin to enable integration between Defender for Identity and Defender for Cloud Apps

> [!NOTE]
>
> - If you don't have a subscription for Microsoft Defender for Cloud Apps, you can still use Defender for Cloud Apps to get Defender for Identity insights.
> - Defender for Identity administrators may require new permissions to access Defender for Cloud Apps. To learn how to assign permissions to Defender for Cloud Apps, see [Manage admin access](manage-admins.md).

## Enable Defender for Identity

To enable Defender for Cloud Apps integration with Defender for Identity:

1. In Defender for Cloud Apps, under the settings cog, select **Settings**.

    ![Settings menu.](media/classic-azip-system-settings.png)

1. Under **Threat Protection**, select **Microsoft Defender for Identity**.

    ![Enable Microsoft Defender for Identity protection.](media/classic-mdi-integration.png)

1. Select **Enable Microsoft Defender for Identity data integration** and then select **Save**.

> [!NOTE]
> It may take up to 12 hours until the integration takes effect.

After enabling Defender for Identity integration, you'll be able to see on-premises activities for all the users in your organization. You will also get advanced insights on your users that combine alerts and suspicious activities across your cloud and on-premises environments. Additionally, alerts from Defender for Identity will appear on the Defender for Cloud Apps policies page. For a list of Defender for Identity alerts, see [Security alerts](/defender-for-identity/alerts-overview). To configure these alerts, see [Configure Defender for Identity detection exclusions](/defender-for-identity/exclusions).

You should also use the **Defender for Identity configuration** links to configure Defender for Identity settings that are relevant to Defender for Cloud Apps. Use the following information to learn more about these settings:

- [Configure Microsoft Defender for Identity sensor settings](/defender-for-identity/configure-sensor-settings)
- [Configure directory service accounts](/defender-for-identity/directory-service-accounts)
- [Defender for Identity VPN integration](/defender-for-identity/vpn-integration)
- [Microsoft Defender for Identity sensor health alerts](/defender-for-identity/health-alerts)

## Disable Defender for Identity

To disable Defender for Cloud Apps integration with Defender for Identity:

1. In Defender for Cloud Apps, under the settings cog, select **Settings**.

1. Under **Threat Protection**, select **Microsoft Defender for Identity**.

1. Clear **Enable Microsoft Defender for Identity data integration** and then select **Save**.

> [!NOTE]
> When the integration is disabled, existing Defender for Identity data is kept in accordance with Defender for Cloud Apps retention policies but the Identity Security Posture assessments section is removed.

## Known issues

### Missing SIEM alert updates

This issue affects alerts that are triggered more than once. The first instance of the alert is sent to the SIEM, but subsequent triggers of the same alert are not sent.

#### Resolution

No known resolution.

## Next steps

> [!div class="nextstepaction"]
> [Control cloud apps with policies](control-cloud-apps-with-policies.md)

[!INCLUDE [Open support ticket](includes/classic-support.md)]
