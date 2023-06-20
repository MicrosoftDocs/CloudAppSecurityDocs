---
title: Classic portal -  Azure Active Directory Identity Protection integration
description: Classic portal -  This article provides information about how to leverage Identity Protection alerts in Defender for Cloud Apps for hybrid risk detection.
ms.date: 01/19/2023
ms.topic: how-to
ROBOTS: NOINDEX
---
# Classic portal: Azure Active Directory Identity Protection integration

[!INCLUDE [Banner for top of topics](includes/banner.md)]

Microsoft Defender for Cloud Apps integrates with Azure Active Directory Identity Protection to provide user entity behavioral analytics (UEBA) across a hybrid environment. For more information about the machine learning and behavioral analytics provided by Identity Protection, see [What is Identity Protection?](/azure/active-directory/identity-protection/overview-identity-protection).

## Prerequisites

- A Cloud App Security Admin account to enable integration between Identity Protection and Defender for Cloud Apps.

## Enable Identity Protection

> [!NOTE]
> The Identity Protection feature is enabled by default. However, if the feature is disabled, you can use these steps to enable it.

To enable Defender for Cloud Apps integration with Identity Protection:

1. In Defender for Cloud Apps, under the settings cog, select **Settings**.

    ![Settings menu.](media/classic-azip-system-settings.png)

1. Under **Threat Protection**, select **Azure AD Identity Protection**.

    ![enable azure advanced threat protection.](media/classic-aadip-integration.png)

1. Select **Enable Azure AD Identity Protection alert integration** and then select **Save**.

After enabling Identity Protection integration, you'll be able to see alerts for all the users in your organization.

## Disable Identity Protection

To disable Defender for Cloud Apps integration with Identity Protection:

1. In Defender for Cloud Apps, under the settings cog, select **Settings**.

1. Under **Threat Protection**, select **Azure AD Identity Protection**.

1. Clear **Enable Azure AD Identity Protection alert integration** and then select **Save**.

> [!NOTE]
>
> - When the integration is disabled, existing Identity Protection alerts are kept per Defender for Cloud Apps retention policies.
> - Since Defender for Cloud Apps only consumes interactive logins from Azure AD, some alerts may not show related activities. You can investigate such activities in the Azure AD portal.

## Configure Identity Protection Policies

The severity slider can fine-tune the Identity Protection policies to your organization's needs. In addition, the sensitivity slider allows you to control which alerts are ingested. This way, you can adapt the detection according to your coverage needs and your (SNR) targets.

The following policies are available:

|Policy|Description|Default state|Default Severity|
|---|---|---|---|
|Leaked Credentials|Shows leaked credentials alerts; user's valid credentials have been leaked|Enabled|Low - Receive all alerts|
|Risky sign-in|Aggregates multiple risky sign-in detections, sign-ins that the user didn't perform |Enabled|High - Receive only high severity alerts|

> [!NOTE]
> Defender for Cloud Apps does not send email notifications for Identity Protection alerts. However, you can configure their email notifications in the Identity Protection portal.

## Next steps

> [!div class="nextstepaction"]
> [Control cloud apps with policies](control-cloud-apps-with-policies.md)

[!INCLUDE [Open support ticket](includes/support.md)]
