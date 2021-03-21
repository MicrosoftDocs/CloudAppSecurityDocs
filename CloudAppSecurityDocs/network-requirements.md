---
title: Network requirements 
description: This article describes the IP addresses and ports you need to open to work with Cloud App Security.
ms.date: 03/14/2021
ms.topic: how-to
---
# Network requirements

[!INCLUDE [Banner for top of topics](includes/banner.md)]

This article provides a list of ports and IP addresses you need to allow and allowlist to work with Microsoft Cloud App Security.

## View your data center

Some of the requirements below depend on which data center you're connected to.

To see which data center you're connecting to, do the following steps:

1. In the Cloud App Security portal, select the **question mark icon** in the menu bar. Then, select **About**.

    ![click About](media/about-menu.png)

2. In the Cloud App Security version screen, you can see the region and the data center.

    ![View your data center](media/data-center.png)

## Portal access

For access to the Cloud App Security portal, add **outbound port 443** for the following IP addresses and DNS names to your firewall's allowlist:

```ini
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
```

For US Government GCC High customers, it's also necessary to add the following DNS names to your firewall's allowlist to provide access for the Cloud App Security GCC High portal:

```ini
portal.cloudappsecurity.us
*.portal.cloudappsecurity.us
cdn.cloudappsecurity.com
```

Additionally, the following items should be allowed, depending on which data center you use:

|Data center|IP addresses|DNS name|
|----|----|----|
|US1|13.64.26.88, 13.64.29.32, 13.80.125.22, 13.91.91.243, 40.74.1.235, 40.74.6.204, 51.143.58.207, 52.137.89.147, 52.183.75.62|\*.us.portal.cloudappsecurity.com|
|US2|13.80.125.22, 20.36.222.59, 20.36.222.60, 40.74.1.235, 40.74.6.204, 51.143.58.207, 52.137.89.147, 52.183.75.62, 52.184.165.82|\*.us2.portal.cloudappsecurity.com|
|US3|13.80.125.22, 40.74.1.235, 40.74.6.204, 40.90.218.196, 40.90.218.198, 51.143.58.207, 52.137.89.147, 52.183.75.62|*.us3.portal.cloudappsecurity.com|
|EU1|13.80.125.22, 40.74.1.235, 40.74.6.204, 40.119.154.72, 51.143.58.207, 52.137.89.147, 52.157.238.58, 52.174.56.180, 52.183.75.62|\*.eu.portal.cloudappsecurity.com<|
|EU2|13.80.125.22, 40.74.1.235, 40.74.6.204, 40.81.156.154, 40.81.156.156, 51.143.58.207, 52.137.89.147, 52.183.75.62|*.eu2.portal.cloudappsecurity.com|
|Gov US1|13.72.19.4, 52.227.143.223|*.us1.portal.cloudappsecurity.us|
|GCC| 52.227.23.181, 52.227.180.126| `portal.cloudappsecuritygov.com`, *.portal.cloudappsecuritygov.com |

> [!NOTE]
> Instead of a wildcard (\*) you can open only your specific tenant URL, for example, based on the screenshot above you can open: mod244533.us.portal.cloudappsecurity.com

## Access and session controls

Configure your firewall for reverse proxy using the settings relevant to your environment.

### Commercial customers

For commercial customers, to enable Cloud App Security reverse proxy, add **outbound port 443** for the following IP addresses and DNS names to your firewall's allowlist:

```ini
*.cas.ms
*.mcas.ms
*.admin-mcas.ms
mcasproxy.azureedge.net
```

Additionally, the following items should be allowed, depending on which data center you use:

| **IP Addresses** | **DNS Name** |
|--|--|
| 40.81.58.184, 40.65.170.125, 40.81.121.140, 104.45.170.196, 191.235.123.114, 52.156.88.173, 52.156.205.222, 40.82.187.211, 20.193.137.191 40.81.62.221, 40.119.203.158, 52.157.233.49, 104.45.170.173, 52.155.181.183, 191.233.23.29, 20.190.7.24, 40.82.187.199, 20.193.131.246 | \*.mcas.ms |
| 40.71.11.134, 13.69.228.51 | \*.us.saml.cas.ms, \*.us2.saml.cas.ms, \*.us3.saml.cas.ms, \*.eu.saml.cas.ms, \*.eu2.saml.cas.ms |

### US Government GCC High customers

For US Government GCC High customers, to enable Cloud App Security reverse proxy, add **outbound port 443** for the following DNS names to your firewall's allowlist:

```ini
*.mcas-gov.us
*.admin-mcas-gov.us
mcasproxy.azureedge.net
```

Additionally, the following items should be allowed:

