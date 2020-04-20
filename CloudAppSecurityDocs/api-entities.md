---
# required metadata
title: Cloud App Security Entities API
description: This article provides information about using the Entities API.
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
# Entities API

*Applies to: Microsoft Cloud App Security*

The Entities API provides you with basic information about the users and accounts using your organization’s cloud apps, allowing you to understand service use patterns.

The following is a list of entity requests:

- [List entities](api-entities-list.md)
- [Fetch entity](api-entities-fetch.md)
- [Fetch entity tree](api-entities-fetch-tree.md)

## Filters

For information about how filters work, see [Filters](api-introduction.md#filters).

The following is a list of supported filters:

| Filter | Type | Operators | Description |
| --- | --- | --- | --- |
| type| string | eq, neq | Filter entities by their type |
| isAdmin | string | eq | Filter entities that are admins |
| entity | entity pk | eq, neq | Filter entities with specific entities pks. If a user is selected, will also return all of it’s accounts. Example: `[{ “id”: “entity-id”, “saas”: 11161, “inst”: 0 }]` |
| userGroups |string | eq, neq | Filter entities by their associated group IDs |
| app | integer | eq, neq | Filter entities using services with the specified saas id for example: 11770 |
| instance | integer | eq, neq | Filter entities using services with the specified Appstances (SaaS Id and Instance Id), for example: 11770, 1059065 |
| isExternal | boolean | eq | The entity’s affiliation. Possible values include:<br /><br />**true**: External<br />**false**: Internal<br />**null**: No value |
| domain | string | eq, neq, isset, isnotset | The entity’s related domain |
| organization | string | eq, neq, isset, isnotset | Filter entities with the specified organization unit |
| lastSeen | timestamp | lte, gte, | range Filter entities that were last seen between the given dates |
| status | string | eq, neq | Filter entities by status. Possible values include:<br /><br />**0**: N/A<br />**1**: Staged<br />**2**: Active<br />**3**: Suspended<br />**4**: Deleted |
| score | integer | lt, gt, isset, isnotset | |

[!INCLUDE [Open support ticket](includes/support.md)]
