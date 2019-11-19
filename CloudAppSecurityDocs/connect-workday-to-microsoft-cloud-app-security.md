---
# required metadata

title: Connect Workday to Cloud App Security (Preview)
description: This article provides information about how to connect your Workday app to Cloud App Security using the API connector for visibility and control over use.
keywords:
author: shsagir
ms.author: shsagir
manager: shsagir
ms.date: 9/8/2019
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
# Connect Workday to Microsoft Cloud App Security (Preview)

*Applies to: Microsoft Cloud App Security*

This article provides instructions for connecting Microsoft Cloud App Security to your existing Workday account using the app connector API. This connection gives you visibility into and control over Workday use.

## Prerequisites

The Workday account used for connecting to Cloud App Security must be a member of a security group (new or existing). We recommended using a Workday Integration System User. The security group must have the following permissions selected for the following domain security policies:

| Functional area | Domain Security policy | Subdomain Security policy | Report/Task Permissions | Integration Permissions |
| --- | --- | --- | --- | --- |
| System | Set Up: Tenant Setup – General | Set Up: Tenant Setup –  Security | View, Modify | Get, Put |
| System | Security Administration | | View, Modify | Get, Put |
| System | System auditing | | View | Get |
| Staffing | Worker Data: Staffing | Worker Data: Public Worker Reports | View | Get |

> [!NOTE]
>
> * The account used to set up permissions for the security group must be a Workday Administrator.
> * To set permissions, go to **Domain Security Policies for Functional Area** and for the respective functional areas (**System**/**Staffing**), set the specified report and integration permissions.
> * Once all permissions have been set, go to **Activate Pending Security Policy Changes** and approve the changes.

For more information about setting up Workday integration users, security groups, and permissions, see steps 1 to 4 of the [Grant Integration or External Endpoint Access to Workday](https://go.microsoft.com/fwlink/?linkid=2103212) guide (accessible with Workday documentation/community credentials).

## How to connect Workday to Cloud App Security using OAuth

1. Sign in to Workday with an account that is a member of the security group mentioned in the prerequisites.

1. Search for "Edit tenant setup – system", and under **User Activity Logging**, select **Enable User Activity Logging**.

    ![Screenshot of allowing user activity logging](media/connect-workday-enable-logging.png)

1. Search for "Edit tenant setup – security", and under **OAuth 2.0 Settings**, select **OAuth 2.0 Clients Enabled**.

1. Search for "Register API Client" and select **Register API Client – Task**.

1. On the **Register API Client** page, fill out the following information, and then click **OK**.

    | Field name | Value |
    | ---- | ---- |
    | Client Name | Microsoft Cloud App Security |
    | Client Grant Type | Authorization Code Grant |
    | Access Token Type | Bearer |
    | Redirection URI | `https://portal.cloudappsecurity.com/api/oauth/connect` |
    | OAuth2 Scopes | **Staffing** and **System** |
    | Scope (Functional Areas) | **Staffing** and **System** |

    ![Screenshot of registering API client](media/connect-workday-register-api-client.png)

1. Once registered, make a note for the following parameters, and then click **Done**.

    * Client ID
    * Client Secret
    * Workday REST API Endpoint
    * Token Endpoint
    * Authorization Endpoint

    ![Screenshot of confirming registration of API client](media/connect-workday-register-api-client-confirm.png)

1. In the Cloud App Security portal, click **Investigate** and then click **Connected Apps**.

1. In the **App connectors** page, click the plus button and then **Workday**.

    ![Screenshot of adding app connector](media/connect-workday-add-app.png)

1. In the popup, add your instance name and then click **Connect Workday**.

    ![Screenshot of adding instance name](media/connect-workday-add-app-connect.png)

1. On the next page, fill out the details with the information you noted earlier, and then click **Connect in Workday**.

    ![Screenshot of filling out app details](media/connect-workday-add-app-connect-details.png)

1. In Workday, a popup will ask you if you want to allow Cloud App Security access to your Workday account. To proceed, click **Allow**.

    ![Screenshot of authorizing access to app](media/connect-workday-add-app-allow.png)

1. Back in the Cloud App Security portal, you should see a message that Workday was successfully connected. Make sure the connection succeeded by clicking **Test API**.

    Testing may take a couple of minutes. After receiving a success notice, click **Close**.

> [!NOTE]
> After connecting Workday, you'll receive events for seven days prior to connection.

## Next steps

[Control cloud apps with policies](control-cloud-apps-with-policies.md)

[Premier customers can also create a new support request directly in the Premier Portal.](https://premier.microsoft.com/)
