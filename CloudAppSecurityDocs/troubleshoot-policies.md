---
# required metadata

title: Troubleshooting Cloud App Security policies | Microsoft Docs
description: This topic describes the process for troubleshooting policy creation in Cloud App Security.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 12/9/2018
ms.topic: conceptual
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

*Applies to: Microsoft Cloud App Security*


# Troubleshooting Microsoft Cloud App Security policies

|Error|Description|Resolution|
|----|----|----|
| **The policy <policy name> was automatically disabled due to a configuration error**|If you get this error in Microsoft Cloud App Security, it means that you need to fix the configuration of the policy that is indicated. When you create a Microsoft Cloud App Security policy, you often make use of other objects that you created within Cloud App Security or in the Security and Compliance Center, such as IP tags or custom sensitive types. If the IP tag or custom sensitive type you used in the policy is subsequently deleted, the policy will automatically be disabled, and you will receive this error. This might also indicate a more general configuration error such as a filter that is too complex. |In order to restore the policy, edit the policy and fix every configuration error mentioned. This usually means that you’ll need to remove any deleted objects from the policy filters and save the policy.|



## See Also
[Control cloud apps with policies](control-cloud-apps-with-policies.md)

[Premier customers can also choose Cloud App Security directly from the Premier Portal](https://premier.microsoft.com/)

