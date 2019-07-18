---
# required metadata

title: Network requirements - Cloud App Security | Microsoft Docs
description: This article describes the IP addresses and ports you need to open to work with Cloud App Security.
keywords:
author: ShlomoSagir-MS
ms.author: shsagir
manager: ShlomoSagir-MS
ms.date: 7/16/2019
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: 4de606f2-a09e-4e48-a578-e223de8b5e69

# optional metadata

#ROBOTS:
#audience:
ms.suite: ems
ms.custom: seodec18

---
# Network requirements

*Applies to: Microsoft Cloud App Security*

This article provides a list of ports and IP addresses you need to allow and allow list to work with Microsoft Cloud App Security.

## View your data center

Some of the requirements below depend on which data center you're connected to. 

To see which data center you're connecting to, do the following steps:

1. In the Cloud App Security portal, click the **question mark icon** in the menu bar. Then, select **About**. 

    ![click About](./media/about-menu.png)

2. In the Cloud App Security version screen, you can see the region and the data center.

    ![View your data center](./media/data-center.png)

## Portal access

For access to the Cloud App Security portal, add **outbound port 443** for the following IP addresses and DNS names to your firewall's allow list:  

    portal.cloudappsecurity.com
    *.portal.cloudappsecurity.com
    cdn.cloudappsecurity.com
    https://adaproddiscovery.azureedge.net 
    *.s-microsoft.com
    *.msecnd.net
    dev.virtualearth.net
    *.cloudappsecurity.com
    flow.microsoft.com
    static2.sharepointonline.com
    dc.services.visualstudio.com
    *.blob.core.windows.net

Additionally, the following items should be whitelisted, depending on which data center you use:
> [!div class="mx-tableFixed"]
> 
> |Data center|IP addresses|DNS name|
> |----|----|----|
> |US1|13.64.26.88<br>13.64.29.32<br>13.80.125.22<br>13.91.91.243<br>40.74.1.235<br>40.74.6.204<br>51.143.58.207<br>52.137.89.147<br>52.183.75.62|\*.us.portal.cloudappsecurity.com|
> |US2|13.80.125.22<br>20.36.222.59<br>20.36.222.60<br>40.74.1.235<br>40.74.6.204<br>51.143.58.207<br>52.137.89.147<br>52.183.75.62<br>52.184.165.82|\*.us2.portal.cloudappsecurity.com|
> |US3|13.80.125.22<br>40.74.1.235<br>40.74.6.204<br>40.90.218.196<br>40.90.218.198<br>51.143.58.207<br>52.137.89.147<br>52.183.75.62|*.us3.portal.cloudappsecurity.com|
> |EU1|13.80.125.22<br>40.119.154.72<br>40.74.1.235<br>40.74.6.204<br>51.143.58.207<br>52.137.89.147<br>52.157.238.58<br>52.174.56.180<br>52.183.75.62|\*.eu.portal.cloudappsecurity.com<|
> |EU2|13.80.125.22<br>40.74.1.235<br>40.74.6.204<br>40.81.156.154<br>40.81.156.156<br>51.143.58.207<br>52.137.89.147<br>52.183.75.62|*.eu2.portal.cloudappsecurity.com|

> [!NOTE]
> Instead of a wildcard (\*) you can open only your specific tenant URL, for example, based on the screenshot above you can open: mod244533.us.portal.cloudappsecurity.com

## SIEM agent connection

To enable Cloud App Security to connect to your SIEM, add **outbound port 443** for the following IP addresses to your firewall's allow list:  

> [!div class="mx-tableFixed"]
> 
> |Data center|IP addresses|  
> |----|----|
> |US1|13.64.26.88<br>13.64.29.32<br>13.80.125.22<br>13.91.91.243<br>40.74.1.235<br>40.74.6.204<br>51.143.58.207<br>52.137.89.147<br>52.183.75.62|
> |US2|13.80.125.22<br>20.36.222.59<br>20.36.222.60<br>40.74.1.235<br>40.74.6.204<br>51.143.58.207<br>52.137.89.147<br>52.183.75.62<br>52.184.165.82|
> |US3|13.80.125.22<br>40.74.1.235<br>40.74.6.204<br>40.90.218.196<br>40.90.218.198<br>51.143.58.207<br>52.137.89.147<br>52.183.75.62|
> |EU1|13.80.125.22<br>40.119.154.72<br>40.74.1.235<br>40.74.6.204<br>51.143.58.207<br>52.137.89.147<br>52.157.238.58<br>52.174.56.180<br>52.183.75.62|
> |EU2|13.80.125.22<br>40.74.1.235<br>40.74.6.204<br>40.81.156.154<br>40.81.156.156<br>51.143.58.207<br>52.137.89.147<br>52.183.75.62|

