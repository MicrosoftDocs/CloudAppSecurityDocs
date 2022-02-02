---
title: Determine your app compliance posture
ms.date: 11/09/2021
ms.topic: conceptual
description: Determine your app compliance posture.
---

# Determine your app compliance posture

App governance allows you to quickly assess the compliance posture of Line of Business and third-party apps and their access to data in your Microsoft 365 tenant from the app governance Overview page in Microsoft 365 Defender.

:::image type="content" source="media\app-governance\mapg-cc-overview.png" alt-text="The app governance overview page in Microsoft 365 Defender." lightbox="media\app-governance\mapg-cc-overview.png":::

>[!Note]
> Your sign-in account must have one of [these roles](app-governance-get-started.md#administrator-roles) to view any app governance data.
>

From this page, you can see:

- For OAuth-enabled apps that use the Microsoft Graph API:

  - How many are in your tenant
  - How many might be overprivileged
  - How many are highly privileged

  From this information, you can determine the level of risk to your organization by overprivileged and highly privileged apps.

- For alerts:

  - How many active alerts your tenant has
  - How many are based on app governance detections (**Threat alerts**)
  - How many are based on app policies you have in place (**Policy alerts**)
  - The 10 latest alerts

  From this information, you can determine how quickly alerts are being generated and the relative number of detected and policy-based alerts.

- For data usage:

  - Total data accessed by apps in the tenant through Graph API over the current month and previous three calendar months. (Currently only includes Mail and File upload and download usage)
  - Data usage over the current month and previous three calendar months, broken down by resource type. (Currently only includes Mail and File upload and download usage)

  From this information, you can determine if there are anomalous spikes in data usage in your Microsoft 365 tenant.
