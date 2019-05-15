---
# required metadata

title: Connect apps to get visibility and control - Cloud App Security | Microsoft Docs
description: This article describes the process for connecting apps with API connectors to apps in your organization's cloud.
keywords:
author: rkarlin
ms.author: rkarlin
manager: barbkess
ms.date: 3/10/2019
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: 3b15ba46-ac9c-4b4f-aefc-137edc903bc1

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: seodec18

---
# Connect apps 

*Applies to: Microsoft Cloud App Security*

App connectors use the APIs of app providers to enable greater visibility and control by Microsoft Cloud App Security over the apps you connect to.  

Microsoft Cloud App Security leverages the APIs provided by the cloud provider. Each service has its own framework and API limitations such as throttling, API limits, dynamic time-shifting API windows, and others. Microsoft Cloud App Security worked with the services to optimize the usage of the APIs and to provide the best performance. Taking into account different limitations services impose on the APIs, the Cloud App Security engines use the allowed capacity. Some operations, such as scanning all files in the tenant, require numerous APIs so they're spread over a longer period. Expect some policies to run for several hours or several days.  

## Multi-instance support

Cloud App Security supports multiple instances of the same connected app. For example, if you have more than one instance of Salesforce (one for sales, one for marketing) you can connect both to Cloud App Security. You can manage the different instances from the same console to create granular policies and deeper investigation. This support applies only to API connected apps, not to Cloud Discovered apps or Proxy connected apps.

> [!NOTE]
> Multi-instance is not supported for Office 365 and Azure.

## How it works  
Cloud App Security is deployed with system admin privileges to allow full access to all objects in your environment.  

The App Connector flow is as follows:

1. Cloud App Security scans and saves authentication permissions.
2. Cloud App Security requests the user list. The first time the request is done, it may take some time until the scan completes. After the user scan is over, Cloud App Security moves on to activities and files. As soon as the scan starts, some activities will be available in Cloud App Security.
3. After completion of the user request, Cloud App Security periodically scans users, groups, activities, and files. All activities will be available after the first full scan.

This connection may take some time depending on the size of the tenant, the number of users, and the size and number of files that need to be scanned. 

Depending on the app to which you're connecting, API connection enables the following items:  

- **Account information** - Visibility into users, accounts, profile information, status (suspended, active, disabled) groups, and privileges.  

- **Audit trail** - Visibility into user activities, admin activities, sign in activity.  

- **Data scan** - Scanning of unstructured data using two processes -periodically (every 12 hours) and in real-time scan (triggered each time a change is detected).  

- **App permissions** - Visibility into issued tokens and their permissions.  

- **Account governance** - Ability to suspend users, revoke passwords, etc.  

- **Data Governance** - Ability to quarantine files, including files in trash, and overwrite files.  

- **App permission governance** - Ability to remove tokens.  

The following table lists, per cloud app, which abilities are supported with App connectors:  

> [!div class="mx-tableFixed"]
> 
> ||**Office 365**|**Box**|**Okta**|**G Suite**|**Service Now**|**Salesforce**|**Dropbox**|**AWS**|  
> |-|-|-|-|-|-|-|-|-|  
> |**List accounts**|✔|✔|✔|✔|✔|✔|✔|✔|  
> |**Group**|✔|✔|✔|✔|✔|✔|✔|✔|  
> |**Privileges**|✔|✔|Not supported by provider|✔|✔|✔|✔||  
> |**User governance**|✔|✔||✔|Coming soon|Coming soon|Coming soon||  
> |**Log on activity**|✔|✔|✔|✔|✔|✔|✔|✔|  
> |**User activity**|✔*|✔|✔|✔ - requires Google Business or Enterprise|Partial|Supported with Salesforce Shield|✔|Not applicable|  
> |**Administrative activity**|✔|✔|✔|✔|Partial|✔|✔|✔|  
> |**Periodic file scan**|✔|✔|Not applicable|✔|✔|✔|✔|Not applicable|  
> |**Near-realtime file scan**|✔|✔|Not applicable|✔ - requires Google Business or Enterprise|||Coming soon||  
> |**Sharing control**|✔|✔|Not applicable|✔|Not applicable||✔||  
> |**Quarantine**|✔|✔|Not applicable|Coming soon|||Coming soon||  
> |**View app permissions**|✔|Not supported by provider|Not applicable|✔||✔|Not supported by provider||  
> |**Revoke app permissions**|✔||Not applicable|✔||✔|Not applicable||  
> |**Apply Azure Information Protection labels**|✔|✔||✔|||||  

## Prerequisites  

- For some apps, it may be necessary to white list IP addresses to enable Cloud App Security to collect logs and provide access for the Cloud App Security console. For more information, see [Network requirements](network-requirements.md).

- For each app that you want to connect with the Cloud App Security API integration, we recommend creating an admin service account dedicated to Cloud App Security.  

> [!NOTE]  
>  To get updates when URLs and IP addresses are changed, subscribe to the RSS as explained in: [Office 365 URLs and IP address ranges](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2).  

To use App Connectors, you need to make sure you have the following things for each specific app:  

|App|License type|User|  
|---------|------------------|----------|  
|Box|Enterprise|It's strongly recommended that you connect to Box as an Admin. Connecting as a Coadmin will result in only partial data visibility. If you connect as a Coadmin, make sure to select all permissions.|  
|G Suite|G Suite Business or Enterprise preferred<br /><br /> G Suite Enterprise (minimally)|Super Admin|  
|Office 365||Global Admin|  
|AWS||Newly created user|  
|Dropbox|Business/Enterprise|Admin|  
|Okta|Enterprise (not trial)|Admin|  
|Exchange||Global Admin|  
|ServiceNow|Eureka and up|Admin +RestAPI role|  
|Salesforce||Admin|  


**ExpressRoute**

Cloud App Security is deployed in Azure and fully integrated with [ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-introduction/). All interactions with the Cloud App Security apps and traffic sent to Cloud App Security, including upload of discovery logs, is routed via ExpressRoute **public peering** for improved latency, performance, and security. There are no configuration steps required from the customer side.  
For more information about  Public Peering, see [ExpressRoute circuits and routing domains](https://azure.microsoft.com/documentation/articles/expressroute-circuit-peerings/).  

## Next steps
 
[Daily activities to protect your cloud environment](daily-activities-to-protect-your-cloud-environment.md)   

[Premier customers can also create a new support request directly in the Premier Portal.](https://premier.microsoft.com/)  

## Check out this video!

[Microsoft Cloud App Security – REST API’s and Tokens](https://channel9.msdn.com/Shows/Microsoft-Security/Microsoft-Cloud-App-Security--REST-APIs-and-Tokens)  
