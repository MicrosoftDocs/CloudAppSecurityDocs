---
title: Classic portal -  Enrich Cloud Discovery data with Azure AD usernames
description: Classic portal -  This article provides information about how to enrich Defender for Cloud Apps Discovery data with Azure AD usernames.
ms.date: 01/19/2023
ms.topic: how-to
ROBOTS: NOINDEX
---
# Classic portal: Enrich Cloud Discovery data with Azure AD usernames

[!INCLUDE [Banner for top of topics](includes/banner.md)]

Cloud Discovery data can now be enriched with Azure Active Directory username data. When you enable this feature, the username, received in discovery traffic logs, is matched and replaced by the Azure AD username. Cloud Discovery enrichment enables the following features:

- You can investigate Shadow IT usage by Azure Active Directory user. The user will be shown with its UPN.
- You can correlate the Discovered cloud app use with the API collected activities.
- You can then create custom logs based on Azure AD user groups. For example, a Shadow IT report for a specific Marketing department.

## Prerequisites

- Data source must provide username information
- [Microsoft 365 app connector](./connect-office-365.md) connected

## Enabling user data enrichment

1. Under the Settings cog, select **Settings**.

1. In the **Settings** page, under **Cloud Discovery**, select **User enrichment**.

1. In the **User enrichment** tab, select **Enrich discovered user identifiers with Azure Active Directory usernames**. This option enables Defender for Cloud Apps to use Azure Active Directory data to enrich usernames by default.

    ![Enrich Defender for Cloud Apps Discovery with Azure AD usernames.](media/classic-discovery-enrichment.png)

## Next steps

> [!div class="nextstepaction"]
> [Control cloud apps with policies](control-cloud-apps-with-policies.md)

[!INCLUDE [Open support ticket](includes/support.md)]
