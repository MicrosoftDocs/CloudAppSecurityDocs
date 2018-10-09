---
# required metadata

title: Configure automatic log upload for continuous reports | Microsoft Docs
description: This topic describes the process configuring automatic log upload for continuous reports in Cloud App Security .
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/09/2018
ms.topic: conceptual
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: c75ba963-ad5a-48e6-8d5d-610fc6e0b990

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


# Configure automatic log upload for continuous reports


Log collectors enable you to easily automate log upload from your network. The log collector runs on your network and receives logs over Syslog or FTP. Each log is automatically processed, compressed and transmitted to the portal. FTP
logs are uploaded to Microsoft Cloud App Security after the file finished the FTP transfer to the Log Collector.  For Syslog, the Log Collector writes the logs received to the disk and uploads the file to Cloud App Security when the file size is larger than 40 KB. 

After a log is uploaded to Cloud App Security, it is moved to a backup directory that stores the last 20 logs at any given moment. When new logs arrive, the old ones are deleted. When the log collector disk space is full, the log collector drops new logs until it has more free disk space. When this happens you will receive a warning on the **Log collectors** tab of the **Upload logs automatically** settings.

Before setting up automatic log file collection, verify that your log matches the expected log type, to make sure Cloud App Security can parse your specific file, in [Using traffic logs for Cloud Discovery](create-snapshot-cloud-discovery-reports.md#log-format).


> [!NOTE]
>-  Cloud App Security provides support for forwarding logs from your SIEM server to the Log Collector assuming the logs are being forwarded in their original format. However, it is highly recommended that you integrate the log collector directly with your firewall and/or proxy.
>- The log collector compresses data before it is uploaded. The outbound traffic on the log collector will be 10% of the size of the traffic logs it receives. 

## Deployment modes

The Log Collector supports two deployment modes:

-   **Container**: Runs as a Docker image on [Ubuntu on premises](discovery-docker-ubuntu.md), [Ubuntu in Azure](discovery-docker-ubuntu-azure.md) or [RHEL on premises](discovery-docker-ubuntu.md). 

-   **Virtual appliance**:  [Runs as an image over Hyper-V or VMware hypervisor](configure-automatic-log-upload-for-continuous-reports.md)




## See also
 
[Create snapshot Cloud Discovery reports](create-snapshot-cloud-discovery-reports.md)

[Working with Cloud Discovery data](working-with-cloud-discovery-data.md)

