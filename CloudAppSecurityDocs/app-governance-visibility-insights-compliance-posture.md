---
title: Determine your app compliance posture
ms.date: 01/29/2023
ms.topic: conceptual
description: Determine your app compliance posture.
---

# Determine your app compliance posture

From this page, you can see:

For OAuth-enabled apps that use the Microsoft Graph API:

- How many are in your tenant
- How many might be overprivileged
- How many are highly privileged

From this information, you can determine the level of risk to your organization by overprivileged and highly privileged apps.

For incidents:

- How many active incidents your tenant has
- How many are based on app governance detections (**Threat incidents**)
- How many are based on app policies you have in place (**Policy incidents**)
- The 10 latest incidents

From this information, you can determine how quickly incidents are being generated and the relative number of detected and policy-based incidents.

> [!div class="mx-imgBorder"]
>![Relative number of detected and policy-based incidents.](incidents-summary1.png)
>
> [!div class="mx-imgBorder"]
>![top alerts.](media/app-governance-visibility-insights-compliance-posture/top-alerts.png)

For data usage:

- Total data accessed by apps in the tenant through Graph API over the current month and previous three calendar months. (Currently includes emails, files, and chat and channel messages read and written by apps that access Microsoft 365 using Graph API)
- Data usage over the current month and previous three calendar months, broken down by resource type. (Currently includes emails, files, and chat and channel messages read and written by apps that access Microsoft 365 using Graph API)

> [!div class="mx-imgBorder"]
>![Total data accessed by apps.](media/app-governance-visibility-insights-compliance-posture/data-usage-chart.png)

For apps that access data on Microsoft 365:

- The number of apps that have accessed data on SharePoint, OneDrive, Exchange Online, or Teams in the last 30 days

> [!div class="mx-imgBorder"]
>![Apps that have accessed data on SharePoint, OneDrive, Exchange Online, or Teams in the last 30 days.](media/app-governance-visibility-insights-compliance-posture/apps-accessed-m365-services-chart.png)

For sensitivity labels accessed:

- The number apps that have accessed content with sensitivity labels on SharePoint, OneDrive, Exchange Online or Teams in the last 30 days

> [!div class="mx-imgBorder"]
>![number apps that have accessed content with sensitivity labels.](sensitive-data-accessed-chart1.png)
