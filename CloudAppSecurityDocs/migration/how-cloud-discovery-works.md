---
title: "How Cloud Discovery works"
ms.custom: na
ms.date: "08/18/2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
ms.assetid: 0de8da1d-115d-4bcf-a661-5886ced314f6
caps.latest.revision: 7
author: "Rkarlin"
ms.author: "rkarlin"
robots: noindex,nofollow
translation.priority.ht: 
  - "cs-cz"
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "hu-hu"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "nl-nl"
  - "pl-pl"
  - "pt-br"
  - "pt-pt"
  - "ru-ru"
  - "sv-se"
  - "tr-tr"
  - "zh-cn"
  - "zh-tw"
---
# How Cloud Discovery works

Cloud Discovery analyzes your traffic logs against Cloud App Security's cloud app catalog of over 13,000 cloud apps that are ranked and scored based more than 50 attributes, to provide you with ongoing visibility into cloud use, shadow IT and the risk they pose on your organization.
The **Cloud app catalog** rates risk for your cloud apps based on regulatory certification, industry standards, and best practices. Four complementary processes run on the Cloud app catalog to keep it up to date:
1.  Automated data extraction directly from the cloud app (for attributes such as SOC 2 compliance).
2.  Automated advanced data extraction for data by our algorithms (for attributes such as HTTP security headers).
3.   Continuous analysis by our cloud analyst team (for attributes such as Encryption at rest).
4.  Customer-based revision requests based on customer submission requests for revisions to the Cloud app catalog . All requests are reviewed by our cloud analyst team and updated based on their findings.
 
## Using traffic logs for  Cloud Discovery
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
For example, **Cisco ASA Firewall** standard log format does not contain the **Amount of uploaded bytes per transaction** nor **Username**, and does not contain **Target URL** (but only target IP).
Therefore, these attributes will be shown in Cloud Discovery data for these logs, and the vibility over the cloud apps we be limited. For Cisco ASA firewalls, it is necessary to set the information level to 6. 
 

In order to successfully generate a Cloud Discovery report, your traffic logs must meet the following conditions:
1.  Data source is supported (see list below).
2.  Log format matches the expected standard format (this will be checked upon upload by the Log tool).
3.  Events are not more than 90 days old.
4.  The log file is valid and includes outbound traffic information.

## Supported firewalls and proxies
- Blue Coat Proxy SG - Access log (W3C)
- Check Point
- Cisco ASA Firewall (For Cisco ASA firewalls, it is necessary to set the information level to 6)
- Cisco IronPort WSA
- Cisco ScanSafe
- Cisco Merkai – URLs log
- Dell Sonicwall
- Fortiner Fortigate
- Juniper SRX
- McAfee Secure Web Gateway
- Microsoft Forefront Threat Management Gateway (W3C)
- Palo Alto series Firewall
- Sophos SG
- Squid (Common)
- Squid (Native)
- Websense - Web Security Solutions - Investigative detail report (CSV)
- Websense - Web Security Solutions - Internet activity log (CEF)
- Zscaler

Data attributes (according to vendor documentation):

|Data source|Target App URL|Target App IP|Username|Origin IP|Total traffic|Uploaded bytes|
|----|----|----|-----|----|----|----|
|Blue Coat|**Yes**|No|**Yes**|**Yes**|**Yes**|**Yes**|
|Checkpoint|No|**Yes**|No|**Yes**|No|No|
|Cisco ASA|No|**Yes**|No|**Yes**|**Yes**|No|
|Cisco FWSM|No|**Yes**|No|**Yes**|**Yes**|No|
|Cisco Ironport WSA|**Yes**|**Yes**|**Yes**|**Yes**|**Yes**|**Yes**|
|Cisco Scansfe|**Yes**|No|**Yes**|**Yes**|**Yes**|**Yes**|
|Dell SonicWall|**Yes**|**Yes**|No|**Yes**|**Yes**|**Yes**|
|Fortigate|No|**Yes**|No|**Yes**|**Yes**|**Yes**|
|Juniper SRX|No|**Yes**|No|**Yes**|**Yes**|**Yes**|
|McAfee SWG|**Yes**|No|No|**Yes**|**Yes**|**Yes**|
|Meraki|**Yes**|**Yes**|No|**Yes**|No|No|
|MS TMG|**Yes**|No|**Yes**|**Yes**|**Yes**|**Yes**|
|PAN|**Yes**|**Yes**|**Yes**|**Yes**|**Yes**|**Yes**|
|Sophos|**Yes**|**Yes**|**Yes**|**Yes**|**Yes**|No|
|Websense|**Yes**|No|No|**Yes**|No|No|
|Zscaler|**Yes**|No|**Yes**|No|**Yes**|No|

