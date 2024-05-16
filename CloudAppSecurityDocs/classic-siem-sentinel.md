---
title: Classic portal -  Microsoft Sentinel integration 
description: Classic portal -  This article provides information integrating Microsoft Sentinel with Defender for Cloud Apps.
ms.date: 01/19/2023
ms.topic: how-to
ROBOTS: NOINDEX
---
# Classic portal: Microsoft Sentinel integration (Preview)

[!INCLUDE [Banner for top of topics](includes/classic-banner.md)]

You can integrate Microsoft Defender for Cloud Apps with Microsoft Sentinel (a scalable, cloud-native SIEM and SOAR) to enable centralized monitoring of alerts and discovery data. Integrating with Microsoft Sentinel allows you to better protect your cloud applications while maintaining your usual security workflow, automating security procedures, and correlating between cloud-based and on-premises events.

Benefits of using Microsoft Sentinel include:

* Longer data retention provided by Log Analytics.
* Out-of-the-box visualizations.
* Use tools such as Microsoft Power BI or Microsoft Sentinel workbooks to create your own discovery data visualizations that fit your organizational needs.

Additional integration solutions include:

* **Generic SIEMs** - Integrate Defender for Cloud Apps with your generic SIEM server. For information in integrating with a Generic SIEM, see [Generic SIEM integration](siem.md).
* **Microsoft security graph API** - An intermediary service (or broker) that provides a single programmatic interface to connect multiple security providers. For more information, see [Security solution integrations using the Microsoft Graph Security API](/graph/security-integration#list-of-connectors-from-microsoft).

## How to integrate

Integrating with your SIEM is accomplished in two steps:

1. Set it up in Defender for Cloud Apps.
1. Set it up in Microsoft Sentinel.

> [!NOTE]
> The option to add Microsoft Sentinel is not available if you have previously performed the integration.

### Prerequisites

To integrate with Microsoft Sentinel:

* You must have a valid Microsoft Sentinel license
* You must be a Global Administrator or a Security Administrator in your tenant.

### Integrating with Microsoft Sentinel

1. In the [Defender for Cloud Apps portal](https://portal.cloudappsecurity.com/), under the **Settings** cog, select **Security extensions**.

1. On the **SIEM agents** tab, select add (**+**), and then choose **Microsoft Sentinel**.

    ![Screenshot showing Add SIEM integration menu.](media/classic-siem0.png)

1. In the wizard, select the data types you want to forward to Microsoft Sentinel. You can configure the integration, as follows:
    1. **Alerts**: Alerts are automatically turned on once Microsoft Sentinel is enabled.
    1. **Discovery logs**: Use the slider to enable and disable them, by default, everything is selected, and then use the **Apply to** drop-down to filter which discovery logs are sent to Microsoft Sentinel.

    ![Screenshot showing start page of Configure Microsoft Sentinel integration.](media/classic-siem-sentinel-configuration.png)

1. Select **Next**, and continue to Microsoft Sentinel to finalize the integration. For information on configuring Microsoft Sentinel, see [the Microsoft Sentinel data connector for Defender for Cloud Apps](/azure/sentinel/data-connectors-reference#microsoft-defender-for-cloud-apps).

    ![Screenshot showing finish page of Configure Microsoft Sentinel integration.](media/classic-siem-sentinel-configuration-complete.png)

> [!NOTE]
> New discovery logs will usually appear in Microsoft Sentinel within 15 minutes of configuring them in the Defender for Cloud Apps portal. However, it may take longer depending on system environment conditions. For more information, see [Handle ingestion delay in analytics rules](/azure/sentinel/ingestion-delay).

## Alerts and discovery logs in Microsoft Sentinel

Once the integration is completed, you can view Defender for Cloud Apps alerts and discovery logs in Microsoft Sentinel.

In Microsoft Sentinel, under **Logs**, under **Security Insights**, you can find the logs for the Defender for Cloud Apps data types, as follows:

| Data type | Table |
| --- | --- |
| Discovery logs | McasShadowItReporting |
| Alerts | SecurityAlert |

The following table describes each field in the **McasShadowItReporting** schema:

| Field | Type | Description | Examples |
| --- | --- | --- | --- |
| TenantId | String | Workspace ID | b459b4u5-912x-46d5-9cb1-p43069212nb4 |
| SourceSystem | String | Source system – static value | Azure |
| TimeGenerated [UTC] | DateTime | Date of discovery data | 2019-07-23T11:00:35.858Z |
| StreamName | String | Name of the specific stream | Marketing Department |
| TotalEvents | Integer | Total number of events per session | 122 |
| BlockedEvents | Integer | Number of blocked events | 0 |
| UploadedBytes | Integer | Amount of uploaded data | 1,514,874 |
| TotalBytes | Integer | Total amount of data | 4,067,785 |
| DownloadedBytes | Integer | Amount of downloaded data | 2,552,911 |
| IpAddress | String | Source IP address | 127.0.0.0 |
| UserName | String | User name | `Raegan@contoso.com` |
| EnrichedUserName | String | Enriched user name with Microsoft Entra username | `Raegan@contoso.com` |
| AppName | String | Name of cloud app | Microsoft OneDrive for Business |
| AppId | Integer | Cloud app identifier | 15600 |
| AppCategory | String | Category of cloud app | Cloud storage |
| AppTags | String array | Built-in and custom tags defined for the app | ["sanctioned"] |
| AppScore | Integer | The risk score of the app in a scale 0-10, 10 being  a score for a non-risky app | 10 |
| Type | String | Type of logs – static value | McasShadowItReporting |

## Use Power BI with Defender for Cloud Apps data in Microsoft Sentinel

Once the integration is completed, you can also use the Defender for Cloud Apps data stored in Microsoft Sentinel in other tools.

This section describes how you can use Microsoft Power BI to easily shape and combine data to build reports and dashboards that meet the needs of your organization.

You can get started quickly by using the following steps:

1. In Power BI, import queries from Microsoft Sentinel for Defender for Cloud Apps data. For more information, see [Import Azure Monitor log data into Power BI](/azure/azure-monitor/logs/log-powerbi).
1. [Install the Defender for Cloud Apps Shadow IT Discovery app](https://aka.ms/MCASShadowITReporting) and [connect it](#connect-the-defender-for-cloud-apps-app) to your discovery log data to view the built-in Shadow IT Discovery dashboard.

    > [!NOTE]
    > Currently, the app is not published on Microsoft AppSource. Therefore, you may need to contact your Power BI admin for permissions to install the app.

    ![Screenshot showing the Shadow IT Discovery dashboard.](media/classic-siem-sentinel-configuration-powerbi-dashboard.png)

1. Optionally, build custom dashboards in Power BI Desktop and tweak it to fit the visual analytics and reporting requirements of your organization.

### Connect the Defender for Cloud Apps app

1. In Power BI, select **Apps**, and then select on the **Shadow IT Discovery** app.

1. On the **Get started with your new app** page, select **Connect**.

    ![Screenshot showing connect app data page.](media/classic-siem-sentinel-powerbi-connect.png)

1. On the workspace ID page, enter your Microsoft Sentinel workspace ID as displayed in your log analytics overview page, and then select **Next**.

    ![Screenshot showing request for workspace ID.](media/classic-siem-sentinel-powerbi-workspace-id.png)

1. On the authentication page, specify the authentication method and privacy level, and then select **Sign in**.

    ![Screenshot showing the authentication page.](media/classic-siem-sentinel-powerbi-authentication.png)

1. After connecting your data, go to the workspace **Datasets** tab and select **Refresh**. This will update the report with your own data.

[!INCLUDE [Open support ticket](includes/classic-support.md)]
