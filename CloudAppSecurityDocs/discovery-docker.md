---
title: Configure automatic log upload for continuous reports in Defender for Cloud Apps
description: This article describes the process configuring automatic log upload for continuous reports in Defender for Cloud Apps.
ms.date: 7/22/2019
ms.topic: how-to
---
# Configure automatic log upload for continuous reports

[!INCLUDE [Banner for top of topics](includes/banner.md)]

Log collectors enable you to easily automate log upload from your network. The log collector runs on your network and receives logs over Syslog or FTP. Each log is automatically processed, compressed, and transmitted to the portal. FTP logs are uploaded to Microsoft Defender for Cloud Apps after the file finished the FTP transfer to the Log Collector. For Syslog, the Log Collector writes the received logs to the disk. Then the collector uploads the file to Defender for Cloud Apps when the file size is larger than 40 KB.

After a log is uploaded to Defender for Cloud Apps, it's moved to a backup directory. The backup directory stores the last 20 logs. When new logs arrive, the old ones are deleted. Whenever the log collector disk space is full, the log collector drops new logs until it has more free disk space. You'll receive a warning on the **Log collectors** tab of the **Upload logs automatically** settings when this happens.

Before setting up automatic log file collection, verify your log matches the expected log type. You want to make sure Defender for Cloud Apps can parse your specific file. For more information, see [Using traffic logs for Cloud Discovery](create-snapshot-cloud-discovery-reports.md#log-format).

> [!NOTE]
>
> * Defender for Cloud Apps provides support for forwarding logs from your SIEM server to the Log Collector assuming the logs are being forwarded in their original format. However, it is highly recommended that you integrate the log collector directly with your firewall and/or proxy.
> * The log collector compresses data before it is uploaded. The outbound traffic on the log collector will be 10% of the size of the traffic logs it receives.
> * If the log collector encounters issues, you will receive an alert after data wasn't received for 48 hours.

## Deployment modes

The Log Collector supports the **Container** deployment mode. It runs as a Docker image on [Windows](discovery-docker-windows.md), [Ubuntu on premises](discovery-docker-ubuntu.md), [Ubuntu in Azure](discovery-docker-ubuntu-azure.md), [RHEL on premises](discovery-docker-ubuntu.md) or CentOS.

## Next steps

> [!div class="nextstepaction"]
> [Working with Cloud Discovery data](working-with-cloud-discovery-data.md)
