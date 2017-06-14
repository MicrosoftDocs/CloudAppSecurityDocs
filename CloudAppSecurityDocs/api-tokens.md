---
# required metadata

title: API token management in Cloud App Security | Microsoft Docs
description: This topic provides information about generating API tokens for Cloud App Security.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 6/14/2017
ms.topic: article
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: 4f5e6b1e-6b2c-4358-98f0-945e2993d5fe


# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# API tokens
    
The Cloud App Security API provides programmatic access to Cloud App Security through REST API endpoints. Applications can use the API to preform read and update operations on Cloud App Security data and objects. For example, the Cloud App Security API supports the following common operations for a user object:

- Upload log files for Cloud Discovery
- Generate block scripts
- List activities, alerts, and policy reports
- Dismiss or resolve alerts

To see the full documentation of the API, in the Cloud App Security portal go to Help > **API documentation**.

In order to access the API, you have to create an API token and use it in your software to connect to the Cloud App Security APi.

The API tokens tab enables you to help you manage all the API tokens of your tenant. 


## Generate a token

1. On the **Settings** menu, select **Security extensions** and then **API tokens**.

2. Click the plus icon, **Generate new token** and provide a name to identify the token in the future, and click **Next**.

3. Copy the token value and save it somewhere for recovery - if you lose it you will need to regenerate the token. The token will have the privileges of the user who issued it. For example, a security reader cannot issue a token that can alter data.

4. You can filter the tokens by status: Active, Inactive or Generated. 

  - Generated are tokens that have never been used. 
  - Active are tokens that were generated and were used within the past 7 days. 
  - Inactive were used but there was no activity in the last 7 days.


## API token management

The API token page includes a table of all the API tokens that were generated.

Full admins will see all tokens generated for this tenant. Other users will only see the tokens that they generated themselves.

The table provides details about when the token was generated and when it was last used and allows you to revoke the token. 

After a token is revoked, it will be removed from the table and the software that was using it will fail to make API calls until a new token is provided. 

> [!NOTE]
> SIEM connectors and log collectors also use API tokens. These tokens should be managed from the log collectors and SIEM agent sections and will not appear in this table. 

## See Also  
[Troubleshooting SIEM integration issues](troubleshooting-siem.md)   
[For technical support, please visit the Cloud App Security assisted support page.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  