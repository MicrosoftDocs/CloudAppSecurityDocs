---
title: Secure apps with app hygiene features
ms.date: 02/28/2023
ms.topic: how-to
description: Learn how to secure apps with app hygiene features
---

# Secure apps with app hygiene features

Have you ever wanted to see the apps that your organization owns but isn't using, but didn't know how to? Or clean up unused or expiring credentials more easily? Azure AD recently released recommendations to help you identify such apps. Now, App Governance provides the app hygiene feature suite which includes controls and insights on unused apps, unused credentials, and expiring credentials. These features enable automatic control over these apps and provide additional app behavior context to help you determine the risk these apps pose in your environment.

Watch this video for a brief explanation of these features:

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWWYEm]

## App insights

App governance allows you to sort and filter on app last used date, credential unused since, and credential expiration date. You can export this custom list for easy reporting and triage across your organization.

:::image type="content" source="media/app-governance/custom-list.png" alt-text="Custom list of apps.":::

Data legend:

- Due to data history or app scope constraints, some apps will show *Over 30 days ago* in the **Last used** or **Credential unused since** column. These apps haven't signed in in the last 30 days, but we don't currently have an exact last sign-in date.
- Apps which don't have a last sign-in date or credential expiration date available will have *Not available* in the respective column.
- Apps with *No credentials* in the **Credential unused since** or **Credential expiration** column don’t have any credentials assigned to the app.

## App hygiene policies

App Governance provides out-of-the-box policies that alert on unused apps, unused credentials, and expiring credentials which automatically alert you on areas to improve app hygiene. 

You can also customize your own policy using the unused app condition. For example, you could create a policy to automatically disable any app that hasn’t been used in the past 90 days, has high privilege permissions, and can access [priority account information](/microsoft-365/admin/setup/priority-accounts). Like all App Governance alerts, these alerts will be aggregated into incidents in your Microsoft 365 Defender alerts queue and flow to advanced hunting and Sentinel.

:::image type="content" source="media/app-governance/edit-policy-conditions.png" alt-text="Edit policy conditions.":::

By staying on top of unused apps and expiring or unused app credentials and cleaning up your SaaS app inventory, you aren't only optimizing app usage and SaaS spend, but also, more importantly, keeping your app attack surface in check.

## Known issues

For the first month after launch, app hygiene data may be missing for multi-tenant apps that are owned by another tenant.

## Next steps

[Determine your overall app compliance posture](app-governance-visibility-insights-compliance-posture.md).
