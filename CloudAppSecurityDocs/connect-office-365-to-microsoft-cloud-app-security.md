---
# required metadata

title: Connect Office 365 to Cloud App Security 
description: This article provides information about how to connect your Office 365 to Cloud App Security using the API connector for visibility and control over use.
keywords:
author: rkarlin
ms.author: rkarlin
manager: angrobe
ms.date: 3/5/2019
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: a79bf393-0d2c-44b6-8dab-86c740fd7333


# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: seodec18

---
# Connect Office 365 to Microsoft Cloud App Security

*Applies to: Microsoft Cloud App Security*

This article provides instructions for connecting Microsoft Cloud App Security to your existing Microsoft Office 365 account using the app connector API.  This connection gives you visibility into and control over Office 365 use.
  
Cloud App Security supports the legacy Office 365 Dedicated Platform as well as the latest offerings of Office 365 services (commonly referred as the vNext release family of Office 365).  Cloud App Security doesn't support the Legacy Microsoft Business Productivity Online Standard Suite (BPOS). 

> [!NOTE]
> In some cases, a vNext service release differs slightly at the administrative and management levels from the standard Office 365 offering.

Cloud App Security supports the following Office 365 apps:

- Office 365
- SharePoint
- OneDrive
- Teams (only appears after activities from Teams are detected in the portal)
- Power BI (only appears after activities from Power BI are detected in the portal, and requires you to turn on auditing)
- Exchange (only appears after activities from Exchange are detected in the portal, and requires you to turn on auditing)
- Dynamics 365
 
## How to connect Office 365 to Cloud App Security  
  
> [!NOTE]
>- You must have at least one assigned Office 365 license to connect Office 365 to Cloud App Security.
>- To enable monitoring of Office 365 activities in Cloud App Security, you are required to enable auditing in the [Office Security and Compliance Center](https://support.microsoft.com/help/4026501/office-auditing-in-office-365-for-admins).
>-  Exchange administrator audit logging, which is enabled by default in Office 365, logs an event in the Office 365 audit log when an administrator (or a user who has been assigned administrative privileges) makes a change in your Exchange Online organization. Changes made using the Exchange admin center or by running a cmdlet in Windows PowerShell are logged in the Exchange admin audit log. For more detailed information about admin audit logging in Exchange, see [Administrator audit logging](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/view-administrator-audit-log).
>- Exchange Mailbox audit logging must be turned on for each user mailbox before user activity in Exchange Online is logged, see [Exchange Mailbox activities](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).
>- If Office apps are enabled, groups that are part of Office 365 are also imported to Cloud App Security from the specific Office apps, for example if SharePoint is enabled, Office 365 groups are imported as SharePoint groups as well.
>- You must [enable auditing in PowerBI](https://powerbi.microsoft.com/documentation/powerbi-admin-auditing/) to get the logs from there. Once auditing is enabled, Cloud App Security starts getting the logs (with a delay of 24-72 hours).
> If your Azure Active Directory is set to automatically sync with the users in your Active Directory on-premises environment the settings in the on-premises environment override the Azure AD settings and use of the **Suspend user** governance action is reverted. 
 
1.  In **Connected apps** page, click the plus button and select **Office 365**.  

      ![connect 0365](./media/connect-0365.png) 

2.  In the Office 365 pop-up, click **Connect Office 365**.

      ![connect 0365](./media/office-connect.png) 
 
3.   After Office 365 is displayed as successfully connected, click **Close**.
  
> [!NOTE] 
> After connecting Office 365, you will see data from a week back including any third-party applications connected to Office 365 that are pulling APIs. For third-party apps that weren't pulling APIs prior to connection, you see events from the moment you connect Office 365, because Cloud App Security turns on any APIs that had been off by default.

## Next steps  
[Control cloud apps with policies](control-cloud-apps-with-policies.md)   

[Premier customers can also create a new support request directly in the Premier Portal.](https://premier.microsoft.com/)  
  
  
