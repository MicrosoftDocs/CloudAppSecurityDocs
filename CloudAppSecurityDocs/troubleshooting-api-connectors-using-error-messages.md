---
# required metadata

title: Troubleshoot App Connector error messages - Cloud App Security | Microsoft Docs
description: This article provides a list of API App connector error messages as well as resolution recommendations for each.
keywords:
author: shsagir
ms.author: shsagir
manager: shsagir
ms.date: 12/10/2018
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: 4b6ac04a-4653-4c4a-bd6f-5926743475cc

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: seodec18

---
# Troubleshooting App Connectors using error messages

*Applies to: Microsoft Cloud App Security*

This article provides a list of API App connector error messages and resolution recommendations for each error.

## Troubleshooting

App connector errors can be seen in the app connector dialog after attempting to connect a cloud app using the API App connector.


> [!div class="mx-tableFixed"]
> 
> |Error message|Relevant app|Description|Resolution|
> |----|----|----|------------|
> |HttpRequestFailure: Server returned: 400 Bad Request: {"error":{"code":"AF20012","message":"Specified tenant ID (Tenant_ID goes here) is incorrectly configured in the system."|Office 365 |No assigned Office 365 licenses were found. |Assign at least one Office 365 license to your tenant.| 
> |AuthFatalFailureException: com.box.boxjavalibv2.exceptions.BoxServerException: {"error":"invalid_grant","error_description":"Invalid refresh token"}|Box|The Box refresh token is not valid|Follow the process to connect Box to Cloud App Security again.|
> |BoxRestException: Failed to parse response.|Box|Internal error|Click the Test now link again to test the connection to Box.|
> |ContextManagerServiceException: com.adallom.adalib.httputils.exceptions.TokenRefreshException: {"error":"invalid_grant","error_description":"Invalid refresh token"}'|Box|The Box refresh token is not valid|Follow the process to connect Box to Cloud App Security again.|
> |BoxServerException: User cannot access this feature without having an enterprise|Box|The Box account is not an Enterprise account.|Upgrade your Box license to the Enterprise version of Box and then follow the process to connect Box to Cloud App Security again.|
> |BoxServerException: Unauthorized - Cannot authorize with this service|Box|The Box admin deleted the Cloud App Security application in Box.|Follow the process to connect Box to Cloud App Security again.|
> |HttpRequestFailure: Server returned: 401 Unauthorized|Okta|The Okta token is not valid.|Follow the process to connect Okta to Cloud App Security again.|
> |IOException:|Okta|Internal error|Contact support|
> |HttpRequestFailure: Server returned: 404 Not Found|Okta|Internal error|Contact support|
> |SocketTimeoutException: Read timed out|Salesforce|Internal error|Click the Test now link again to test the connection to Salesforce.|
> |HttpRequestFailure: Server returned: 400 Bad Request|Salesforce|Either the connection to Salesforce did not complete or is expired.|Follow the process to connect Salesforce to Cloud App Security again.|
> |HttpRequestFailure: Server returned: 401 Unauthorized|Office 365|Internal problem|Click the Test now link again|
> |TokenRefreshException: {"error":"invalid_grant","error_description":"AADSTS70002: Error validating credentials. AADSTS70008: The provided authorization code or refresh token is expired. Send a new interactive authorization request for this user and resource.|Office 365|Token expired|Follow the process to connect Office 365 to Cloud App Security again.|
> |SocketTimeoutException: Read timed out|Office 365|Internal error|Click the Test now link again|
> |NullPointerException|Office 365|Internal error|Contact support|
> |IgniteException|Office 365|Domain or user are not valid|Reset your settings and follow the process to connect Office 365 to Cloud App Security again.|
> |ContextManagerServiceException: com.adallom.adalib.httputils.exceptions.TokenRefreshException: {"error":"invalid_grant","error_description":"AADSTS70002: Error validating credentials. AADSTS70008: The provided authorization code or refresh token is expired. Send a new interactive authorization request for this user and resource.|Office 365|Domain or user are not valid|Reset your settings and follow the process to connect Office 365 to Cloud App Security again.|
> |HttpRequestFailure: Server returned: 400 Bad Request|Office 365|Internal error|Click the Test now link again in a few minutes, if it does not work, follow the process to connect Office 365 to Cloud App Security again.|
> |GoogleJsonResponseException: 401 Unauthorized|G Suite|Access denied. You are not authorized to read activity records. The user you log into G Suite with must be an admin user.|Follow the process to connect G Suite to Cloud App Security again using an admin account.|
> |GoogleJsonResponseException: 403 Forbidden|G Suite|Problem running the G Suite API.|If you just deployed the Cloud App Security App Connector for G Suite, check the following: If you clicked Unlimited, make sure that your G Suite account is really unlimited. If it is not, run the App Connector again and un-select the option for an unlimited account. Check that the scopes you defined during setup are correct. If this is not a new deployment and you see this error, it may be that you reached the API limit for today and G Suite events will be renewed tomorrow.|
> |TokenResponseException: 400 Bad Request|G Suite|Either the connection to G Suite did not complete or is expired.|Follow the process to connect G Suite to Cloud App Security again.|
> |RuntimeException: com.adallom.adalib.httputils.exceptions.HttpRequestFailure: Server returned: 403 Forbidden|ServiceNow|Permissions are incorrect|Follow the process to connect ServiceNow to Cloud App Security again using an admin account.|
> |HttpRequestFailure: Server returned: 401 Unauthorized|Exchange Online|User or password are incorrect|Make sure the username and password are correct and Follow the process to connect Exchange Online to Cloud App Security again.|
> |HttpRequestFailure: Server returned: 404 Not Found|Exchange Online|The user you are using to log into Exchange Online does not have a primary mailbox in Exchange Online (for example, a user who does not exist in Azure AD or a user exists in Azure AD, but does not have an Exchange Online license).|Follow the process to connect Exchange Online to Cloud App Security again using a new admin account.|
> |NullPointerException|AWS|Internal error|Contact support|
> |HttpRequestFailure: Server returned: 500 Internal server error|All apps|There was an error in the app.|Check the status of the app|
> |Service timeout|All apps|A timeout was detected in the connection between Cloud App Security and the app. This could be due to a problem with the app.|Try again later.|

## Next steps

[Daily activities to protect your cloud environment](daily-activities-to-protect-your-cloud-environment.md)   

[!INCLUDE [Open support ticket](includes/support.md)]  

