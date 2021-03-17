---
title: Troubleshooting Cloud App Security policies
description: This article describes the process for troubleshooting policy creation in Cloud App Security.
ms.date: 12/10/2018
ms.topic: conceptual
---
# Troubleshooting Microsoft Cloud App Security policies

[!INCLUDE [Banner for top of topics](includes/banner.md)]

This article describes the process for troubleshooting policy creation in Cloud App Security.

## Troubleshooting

The following chart has the description and resolution for errors you might see for policies.

|Error|Description|Resolution|
|----|----|----|
| **The policy  <*name*> was automatically disabled due to a configuration error**|If you get this error in Microsoft Cloud App Security, it means that you need to fix the configuration of the indicated policy. When you create a Microsoft Cloud App Security policy, you often make use of other objects created within Cloud App Security or the Security and Compliance Center such as IP tags or custom sensitive types. If the IP tag or custom sensitive type you used in the policy is deleted, the policy will automatically be disabled, and you'll receive this error. This message might also indicate a more general configuration error such as a filter that is too complex. |To restore the policy, edit the policy and fix every configuration error mentioned. This error usually means you need to remove any deleted objects from the policy filters and save the policy.|

## Next steps

> [!div class="nextstepaction"]
> [Control cloud apps with policies](control-cloud-apps-with-policies.md)

[!INCLUDE [Open support ticket](includes/support.md)]
