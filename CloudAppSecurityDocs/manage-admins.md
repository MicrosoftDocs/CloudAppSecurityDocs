---
# required metadata

title: Manage admin access to the Cloud App Security portal | Microsoft Docs
description: This topic provides instructions for setting access to the Cloud App Security portal for your admins.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 7/31/2017
ms.topic: get-started-article
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: b718edad-350c-4d90-b045-92529d701dc5

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

## Managing admin access

Cloud App Security supports Role based access control. By default, the following Office 365 and Azure AD admin roles have access to Cloud App Security:

- Global administrator and Security administrator: Admins with **Full access** will have full permissions in Cloud App Security to add admins, add policies and settings, upload logs and perform governance actions.

- Security reader: Has read-only permissions and can manage alerts. The Security reader is restricted from performing the following:
      - Create policies or edit and change existing ones 
      - Performing any governance actions 
      - Uploading discovery logs
      - Banning or approving third party apps
      - Accessing and viewing the IP address range settings page
      - Accessing and viewing any settings pages 
      - Accessing and viewing the Discovery settings 
      - Accessing and viewing the App connectors page
      - Accessing and viewing the Governance log 
      - Accessing and viewing the Manage snapshot reports page 

For more information see [Assigning administrator roles in Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-assign-admin-roles).

You can also add additional admins to Cloud App Security, without adding users to Azure Active Directory administrative roles, by performing the following:

1. Click the settings cog ![settings icon](./media/settings-icon.png "settings icon") and then **Manage admin access**. 

2. Add the admins who should have access to Cloud App Security.
  
      
3. Next, click the drop down to set what type of access the admin will have, **Full access** or **Read only and manage alerts**.

     >[!NOTE]
      >Any admin whose access is limited to **Read only and manage alerts** who attempts to access a restricted page or perform a restricted action will receive an error that they don't have permission to access the page or perform the action.

   ![manage admin access](./media/manage-admin-access.png "manage admin access")  

4. Click **Close**.  

   >[!NOTE]
    >Only Global administrators or Security administrators can grant access to other users to Cloud App Security.
  
**To override admin permissions:**

If you want to override an administrator's permission from Azure Active Directory or Office 365, you can do so by manually adding the user to Cloud App Security and assigning the user permissions.
For example, if you want to assign Stephanie, who is a Security reader in Azure Active Directory to have **Full access** in Cloud App Security, you can add her manually to Cloud App Security and assign her **Full access** to override her role and allow her the desired permissions in Cloud App Security. 


To add additional admins to Cloud App Security:
1. Click the settings cog ![settings icon](./media/settings-icon.png "settings icon") and then **Manage admin access**. 

2. Add the admins who should have access to Cloud App Security, select their access level and click **Close**.



## See Also  
[Set up Cloud Discovery](set-up-cloud-discovery.md)   
[For technical support, please visit the Cloud App Security assisted support page.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  