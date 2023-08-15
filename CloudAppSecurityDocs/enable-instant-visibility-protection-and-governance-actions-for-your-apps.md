---
title: Connect apps to get visibility and control 
description: This article describes the process for connecting apps with API connectors to apps in your organization's cloud.
ms.date: 04/24/2023
ms.topic: how-to
---

# Connect apps to get visibility and control with Microsoft Defender for Cloud Apps

[!INCLUDE [Banner for top of topics](includes/banner.md)]

App connectors use the APIs of app providers to enable greater visibility and control by Microsoft Defender for Cloud Apps over the apps you connect to.

Microsoft Defender for Cloud Apps leverages the APIs provided by the cloud provider. All communication between Defender for Cloud Apps and connected apps is encrypted using HTTPS. Each service has its own framework and API limitations such as throttling, API limits, dynamic time-shifting API windows, and others. Microsoft Defender for Cloud Apps worked with the services to optimize the usage of the APIs and to provide the best performance. Taking into account different limitations services impose on the APIs, the Defender for Cloud Apps engines use the allowed capacity. Some operations, such as scanning all files in the tenant, require numerous APIs so they're spread over a longer period. Expect some policies to run for several hours or several days.

## Multi-instance support

Defender for Cloud Apps supports multiple instances of the same connected app. For example, if you have more than one instance of Salesforce (one for sales, one for marketing) you can connect both to Defender for Cloud Apps. You can manage the different instances from the same console to create granular policies and deeper investigation. This support applies only to API connected apps, not to Cloud Discovered apps or Proxy connected apps.

> [!NOTE]
> Multi-instance is not supported for Microsoft 365 and Azure.

## How it works

Defender for Cloud Apps is deployed with system admin privileges to allow full access to all objects in your environment.

The App Connector flow is as follows:

1. Defender for Cloud Apps scans and saves authentication permissions.

1. Defender for Cloud Apps requests the user list. The first time the request is done, it may take some time until the scan completes. After the user scan is over, Defender for Cloud Apps moves on to activities and files. As soon as the scan starts, some activities will be available in Defender for Cloud Apps.
1. After completion of the user request, Defender for Cloud Apps periodically scans users, groups, activities, and files. All activities will be available after the first full scan.

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

>[!NOTE]
>Since not all app connectors support all abilities, some rows may be empty.

### Users and activities

|   App                | List accounts                        | List groups                          | List privileges                      | Log on activity                      | User activity                               | Administrative activity   |
| ----------------- | ------------------------------------ | ------------------------------------ | ------------------------------------ | ------------------------------------ | ------------------------------------------- | ------------------------- |
| Atlassian         | ✔ |  |  | ✔ | ✔ | ✔ |
| AWS               | ✔                                    |                                      |                                      | ✔                                    | Not applicable                              | ✔                         |
| Azure             | ✔                                    | ✔                                    |                                      | ✔                                    |                                             |                        |
| Box               | ✔                                    | ✔                                    | ✔                                    | ✔                                    | ✔                                           | ✔                         |
| Citrix share file  |  |  |  |   |
| DocuSign          | ✔ |  |  | ✔ | ✔ | ✔ |
| Dropbox           | ✔                                    | ✔                                    | ✔                                    | ✔                                    | ✔                                           | ✔                         |
| Egnyte  | ✔ |  | ✔ | ✔ | ✔ | ✔ |
| GitHub            | ✔                                    |                                      | ✔                                    |                                      | ✔                                           | ✔                         |
| GCP               | Subject Google Workspace  connection | Subject Google Workspace  connection | Subject Google Workspace  connection | Subject Google Workspace  connection | ✔                                           | ✔                         |
| Google  Workspace | ✔                                    | ✔                                    | ✔                                    | ✔                                    | ✔ - requires Google Business or  Enterprise | ✔                         |
| NetDocuments  | ✔ |  | ✔ |  | ✔ | ✔ |
| Microsoft 365        | ✔                                    | ✔                                    | ✔                                    | ✔                                    | ✔                                           | ✔                         |
| Okta              | ✔                                    |                                      | Not supported by provider            | ✔                                    | ✔                                           | ✔                         |
| OneLogin | ✔ | | ✔ | ✔ | ✔ | ✔ |
| Service  Now      | ✔                                    | ✔                                    | ✔                                    | ✔                                    | Partial                                     | Partial                   |
| Salesforce        | ✔                                    | ✔                                    | ✔                                    | ✔                                    | Supported with Salesforce Shield            | ✔                         |
| Slack | ✔ |  | ✔ | ✔ | ✔ | ✔ |
| Smartsheet | ✔ | | ✔ |  | ✔ | ✔ |
| Webex             | ✔                                    |                                      | ✔                                    |                                    | ✔                                           |  Not supported by provider |
| Workday           | ✔                                    | Not supported by provider            | Not supported by provider            | ✔                                    | ✔                                           | Not supported by provider |
|Workplace by Meta|✔||✔|✔|✔|✔|
| Zendesk | ✔ |  | ✔ | ✔ | ✔ | ✔ |
| Zoom  |  |  |  |   |

### User, app governance, and security configuration visibility

