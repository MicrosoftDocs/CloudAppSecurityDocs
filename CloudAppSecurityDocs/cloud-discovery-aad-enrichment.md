---
title: Enrich Defender for Cloud Apps Discovery data with Azure AD usernames
description: This article provides information about how to enrich Defender for Cloud Apps Discovery data with Azure AD usernames.
ms.date: 09/09/2021
ms.topic: how-to
---
# Cloud Discovery enrichment

[!INCLUDE [Banner for top of topics](includes/banner.md)]

Cloud Discovery data can now be enriched with Azure Active Directory username data. When you enable this feature, the username, received in discovery traffic logs, is matched and replaced by the Azure AD username. Cloud Discovery enrichment enables the following features:

- You can investigate Shadow IT usage by Azure Active Directory user.
- You can correlate the Discovered cloud app use with the API collected activities.
- You can then create custom logs based on Azure AD user groups. For example, a Shadow IT report for a specific Marketing department.

## Prerequisites

- Data source must provide username information
- [Office 365 app connector](connect-office-365-to-microsoft-cloud-app-security.md) connected

## Enabling user data enrichment

1. Under the Settings cog, select **Settings**.

1. In the **Settings** page, under **Cloud Discovery**, select **User enrichment**.

1. In the **User enrichment** tab, select **Enrich discovered user identifiers with Azure Active Directory usernames**. This option enables Defender for Cloud Apps to use Azure Active Directory data to enrich usernames by default.

    ![Enrich Defender for Cloud Apps Discovery with Azure AD usernames.](media/discovery-enrichment.png)

## Next steps

> [!div class="nextstepaction"]
> [Control cloud apps with policies](control-cloud-apps-with-policies.md)

[!INCLUDE [Open support ticket](includes/support.md)]
