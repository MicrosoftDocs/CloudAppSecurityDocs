---
# required metadata

title: Enrich Cloud App Security Discovery data with Azure AD usernames | Microsoft Docs
description: This article provides information about how to enrich Cloud App Security Discovery data with Azure AD usernames.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/15/2018
ms.topic: article
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: 45295c2c-3e4d-4482-bf95-2e47072f9236

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Cloud Discovery enrichment

Cloud Discovery data can now be enriched with Azure Active Directory username data. When you enable this feature, the username received in the discovery traffic logs is matched and replaced by the Azure AD username enabling the following new features:
-	You can investigate Shadow IT usage by Azure Active Directory user.
-	You can correlate the Discovered cloud app use with the API collected activities.
-	You can then create custom logs based on Azure AD user groups. For example, a Shadow IT report for a specific Marketing department.


## Prerequisites:
- Data source must provide username information
- Office 365 app connector connected

## Enabling user data enrichment 
    
1. Under the Settings cog, select **Cloud Discovery settings**.
     
2. In the **User enrichment** tab, to enable Cloud App Security to use Azure Active Directory data to enrich usernames by default, select **Enrich discovered user identifiers with Azure Active Directory usernames**.

3. Click **Save**.
 
![Enrich Cloud App Security Discovery with Azure AD usernames](./media/discovery-enrichment.png)
  

  
      
## See Also  
[Control cloud apps with policies](control-cloud-apps-with-policies.md)   

[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
    
      
  