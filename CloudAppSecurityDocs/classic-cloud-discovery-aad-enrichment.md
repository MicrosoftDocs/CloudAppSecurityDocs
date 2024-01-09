---
title: Classic portal -  Enrich Cloud Discovery data with Microsoft Entra usernames
description: Classic portal -  This article provides information about how to enrich Defender for Cloud Apps Discovery data with Microsoft Entra usernames.
ms.date: 01/19/2023
ms.topic: how-to
ROBOTS: NOINDEX
---
# Classic portal: Enrich Cloud Discovery data with Microsoft Entra usernames

[!INCLUDE [Banner for top of topics](includes/classic-banner.md)]

Cloud Discovery data can now be enriched with Microsoft Entra username data. When you enable this feature, the username, received in discovery traffic logs, is matched and replaced by the Microsoft Entra username. Cloud Discovery enrichment enables the following features:

- You can investigate Shadow IT usage by Microsoft Entra user. The user will be shown with its UPN.
- You can correlate the Discovered cloud app use with the API collected activities.
- You can then create custom logs based on Microsoft Entra user groups. For example, a Shadow IT report for a specific Marketing department.

## Prerequisites

- Data source must provide username information
- [Microsoft 365 app connector](./connect-office-365.md) connected

## Enabling user data enrichment

1. Under the Settings cog, select **Settings**.

1. In the **Settings** page, under **Cloud Discovery**, select **User enrichment**.

1. In the **User enrichment** tab, select **Enrich discovered user identifiers with Microsoft Entra usernames**. This option enables Defender for Cloud Apps to use Microsoft Entra data to enrich usernames by default.

    ![Enrich Defender for Cloud Apps Discovery with Microsoft Entra usernames.](media/classic-discovery-enrichment.png)

## Next steps

> [!div class="nextstepaction"]
> [Control cloud apps with policies](control-cloud-apps-with-policies.md)

[!INCLUDE [Open support ticket](includes/classic-support.md)]
