---
# required metadata

title: Create snapshot reports of Cloud Discovery cloud app use
description: This article provides information about how to upload logs manually to create a snapshot report of your Cloud Discovery apps.
keywords:
author: rkarlin
ms.author: rkarlin
manager: rkarlin
ms.date: 04/07/2019
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: ecc1949d-c861-4636-952a-c3a260719bb5

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: seodec18


---
# Create snapshot Cloud Discovery reports

*Applies to: Microsoft Cloud App Security*

It's important to upload a log manually and let Microsoft Cloud App Security parse it before trying to use the automatic log collector. For information on how the log collector works and the expected log format, see [Using traffic logs for Cloud Discovery](#log-format).

If you don't have a log yet and you want to see an example of what your log should look like, download a sample log file. Follow the procedure below to see what your log should look like.


To create a snapshot report:
  
1. Collect log files from your firewall and proxy, through which users in your organization access the Internet. Make sure to gather logs during times of peak traffic that are representative of all user activity in your organization.  
  
2. In the Cloud App Security portal, click on **Discover** then **Create snapshot report**.  
  
   ![Create new snapshot report](./media/create-new-snapshot-report.png)
     
3. Enter a **Report name** and a **Description**
  
    ![New snapshot report](./media/new-snapshot-report.png) 

4. Select the **Data source** from which you want to upload the log files.  
  
5. Verify your log format to make sure that it's formatted properly according to the sample log you can download. Click **View and verify** then **Download sample log**. Compare your log with the sample provided to make sure it's compatible. 

   ![Verify your log format](./media/cloud-discovery-snapshot-verify.png)  

   > [!NOTE]
   > The FTP sample format is supported in snapshots and automated upload while syslog is supported in automated upload only.<br></br>
   Downloading a sample log will download a sample FTP log.


6. **Choose the traffic logs** that you want to upload. You can upload up to 20 files at once. Compressed and zipped files are also supported.  
  
7. Click **Create**.  

8. After upload completes, the status message will appear at the top right corner of your screen letting you know that your log was successfully uploaded.  
  
9. After you upload your log files, it will take some time for them to be parsed and analyzed.  
   After processing of your log files completes, you'll receive an email to notify you that it's done. 
  
10. A notification banner will appear in the status bar at the top of the **Cloud Discovery dashboard**. The banner updates you with the processing status of your log files.  
    ![processing log file menu bar](./media/processing-log-file-menu-bar.png) 
   
11. After the logs are uploaded successfully, you should see a notification letting you know that the log file processing completed successfully. At this point, you can view the report either by clicking the link in the status bar, or by going to the Settings cog and selecting **Cloud Discovery settings**.   
  
     ![Discovery settings tab](./media/discovery-settings-tab.png)
12. Then selecting **Snapshot reports** and select your snapshot report.
 
     ![snapshot report management](./media/snapshot-report-managment.png)

  
## Using traffic logs for Cloud Discovery <a name="log-format"></a>
Cloud Discovery uses the data in your traffic logs. The more detailed your log, the better visibility you get. Cloud Discovery requires web-traffic data with the following attributes:
- Date of the transaction
- Source IP
- Source user - highly recommended
- Destination IP address
- Destination URL **recommended** (URLs provide higher accuracy for cloud app detection than IP addresses)
- Total amount of data (data information is highly valuable)
- Amount of uploaded or downloaded data (provides insights about the usage patterns of the cloud apps)
- Action taken (allowed/blocked)

Cloud Discovery can't show or analyze attributes that aren't included in your logs.
For example, **Cisco ASA Firewall** standard log format doesn't have the **number of uploaded bytes per transaction**, **Username**, and  **Target URL** (only target IP).
Therefore, these attributes will not be shown in Cloud Discovery data for these logs, and the visibility into the cloud apps will be limited. For Cisco ASA firewalls, it is necessary to set the information level to 6. 


To successfully generate a Cloud Discovery report, your traffic logs must meet the following conditions:
1. [Data source is supported](set-up-cloud-discovery.md#supported-firewalls-and-proxies).
2. Log format matches the expected standard format (format checked upon upload by the Log tool).
3. Events aren't more than 90 days old.
4. The log file is valid and includes outbound traffic information.


 
## Next steps  
[Control cloud apps with policies](control-cloud-apps-with-policies.md)   

[Premier customers can also create a new support request directly in the Premier Portal.](https://premier.microsoft.com/)  
    
      
  
