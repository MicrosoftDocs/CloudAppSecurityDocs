---
# required metadata

title: Integrate Azure Advanced Threat Protection with Cloud App Security
description: This article provides information about how to leverage Azure Advanced Threat Protection insights in Cloud App Security for hybrid risk detection.
keywords:
author: rkarlin
ms.author: rkarlin
manager: rkarlin
ms.date: 6/21/2019
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: 63e82b47-bb08-4614-af55-f85d04edfc5a


# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: seodec18

---

# Azure Information Protection integration

*Applies to: Microsoft Cloud App Security*

Microsoft Cloud App Security integrates with Azure Advanced Threat Protection (Azure ATP) to provide user entity behavioral analytics (UEBA) across a hybrid environment - both cloud app and on-premises. For more information about the machine learning and behavioral analytics provided by Azure ATP, see [What is Azure ATP?](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp).

By integrating with Azure ATP, your Cloud App Security portal will provide alerts and insights from:
- Microsoft Cloud App Security, which identifies attacks within a cloud session, covering not only Microsoft products but also third-party applications
- Azure Advanced Threat Protection, which uses machine learning and behavioral analytics to identify attacks across your on-premises network
- Azure Active Directory Identity Protection, which detects and proactively prevents user and sign-in risks to identities in the cloud


## Prerequisites

For complete user investigation across a hybrid environment, you must have:

- A valid license for Microsoft Cloud App Security
- A valid license for Azure ATP connected to your Active Directory instance

>[!NOTE]
>If you don't have a subscription for Azure ATP, you will still be able to use the Cloud App Security portal to investigate users, but you won't receive insights from your on-premises environment.


## Enable Azure Advanced Threat Protection

All you have to do to integrate Azure Advanced Threat Protection with Cloud App Security is click a single checkbox. By enabling integration, you allow Cloud App Security to access and analyze the on-premises suspicious activities seen by Azure ATP, pull them  into the Cloud App Security and provide you with a full picture of your hybrid environment and all the risky activities performed by your users.

To enable Cloud App Security to integrate with Azure ATP:

1. In Cloud App Security, under the settings cog, select **Settings**.
    ![Settings menu](./media/azip-system-settings.png)
1. Under **Threat Protection**, select **Azure ATP**.
    ![enable azure advanced threat protection](./media/aatp-integration.png)
3. Select the checkbox to **Connect Azure ATP data including alerts and activities with Cloud App Security**.
 
After enabling Azure Advanced Threat Protection integration, you'll be able to see on-premises activities for all the users in your organization. You will also get advanced insights on your users that combine alerts and suspicious activities across your cloud and on-prem environments.



Learn more about [Investigating risky users](tutorial-ueba.md).


## Next steps 
[Control cloud apps with policies](control-cloud-apps-with-policies.md)   

[Premier customers can also create a new support request directly in the Premier Portal.](https://premier.microsoft.com/)  
  
