---
# required metadata

title: Visibility into cloud app accounts | Microsoft Docs
description: This topic pro.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 4/23/2016
ms.topic: article
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: 7811f23b-6100-427f-93b1-44f5f81f6c76

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---
# Accounts
Cloud App Security gives you visibility into all the accounts from your connected apps. After you connect Cloud App Security to an app using the App connector, Cloud App Security scans all the accounts associated with the apps. The Accounts page enables you to investigate those accounts, the groups they are members of, their aliases and the apps they are using. 


The **Accounts** log can be filtered to enable you to find specific accounts and to deep dive into different types of accounts, for example, you can filter for all External accounts that have not been accessed since last year. You can create policies based on the accounts and then define what you want to be alerted about and act on. 

The **Accounts** page enables you to easily investigate your accounts for issues including the following:  

-   Check if any accounts have been inactive in a particular service for a long time (Maybe you should revoke the license for that user to that service)  
-   You can filter for the list of users with admin permissions  

-   You can view which accounts are active but belong to users who are no longer part of your organization  

-   You can revoke a user's permission to a specific app (depending on the app) or require a specific user to perform multi-factor authentication
    
-   You can see which accounts are included in each user group  

-   You can see which apps are accessed by each account and which apps are deleted for specific accounts
    
-   You can also drill down into the user's account and select relevant governance actions, such as **Suspend user** or **Remove user's collaborations**. If the user was imported from Azure Active Directory, you can also click on **Azure AD account settings** to get easy access to advanced user management features like group management, multi-factor authentication, details about the user's sign ins and the ability to block sign in.

![accounts screen](./media/accounts-page.png)

## Account filters
Below is a list of the account filters that can be applied. Most filters support multiple values as well as NOT, in order to provide you with a very powerful tool for policy creation.  
  
- **Account name**: The account name is the primary alias of the user, but other identifiers from other Microsoft accounts (Office 365 and Azure Active Directory) such as proxy addresses, aliases, SID are supported and consolidated beneath the primary alias.

- **Affiliation**: The affiliation will be either **Internal** or **External**. To set which users and accounts are internal, under **Settings** make sure to set the **IP address range** of your internal organization. In the event that the account has admin permissions the icon in the Accounts table will appear with the addition of the red tie ![accounts admin icon](./media/accounts-admin-icon.png).

- **App**: You can filter for any API connected app being used by accounts in your organization.

- **Domain**: Enables you to filter for users in specific domains.

- **Last seen**: The **last seen** filter enables you to find accounts that are dormant and whose users haven't performed any activities in a while.

- **Organization/Department**: Enables you to filter for members of specific Azure Active Directory or Office 365 organizational groups.

- **User group**: Enables you to filter for members of user groups in Cloud App Security - both built-in user groups and imported user groups.


## See Also  
[Daily activities to protect your cloud environment](daily-activities-to-protect-your-cloud-environment.md)   
[For technical support, please visit the Cloud App Security assisted support page.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  