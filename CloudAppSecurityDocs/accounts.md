---
# required metadata

title: Visibility into cloud app accounts | Microsoft Docs
description: This topic pro.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 4/20/2016
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

You can check the following:  

    -   Have any accounts been inactive in a particular service for a long time? (Maybe you can revoke the license for that user to that service?)  

    -   Do you want to know which users have a specific role?  

    -   Was someone fired but they still have access to an app and can use that access to steal information?  

    -   Do you want to revoke a user's permission to a specific app or require a specific user to perform multi-factor authentication?  
    
    -   You can also drill down into the user's account by clicking the three dots at the end of the user's account row and selecting an action to take, such as **Suspend user** or **Remove user's collaborations**. If the user was imported from Azure Active Directory, you can also click on **Azure AD account settings** to get easy access to advanced user management features like group management, MFA, details about the user's sign ins and the ability to block sign in.



## Account filters
Below is a list of the account filters that can be applied. Most filters support multiple values as well as NOT, in order to provide you with a very powerful tool for policy creation.  
  
- Account name: 

- Affiliation: The affiliation will be either **Internal** or **External**. To set which users and accounts are internal, under **Settings** make sure to set the **IP address range** of your internal organization. 

- App: 

- Domain: 

- Last seen: 

- Organization: 

- User group: 


## See Also  
[Daily activities to protect your cloud environment](daily-activities-to-protect-your-cloud-environment.md)   
[For technical support, please visit the Cloud App Security assisted support page.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  