---
title: App governance visibility and insights | Microsoft Defender for Cloud Apps
ms.date: 05/28/2023
ms.topic: conceptual
description: Learn about visibility and insights available for app governance with Microsoft Defender for Cloud Apps in Microsoft 365 Defender.
---

# App governance visibility and insights

Use app governance to gain visibility and meaningful insights on your app ecosystem, including:

- A list of the OAuth-enabled apps registered to Azure Active Directory in your tenant.
- A rich view on app activities, so that you can react or respond to them.

## Required administrator roles

For more information, see [App governance roles](app-governance-get-started.md#roles).

## Visibility and insight scope

With app governance, you can see:

- A dashboard of all insights.
- Data accessed and permissions used by single and all apps with workload and user level insights.
- App information and metadata, such as Graph API and legacy permissions, registration date, and certification.
- Publisher information and metadata, such as name and verification status.
- Usage of top resources (emails and files) across the tenant.
- Insights on:

  - High-privileged apps.
  - Overprivileged apps.
  - High-usage apps.
  - Top consented users whose data a specific app can access.
  - Priority accounts who have data that a specific app can access.
  - OAuth applications that have accessed sensitive or regular content on SharePoint, OneDrive, Exchange Online, or Teams.

- A cumulative view of users accessing apps.
- Alerts insights.
- Policy list insights.

You can also:

- Drill down to a single app (app page) with all its associated insights.
- Drill-down into top users by data, and priority accounts within a single app.
- Export a list of your apps plus respective insights

## Limitations to Microsoft 365 activity insights

To provide insights into how OAuth apps use Microsoft 365 data, including data with sensitivity labels, app governance tracks a set of commonly used Graph API operations. While these insights don’t cover all app activity on Microsoft 365, they can flag risky behavior associated with increased data usage and access to potentially sensitive data.

To get detailed information about app activity on Microsoft 365, search the Microsoft Purview audit log.

## Next step

[Get started with visibility and insights](app-governance-visibility-insights-get-started.md)