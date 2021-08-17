---
title: Connect apps to get visibility and control 
description: This article describes the process for connecting apps with API connectors to apps in your organization's cloud.
ms.date: 03/10/2021
ms.topic: how-to
---
# Connect apps

[!INCLUDE [Banner for top of topics](includes/banner.md)]

App connectors use the APIs of app providers to enable greater visibility and control by Microsoft Cloud App Security over the apps you connect to.

Microsoft Cloud App Security leverages the APIs provided by the cloud provider. All communication between Cloud App Security and connected apps is encrypted using HTTPS. Each service has its own framework and API limitations such as throttling, API limits, dynamic time-shifting API windows, and others. Microsoft Cloud App Security worked with the services to optimize the usage of the APIs and to provide the best performance. Taking into account different limitations services impose on the APIs, the Cloud App Security engines use the allowed capacity. Some operations, such as scanning all files in the tenant, require numerous APIs so they're spread over a longer period. Expect some policies to run for several hours or several days.

## Multi-instance support

Cloud App Security supports multiple instances of the same connected app. For example, if you have more than one instance of Salesforce (one for sales, one for marketing) you can connect both to Cloud App Security. You can manage the different instances from the same console to create granular policies and deeper investigation. This support applies only to API connected apps, not to Cloud Discovered apps or Proxy connected apps.

> [!NOTE]
> Multi-instance is not supported for Office 365 and Azure.

## How it works

Cloud App Security is deployed with system admin privileges to allow full access to all objects in your environment.

The App Connector flow is as follows:

1. Cloud App Security scans and saves authentication permissions.

1. Cloud App Security requests the user list. The first time the request is done, it may take some time until the scan completes. After the user scan is over, Cloud App Security moves on to activities and files. As soon as the scan starts, some activities will be available in Cloud App Security.
1. After completion of the user request, Cloud App Security periodically scans users, groups, activities, and files. All activities will be available after the first full scan.

This connection may take some time depending on the size of the tenant, the number of users, and the size and number of files that need to be scanned.

Depending on the app to which you're connecting, API connection enables the following items:

- **Account information** - Visibility into users, accounts, profile information, status (suspended, active, disabled) groups, and privileges.
- **Audit trail** - Visibility into user activities, admin activities, sign-in activities.
- **Account governance** - Ability to suspend users, revoke passwords, etc.
- **App permissions** - Visibility into issued tokens and their permissions.
- **App permission governance** - Ability to remove tokens.
- **Data scan** - Scanning of unstructured data using two processes -periodically (every 12 hours) and in real-time scan (triggered each time a change is detected).
- **Data governance** - Ability to quarantine files, including files in trash, and overwrite files.

The following tables list, per cloud app, which abilities are supported with App connectors:

### Users and activities

|   App                | List accounts                        | List groups                          | List privileges                      | Log on activity                      | User activity                               | Administrative activity   |
| ----------------- | ------------------------------------ | ------------------------------------ | ------------------------------------ | ------------------------------------ | ------------------------------------------- | ------------------------- |
| AWS               | ✔                                    |                                      |                                      | ✔                                    | Not applicable                              | ✔                         |
| Azure             | ✔                                    | ✔                                    |                                      | ✔                                    |                                             | ✔                         |
| Box               | ✔                                    | ✔                                    | ✔                                    | ✔                                    | ✔                                           | ✔                         |
| Dropbox           | ✔                                    | ✔                                    | ✔                                    | ✔                                    | ✔                                           | ✔                         |
| GitHub            | ✔                                    |                                      | ✔                                    |                                      | ✔                                           | ✔                         |
| GCP               | Subject Google Workspace  connection | Subject Google Workspace  connection | Subject Google Workspace  connection | Subject Google Workspace  connection | ✔                                           | ✔                         |
| Google  Workspace | ✔                                    | ✔                                    | ✔                                    | ✔                                    | ✔ - requires Google Business or  Enterprise | ✔                         |
| Office 365        | ✔                                    | ✔                                    | ✔                                    | ✔                                    | ✔                                           | ✔                         |
| Okta              | ✔                                    |                                      | Not supported by provider            | ✔                                    | ✔                                           | ✔                         |
| OneLogin (Preview) | ✔ | | ✔ | ✔ | ✔ | ✔ |
| Service  Now      | ✔                                    | ✔                                    | ✔                                    | ✔                                    | Partial                                     | Partial                   |
| Salesforce        | ✔                                    | ✔                                    | ✔                                    | ✔                                    | Supported with Salesforce Shield            | ✔                         |
| Slack (Preview) | ✔ |  | ✔ | ✔ | ✔ | ✔ |
| Webex             | ✔                                    |                                      | ✔                                    | ✔                                    | ✔                                           | ✔                         |
| Workday           | ✔                                    | Not supported by provider            | Not supported by provider            | ✔                                    | ✔                                           | Not supported by provider |
| Zendesk (Preview) | ✔ |  | ✔ | ✔ | ✔ | ✔ |

### User and app governance

|  App                 | User governance                      | View app permissions      | Revoke app permissions    |
| ----------------- | ------------------------------------ | ------------------------- | ------------------------- |
| AWS               |                                      | Not applicable            | Not applicable            |
| Azure             |                                      |                           | Not supported by provider |
| Box               | ✔                                    | Not supported by provider |                           |
| Dropbox           | Coming soon                          | Coming soon               | Coming soon               |
| GitHub            |                                      | ✔                         |                           |
| GCP               | Subject Google Workspace  connection | Not applicable            | Not applicable            |
| Google  Workspace | ✔                                    | ✔                         | ✔                         |
| Office 365        | ✔                                    | ✔                         | ✔                         |
| Okta              |                                      | Not applicable            | Not applicable            |
| OneLogin (Preview) | |  |  |
| Service  Now      |                                      |                           |                           |
| Salesforce        | ✔                                    | ✔                         | ✔                         |
| Slack (Preview) |  |  |  |
| Webex             |                                      | Not applicable            | Not applicable            |
| Workday           | Not supported by provider            | Not applicable            | Not applicable            |
| Zendesk (Preview) |  |  |  |

