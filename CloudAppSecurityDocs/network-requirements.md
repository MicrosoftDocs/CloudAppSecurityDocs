---
# required metadata

title: Cloud App Security Network requirements | Microsoft Docs
description: This topic describes the IP addresses and ports you need to open to work with Cloud App Security.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 8/30/2018
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
*Applies to: Microsoft Cloud App Security*


# Network requirements

This topic provides a list of ports and IP addresses you need to allow and white list in order to work with Microsoft Cloud App Security. 


## View your data center

Some of the requirements below depend on which data center you are connected to. 

To see which data center you are connecting to:

1. In the Cloud App Security portal, click the **?** in the menu bar and select **About**. 

    ![click About](./media/about-menu.png)

2. In the Cloud App Security version screen, you can see the region and the data center.

    ![View your data center](./media/data-center.png)

## Portal access

For access to the Cloud App Security portal, add **outbound port 443** for the following IP addresses and DNS names to your firewall's white list:  


> [!div class="mx-tableFixed"]
> 
> |Data center|IP addresses|DNS name|
> |----|----|----|
> |US|13.80.125.22<br></br>52.183.75.62<br></br>13.91.91.243|portal.cloudappsecurity.com<br></br>\*.portal.cloudappsecurity.com <br></br>\*.us.portal.cloudappsecurity.com|
> |US2|13.80.125.22<br></br>52.183.75.62<br></br>52.184.165.82|portal.cloudappsecurity.com<br></br>\*.portal.cloudappsecurity.com <br></br>\*.us2.portal.cloudappsecurity.com|
> |US3|13.80.125.22<br></br>52.183.75.62<br></br>40.90.218.198<br></br>40.90.218.196|portal.cloudappsecurity.com<br></br>*.portal.cloudappsecurity.com <br></br>*.us3.portal.cloudappsecurity.com|
> |EU|13.80.125.22<br></br>52.183.75.62<br></br>52.174.56.180|portal.cloudappsecurity.com<br></br>\*.portal.cloudappsecurity.com <br></br>\*.eu.portal.cloudappsecurity.com|
> |EU2|13.80.125.22<br></br>52.183.75.62<br></br>40.81.156.154<br></br>40.81.156.156|portal.cloudappsecurity.com<br></br>*.portal.cloudappsecurity.com <br></br>*.eu2.portal.cloudappsecurity.com|


> 
> [!NOTE]
> Instead of a wildcard (\*) you can open only your specific tenant URL, for example, based on the screenshot above you can open: mod244533.us.portal.cloudappsecurity.com

## SIEM agent connection

To enable Cloud App Security to connect to your SIEM, add **outbound port 443** for the following IP addresses to your firewall's white list:  


> [!div class="mx-tableFixed"]
> 
> |Data center|IP addresses|  
> |----|----|
> |US|13.91.91.243|
> |US2|52.184.165.82|
> |US3|40.90.218.198<br>40.90.218.196|
> |EU|52.174.56.180|
> |EU2|40.81.156.154<br>40.81.156.156|

## App connector

For some third-party apps to be accessed by Cloud App Security, these IP addresses may be used to enable Cloud App Security to collect logs and provide access for the Cloud App Security console. 

> [!NOTE]
>You may see these IP addresses in activity logs from the vendor because Cloud App Security performs governance actions and scans from these IP addresses. 

To connect to third-party apps, enable Cloud App Security to connect from these IP addresses:


> [!div class="mx-tableFixed"]
> 
> |Data center|IP addresses|  
> |----|----|
> |US|13.91.91.243 <br></br> 104.209.35.177 <br></br> 13.91.98.185 <br></br> 40.118.211.172 <br></br> 13.93.216.68 <br></br> 13.91.61.249 <br></br> 13.93.233.42 <br></br> 13.64.196.27 <br></br> 13.64.198.97 <br></br> 13.64.199.41 <br></br> 13.64.198.19|
> |US2|52.184.165.82<br></br> 40.84.4.93 <br></br> 40.84.4.119 <br></br> 40.84.2.83 |
> |US3|40.90.218.197<br>40.90.218.203|
> |EU|52.174.56.180<br></br>13.80.22.71<br></br>13.95.29.177<br></br>13.95.30.46|
> |EU2|40.81.156.155<br>40.81.156.153|


