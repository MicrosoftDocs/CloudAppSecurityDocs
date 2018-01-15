---
# required metadata

title: Troubleshooting Cloud App Security policies | Microsoft Docs
description: This topic describes the process for troubleshooting policy creation in Cloud App Security.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/15/2018
ms.topic: get-started-article
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: 828cc94a-248b-44f6-a1ba-c28c0a135f8c

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Troubleshooting Cloud App Security policies

|Error|Description|Resolution|
|----|----|----|
| **The policy <policy name> was automatically disabled due to a configuration error.**|If you get this error in Cloud App Security, it means that you need to fix the configuration of the policy named. When you create a Cloud App Security policy, you often make use of other objects that you created within Cloud App Security, such as IP tags or an IP range filters. If the IP tag or range you used in the policy is subsequently deleted, the policy will automatically be disabled, and you will receive this error. |In order to restore the policy, edit the policy and remove any deleted objects from its filters, and save the policy.|



## See Also
[Control cloud apps with policies](control-cloud-apps-with-policies.md)

[Premier customers can also choose Cloud App Security directly from the Premier Portal](https://premier.microsoft.com/)

