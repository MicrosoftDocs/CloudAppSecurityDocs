---
title: include file
description: include file
ms.collection: M365-security-compliance
ms.service: defender-for-cloud-apps
author: batamig
ms.topic: include
ms.date: 12/31/2023
ms.author: bagol
ms.custom: include file
---

### Sample: Create Microsoft Entra ID Conditional Access policies for use with Defender for Cloud Apps

This procedure provides a high-level example of how to create a Conditional Access policy for use with Defender for Cloud Apps.

1. In Microsoft Entra ID Conditional Access, select **Create new policy**.

1. Enter a meaningful name for your policy, and then select the link under **Session** to add controls to your policy.

1. In the **Session** area, select **Use Conditional Access App Control**.

1. In the **Users** area, select to include all users, or specific users and groups only.

1. In the **Conditions** and **Client apps** areas, select the conditions and client apps that you want to include in your policy.

1. Save the policy by toggling **Report-only** to **On**, and then selecting **Create**.

Microsoft Entra ID supports both browser-based and non browser-based policies. We recommend that you create both types for increased security coverage.

Repeat this procedure to create a nonbrowser based Conditional Access policy. In the **Client apps** area, toggle the **Configure** option to **Yes**. Then, under **Modern authentication clients**, clear the **Browser** option. Leave all other default selections selected.

Note: The Enterprise application “Microsoft Defender for Cloud Apps – Session Controls” is used internally by the Conditional Access App Control service. 
Please ensure the CA policy does not restrict access to this application in the **Target resources**. 

For more information, see [Conditional Access policies](/azure/active-directory/conditional-access/overview) and [Building a Conditional Access policy](/entra/identity/conditional-access/concept-conditional-access-policies).
