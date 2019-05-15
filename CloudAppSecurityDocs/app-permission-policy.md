---
# required metadata

title: Create policies to control OAuth apps in Cloud App Security
description: This article provides instructions for creating and working with app permission policies in Microsoft Cloud App Security.
keywords:
author: rkarlin
ms.author: rkarlin
manager: angrobe
ms.date: 12/10/2018
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: 9f68302c-bb3d-450c-bbf5-f8130cb163e3

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: seodec18

---
# OAuth app policies

*Applies to: Microsoft Cloud App Security*

In addition to the [existing investigation of OAuth apps](manage-app-permissions.md) connected to your environment, you can set permission policies to so that you get automated notifications when an OAuth app meets certain criteria. For example, you can automatically be alerted when there are apps that require a high permission level and were authorized by more than 50 users. 

OAuth app policies enable you to investigate which permissions each app requested and which users authorized them for Office 365, G Suite, and Salesforce. You're also able to mark these permissions as approved or banned. Marking them as banned will revoke permissions for each app for each user who authorized it. 

## Create a new OAuth app policy
There are two ways to create a new OAuth app policy. The first way is under **Investigate** and the second is under **Control**. 

To create a new OAuth app policy:

1. Under **Investigate** select **OAuth app**.
2. Filter the apps according to your needs, for example, you can view all apps that request **Permission** to **Modify calendars in your mailbox**.
3. Click the **New policy from search** button. 
    ![new policy from search](./media/app-permissions-filter.png)
4. You can use the **Community use** filter to get information on whether allowing permission to this app is common, uncommon, or rare. This filter can be helpful if you have an app that's rare and requests permission that has a high severity level or requests permission from many users. 
5. You can set the policy based on the group memberships of the users who authorized the apps. For example, an admin can decide to set a policy that revokes uncommon apps if they ask for high permissions, only if the user who authorized the permissions is a member of the administrators group.

Alternatively, you can also create the policy by clicking **Control** followed by **Policies**. Then click **Create policy** followed by **OAuth app policy**.

  
   ![new OAuth app policy](./media/app-permissions-policy.png)



  ## Next steps 
  [Data protection policies](data-protection-policies.md)   

[Premier customers can also create a new support request directly in the Premier Portal.](https://premier.microsoft.com/)  
  
  