|IP addresses|DNS name|
|----|----|
|13.72.27.223, 13.72.27.219, 13.72.27.220, 13.72.27.222, 52.244.39.14, 52.244.38.212, 52.244.39.0, 52.244.39.80|\*.mcas-gov.us<br />\*.admin-mcas-gov.us mcasproxy.azureedge.net|
|13.72.27.216, 13.72.27.215,52.244.39.82, 52.244.39.15|\*.access.cloudappsecurity.us<br />\*.saml.cloudappsecurity.us|

## SIEM agent connection

To enable Cloud App Security to connect to your SIEM, add **outbound port 443** for the following IP addresses to your firewall's allowlist:

|Data center|IP addresses|
|----|----|
|US1|13.64.26.88, 13.64.29.32, 13.80.125.22, 13.91.91.243, 40.74.1.235, 40.74.6.204, 51.143.58.207, 52.137.89.147, 52.183.75.62|
|US2|13.80.125.22, 20.36.222.59, 20.36.222.60, 40.74.1.235, 40.74.6.204, 51.143.58.207, 52.137.89.147, 52.183.75.62, 52.184.165.82|
|US3|13.80.125.22, 40.74.1.235, 40.74.6.204, 40.90.218.196, 40.90.218.198, 51.143.58.207, 52.137.89.147, 52.183.75.62|
|EU1|13.80.125.22, 40.74.1.235, 40.74.6.204, 40.119.154.72, 51.143.58.207, 52.137.89.147, 52.157.238.58, 52.174.56.180, 52.183.75.62|
|EU2|13.80.125.22, 40.74.1.235, 40.74.6.204, 40.81.156.154, 40.81.156.156, 51.143.58.207, 52.137.89.147, 52.183.75.62|
|Gov US1|13.72.19.4, 52.227.143.223|
|GCC| 52.227.23.181, 52.227.180.126|

> [!NOTE]
> If you didn't specify a proxy when you set up the Cloud App Security SIEM agent, you need to allow http connections on port 80 for the URLs listed on the [Azure TLS certificate changes](/azure/security/fundamentals/tls-certificate-changes#will-this-change-affect-me) page. This is used for checking certificate revocation status when you connect to the Cloud App Security portal.

## App connector

For some third-party apps to be accessed by Cloud App Security, these IP addresses may be used. The IP addresses enable Cloud App Security to collect logs and provide access for the Cloud App Security console.

> [!NOTE]
> You may see these IP addresses in activity logs from the vendor because Cloud App Security performs governance actions and scans from these IP addresses.

To connect to third-party apps, enable Cloud App Security to connect from these IP addresses:

|Data center|IP addresses|
|----|----|----|
|US1|13.64.26.88, 13.64.29.32, 13.64.30.76, 13.64.30.117, 13.64.30.118, 13.64.31.116, 13.64.196.27, 13.64.198.19, 13.64.198.97, 13.64.199.41, 13.68.76.47, 13.86.176.189, 13.86.176.211, 13.91.61.249, 13.91.91.243, 13.91.98.185, 13.93.216.68, 13.93.233.42, 40.118.211.172, 104.42.54.148, 104.209.35.177|
|US2|13.68.76.47, 20.36.222.59, 20.36.222.60, 40.67.152.91, 40.67.154.160, 40.67.155.146, 40.67.159.55, 40.84.2.83, 40.84.4.93, 40.84.4.119, 52.184.165.82, 52.232.224.227, 52.232.225.84, 104.42.54.148, 104.46.116.211, 104.46.116.211, 104.46.121.72, 104.46.121.72, 104.46.122.189, 104.46.122.189|
|US3|13.68.76.47, 40.90.218.196, 40.90.218.197, 40.90.218.198, 40.90.218.203, 40.90.220.190, 40.90.220.196, 51.143.120.236, 51.143.120.242, 104.42.54.148|
|EU1|13.80.22.71, 13.95.29.177, 13.95.30.46, 40.67.219.133, 40.114.217.8, 40.114.217.8, 40.115.24.65, 40.115.24.65, 40.115.25.50, 40.115.25.50, 40.119.154.72, 51.105.55.62, 51.105.179.157, 51.137.200.32, 52.157.232.110, 52.157.233.92, 52.157.233.133, 52.157.238.58, 52.157.239.110, 52.174.56.180|
|EU2|40.81.152.171, 40.81.152.172, 40.81.156.153, 40.81.156.154, 40.81.156.155, 40.81.156.156, 51.105.55.62, 51.137.200.32, 51.145.108.227, 51.145.108.250|
|Gov US1|52.227.138.248, 52.227.142.192, 52.227.143.223|
|GCC|52.227.23.181, 52.227.180.126|

## Third-party DLP integration

To enable Cloud App Security to send data through your stunnel to your ICAP server, open your DMZ firewall to these IP addresses with a dynamic source port number.

1. **Source addresses** - These addresses should be allowed as listed above for API connector third-party apps
2. **Source TCP port** - Dynamic
3. **Destination address(es)** - One or two IP address of the stunnel connected to the external ICAP server
4. **Destination TCP port** - As defined in your network

