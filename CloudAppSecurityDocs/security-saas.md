---
title: Turn on and manage SaaS security posture management (SSPM) - Microsoft Defender for Cloud Apps
description: Learn how to get security configuration recommendations in Defender for Cloud Apps for your organization's SaaS applications.
ms.date: 01/18/2024
ms.topic: how-to
---

# Turn on and manage SaaS security posture management (SSPM)

Your SaaS application environments may be configured in a risky posture. Microsoft Defender for Cloud Apps provides you with risk security configuration assessments for your SaaS applications to help you prevent possible risks. These recommendations are shown via [Microsoft Secure Score](/microsoft-365/security/defender-endpoint/tvm-security-recommendation) once you have a connector to an application. For example:

![Screenshot of the SalesForce recommendations in Secure Score.](media/security-saas-sspm-in-secure-score-salesforce-filter.png)

## Prerequisites

- Your organization must have Microsoft Defender for Cloud Apps licenses.
- Your app must be connected to Defender for Cloud Apps. For more information, see:

    - [Connect apps to get visibility and control with Microsoft Defender for Cloud Apps](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md)
    - [User, app governance, and security configuration visibility](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md#user-app-governance-and-security-configuration-visibility)

## Turn on Secure Score recommendations

This procedure describes how to ensure that your connector is set to show data in Microsoft Secure Score for SaaS app security posture management.

1. In Microsoft Defender XDR, select **Settings** > **Cloud Apps** > **Connected apps** > **App Connectors**.

1. Use the filter to locate the app where you want to turn on Secure Score recommendations.

    > [!TIP]
    > If you have multiple instances of the same app and also have Defender for Cloud *Preview* features turned on, you'll have an instance drawer for each instance of the app. Multiple instances of the same app aren't supported without [Preview features turned on](/microsoft-365/security/defender/preview).
    >

1. Open the instance drawer and note whether Secure Score recommendations are turned on or off. For example, the following screenshot shows that Secure Score recommendations are turned on for **Okta Contoso EU** instance:

    :::image type="content" source="media/security-saas-secure-score-main-instance-drawer.png" alt-text="Screenshot of an instance where Secure Score recommendations are turned on." lightbox="media/security-saas-secure-score-main-instance-drawer.png":::

    If the instance is currently set to **Off**, select the **...** options menu and then select **Turn on Secure Score recommendations**. For example:

    :::image type="content" source="media/security-saas-choose-secure-score-main-instance.png" alt-text="Screenshot of the Turn on Secure Score recommendations option." lightbox="media/security-saas-choose-secure-score-main-instance.png":::

Security recommendations are shown automatically in [Microsoft Secure Score](/microsoft-365/security/defender/microsoft-secure-score). Recommendations are based on Microsoft benchmarks, and may take up to 24 hours to update.

If you have Preview features turned on and you have multiple instances of an app, adding an app instance is irreversible. Security recommendations for the selected instance are added to your Secure Score and impact your Secure Score rating.

In Microsoft Secure Score, filter the **Recommended actions** tab by product to view any recommended actions. If you have multiple instances of an app, you can select to filter recommendations from specific instances only. For example:

:::image type="content" source="media/secure-score-filter.png" alt-text="Screenshot of a Secure Score filter showing multiple instances of an app.":::

Select a recommendation and then select the **Implementation** tab in the details pane for a step-by-step remediation guide.

For more information, see [Assess your security posture with Microsoft Secure Score](/microsoft-365/security/defender/microsoft-secure-score-improvement-actions).

## Next steps

> [!div class="nextstepaction"]
> [Control cloud apps with policies](control-cloud-apps-with-policies.md)

[!INCLUDE [Open support ticket](includes/support.md)]
