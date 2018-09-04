---
# required metadata

title: Connect Azure to Cloud App Security for visibility and control over use | Microsoft Docs
description: This topic provides information about how to connect Azure to Cloud App Security using the API connector.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 5/23/2018
ms.topic: conceptual
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: 3a677bc7-c8b7-4c6a-aada-82c8b3778352


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


# Connect Azure to Microsoft Cloud App Security

This section provides instructions for connecting Microsoft Cloud App Security to your existing Azure account using the app connector API.  
  
## How to connect Azure to Cloud App Security  
  
> [!NOTE]
> - User must be a Global administrator in Azure AD to connect Azure to Microsoft Cloud App Security. 
> - Cloud App Security displays activities from **all** subscriptions.
>-  Currently, Cloud App Security monitors only ARM activities. 
 
1.  In **Connected apps** page, click the plus button and select **Microsoft Azure**.  
  
     ![connect Azure](./media/connect-azure-menu.png) 

2.  In the Azure pop-up, click **Connect Microsoft Azure**.

      ![connect Azure](./media/connect-azure.png) 
 
> [!NOTE] 
> After connecting Azure, data will be pulled. You will see data from then onwards.


## See Also  
[Control cloud apps with policies](control-cloud-apps-with-policies.md)   

[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  