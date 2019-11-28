---
# required metadata

title: Configure automatic log upload using on-premise Docker
description: This article describes the process configuring automatic log upload for continuous reports in Cloud App Security using a Docker on Ubuntu or RHEL in an on-premises server.
keywords:
author: shsagir
ms.author: shsagir
manager: shsagir
ms.date: 11/19/2019
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.prod:
ms.service: cloud-app-security
ms.technology:

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: seodec18

---
# Docker on Ubuntu and RHEL on-premises

*Applies to: Microsoft Cloud App Security*

You can configure automatic log upload for continuous reports in Cloud App Security using a Docker on an on-premises Ubuntu or RHEL server.

## Technical requirements

* OS: Ubuntu 14.04, 16.04, and 18.04; RHEL 7.2 or higher, or CentOS 7.2 or higher 

* Disk space: 250 GB

* CPU: 2

* RAM: 4 GB

* Set your firewall as described in [Network requirements](network-requirements.md#log-collector)

> [!NOTE]
> If you have an existing log collector and want to remove it before deploying it again, or if you simply want to remove it, run the following commands:
>
> ```console
> docker stop <collector_name>
> docker rm <collector_name>
> ```

## Log collector performance

The Log collector can successfully handle log capacity of up to 50 GB per hour. The main bottlenecks in the log collection process are:

* Network bandwidth - Your network bandwidth determines the log upload speed.

* I/O performance of the virtual machine - Determines the speed at which logs are written to the log collector’s disk. The log collector has a built-in safety mechanism that monitors the rate at which logs arrive and compares it to the upload rate. In cases of congestion, the log collector starts to drop log files. If your setup typically exceeds 50 GB per hour, it's recommended that you split the traffic between multiple log collectors.

## Set up and configuration  

### Step 1 – Web portal configuration: Define data sources and link them to a log collector

1. Go to the **Automatic log upload** settings page.

    1. In the Cloud App Security portal, click the settings icon followed by **Log collectors**.

    ![settings icon](media/settings-icon.png)

1. For each firewall or proxy from which you want to upload logs, create a matching data source.

    1. Click **Add data source**.  
    ![Add a data source](media/add-data-source.png)
    1. **Name** your proxy or firewall.  
    ![ubuntu1](media/ubuntu1.png)
    1. Select the appliance from the **Source** list. If you select **Custom log format** to work with a network appliance that isn't listed, see [Working with the custom log parser](custom-log-parser.md) for configuration instructions.
    1. Compare your log with the sample of the expected log format. If your log file format doesn't match this sample, you should add your data source as **Other**.
    1. Set the **Receiver type** to either **FTP**, **FTPS**, **Syslog – UDP**, or **Syslog – TCP**, or **Syslog – TLS**.

    > [!NOTE]
    > Integrating with secure transfer protocols (FTPS and Syslog – TLS) often requires additional settings or your firewall/proxy.

    f. Repeat this process for each firewall and proxy whose logs can be used to detect traffic on your network. It's recommended to set up a dedicated data source per network device to enable you to:

    * Monitor the status of each device separately, for investigation purposes.
    * Explore Shadow IT Discovery per device, if each device is used by a different user segment.

1. Go to the **Log collectors** tab at the top.

    1. Click **Add log collector**.
    1. Give the log collector a **name**.
    1. Enter the **Host IP address** of the machine you'll use to deploy the Docker. The host IP address can be replaced with the machine name, if there is a DNS server (or equivalent) that will resolve the host name.
    1. Select all **Data sources** that you want to connect to the collector, and click **Update** to save the configuration.

    ![ubuntu2](media/ubuntu2.png)

1. Further deployment information will appear. **Copy** the run command from the dialog. You can use the copy to clipboard icon. ![copy to clipboard icon](media/copy-icon.png)

1. **Export** the expected data source configuration. This configuration describes how you should set the log export in your appliances.

    ![Create log collector](media/windows7.png)

    > [!NOTE]
    >
    > * A single Log collector can handle multiple data sources.
    > * Copy the contents of the screen because you will need the information when you configure the Log Collector to communicate with Cloud App Security. If you selected Syslog, this information will include information about which port the Syslog listener is listening on.
    > * For users sending log data via FTP for the first time, we recommend changing the password for the FTP user. For more information, see [Changing the FTP password](log-collector-ftp.md#changing-the-ftp-password).

### Step 2 – On-premises deployment of your machine

The following steps describe the deployment in Ubuntu. The deployment steps for other platforms are slightly different.

1. Open a terminal on your Ubuntu machine.

1. Change to root privileges using the command: `sudo -i`

1. To bypass a proxy in your network, run the following two commands:

    ```bash
    export http_proxy='<IP>:<PORT>' (e.g. 168.192.1.1:8888)
    export https_proxy='<IP>:<PORT>'
    ```

1. If you accept the [software license terms](https://go.microsoft.com/fwlink/?linkid=862492), uninstall old versions and install Docker CE by running the following command:

    ```bash
    curl -o /tmp/MCASInstallDocker.sh https://adaprodconsole.blob.core.windows.net/public-files/MCASInstallDocker.sh && chmod +x /tmp/MCASInstallDocker.sh; /tmp/MCASInstallDocker.sh
    ```

    > [!NOTE]
    > If this command fails to validate your proxy certificate, run the command using `curl -k` at the beginning.

    ![ubuntu5](media/ubuntu5.png)

1. Deploy the collector image on the hosting machine by importing the collector configuration. Import the configuration by copying the run command generated in the portal. If you need to configure a proxy, add the proxy IP address and port number. For example, if your proxy details are 192.168.10.1:8080, your updated run command is:

    ```bash
    (echo 6f19225ea69cf5f178139551986d3d797c92a5a43bef46469fcc997aec2ccc6f) | docker run --name MyLogCollector -p 21:21 -p 20000-20099:20000-20099 -e "PUBLICIP='192.2.2.2'" -e "PROXY=192.168.10.1:8080" -e "CONSOLE=tenant2.eu1-rs.adallom.com" -e "COLLECTOR=MyLogCollector" --security-opt apparmor:unconfined --cap-add=SYS_ADMIN --restart unless-stopped -a stdin -i microsoft/caslogcollector starter
    ```

    ![Create log collector](media/windows7.png)

1. Verify that the collector is running properly with the following command: `docker logs <collector_name>`

You should see the message: **Finished successfully!**
![ubuntu8](media/ubuntu8.png)

### Step 3 - On-premises configuration of your network appliances

Configure your network firewalls and proxies to periodically export logs to the dedicated Syslog port of the FTP directory according to the directions in the dialog. For example:

```bash
BlueCoat_HQ - Destination path: \<<machine_name>>\BlueCoat_HQ\
```

### Step 4 - Verify the successful deployment in the Cloud App Security portal

Check the collector status in the **Log collector** table and make sure the status is **Connected**. If it's **Created**, it's possible the log collector connection and parsing haven't completed.

![ubuntu9](media/ubuntu9.png)

You can also go to the **Governance log** and verify that logs are being periodically uploaded to the portal.

If you have problems during deployment, see [Troubleshooting Cloud Discovery](troubleshooting-cloud-discovery.md).

### Optional - Create custom continuous reports

Verify that the logs are being uploaded to Cloud App Security and that reports are generated. After verification, create custom reports. You can create custom discovery reports based on Azure Active Directory user groups. For example, if you want to see the cloud use of your marketing department, import the marketing group using the import user group feature. Then create a custom report for this group. You can also customize a report based on IP address tag or IP address ranges.

1. In the Cloud App Security portal, under the Settings cog, select Cloud Discovery settings, and then select **Continuous reports**.
1. Click the **Create report** button and fill in the fields.
1. Under the **Filters** you can filter the data by data source, by [imported user group](user-groups.md), or by [IP address tags and ranges](ip-tags.md).

![Custom continuous report](media/custom-continuous-report.png)

## Next steps

> [!div class="nextstepaction"]
> [Log collector FTP configuration](log-collector-ftp.md)

[!INCLUDE [Open support ticket](includes/support.md)]