|  App                 | User governance                      | View app permissions      | Revoke app permissions    | SaaS Security Posture Management (SSPM) |
| ----------------- | ------------------------------------ | ------------------------- | ------------------------- | ------------------------- |
| Atlassian         |  |  |  |  |
| AWS               |                                      | Not applicable            | Not applicable            |             |
| Azure             |                                      |                           | Not supported by provider |  |
| Box               | ✔                                    | Not supported by provider |                           |                           |
| Citrix Share file          |  |  | | Preview  |
| DocuSign          |  |  | | Preview  |
| Dropbox           |                                      |                           |                            |                            |
| Egnyte | | | | |
| GitHub            |                                      | ✔                         |                           | Preview                          |
| GCP               | Subject Google Workspace  connection | Not applicable            | Not applicable            |             |
| Google  Workspace | ✔                                    | ✔                         | ✔                         |   Preview                       |
| NetDocuments  |  |  |  |  |
| Microsoft 365        | ✔                                    | ✔                         | ✔                         | ✔                 |
| Okta              |                                      | Not applicable            | Not applicable            | Preview            |
| OneLogin | |  |  |  |
| Service  Now      |                                      |                           |                           | ✔ |
| Salesforce        | ✔                                    | ✔                         | ✔                         | ✔ |
| Slack |  |  |  |  |
| Smartsheet | | | | |
| Webex             |                                      | Not applicable            | Not applicable            |             |
| Workday           | Not supported by provider            | Not applicable            | Not applicable            |             |
|Workplace by Meta|||||
| Zendesk  |  |  |  |  |
| Zoom  |  |  |  | Preview  |


### Information protection

|     App              | DLP - Periodic backlog scan       | DLP - Near real-time scan                | Sharing control           | File governance           | Apply sensitivity labels from Microsoft Purview Information Protection |
| ----------------- | ------------------------- | ---------------------------------------- | ------------------------- | ------------------------- | ------------------------------------------ |
| Atlassian         |  |  |  |  |  |
| AWS               |                           | ✔ - S3 Bucket discovery only             | ✔                         | ✔                         | Not applicable                             |
| Azure             |                           |                                          |                           |                           |                                            |
| Box               | ✔                         | ✔                                        | ✔                         | ✔                         | ✔                                          |
| Citrix share file  |  |  |  |   |
| DocuSign          |  |  |  |  |  |
| Dropbox           | ✔                         | ✔                                        | ✔                         | ✔                         |                                            |
| Egnyte  |  |  |  |  | |
| GitHub            |                           |                                          |                           |                           |                                            |
| GCP               | Not applicable            | Not applicable                           | Not applicable            | Not applicable            | Not applicable                             |
| Google  Workspace | ✔                         | ✔ - requires Google Business  Enterprise | ✔                         | ✔                         | ✔                                          |
| NetDocuments  |  |  |  |  |  |
| Microsoft 365        | ✔                         | ✔                                        | ✔                         | ✔                         | ✔                                          |
| Okta              | Not applicable            | Not applicable                           | Not applicable            | Not applicable            | Not applicable                             |
| OneLogin |  |  |  |  |  |
| Service  Now      | ✔                         | ✔                                        | Not applicable            |                           |                                            |
| Salesforce        | ✔                         | ✔                                        |                           | ✔                         |                                            |
| Slack |  |  | |  | |
| Smartsheet | | | | | |
| Webex             | ✔                         | ✔                                        | ✔                         | ✔                         | Not applicable                             |
| Workday           | Not supported by provider | Not supported by provider                | Not supported by provider | Not supported by provider | Not applicable                             |
|Workplace by Meta||||||
| Zendesk  |  |  |  |  |  |
| Zoom  |  |  |  |   |

## Prerequisites

- When working with the [Microsoft 365 connector](protect-office-365.md), you'll need a license for each service where you want to view security recommendations. For example, to view recommendations for Microsoft Forms, you'll need a license that supports Forms.

- For some apps, it may be necessary to allow list IP addresses to enable Defender for Cloud Apps to collect logs and provide access for the Defender for Cloud Apps console. For more information, see [Network requirements](network-requirements.md).

> [!NOTE]
> To get updates when URLs and IP addresses are changed, subscribe to the RSS as explained in: [Microsoft 365 URLs and IP address ranges](/microsoft-365/enterprise/urls-and-ip-address-ranges).

### ExpressRoute

Defender for Cloud Apps is deployed in Azure and fully integrated with [ExpressRoute](/azure/expressroute/expressroute-introduction). All interactions with the Defender for Cloud Apps apps and traffic sent to Defender for Cloud Apps, including upload of discovery logs, is routed via ExpressRoute for improved latency, performance, and security.
For more information about  Microsoft Peering, see [ExpressRoute circuits and routing domains](/azure/expressroute/expressroute-circuit-peerings).

## Disable app connectors

> [!NOTE]
>
> - Before disabling an app connector, make sure you have the connection details available as you will need them if you want to re-enable the connector.
> - Once an Azure connector is disabled, it can't be re-enabled. If the connector is disabled by accident, contact Microsoft support.
> - These steps cannot be used to disable Conditional Access App Control apps and Security configuration apps.

To disable connected apps:

1. In the **Connected apps** page, in the relevant row, select the three dots and choose **Disable App connector**.
1. In the pop-up, click **Disable App connector instance** to confirm the action.

Once disabled, the connector instance will stop consuming data from the connector.

## Re-enable app connectors

To re-enable connected apps:

1. In the **Connected apps** page, in the relevant row, select the three dots and choose **Edit settings**. This starts the process to add a connector.
1. Add the connector using the steps in the relevant API connector guide. For example, if you are re-enabling GitHub, use the steps in [Connect GitHub Enterprise Cloud to Defender for Cloud Apps](./connect-github-ec.md).

## Related videos

> [!div class="nextstepaction"]
> [Connecting third-party apps webinar](webinars.md#on-demand-webinars)

## Next steps

> [!div class="nextstepaction"]
> [Best practices for protecting your organization](best-practices.md)

[!INCLUDE [Open support ticket](includes/support.md)]

