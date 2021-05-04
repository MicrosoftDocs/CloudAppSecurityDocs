---
title: Managing API tokens
description: This article provides information about generating and managing API tokens for Cloud App Security.
ms.date: 04/14/2021
ms.topic: reference
---
# Managing API tokens

[!INCLUDE [Banner for top of topics](includes/banner.md)]

Cloud App Security exposes much of its data and actions through a set of programmatic APIs. Those APIs will enable you to automate workflows and innovate based on Cloud App Security capabilities.

To access the Cloud App Security API, you have to create an API token and use it in your software to connect to the API. This token will be included in the header when Cloud App Security makes API requests.

The API access requires OAuth2.0 authentication. For more information, see [OAuth 2.0 Authorization Code Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

In general, you’ll need to take the following steps to use the APIs:

- Create an AAD application
- Get an access token using this application
- Use the token to access the Cloud App Security API

You can access the Cloud App Security API with **Application Context** or **User Context**.

>[!NOTE]
>[The legacy method](api-tokens-legacy.md) of accessing the Cloud App Security is still supported. However, it is on a deprecation path, so we recommend using the methods described on this page.

## Application context (recommended)
  
Used by apps that run without a signed-in user present. For example, apps that run as background services or daemons.

Steps that need to be taken to access Cloud App Security API with application context:

1. Create an AAD Web-Application.
1. Assign the desired permission to the application. For example, **Read Alerts** or **Upload Discovery Report**.
1. Create a key for this application.
1. Get the token using the application with its key.
1. Use the token to access the Cloud App Security API

For more information, see [Get access with application context](api-authentication-application.md).

## User context

Used to perform actions in the API on behalf of a user.

Steps to take to access the Cloud App Security API with application context:

1. Create an AAD Native-Application.
1. Assign the desired permission to the application. For example, **Read Alerts** or **Upload Discovery Report**.
1. Get the token using the application with user credentials.
1. Use the token to access the Cloud App Security API.

For more information, see [Get access with user context](api-authentication-user.md).

## Related articles

- [Access Microsoft Cloud App Security with application context](api-authentication-application.md)
- [Access Microsoft Cloud App Security with user context](api-authentication-user.md)
