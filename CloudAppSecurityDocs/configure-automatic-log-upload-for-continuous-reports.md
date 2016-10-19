---
# required metadata

title: Configure automatic log upload for continuous reports | Microsoft Docs
description: This topic provides information about how to upload logs to create automatic Cloud Discovery reports.
keywords:
author: rkarlin
manager: mbaldwin
ms.date: 10/15/2016
ms.topic: article
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: c4123272-4111-4445-b6bd-2a1efd3e0c5c

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Configure automatic log upload for continuous reports
Before setting up automatic log file collection, verify that your log matches the expected log type, to make sure Cloud App Security can parse your specific file. 

## Technical requirements
- Hypervisor: HyperV or VMware
- Disk space: 250 GB
- CPU: 2
- RAM: 4 GB 
- Firewall settings: 
- Allow the log collector to receive inbound FTP and Syslog traffic
- Allow the log collector to initiate outbound traffic to the portal (for example contoso.cloudappsecurity.com) on port 443

  
## Set up automatic log file collection  
  
Log collectors enable you to easily automate log upload from your network. The log collector runs on your network and receives logs over Syslog or FTP. Each log is automatically processed, compressed and transmitted to the portal. FTP logs are uploaded to Cloud App Security after the file finished the FTP transfer to the Log Collector and for Syslogs, the Log Collector writes the logs received to disk every 20 minutes and then uploads the file to Cloud App Security.  The log collector virtual machine is available for Hyper-V (VHD format) and VMware hypervisor (OVF format) and requires 250GB disk space, 2 CPUs and 4GB RAM. 
     
  
     The log collector VHD image can be downloaded and run on Azure servers.  
  
2.  Go to the automated upload setting page:  
    In the Cloud App Security portal, click the settings icon ![settings icon](./media/settings-icon.png "settings icon"), followed by  **Cloud Discovery Settings** and then select the **Upload logs automatically** tab.  
  
3.  For each firewall or proxy from which you want to upload logs, create a matching data source:  
  
    1.  Click **Add data source**.  
  
    2.  **Name** your proxy or firewall.  
  
    3.  Select the appliance from the **Source** list.  
  
    4.  Compare your log with the sample of the expected log format. If your log file format does not match this sample, you should add your data source as **Other**.  
  
    5.  Set the **Receiver type** to either **FTP** or **Syslog**.  
  
         For **Syslog**, choose **UDP** or **TCP**.  
  
    6.  Repeat this process for each firewall and proxy whose logs can be used to detect traffic on your network.  
  
4.  Go to the **Log collectors** tab at the top.  
  
    1.  Click **Add log collector**.  
  
    2.  Give the log collector a **name**.  
  
    3.  Select all **Data sources** that you want to connect to the collector, and click **Update**.  
  
         > [!NOTE] 
       > Copy the contents of the screen because you will need the information when you configure the Log Collector to communicate with Cloud App Security. If you selected Syslog, this information will include information about which port the Syslog listener is listening on.
         
![discovery data sources](./media/discovery-data-sources.png)
> [!NOTE] 
         > A single Log collector can handle multiple data sources.
  
4.  **Download** a new log collector virtual machine by clicking on Hyper-V or VMWare and unzip the file using the password you received in the portal.  
  
## Set up your virtual machine in Hyper-V:  
  
1.  Open the Hyper-V Manager.  
  
2.  Select **New** and then **Virtual Machine** and click **Next**.  
  
             ![discovery hyperv virtual machine](./media/discovery-hyperv-virtual-machine.png "discovery hyperv virtual machine")  
  
3.  Provide a **Name** for the new virtual machine, for example CloudAppSecurityLogCollector01.then click **Next**.  
  
4.  Select **Generation 1** and click **Next**.  
  
5.  Change the **Startup memory** to **4096 MB**.  
        
6. Check **Use Dynamic Memory** for this virtual machine and click **Next**.  
  
7.  If available, choose the network **Connection** and click **Next**.  
  
8.  Choose **Use an existing virtual hard disk** and select the .**vhd** file that was included in the Zip file you downloaded.  
  
9.  Click **Next** and then click **Finish**.  
  
             The machine will be added to your Hyper-V environment.  
  
9. Click on the machine in the **Virtual Machines** table and click **Start**.   
  
10. Connect to the Log Collector virtual machine to see if it has been assigned a DHCP address: 
Click on the virtual machine and select **Connect**. You should see the login prompt. If you see an IP address, then you can connect to the virtual machine using a terminal/SSH tool.  If you do not see an IP address, log in using the Hyper-V/VMWare connection tools with the credentials you copied down when you created the Log Collector above. You can change the password and you configure the virtual machine by running the following command
```
sudo network_config
```
> [!NOTE]
> The virtual machine is pre-configured to obtain an IP address from a DHCP server. If you need to configure a static IP addresses, default gateway, hostname, DNS servers and NTPS, you can use the **network_config** utility or perform changes manually.


At this point, your log collector should be connected to your network and should be able to reach the Cloud App Security portal.  

## Log in and import 
The first time you log into the log collector and import the log collector's configuration from the portal, as follows. 

1.  Log into the log collector over SSH using the Interactive admin credentials provided to you in the portal. (If this is your first time logging into the console, you will need to change the password and log in again after changing the password. If you are using a terminal session you might need to restart the terminal session. )
2.  Run the collector config utility with the access token provided to you when you created the log collector. 

```
sudo collector_config <access token>
```

3. Enter your console domain, for example:

```
contoso.portal.cloudappsecurity.com
```

This is available from the URL you see after logging into the Cloud App Security portal. 
 

4. Enter the name of the log collector you want to configure, for example:

**CloudAppSecurityLogCollector01** or **NewYork** from the picture above.
 
8.  Import the log collector's configuration from the portal, as follows:  
  
      1.  Log into the log collector over SSH using the Interactive admin credentials provided to you in the portal.  
  
       2.  Run the collector config utility with the access token provided to you in the command **sudo collector_config \<access token>**  
  
             Enter your console domain, for example:  
  
             **contoso.portal.cloudappsecurity.com ** 
  
             Enter the name of the log collector you want to configure, for example:  
  
             **CloudAppSecurityLogCollector01**  
  
5.  Configure your network firewalls and proxies to periodically export logs to the dedicated Syslog port of the FTP directory according to the directions in the dialog, for example:  
  
     `London Zscaler - Destination path: 614`  
  
     `SF Blue Coat - Destination path: \\CloudAppSecurityCollector01\BlueCoat\`  
  
6.  Use the Governance log to verify that logs are being periodically uploaded to the portal.  
  
## Log collector performance
The Log collector can successfully handle log capacity of up to 50 GB per hour.

The main bottlenecks in the log collection process are:
* Network bandwidth - your network bandwidth determines the log upload speed.
* I/O performance of the virtual machine allocated by your IT - determines the speed at which logs are written to the log collector’s disk.

The log collector has a built-in safety mechanism that monitors the rate at which logs arrive and compares it to the upload rate. In cases of congestion, the log collector starts to drop log files. If your setup generally exceeds 50 GB per hour, it is recommended to split the traffic between multiple log collectors.