> [!NOTE]
>
> - By default the stunnel port number is set to 11344. You can change it to another port if necessary, but be sure to make note of the new port number.
> - You may see these IP addresses in activity logs from the vendor because Cloud App Security performs governance actions and scans from these IP addresses.

To connect to third-party apps and integrate with external DLP solutions, enable Cloud App Security to connect from these IP addresses:

|Data center|IP addresses|
|----|----|----|
|US1|13.64.26.88, 13.64.29.32, 13.64.30.76, 13.64.30.117, 13.64.30.118, 13.64.31.116, 13.64.196.27, 13.64.198.19, 13.64.198.97, 13.64.199.41, 13.86.176.189, 13.86.176.211, 13.91.61.249, 13.91.91.243, 13.91.98.185, 13.93.216.68, 13.93.233.42, 40.118.211.172, 104.209.35.177|
|US2|20.36.222.59, 20.36.222.60, 40.67.152.91, 40.67.154.160, 40.67.155.146, 40.67.159.55, 40.84.2.83, 40.84.4.93, 40.84.4.119, 52.184.165.82, 52.232.224.227, 52.232.225.84, 104.46.116.211, 104.46.116.211, 104.46.121.72, 104.46.121.72, 104.46.122.189, 104.46.122.189|
|US3|40.90.218.196, 40.90.218.197, 40.90.218.198, 40.90.218.203, 40.90.220.190, 40.90.220.196, 51.143.120.236, 51.143.120.242|
|EU1|13.80.22.71, 13.95.29.177, 13.95.30.46, 40.67.219.133, 40.114.217.8, 40.114.217.8, 40.115.24.65, 40.115.24.65, 40.115.25.50, 40.119.154.72, 51.105.179.157, 52.157.232.110, 52.157.233.92, 52.157.233.133, 52.157.238.58, 52.157.239.110, 52.174.56.180|
|EU2|40.81.152.171, 40.81.152.172, 40.81.156.153, 40.81.156.154, 40.81.156.155, 40.81.156.156, 51.145.108.227, 51.145.108.250|

## Mail server

To enable notifications to be sent from the default template and settings, add these IP addresses to your anti-spam allowlist. The Cloud App Security dedicated email IP addresses are:

- 65.55.234.192/26
- 207.46.50.192/26
- 65.55.52.224/27
- 94.245.112.0/27
- 111.221.26.0/27
- 207.46.200.0/27

If you want to customize the email sender identity, Microsoft Cloud App Security enables customization by using MailChimp&reg;, a third-party email service. To make it work, in the Microsoft Cloud App Security portal, go to **Settings**. Select **Mail settings** and review MailChimp's Terms of Service and Privacy Statement. Then, give Microsoft permission to use MailChimp on your behalf.

If you don't customize the sender identity, your email notifications will be sent using all the default settings.

To work with MailChimp, add this IP address to your anti-spam allowlist to enable notifications to be sent: 198.2.134.139 (mail1.cloudappsecurity.com)

## Log collector

To enable Cloud Discovery features using a log collector and detect Shadow IT in your organization, open the following items:

- Allow the log collector to receive inbound FTP and Syslog traffic.
- Allow the log collector to initiate outbound traffic to the portal (for example contoso.cloudappsecurity.com) on port 443.
- Allow the log collector to initiate outbound traffic to the Azure blob storage on port 443:

  | Data center |                        URL                                 |
  |-------------|------------------------------------------------------------|
  |     US1     | <https://adaprodconsole.blob.core.windows.net/>             |
  |     US2     | <https://prod03use2console1.blob.core.windows.net/>         |
  |     US3     | <https://prod5usw2console1.blob.core.windows.net/>          |
  |     EU1     | <https://prod02euwconsole1.blob.core.windows.net/>          |
  |     EU2     | <https://prod4uksconsole1.blob.core.windows.net/>           |
  |   Gov US1   | <https://gprd1usgvconsole1.blob.core.usgovcloudapi.net/>    |

> [!NOTE]
>
> - If your firewall requires a static IP address access list and does not support allowing based on URL, allow the log collector to initiate outbound traffic to the [Microsoft Azure datacenter IP ranges](https://www.microsoft.com/download/details.aspx?id=56519) on port 443.
> - Allow the log collector to initiate outbound traffic to the Cloud App Security portal.
> - If you didn't specify a proxy when you set up the log collector, you need to allow http connections on port 80 for the URLs listed on the [Azure TLS certificate changes](/azure/security/fundamentals/tls-certificate-changes#will-this-change-affect-me) page. This is used for checking certificate revocation status when you connect to the Cloud App Security portal.

## Next steps

> [!div class="nextstepaction"]
> [Daily activities to protect your cloud environment](daily-activities-to-protect-your-cloud-environment.md)

[!INCLUDE [Open support ticket](includes/support.md)]
