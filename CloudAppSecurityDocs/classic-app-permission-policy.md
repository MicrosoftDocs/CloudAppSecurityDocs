---
title: Classic portal -  Create policies to control OAuth apps 
description: Classic portal -  This article provides instructions for creating and working with app permission policies in Microsoft Defender for Cloud Apps.
ms.date: 01/19/2023
ms.topic: how-to
ROBOTS: NOINDEX
---
# Classic portal: Create policies to control OAuth apps

[!INCLUDE [Banner for top of topics](includes/banner.md)]

In addition to the [existing investigation of OAuth apps](manage-app-permissions.md) connected to your environment, you can set permission policies so that you get automated notifications when an OAuth app meets certain criteria. For example, you can automatically be alerted when there are apps that require a high permission level and were authorized by more than 50 users.

OAuth app policies enable you to investigate which permissions each app requested and which users authorized them for Microsoft 365, Google Workspace, and Salesforce. You're also able to mark these permissions as approved or banned. Marking them as banned will disable the correlating Enterprise Application.

## Create a new OAuth app policy

There are two ways to create a new OAuth app policy. The first way is under **Investigate** and the second is under **Control**.

To create a new OAuth app policy:

1. Under **Investigate**, select **OAuth apps**.

1. Filter the apps according to your needs. For example, you can view all apps that request **Permission** to **Modify calendars in your mailbox**.
1. Select the **New policy from search** button.
    ![New policy from search.](media/classic-app-permissions-filter.png)
1. You can use the **Community use** filter to get information on whether allowing permission to this app is common, uncommon, or rare. This filter can be helpful if you have an app that's rare and requests permission that has a high severity level or requests permission from many users.
1. You can set the policy based on the group memberships of the users who authorized the apps. For example, an admin can decide to set a policy that revokes uncommon apps if they ask for high permissions, only if the user who authorized the permissions is a member of the Administrators group.

Alternatively, you can also create the policy by selecting **Control** followed by **Policies**. Then select **Create policy** followed by **OAuth app policy**.

   ![new OAuth app policy.](media/classic-app-permissions-policy.png)

> [!NOTE]
> OAuth apps policies will trigger alerts only on policies that were authorized by users in the tenant.

## OAuth app anomaly detection policies

In addition to OAuth app policies you can create, there are the following out-of-the-box anomaly detection policies that profile metadata of OAuth apps to identify ones that are potentially malicious:

| Policy name | Policy description |
| --- | --- |
| Misleading OAuth app name | Scans OAuth apps connected to your environment and triggers an alert when an app with a misleading name is detected. Misleading names, such as foreign letters that resemble Latin letters, could indicate an attempt to disguise a malicious app as a known and trusted app. |
| Misleading publisher name for an OAuth app | Scans OAuth apps connected to your environment and triggers an alert when an app with a misleading publisher name is detected. Misleading publisher names, such as foreign letters that resemble Latin letters, could indicate an attempt to disguise a malicious app as an app coming from a known and trusted publisher. |
| Malicious OAuth app consent | Scans OAuth apps connected to your environment and triggers an alert when a potentially malicious app is authorized. Malicious OAuth apps may be used as part of a phishing campaign in an attempt to compromise users. This detection leverages Microsoft security research and threat intelligence expertise to identify malicious apps. |
| Suspicious OAuth app file download activities | See [Anomaly detection policies](anomaly-detection-policy.md#suspicious-oauth-app-file-download-activities) |

> [!NOTE]
>
> - Anomaly detection policies are only available for OAuth apps that are authorized in your Azure Active Directory.
> - The severity of OAuth app anomaly detection policies cannot be modified.

## Next steps

> [!div class="nextstepaction"]
> [Data protection policies](data-protection-policies.md)

[!INCLUDE [Open support ticket](includes/support.md)]
