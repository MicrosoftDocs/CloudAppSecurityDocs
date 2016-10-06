---
title: "Enable instant visibility, protection and governance actions for your apps"
ms.custom: na
ms.date: "09/25/2016"
ms.prod: "identity-cas"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "get-started-article"

ms.assetid: 3b15ba46-ac9c-4b4f-aefc-137edc903bc1
caps.latest.revision: 30
author: "Rkarlin"
ms.author: "rkarlin"
robots: noindex,nofollow
---
# Enable instant visibility, protection and governance actions for your apps
  App connectors leverage the APIs of app providers to enable greater visibility and control by [!INCLUDE[Adallom](./includes/adallom_md.md)] over the apps you connect to.  
  
 [!INCLUDE[Adallom](./includes/adallom_md.md)] leverages the APIs provided by the cloud provider, each service has its own framework and API limitations. [!INCLUDE[Adallom](./includes/adallom_md.md)] worked with the services to optimize the usage of the APIs and to ensure the best performance. Taking into account the different limitations the services impose on the APIs (such as throttling, API limits, dynamic time-shifting API windows, etc.), the [!INCLUDE[Adallom](./includes/adallom_md.md)] engines leverage the allowed capacity. Some operations, such as scanning of all files in the tenant, require a large amount of APIs and therefore are spread over a longer period. Expect some policies to run for several hours or several days.  
  
 **ExpressRoute**  
  
 [!INCLUDE[Adallom](./includes/adallom_md.md)] is deployed in Azure and fully integrated with [ExpressRoute](https://azure.microsoft.com/en-us/documentation/articles/expressroute-introduction/). All interactions with the [!INCLUDE[Adallom](./includes/adallom_md.md)] apps and traffic sent to [!INCLUDE[Adallom](./includes/adallom_md.md)], including upload of discovery logs, is routed via ExpressRoute **public peering** for improved latency, performance and security. There are no configuration steps required from the customer side.  
For more information about  Public Peering, see [ExpressRoute circuits and routing domains](https://azure.microsoft.com/en-us/documentation/articles/expressroute-circuit-peerings/).  
  
## How it works  
 [!INCLUDE[Adallom](./includes/adallom_md.md)] is deployed with system admin privileges to allow full access to all objects in your environment.  
  
 The App Connector flow is as follows:
 1. Cloud App Security scans and saves Authentication permissions.
 2.  Cloud App Security requests the user list. The first time this is performed, it may take some time until the scan completes. After the user scan is over, Cloud App Security moves on to activities and files. As soon as the scan starts, some activities will be available in Cloud App Security. 
 4. After completion of the user request, Cloud App Security periodically scans users, groups, activities and files. All activities will be available after the first full scan. 
 
 This may take some time, depending on the size of the tenant, the number of users and the size and number of files that need to be scanned. 
 
 Depending on the app you are connecting to (see table, below) API connection enables the following:  
  
-   **Account information:**  
  
     Visibility into users, accounts, profile information, status (suspended, active, disabled) groups, and privileges.  
  
-   **Audit trail:**  
  
     Visibility into user activities, admin activities, log on activity.  
  
-   **Data scan:**  
  
     Scanning of unstructured data using two processes -periodically (every 12 hours) and in real-time scan (triggered each time a change is detected).  
  
-   **App permissions:**  
  
     Visibility into issued tokens and their permissions.  
  
-   **Account governance:**  
  
     Ability to suspend users, revoke passwords, etc.  
  
-   **Data Governance:**  
  
     Ability to quarantine files, including files in trash, and overwrite files.  
  
-   **App permission governance:**  
  
     Ability to remove tokens.  
  
 The following table lists, per cloud app, which abilities are supported with App connectors:  
  
||||||||||  
|-|-|-|-|-|-|-|-|-|  
||**Office 365**|**Box**|**Okta**|**Google Apps**|**Service Now**|**Salesforce**|**Dropbox**|**AWS**|  
|**List accounts**|✔|✔|✔|✔|✔|✔|✔|✔|  
|**Group**|✔|✔|✔|✔|✔|✔|✔|✔|  
|**Privileges**|✔|✔|Not supported by provider|✔|✔|✔|✔||  
|**User governance**|✔|✔||✔|Coming soon|Coming soon|Coming soon||  
|**Log on activity**|✔|✔|✔|✔|✔|✔|✔|✔|  
|**User activity**|✔*|✔|✔|✔ - requires Google Unlimited|Partial|Salesforce Shield support coming soon|✔|Not applicable|  
|**Administrative activity**|✔|✔|✔|✔|Partial|✔|✔|✔|  
|**Periodic file scan**|✔|✔|Not applicable|✔|✔|✔|✔|Coming soon|  
|**Near-realtime file scan**|Coming soon|✔|Not applicable|✔ - requires Google Unlimited|||Coming soon||  
|**Sharing control**|✔|✔|Not applicable|✔|Not applicable||✔||  
|**Quarantine**|✔|✔|Not applicable|Coming soon|||Coming soon||  
|**View app permissions**|✔|Not supported by provider|Not applicable|✔||✔|Not supported by provider||  
|**Revoke app permissions**|✔||Not applicable|✔||✔|Not applicable||  
  
 \* The Office 365 App Connector includes admin activity for Exchange Online. To add user activity for Exchange Online, you will need to deploy the Exchange Online connector separately.  
  
## Prerequisites  
 For some apps, it may be necessary to add the following IP addresses to the whitelist to enable [!INCLUDE[Adallom](./includes/adallom_md.md)] to collect logs and provide access for the [!INCLUDE[Adallom](./includes/adallom_md.md)] console:  
  
-   For the logs:  
  
     104.209.35.177  
  
     13.91.98.185  
  
-   For the console:  
  
     104.42.231.28  
  
> [!NOTE]  
>  To get updates when URLs and IP addresses are changed, subscribe to the RSS as explained in: [Office 365 URLs and IP address ranges](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US).  
  
 To use App Connectors, you need to make sure you have the following for each specific app:  
  
|App|License type|User|  
|---------|------------------|----------|  
|Box|Enterprise|Admin, Co-Admin (When connecting as a Co-Admin files owned by other admins will not be scanned.)|  
|Google Apps|Google Apps Unlimited preferred<br /><br /> Google Apps Enterprise (minimally)|Super Admin|  
|Office 365||Global Admin|  
|AWS||Newly created user|  
|Dropbox|Business/Enterprise|Admin|  
|Okta|Enterprise (not trial)|Admin|  
|Exchange||Global Admin|  
|ServiceNow|Eureka and up|Admin +RestAPI role|  
|Salesforce||Admin|  
  
  