> [!NOTE]
> If you didn't specify a proxy when you set up the Cloud App Security SIEM agent, you need to allow http connections to http://ocsp.msocsp.com/ and ocsp.digicert.com on port 80. This is used for checking certificate revocation status when you connect to the Cloud App Security portal.

## App connector

For some third-party apps to be accessed by Cloud App Security, these IP addresses may be used. The IP addresses enable Cloud App Security to collect logs and provide access for the Cloud App Security console.

> [!NOTE]
>You may see these IP addresses in activity logs from the vendor because Cloud App Security performs governance actions and scans from these IP addresses.

To connect to third-party apps, enable Cloud App Security to connect from these IP addresses:

> [!div class="mx-tableFixed"]
> 
> |Data center|IP addresses||
> |----|----|----|
> |US1|104.209.35.177<br>13.64.196.27<br>13.64.198.19<br>13.64.198.97<br>13.64.199.41<br>13.64.26.88<br>13.64.29.32<br>13.64.30.117<br>13.64.30.118<br>13.64.30.76|13.64.31.116<br>13.86.176.189<br>13.86.176.211<br>13.91.61.249<br>13.91.91.243<br>13.91.98.185<br>13.93.216.68<br>13.93.233.42<br>40.118.211.172<br><br>|
> |US2|104.46.116.211<br>104.46.116.211<br>104.46.121.72<br>104.46.121.72<br>104.46.122.189<br>104.46.122.189<br>20.36.222.59<br>20.36.222.60<br>40.67.152.91|40.67.154.160<br>40.67.155.146<br>40.67.159.55<br>40.84.2.83<br>40.84.4.119<br>40.84.4.93<br>52.184.165.82<br>52.232.224.227<br>52.232.225.84|
> |US3|40.90.218.196<br>40.90.218.197<br>40.90.218.198<br>40.90.218.203<br>40.90.220.190<br>40.90.220.196<br>51.143.120.236<br>51.143.120.242||
> |EU1|13.80.22.71<br>13.95.29.177<br>13.95.30.46<br>40.114.217.8<br>40.114.217.8<br>40.115.24.65<br>40.115.24.65<br>40.115.25.50<br>40.115.25.50|40.119.154.72<br>40.67.219.133<br>51.105.179.157<br>52.157.232.110<br>52.157.233.133<br>52.157.233.92<br>52.157.238.58<br>52.157.239.110<br>52.174.56.180|
> |EU2|40.81.152.171<br>40.81.152.172<br>40.81.156.153<br>40.81.156.154<br>40.81.156.155<br>40.81.156.156<br>51.145.108.227<br>51.145.108.250|

## Third-party DLP integration

To enable Cloud App Security to send data through your stunnel to your ICAP server, open your DMZ firewall to these IP addresses with a dynamic source port number. 

1. **Source addresses** - These addresses should be whitelisted as listed above for API connector third-party apps
2. **Source TCP port** - Dynamic
3. **Destination address(es)** - One or two IP address of the stunnel connected to the external ICAP server
4. **Destination TCP port** - As defined in your network

> [!NOTE] 
> -  By default the stunnel port number is set to 11344. You can change it to another port if necessary, but be sure to make note of the new port number.
> - You may see these IP addresses in activity logs from the vendor because Cloud App Security performs governance actions and scans from these IP addresses.

To connect to third-party apps and integrate with external DLP solutions, enable Cloud App Security to connect from these IP addresses:

