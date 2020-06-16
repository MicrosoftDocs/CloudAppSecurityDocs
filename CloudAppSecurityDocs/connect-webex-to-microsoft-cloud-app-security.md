---
# required metadata

title: Connect Webex to Cloud App Security
description: This article provides information about how to connect your Webex app to Cloud App Security using the API connector  for visibility and control over use.
keywords:
author: shsagir
ms.author: shsagir
manager: shsagir
ms.date: 04/16/2019
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.prod:
ms.service: cloud-app-security
ms.technology:

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: seodec18

---
# Connect Cisco Webex to Microsoft Cloud App Security

*Applies to: Microsoft Cloud App Security*

This article provides instructions for connecting Microsoft Cloud App Security to your existing Cisco Webex account using the connector APIs. This connection gives you visibility into and control over Webex users, activities, and files. For information about how Cloud App Security protects Cisco Webex, see [Protect Cisco Webex](protect-webex.md).

## Prerequisites

- We suggest that you create a dedicated service account for the connection. This enables you to see that governance actions performed in Webex as being performed from this account, such as delete messages sent in Webex. Otherwise, the name of the admin who connected Cloud App Security to Webex will appear as the user who performed the actions.
- You must have Full administrator **and** Compliance administrator permissions in Webex.

## How to connect Webex to Cloud App Security

1. In the Cloud App Security console, click **Investigate** and then **Connected apps**.

1. In the **App connectors** page, click the plus button followed by **Cisco Webex**.

    ![connect Webex](media/cisco-webex.png "connect Webex")

1. In the pop-up, enter the instance name of this connector.

1. Click **Connect Cisco Webex**. The Webex sign in page opens. Enter your credentials to allow Cloud App Security access to your team's Webex instance.

1. Webex asks you if you want to allow Cloud App Security access to your team information, activity log, and perform activities as a team member. To proceed, click **Allow**.

1. Back in the Cloud App Security console, you should receive a message that Webex was successfully connected.

1. Make sure the connection succeeded by clicking **Test API**.

    Testing may take a couple of minutes. After you receive a success notice, click **Close**.

After connecting Webex, you'll receive events for 7 days prior to connection. Cloud App Security scans events over the past three months. To increase this, you must have a Cisco Webex pro license and open a ticket with Cloud App Security support.

If you have any problems connecting the app, see [Troubleshooting App Connectors](troubleshooting-api-connectors-using-error-messages.md).

## Next steps

> [!div class="nextstepaction"]
> [Control cloud apps with policies](control-cloud-apps-with-policies.md)

[!INCLUDE [Open support ticket](includes/support.md)]