## Third-party DLP integration

In order for Cloud App Security to send data through your stunnel to your ICAP server, open your DMZ firewall to these IP addresses with a dynamic source port number. 

1.  Source addresses: these should be white listed as listed above for API connector third-party apps
2.  Source TCP port: Dynamic
3.  Destination address(es): one or two IP address of the stunnel connected to the external ICAP server
4.  Destination TCP port: As defined in your network

> [!NOTE] 
> -  By default the stunnel port number is set to 11344. You can change it to another port if necessary, but be sure to make note of the new port number.
> - You may see these IP addresses in activity logs from the vendor because Cloud App Security performs governance actions and scans from these IP addresses. 

To connect to third-party apps and integrate with external DLP solutions, enable Cloud App Security to connect from these IP addresses:

> [!div class="mx-tableFixed"]
> 
> |Data center|IP addresses|  
> |----|----|
> |US|13.91.91.243 <br></br> 104.209.35.177 <br></br> 13.91.98.185 <br></br> 40.118.211.172 <br></br> 13.93.216.68 <br></br> 13.91.61.249 <br></br> 13.93.233.42 <br></br> 13.64.196.27 <br></br> 13.64.198.97 <br></br> 13.64.199.41 <br></br> 13.64.198.19|
> |US2|52.184.165.82<br></br> 40.84.4.93 <br></br> 40.84.4.119 <br></br> 40.84.2.83 |
> |US3|40.90.218.197<br>40.90.218.203|
> |EU|52.174.56.180<br></br>13.80.22.71<br></br>13.95.29.177<br></br>13.95.30.46|
> |EU2|40.81.156.155<br>40.81.156.153|

## Mail server

To enable notifications to be sent from the default template and settings, add these IP addresses to your anti-spam whitelist. The Cloud App Security dedicated email IP addresses are: 

- 65.55.234.192/26
- 207.46.200.0/27
- 65.55.52.224/27
- 94.245.112.0/27
- 111.221.26.0/27
- 207.46.50.192/26

If you want to customize the email sender identity, Microsoft Cloud App Security enables this for you using MailChimp®, a third-party email service. To make it work, in the Microsoft Cloud App Security portal, under **Settings**, select **Mail settings** review MailChimp’s Terms of Service and Privacy Statement and give Microsoft permission to use MailChimp on your behalf.

If you don’t do this, your email notifications will be sent using all the default settings.

To work with MailChimp, add this IP address to your anti-spam whitelist to enable notifications to be sent: 198.2.134.139 (mail1.cloudappsecurity.com)


## Log collector 

To enable Cloud Discovery features using a log collector and detect Shadow IT in your organization, it is necessary to open the following:

- Allow the log collector to receive inbound FTP and Syslog traffic.
- Allow the log collector to initiate outbound traffic to the portal (for example contoso.cloudappsecurity.com) on port 443.
- Allow the log collector to initiate outbound traffic to the Azure blob storage on ports 80 and 443:


  | Data center |                        URL                        |
  |-------------|---------------------------------------------------|
  |     US      |   https://adaprodconsole.blob.core.windows.net/   |
  |     US2     | https://prod03use2console1.blob.core.windows.net/ |
  |     US3     |https://prod5usw2console1.blob.core.windows.net/   |
  |     EU      | https://prod02euwconsole1.blob.core.windows.net/  |
  |     EU2     |https://prod4uksconsole1.blob.core.windows.net/    |

> [!NOTE]
> - If your firewall requires a static IP address access list and does not support whitelisting based on URL, allow the log collector to initiate outbound traffic to the [Microsoft Azure datacenter IP ranges](https://www.microsoft.com/download/details.aspx?id=41653) on port 443.
>- Allow the log collector to initiate outbound traffic to the Cloud App Security portal.



## See Also  
[Daily activities to protect your cloud environment](daily-activities-to-protect-your-cloud-environment.md)   

[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  

