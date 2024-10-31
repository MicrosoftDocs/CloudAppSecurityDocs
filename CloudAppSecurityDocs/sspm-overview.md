---
title: SaaS security posture management(SSPM) - overview 
description: Learn what is SaaS security posture management(SSPM) in Microsoft defender for cloud apps
ms.topic: how-to
ms.date: 10/31/2024
---

# SaaS security posture management(SSPM) - overview 

One of Microsoft Defender for Cloud Apps’ core pillars is SaaS Security Posture Management (SSPM), which offers detailed visibility into the security state of your SaaS applications and provides actionable guidance to help you strengthen your security posture efficiently. Your SaaS application environments may be configured in a risky posture, and Defender for Cloud Apps provides risk-based security configuration assessments to help you identify and mitigate potential risks. These recommendations are shown via [Microsoft Security Exposure Management](https://learn.microsoft.com/security-exposure-management/microsoft-security-exposure-management) in the SaaS security initiative once you have a connector to an application. For example:


![Screenshot of the SaaS security initiative](https://github.com/user-attachments/assets/f7efaac0-234f-4994-802b-7b29bb545e7c)

## How to manage your organization SaaS security posture
To effectively manage your organization’s SaaS security posture, we recommend beginning with the SaaS Security initiative in Microsoft Defender XDR. This initiative consolidates best practices and measurable metrics specifically for securing SaaS applications, allowing you to prioritize and address the most impactful recommendations for SaaS environments. For more information, see:

- [SaaS security initiative](https://learn.microsoft.com/en-us/defender-cloud-apps/saas-security-initiative.md)

In addition you can find a variety of SSPM recommendations under different initiatives. Key initiatives include:

- SaaS Security
- CIS M365 Foundations Benchmark
- Ransomware Protection
- Identity Security
- Business Email Compromise - Financial fraud
- Zero Trust (Foundational)
- ...


## Prerequisites

- Your organization must have Microsoft Defender for Cloud Apps licenses.
- Your app must be connected to Defender for Cloud Apps. For more information, see:

    - [Connect apps to get visibility and control with Microsoft Defender for Cloud Apps](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md)
    - [Learn which of the apps connectors provides security recommendations ](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md#user-app-governance-and-security-configuration-visibility)

## Turn on SSPM recommendations

This procedure describes how to ensure that your connector is set to show data in Microsoft Security Exposure Management for SaaS app security posture management.

1. In Microsoft Defender XDR, select **Settings** > **Cloud Apps** > **Connected apps** > **App Connectors**.

1. Use the filter to locate the app where you want to turn on SSPM recommendations.

1. Open the instance drawer and note whether 'Secure score' or 'Exposure management' recommendations are turned on or off. For example, the following screenshot shows that 'Secure score' or 'Exposure management' recommendations are turned on for **Okta Contoso EU** instance:
![Screenshot of an instance where Secure Score recommendations are turned on.](https://github.com/user-attachments/assets/196fcbe4-8b9a-41b9-b33e-4e1a65efd0b5)

    If the instance is currently set to **Off**, select the **...** options menu and then select **Turn on 'Secure Score' or 'Exposure management' recommendations**. For example:
![Screenshot of the Turn on Secure Score or 'Exposure management' recommendations option.](https://github.com/user-attachments/assets/421ddd6b-2504-4e61-8704-4dfc846c1959)

    > [!NOTE]
    > In case you have multiple instances of the same app, you can send security recommendations for each instance separately.
Security recommendations for the selected instance are added to Microsoft Security Exposure Management in addition to the current recommendations.
    >

Security recommendations are shown automatically in [Microsoft Security Exposure Management](/microsoft-365/security/defender/microsoft-secure-score). Recommendations are based on Microsoft benchmarks, and may take up to 24 hours to update.

In SaaS security initiative, in the **Security recommendations** filter by product to view any recommended actions. If you have multiple instances of an app, you can select to filter recommendations from specific instances only. For example:
![Screenshot of a SaaS initiative filter showing multiple instances of an app.](https://github.com/user-attachments/assets/28149da7-de73-4b20-bd83-da3a8cd6cb1b)



## Next steps

> [!div class="nextstepaction"]
> [Control cloud apps with policies](control-cloud-apps-with-policies.md)

[!INCLUDE [Open support ticket](includes/support.md)]
