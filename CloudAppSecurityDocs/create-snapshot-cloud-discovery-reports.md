---
title: "Create snapshot Cloud Discovery reports"
ms.custom: na
ms.date: "08/21/2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
ms.assetid: ecc1949d-c861-4636-952a-c3a260719bb5
caps.latest.revision: 7
author: "Rkarlin"
ms.author: "rkarlin"
---
# Create snapshot Cloud Discovery reports
It is important to upload a log manually and let Cloud App Security parse it before attempting to use the automatic log collector.

To create a snapshot report:
  
1.  Collect log files from your firewall and proxy, through which users in your organization access the Internet. Make sure to gather logs during times of peak traffic that are representative of all user activity in your organization.  
  
2.  In the [!INCLUDE[Adallom](./includes/adallom_md.md)] portal, click on **Discover** and then **Create new snapshot report**.  
  
     ![Create new snapshot report](./media/create-new-snapshot-report.png)
     
      
3.  Enter a **Report name** and a **Description**
  
4.  Select the **Data source** from which you want to upload the log files.  
  
5.  **Choose the traffic logs** that you want to upload. You can upload up to 20 files at once.  
  
6.  Click **Create**.  
  
     ![New snapshot report](./media/new-snapshot-report.png) 
  
7.  After upload completes, the status message will appear at the top right corner of your screen letting you know that your log was successfully uploaded.  
  
8.  After you upload your log files, it will take some time for them to be parsed and analyzed.  
 After processing of your log files completes, you will receive an email to notify you that it is done. 
  
9. A notification banner will appear in the status bar at the top of the portal to update you with the processing status of your log files.  
  
  ![processing log file menu bar](./media/processing-log-file-menu-bar.png) 
  
     After the logs are uploaded successfully, you should see a notification letting you know that the log file processing completed successfully.  
   
 10. At this point, a you can view the report either by clicking the link in the status bar, or by going to the Settings cog, and selecting **Cloud Discovery settings**.   
  
     ![Discovery settings tab](./media/discovery-settings-tab.png)
 11. Then selecting **Manage snapshot reports** and select your snapshot report.
 
 ![snapshot report managment](./media/snapshot-report-managment.png)
      
  
      
  