### Information protection

|     App              | DLP - Periodic backlog scan       | DLP - Near real-time scan                | Sharing control           | File governance           | Apply Azure Information Protection  labels |
| ----------------- | ------------------------- | ---------------------------------------- | ------------------------- | ------------------------- | ------------------------------------------ |
| AWS               |                           | ✔                                        | ✔                         | ✔                         | Not applicable                             |
| Azure             |                           |                                          |                           |                           |                                            |
| Box               | ✔                         | ✔                                        | ✔                         | ✔                         | ✔                                          |
| Dropbox           | ✔                         | ✔                                        | ✔                         | ✔                         |                                            |
| GitHub            |                           |                                          |                           |                           |                                            |
| GCP               | Not applicable            | Not applicable                           | Not applicable            | Not applicable            | Not applicable                             |
| Google  Workspace | ✔                         | ✔ - requires Google Business  Enterprise | ✔                         | ✔                         | ✔                                          |
| Office 365        | ✔                         | ✔                                        | ✔                         | ✔                         | ✔                                          |
| Okta              | Not applicable            | Not applicable                           | Not applicable            | Not applicable            | Not applicable                             |
| OneLogin (Preview) |  |  |  |  |  |
| Service  Now      | ✔                         | ✔                                        | Not applicable            |                           |                                            |
| Salesforce        | ✔                         | ✔                                        |                           | ✔                         |                                            |
| Slack (Preview) |  |  | |  | |
| Webex             | ✔                         | ✔                                        | ✔                         | ✔                         | Not applicable                             |
| Workday           | Not supported by provider | Not supported by provider                | Not supported by provider | Not supported by provider | Not applicable                             |
| Zendesk (Preview) |  |  |  |  |  |

## Prerequisites

- For some apps, it may be necessary to allow list IP addresses to enable Cloud App Security to collect logs and provide access for the Cloud App Security console. For more information, see [Network requirements](network-requirements.md).

- For each app that you want to connect with the Cloud App Security API integration, we recommend creating an admin service account dedicated to Cloud App Security.

> [!NOTE]
> To get updates when URLs and IP addresses are changed, subscribe to the RSS as explained in: [Office 365 URLs and IP address ranges](/microsoft-365/enterprise/urls-and-ip-address-ranges).

To use App Connectors, you need to make sure you have the following things for each specific app:

| App | License type | User |
|-----|--------------|------|
| Azure | | Global Admin |
| AWS | | Newly created user |
| Box | Enterprise | It's strongly recommended that you connect to Box as an Admin. Connecting as a Coadmin will result in only partial data visibility. If you connect as a Coadmin, make sure to select all permissions. |
| Dropbox | Business/Enterprise | Admin |
| GitHub | GitHub Enterprise Cloud | Owner |
| GCP | | See the [connect GCP prerequisites](connect-google-gcp-to-microsoft-cloud-app-security.md#prerequisites) |
| Google Workspace | Google Workspace Business or Enterprise preferred<br /><br />Google Workspace Enterprise (minimally) | Super Admin |
| Office 365 | | Global Admin |
| Okta | Enterprise (not trial) | Admin |
| Salesforce | | Admin |
| ServiceNow | Eureka and up | Admin + RestAPI role |
| Webex | | Admin + Compliance Admin |
| Workday | | See the [connect Workday prerequisites](connect-workday-to-microsoft-cloud-app-security.md#prerequisites) |

### ExpressRoute

Cloud App Security is deployed in Azure and fully integrated with [ExpressRoute](/azure/expressroute/expressroute-introduction). All interactions with the Cloud App Security apps and traffic sent to Cloud App Security, including upload of discovery logs, is routed via ExpressRoute for improved latency, performance, and security. There are no configuration steps required from the customer side.
For more information about  Public Peering, see [ExpressRoute circuits and routing domains](/azure/expressroute/expressroute-circuit-peerings).

## Disable app connectors

> [!NOTE]
>
> - Before disabling an app connector, make sure you have the connection details available as you will need them if you want to re-enable the connector.
> - These steps cannot be used to disable the Azure connector.
> - These steps cannot be used to disable Conditional Access App Control apps and Security configuration apps.

To disable connected apps:

1. In the **Connected apps** page, in the relevant row, click the three dots and select **Disable App connector**.
1. In the pop-up, click **Disable App connector instance** to confirm the action.

Once disabled, the connector instance will stop consuming data from the connector.

## Re-enable app connectors

To re-enable connected apps:

1. In the **Connected apps** page, in the relevant row, click the three dots and select **Edit app**. This starts the process to add a connector.
1. Add the connector using the steps in the relevant API connector guide. For example, if you are re-enabling GitHub, use the steps in [Connect GitHub Enterprise Cloud to Cloud App Security](connect-github-ec-to-microsoft-cloud-app-security.md).

## Related videos

> [!div class="nextstepaction"]
> [Connecting third-party apps webinar](webinars.md#on-demand-webinars)

> [!div class="nextstepaction"]
> [Microsoft Cloud App Security – REST API's and Tokens](https://channel9.msdn.com/Shows/Microsoft-Security/Microsoft-Cloud-App-Security--REST-APIs-and-Tokens)

## Next steps

> [!div class="nextstepaction"]
> [Daily activities to protect your cloud environment](daily-activities-to-protect-your-cloud-environment.md)

[!INCLUDE [Open support ticket](includes/support.md)]
