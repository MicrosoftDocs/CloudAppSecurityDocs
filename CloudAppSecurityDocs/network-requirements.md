---
# required metadata

title: Cloud App Security Network requirements | Microsoft Docs
description: This topic describes the IP addresses and ports you need to open to work with Cloud App Security.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 8/27/2017
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

This topic provides a list of ports and IP addresses you need to allow and whitelist in order to work with Cloud App Security. 


## Portal access

For portal access it is necessary to add the following IP addresses to your firewall's whitelist to provide access for the Cloud App Security portal:  
  
104.42.231.28  


## App connector access

For some third-party apps to be accessed by Cloud App Security, it may be necessary to add the following IP addresses to the whitelist to enable Cloud App Security to collect logs and provide access for the Cloud App Security console:  
  
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

> [!NOTE]
>You may see these IP addresses in activity logs from the vendor because Cloud App Security performs governance actions and scans from these IP addresses. 
  

## SIEM agent and Log collector

To enable Cloud App Security to connect to your SIEM and to enable the Cloud App Security log collector to run, it is necessary to open:

- Outbound port 443 to 104.42.231.28

## External DLP integration

In order for Cloud App Security to send data through your stunnel to your ICAP server, open your DMZ firewall to the external IP addresses used by Cloud App Security with a dynamic source port number. 

1.	Source addresses: these should be whitelisted as listed above for API connector third-party apps
2.	Source TCP port: Dynamic
3.	Destination address(es): one or two IP address of the stunnel connected to the external ICAP server
4.	Destination TCP port: As defined in your network

> [!NOTE] 
> By default the stunnel port number is set to 11344. You can change it to another port if necessary, but be sure to make note of the new port number.



  
## See Also  
[Daily activities to protect your cloud environment](daily-activities-to-protect-your-cloud-environment.md)   
[For technical support, please visit the Cloud App Security assisted support page.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  

   