> [!div class="mx-tableFixed"]
> 
> |Data center|IP addresses||
> |----|----|----|
> |US1|104.209.35.177<br>13.64.196.27<br>13.64.198.19<br>13.64.198.97<br>13.64.199.41<br>13.64.26.88<br>13.64.29.32<br>13.64.30.117<br>13.64.30.118<br>13.64.30.76|13.64.31.116<br>13.86.176.189<br>13.86.176.211<br>13.91.61.249<br>13.91.91.243<br>13.91.98.185<br>13.93.216.68<br>13.93.233.42<br>40.118.211.172<br><br>|
> |US2|104.46.116.211<br>104.46.116.211<br>104.46.121.72<br>104.46.121.72<br>104.46.122.189<br>104.46.122.189<br>20.36.222.59<br>20.36.222.60<br>40.67.152.91|40.67.154.160<br>40.67.155.146<br>40.67.159.55<br>40.84.2.83<br>40.84.4.119<br>40.84.4.93<br>52.184.165.82<br>52.232.224.227<br>52.232.225.84|
> |US3|40.90.218.196<br>40.90.218.197<br>40.90.218.198<br>40.90.218.203<br>40.90.220.190<br>40.90.220.196<br>51.143.120.236<br>51.143.120.242||
> |EU1|13.80.22.71<br>13.95.29.177<br>13.95.30.46<br>40.114.217.8<br>40.114.217.8<br>40.115.24.65<br>40.115.24.65<br>40.115.25.50<br>40.119.154.72|40.67.219.133<br>51.105.179.157<br>52.157.232.110<br>52.157.233.133<br>52.157.233.92<br>52.157.238.58<br>52.157.239.110<br>52.174.56.180<br><br>|
> |EU2|40.81.152.171<br>40.81.152.172<br>40.81.156.153<br>40.81.156.154<br>40.81.156.155<br>40.81.156.156<br>51.145.108.227<br>51.145.108.250||

## Mail server

To enable notifications to be sent from the default template and settings, add these IP addresses to your anti-spam allow list. The Cloud App Security dedicated email IP addresses are:

- 65.55.234.192/26
- 207.46.200.0/27
- 65.55.52.224/27
- 94.245.112.0/27
- 111.221.26.0/27
- 207.46.50.192/26

If you want to customize the email sender identity, Microsoft Cloud App Security enables customization by using MailChimp®, a third-party email service. To make it work, in the Microsoft Cloud App Security portal, go to **Settings**. Select **Mail settings** and review MailChimp’s Terms of Service and Privacy Statement. Then, give Microsoft permission to use MailChimp on your behalf.

If you don’t customize the sender identity, your email notifications will be sent using all the default settings.

To work with MailChimp, add this IP address to your anti-spam allow list to enable notifications to be sent: 198.2.134.139 (mail1.cloudappsecurity.com)

## Log collector

To enable Cloud Discovery features using a log collector and detect Shadow IT in your organization, open the following items:

- Allow the log collector to receive inbound FTP and Syslog traffic.
- Allow the log collector to initiate outbound traffic to the portal (for example contoso.cloudappsecurity.com) on port 443.
- Allow the log collector to initiate outbound traffic to the Azure blob storage on port 443:

  | Data center |                        URL                        |
  |-------------|---------------------------------------------------|
  |     US1     | https://adaprodconsole.blob.core.windows.net/     |
  |     US2     | https://prod03use2console1.blob.core.windows.net/ |
  |     US3     | https://prod5usw2console1.blob.core.windows.net/  |
  |     EU1     | https://prod02euwconsole1.blob.core.windows.net/  |
  |     EU2     | https://prod4uksconsole1.blob.core.windows.net/   |

> [!NOTE]
> - If your firewall requires a static IP address access list and does not support whitelisting based on URL, allow the log collector to initiate outbound traffic to the [Microsoft Azure datacenter IP ranges](https://www.microsoft.com/download/details.aspx?id=41653) on port 443.
>- Allow the log collector to initiate outbound traffic to the Cloud App Security portal.
>- If you didn't specify a proxy when you set up the log collector, you need to allow http connections to http://ocsp.msocsp.com/ and ocsp.digicert.com on port 80. This is used for checking certificate revocation status when you connect to the Cloud App Security portal.

## Next steps

[Daily activities to protect your cloud environment](daily-activities-to-protect-your-cloud-environment.md)

[Premier customers can also create a new support request directly in the Premier Portal.](https://premier.microsoft.com/)