---
# required metadata

title: Deploy Cloud Discovery with Microsoft Cloud App Security | Microsoft Docs
description: This topic describes the setup procedure for getting Cloud Discovery working.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 4/22/2017
ms.topic: get-started-article
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: a9b5bd8d-305b-4e93-9a4c-a4683ea09080

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


# Set up Cloud Discovery
Cloud Discovery analyzes your traffic logs against Microsoft Cloud App Security's cloud app catalog of over 15,000 cloud apps that are ranked and scored based on more than 60 risk factors, to provide you with ongoing visibility into cloud use, Shadow IT, and the risk Shadow IT poses into your organization.

## Snapshot and continuous risk assessment reports 

There are two types of reports you can generate: 
- **Snapshot reports** provide ad-hoc visibility on a set on traffic logs you manually upload from your firewalls and proxies.

- **Continuous reports** analyze all logs that are forwarded from your network using Cloud App Security’s log collector. They provide improved visibility over all data, and automatically identify anomalous use using either the Machine Learning anomaly detection engine or by using custom policies that you define.

## Log process flow: From raw data to risk assessment  
The process of generating a risk assessment consists of the following steps and takes between a few minutes to several hours depending on the amount of data processed.  

-   **Upload** – Web traffic logs from your network are uploaded to the portal.  

-   **Parse** – Cloud App Security parses and extracts traffic data from the traffic logs with a dedicated parser for each data source.  

-   **Analyze** – Traffic data is analyzed against the Cloud App Catalog to identify more than 15,000 cloud apps and to assess their risk score. Active users and IP addresses are also identified as part of the analysis.  

-   **Generate report** - A risk assessment report of the data extracted from log files is generated.   


>[!NOTE]
>- Continuous report data is analyzed twice a day.
>- The log collector compresses data before it is uploaded. The outbound traffic on the log collector will be 10% of the size of the traffic logs it receives. 

## Using traffic logs for Cloud Discovery
Cloud Discovery utilizes the data in your traffic logs. The more detailed your log, the better visibility you get. Cloud Discovery requires web-traffic data with the following attributes:
- Date of the transaction
- Source IP
- Source user - highly recommended
- Destination IP address
- Destination URL **recommended** (URLs provide higher accuracy for cloud app detection than IP addresses)
- Total amount of data (data information is highly valuable)
- Amount of uploaded or downloaded data (provides insights about the usage patterns of the cloud apps)
- Action taken (allowed/blocked)

Cloud Discovery cannot show or analyze attributes that are not included in your logs.
For example, **Cisco ASA Firewall** standard log format does not contain the **number of uploaded bytes per transaction** nor **Username**, and does not contain **Target URL** (but only target IP).
Therefore, these attributes will not be shown in Cloud Discovery data for these logs, and the visibility into the cloud apps will be limited. For Cisco ASA firewalls, it is necessary to set the information level to 6. 


In order to successfully generate a Cloud Discovery report, your traffic logs must meet the following conditions:
1.  Data source is supported (see list below).
2.  Log format matches the expected standard format (this will be checked upon upload by the Log tool).
3.  Events are not more than 90 days old.
4.  The log file is valid and includes outbound traffic information.



## Supported firewalls and proxies <a name="supported-firewalls-and-proxies"></a>

- Barracuda - Web App Firewall (W3C)
- Blue Coat Proxy SG - Access log (W3C)
- Check Point
- Cisco ASA Firewall (For Cisco ASA firewalls, it is necessary to set the information level to 6)
- Cisco ASA with FirePOWER
- Cisco IronPort WSA
- Cisco ScanSafe
- Cisco Meraki – URLs log
- Clavister NGFW (Syslog)
- Dell Sonicwall
- Digital Arts i-FILTER
- Fortinet Fortigate
- Juniper SRX
- Juniper SSG
- McAfee Secure Web Gateway
- Microsoft Forefront Threat Management Gateway (W3C)
- Palo Alto series Firewall
- Sophos SG
- Sophos Cyberoam
- Squid (Common)
- Squid (Native)
- Websense - Web Security Solutions - Investigative detail report (CSV)
- Websense - Web Security Solutions - Internet activity log (CEF)
- Zscaler

> [!NOTE]
> Cloud Discovery supports both IPv4 and IPv6 addresses.

If your log is not supported, select **Other** as the **Data source** and specify the appliance and log you are trying to upload. Your log will be reviewed by the Cloud App Security cloud analyst team and you will be notified if support for your log type is added. Alternatively, you can define a custom parser that matches your format. For more information, see [Use a custom log parser](custom-log-parser.md).


Data attributes (according to vendor documentation):


