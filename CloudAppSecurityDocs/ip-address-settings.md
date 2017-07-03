---
# required metadata

title: Connect apps to get deep visibility and control with Cloud App Security | Microsoft Docs
description: This topic describes the process for connecting apps with API connectors to apps in your organization's cloud.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 7/3/2017
ms.topic: get-started-article
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: 7e718d77-aae7-4a3a-8421-5ba7cee7d67c

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

 
Cloud App Security requires access as follows to connect to your network. 

## Cloud App Security System IP addresses

The following IP addresses are used by Cloud App Security to connect to customer environments. This is necessary when connecting using [ICAP](icap-stunnel.md) and when connecting App connectors. For some apps, it may be necessary to add the following IP addresses to the whitelist to enable Cloud App Security to collect logs and provide access for the Cloud App Security console. In some apps these IP addresses can also be used to identify Cloud App Security activities, such as in the service’s audit logs. 
  
-   For the logs:  
  
    104.209.35.177  
  
    13.91.98.185
 
    40.118.211.172

    13.93.216.68

    13.91.61.249

    13.93.233.42

    13.64.196.27

    13.64.198.97

    13.64.199.41

    13.64.198.19
  
  
## CAS portal URL and IP addresses

The Cloud App Security URL, port 443 and IP addresses are used for customer access to portal, API connections when connecting to the CAS APIs, Log collector and SIEM agent. 
  
     104.42.231.28  

 
  
> [!NOTE]  
>  To get updates when URLs and IP addresses are changed, subscribe to the RSS as explained in: [Office 365 URLs and IP address ranges](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2).  
  

  
## See Also  
[Daily activities to protect your cloud environment](daily-activities-to-protect-your-cloud-environment.md)   
[For technical support, please visit the Cloud App Security assisted support page.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  

   