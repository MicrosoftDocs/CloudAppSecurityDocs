---
title: Learn about visibility and insights
ms.date: 01/29/2023
ms.topic: conceptual
description: Learn about visibility and insights.
---

# Learn about visibility and insights

With app governance, you can quickly gain visibility and meaningful insights on your app ecosystem. You start from the app governance dashboard that provides a high-level overview of the alerts and apps in your tenant that require administrator attention.

With app governance visibility and insights, you can see:

- A list of the OAuth-enabled apps registered to Azure Active Directory in your tenant.
- A rich view on app activities so that you can react or respond to them.

See [administrator roles](app-governance-get-started.md#roles) for an overview of required administrator roles for visibility and insights.

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

[Get started with application insights.](app-governance-visibility-insights-get-started.md)
