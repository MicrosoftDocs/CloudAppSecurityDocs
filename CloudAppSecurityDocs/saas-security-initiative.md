---
title: SaaS security initiative
description: Learn how to use the "SaaS security initiative" in Microsoft XDR
ms.topic: how-to
ms.date: 10/31/2024
---
## SaaS Security Initiative 

The SaaS Security Initiative provides a centralized place for SaaS security best practices, enabling organizations to manage and prioritize security recommendations effectively. By focusing on the most impactful metrics, organizations can enhance their SaaS security posture efficiently.
![image of the SaaS security initiative home page](https://github.com/user-attachments/assets/b4d09dae-eda4-4c72-a665-cafe3f474e86)


### What is the SaaS Security Initiative?

The SaaS Security Initiative serves as the main hub for SaaS Security Posture Management (SSPM), consolidating best-practice recommendations into 12 measurable metrics. These metrics facilitate the management and prioritization of a large number of security recommendations.

### Prerequisites

- Your organization must have Microsoft Defender for Cloud Apps licenses.
- Your app must be connected to Defender for Cloud Apps.
- For more information, see:

    - [Connect apps to get visibility and control with Microsoft Defender for Cloud Apps](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md)
    - [Learn which of the apps connectors provides security recommendations ](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md#user-app-governance-and-security-configuration-visibility)

### Operational Guidelines
To initiate the process, navigate to the **Exposure Management** blade and select **Initiatives**. Click on the **SaaS Security** initiative and then select **Open Initiative Page**.

On this page, you will find 12 measurable metrics that categorize hundreds of best practice recommendations. 

It is recommended to prioritize metrics with the highest **Impact on Initiative Score**, which is a composite measure that considers both the **Weight** of each recommendation and the percentage of **Non-Compliant** recommendations. To effectively monitor progress, it is advisable to set a **target score** for your organization’s security posture. This target will serve as a benchmark for improvement and help track advancements over time.

For instance, to gain visibility into all best practice recommendations pertaining to privileged access within SaaS applications, select the metric labeled **Missing Best Practices to Secure Privileged Access in SaaS Apps**.

Once selected, you can click on any of the **Non-Compliant** recommendations to access the associated remediation steps.

### Additional Information

- Each metric includes a list of associated app connectors, encouraging organizations to enable additional connectors for enhanced visibility. If you are interested in recommendations for specific applications, navigate to the **Security Recommendations** tab and filter by the relevant application.
- To learn more about inactives visit [here](https://learn.microsoft.com/en-us/security-exposure-management/initiatives)