|                 Data source                  |    Target App URL    |    Target App IP     |       Username       |      Origin IP       |    Total traffic     |    Uploaded bytes    |
|----------------------------------------------|----------------------|----------------------|----------------------|----------------------|----------------------|----------------------|
|                  Barracuda                   | <strong>Yes</strong> | <strong>Yes</strong> | <strong>Yes</strong> | <strong>Yes</strong> |          No          |          No          |
|                  Blue Coat                   | <strong>Yes</strong> |          No          | <strong>Yes</strong> | <strong>Yes</strong> | <strong>Yes</strong> | <strong>Yes</strong> |
|                  Checkpoint                  |          No          | <strong>Yes</strong> |          No          | <strong>Yes</strong> |          No          |          No          |
|              Cisco ASA (Syslog)              |          No          | <strong>Yes</strong> |          No          | <strong>Yes</strong> | <strong>Yes</strong> |          No          |
|           Cisco ASA with FirePOWER           | <strong>Yes</strong> | <strong>Yes</strong> | <strong>Yes</strong> | <strong>Yes</strong> | <strong>Yes</strong> | <strong>Yes</strong> |
|                  Cisco FWSM                  |          No          | <strong>Yes</strong> |          No          | <strong>Yes</strong> | <strong>Yes</strong> |          No          |
|              Cisco Ironport WSA              | <strong>Yes</strong> | <strong>Yes</strong> | <strong>Yes</strong> | <strong>Yes</strong> | <strong>Yes</strong> | <strong>Yes</strong> |
|                 Cisco Meraki                 | <strong>Yes</strong> | <strong>Yes</strong> |          No          | <strong>Yes</strong> |          No          |          No          |
|           Clavister NGFW (Syslog)            | <strong>Yes</strong> | <strong>Yes</strong> | <strong>Yes</strong> | <strong>Yes</strong> | <strong>Yes</strong> | <strong>Yes</strong> |
|                Dell SonicWall                | <strong>Yes</strong> | <strong>Yes</strong> |          No          | <strong>Yes</strong> | <strong>Yes</strong> | <strong>Yes</strong> |
|            Digital Arts i-FILTER             | <strong>Yes</strong> | <strong>Yes</strong> | <strong>Yes</strong> | <strong>Yes</strong> | <strong>Yes</strong> | <strong>Yes</strong> |
|                  Fortigate                   |          No          | <strong>Yes</strong> |          No          | <strong>Yes</strong> | <strong>Yes</strong> | <strong>Yes</strong> |
|                 Juniper SRX                  |          No          | <strong>Yes</strong> |          No          | <strong>Yes</strong> | <strong>Yes</strong> | <strong>Yes</strong> |
|                 Juniper SSG                  |          No          | <strong>Yes</strong> | <strong>Yes</strong> | <strong>Yes</strong> | <strong>Yes</strong> | <strong>Yes</strong> |
|                  McAfee SWG                  | <strong>Yes</strong> |          No          |          No          | <strong>Yes</strong> | <strong>Yes</strong> | <strong>Yes</strong> |
|                    MS TMG                    | <strong>Yes</strong> |          No          | <strong>Yes</strong> | <strong>Yes</strong> | <strong>Yes</strong> | <strong>Yes</strong> |
|              Palo Alto Networks              |          No          | <strong>Yes</strong> | <strong>Yes</strong> | <strong>Yes</strong> | <strong>Yes</strong> | <strong>Yes</strong> |
|                    Sophos                    | <strong>Yes</strong> | <strong>Yes</strong> | <strong>Yes</strong> | <strong>Yes</strong> | <strong>Yes</strong> |          No          |
|                Squid (Common)                | <strong>Yes</strong> |          No          | <strong>Yes</strong> | <strong>Yes</strong> |          No          | <strong>Yes</strong> |
|                Squid (Native)                | <strong>Yes</strong> |          No          | <strong>Yes</strong> | <strong>Yes</strong> |          No          | <strong>Yes</strong> |
| Websense - Investigative detail report (CSV) | <strong>Yes</strong> | <strong>Yes</strong> | <strong>Yes</strong> | <strong>Yes</strong> | <strong>Yes</strong> | <strong>Yes</strong> |
|    Websense - Internet activity log (CEF)    | <strong>Yes</strong> | <strong>Yes</strong> | <strong>Yes</strong> | <strong>Yes</strong> | <strong>Yes</strong> | <strong>Yes</strong> |
|                   Zscaler                    | <strong>Yes</strong> | <strong>Yes</strong> | <strong>Yes</strong> | <strong>Yes</strong> | <strong>Yes</strong> | <strong>Yes</strong> |

## See also

[Create snapshot Cloud Discovery reports](create-snapshot-cloud-discovery-reports.md)

[Configure automatic log upload for continuous reports](configure-automatic-log-upload-for-continuous-reports.md)

[Working with Cloud Discovery data](working-with-cloud-discovery-data.md)