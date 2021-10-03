---
title: Connect Slack to Cloud App Security (Preview)
description: This article provides instructions for connecting Microsoft Cloud App Security to your existing Slack using the App Connector APIs. 
ms.date: 06/09/2021
ms.topic: how-to
---
# Connect Slack to Microsoft Cloud App Security (Preview)

[!INCLUDE [Banner for top of topics](includes/banner.md)]

This article provides instructions for connecting Microsoft Cloud App Security to your existing Slack using the App Connector APIs. This connection gives you visibility into and control over your organization’s Slack use.

## Prerequisites

* Your Slack tenant must meet the following requirements:
  * Your Slack tenant must have an **Enterprise** license. Cloud App Security doesn't support non-enterprise licenses.
  * Your Slack tenant should have **Discovery API** enabled. To enable **Discovery API** for your Slack tenant, contact Slack support.

* The org Owner needs to be logged into their Slack organization within their browser before installing the connector.

## How to connect Slack to Cloud App Security

1. In the [Cloud App Security portal](https://portal.cloudappsecurity.com/), select **Investigate** and then **Connected apps**.

1. In the **App connectors** page, select the plus button followed by **Slack**.

1. In the pop-up, give the connector a descriptive name, and press **Connect**.

    ![Connect Slack](media/connect-slack.png)

1. In the next screen, select **Connect in Slack**.

    ![Connect in Slack](media/connect-in-slack.png)

1. You'll be redirected to the Slack page. Make sure the org Owner is already logged into the Slack organization.

1. In the Slack Authorization page, make sure to choose the correct organization from the dropdown in the top-right corner.

    >[!NOTE]
    >
    > * The first connection can take up to 4 hours to get all users and their activities in the 7 days before the connection.
    > * After the connector’s **Status** is marked as **Connected**, the connector is live and works.
    > * The received activities are from the Slack Audit Log API. You can find them in the [Slack documentation](https://api.slack.com/admins/audit-logs#audit_logs_actions).
    > * **Send Slack message** activity is an activity that can be received from [Conditional Access App Control](proxy-deployment-aad.md), and not from the Slack API connector.

## Next steps

> [!div class="nextstepaction"]
> [Control cloud apps with policies](control-cloud-apps-with-policies.md)

[!INCLUDE [Open support ticket](includes/support.md)]
