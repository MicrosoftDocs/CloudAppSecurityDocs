---
# required metadata
title: Cloud App Security REST API
description: This article describes how to interact with Cloud App Security over HTTPS.
keywords:
author: shsagir
ms.author: shsagir
manager: shsagir
ms.date: 03/27/2020
ms.topic: reference
ms.collection: M365-security-compliance
ms.service: cloud-app-security

# optional metadata
ms.suite: ems
---
# Cloud App Security REST API

*Applies to: Microsoft Cloud App Security*

This article describes how to interact with Cloud App Security over HTTPS.

The Microsoft Cloud App Security API provides programmatic access to Cloud App Security through REST API endpoints. Applications can use the API to perform read and update operations on Cloud App Security data and objects. For example, the Cloud App Security API supports the following common operations for a user object:

- Upload log files for Cloud Discovery
- Generate block scripts
- List activities, alerts, and policy reports
- Dismiss or resolve alerts

## What actions are supported?

The following is a list of actions supported:

|Action|HTTP verb|URI template|
|---|---|---|
|Discovery|GET, POST, or PUT|/api/v1/discovery  |
|Data enrichment|POST|/cas/api/subnet|
|Activities|GET or POST|/api/v1/activities|
|Alerts|GET or POST|/api/v1/alerts|
|Entities|GET or POST|/api/v1/entities|
|Files|GET or POST|/api/v1/files|

Where **Action** represents a group of related activities.

## What field types are supported?

The following is a list of field types supported:

|Field|Description|
|---|---|
|string|A textual string|
|boolean|A boolean value representing true/false|
|integer|32-bit signed integer|
|timestamp|Milliseconds since epoch|

## Limits

You can choose to limit your requests by providing a limit parameter in the request.

The following methods are supported for providing the limit parameter:

- URL-encoded (with `Content-Type: application/x-www-form-urlencoded` header)
- Form data
- JSON body (with `Content-Type: multipart/form-data` and an appropriate boundary header)

> [!NOTE]
>
> - If no limit is provided a default of 100 will be set.
> - Responses for all requests made with the API token are limited to maximum of 100 items.

## Next steps

> [!div class="nextstepaction"]
> [API tokens](api-tokens.md)

[!INCLUDE [Open support ticket](includes/support.md)]

## Check out this video!

[Microsoft Cloud App Security – REST API's and Tokens](https://channel9.msdn.com/Shows/Microsoft-Security/Microsoft-Cloud-App-Security--REST-APIs-and-Tokens)
