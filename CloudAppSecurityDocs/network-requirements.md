---
# required metadata

title: Cloud App Security Network requirements | Microsoft Docs
description: This topic describes the IP addresses and ports you need to open to work with Cloud App Security.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 9/27/2017
ms.topic: get-started-article
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: 4de606f2-a09e-4e48-a578-e223de8b5e69

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Network requirements

This topic provides a list of ports and IP addresses you need to allow and white list in order to work with Cloud App Security. 

For information on how to see which Cloud App Security data center you are connected to, see [API tokens](api-tokens.md)



## Portal access, SIEM agent, authentication gateway, and log collector

For portal and authentication gateway access, and to enable Cloud App Security to connect to your SIEM, as well as to enable the Cloud App Security log collector to run it is necessary to add **outbound port 443** for the following IP addresses to your firewall's white list:  


> [!div class="mx-tableFixed"]
|Data center|IP addresses|  
|----|----|
|US1|13.91.91.243<br></br>52.183.75.62|
|EU1|52.174.56.180<br></br>13.80.125.22|

## App connector access and external DLP integration

To connect to third-party apps and integrate with external DLP solutions, enable Cloud App Security from connect to these IP addresses:


> [!div class="mx-tableFixed"]
|Data center|IP addresses|  
|----|----|
|US1|104.209.35.177<br></br>13.91.98.185<br></br>40.118.211.172<br></br>13.93.216.68<br></br>13.91.61.249<br></br>13.93.233.42<br></br>13.64.196.27<br></br>13.64.198.97<br></br>13.64.199.41<br></br>13.64.198.19|
|EU1|13.80.22.71<br></br>13.95.29.177<br></br>13.95.30.46|


### App connector
For some third-party apps to be accessed by Cloud App Security, these IP addresses may be used to enable Cloud App Security to collect logs and provide access for the Cloud App Security console. 

> [!NOTE]
>You may see these IP addresses in activity logs from the vendor because Cloud App Security performs governance actions and scans from these IP addresses. 
  

### DLP integration

In order for Cloud App Security to send data through your stunnel to your ICAP server, open your DMZ firewall to these IP addresses with a dynamic source port number. 

1.	Source addresses: these should be white listed as listed above for API connector third-party apps
2.	Source TCP port: Dynamic
3.	Destination address(es): one or two IP address of the stunnel connected to the external ICAP server
4.	Destination TCP port: As defined in your network

> [!NOTE] 
> By default the stunnel port number is set to 11344. You can change it to another port if necessary, but be sure to make note of the new port number.

## Email server

The Cloud App Security dedicated email IP address is: 

198.2.134.139 (mail1.cloudappsecurity.com)

Make sure to whitelist this IP address with your anti-spam service to enable notifications to be sent.
    



  
## See Also  
[Daily activities to protect your cloud environment](daily-activities-to-protect-your-cloud-environment.md)   
[For technical support, please visit the Cloud App Security assisted support page.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  

   