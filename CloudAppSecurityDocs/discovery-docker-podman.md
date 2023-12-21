---
title: Configure automatic log upload using on-premises Podman on Linux | Microsoft Defender for Cloud Apps
description: This article describes how to configure automatic log upload for continuous reports in Defender for Cloud Apps using a Podman container on Linux in an on-premises server.
ms.date: 12/21/2023
ms.topic: how-to
---

# Configure automatic log upload using Podman

[!INCLUDE [Banner for top of topics](includes/banner.md)]

This article describes how to configure automatic log upload for continuous reports in Defender for Cloud Apps using a Podman container on Linux in an on-premises server. Customers using RHEL 8 or higher must use Podman for automatic log collection.

## Prerequisites

Before you start, make sure you're using a container with RHEL 8 and higher.

Also, since Docker and Podman can't coexist on the same machine, make sure to uninstall any Docker installations before running Podman.

## Setup and configuration

1. Sign into Microsoft Defender XDR and select **Settings > Cloud Apps > Cloud Discovery > Automatic log upload**.

1. Make sure that you have a data source defined on the **Data sources** tab. If you don't, select **Add a data source** to add one. <!--i don't see this option?-->

1. Select the **Log collectors** tab, which lists all the log collectors deployed on your tenant.

1. Select the **Add log collector** link. Then, in the **Create log collector** dialog enter:

    |Field  |Description  |
    |---------|---------|
    |**Name**     |    Enter a meaningful name, based on key information that the log collector uses, such as your internal naming standard or a site location.     |
    |**Host IP address or FQDN**     |  Enter your log collector's host machine or virtual machine (VM) IP address. Make sure that your syslog service or firewall can access the IP address / FQDN you enter. |
    |**Data source(s)**     |  Select the data source you want to use.  If you're using multiple data sources, the selected source is applied to a separate port so that the log collector can continue to send data consistently.  <br><br>For example, the following list shows examples of data source and port combinations: <br>- Palo Alto: 601 <br>- CheckPoint: 602 <br>- ZScaler: 603 |

1. Select **Create** to show further instructions on the screen for your specific situation.

1. Copy the command displayed and modify it as needed based on the container service you're using. For example:

    ```bash
    (echo <key>) | podman run --privileged --name PodmanRun -p 601:601/tcp -p 21:21 -p 20000-20099:20000-20099 -e "PUBLICIP='10.0.2.15'" -e "PROXY=" -e "SYSLOG=true" -e "CONSOLE= <tenant>.us3.portal.cloudappsecurity.com" -e "COLLECTOR=PodmanTest" --security-opt apparmor:unconfined --cap-add=SYS_ADMIN --restart unless-stopped -a stdin -i mcr.microsoft.com/mcas/logcollector starter 
    ```

1. Run the modified command on your machine to deploy the container. When successful, the logs show pulling an image from mcr.microsoft.com and continuing to create blobs for the container.

1. When the container is fully deployed, verify that it's working by checking with the containerization service:

    ```bash
    podman ps
    ```

> [!NOTE]
> Restarting the Podman host machine requires you to start the container again too.
 
Known Issues:  
1.	Podman container will not start upon host server reboot – 
a.	Issue: https://linuxhandbook.com/autostart-podman-containers/ 
b.	Podman’s architecture was not built to restart container’s at server boot. As a result you need to continue and setup a new command on Systemd in order to start on boot.  
2.	Podman container when deployed does not continue to get firewall logs. Logs do not seem to continue and get sent up to the Defender for Cloud Apps portal.  
a.	Verify that rsyslog is continuing to rotate on the log collector first. If it is, wait a couple of hours and see if anything changes. 
i.	podman logs <container name>  
b.	if the logs do not continue to get sent, make sure that the deployment of the container itself continued to utilize the --privileged flag. Failure to do so will not see the container continue to gather uploaded logs to the host machine.  

## Related content

For more information, see [Configure automatic log upload for continuous reports](discovery-docker.md). 