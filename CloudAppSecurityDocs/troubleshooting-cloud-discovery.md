---
# required metadata

title: Troubleshooting Cloud Discovery errors - Cloud App Security | Microsoft Docs
description: This article provides a list of Cloud Discovery frequent errors and resolution recommendations for each.
keywords:
author: shsagir
ms.author: shsagir
manager: shsagir
ms.date: 04/19/2019
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: 76dfaebb-d477-4bdb-b3d7-04cc3fe6431d

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: seodec18

---
# Troubleshooting Cloud Discovery

*Applies to: Microsoft Cloud App Security*

This article provides a list of Cloud Discovery errors and resolution recommendations for each.

## Microsoft Defender ATP integration

If you integrated Microsoft Defender ATP with Cloud App Security, and you don't see the results of the integration - there's not a **Win10 endpoint users** report - make sure the machines you're connecting to are Windows 10 version 1809 or later, and that you waited the necessary two hours that it takes before your data is accessible.


## Log parsing errors

You can track the processing of Cloud Discovery logs using the governance log. This article provides resolution actions to be taken for each error that can be displayed there.

### Governance log errors

|Error|Description|Resolution|
|----|----|----|
|Unsupported file type|The file uploaded isn't a valid log file (for example, an image file).|Upload a **text**, **zip, or **gzip** file that was directly exported from your firewall or proxy.|
|The log format does not match|The log format you uploaded didn't match the expected log format for this data source.|1. Verify that the log isn't corrupt. <br /> 2. Compare and match your log to the sample format shown in the upload page.|
|Transactions are more than 90 days old|All transactions are more than 90 days old and are being ignored.|Export a new log with recent events and reupload it.|
|No transactions to cataloged cloud apps|No transactions to any recognized cloud apps are found in the log.|Verify that the log contains outbound traffic information.|
|Unsupported log type|When you select **Data source = Other (unsupported)**, the log isn't parsed. Instead, it's sent for review to the Cloud App Security technical team.|The Cloud App Security technical team builds a dedicated parser per each data source. Most popular data sources are [already supported](set-up-cloud-discovery.md). Each upload of an unsupported data source is reviewed and added to the pipeline for new data source parsers. New parser notifications are published as part of the Cloud App Security [release notes](release-notes.md).|

## Log collector errors

|ISSUE | RESOLUTION |
|--------|--|
|Could not connect to the log collector over FTP| 1. Verify that you are using FTP credentials and not SSH credentials. <br />2. Verify that the FTP client you are using is not set to SFTP.  |
|Failed updating collector configuration | 1. Verify that you entered the latest access token. <br />2. Verify in your firewall that the log collector is allowed to initiate outbound traffic on port 443.|
|Logs sent to the collector do not appear in the portal | 1.  Check to see if there are failed parsing tasks in the Governance log.  <br />  &nbsp;&nbsp;&nbsp;&nbsp;If so, troubleshoot the error with the Log Parsing error table above.<br /> 2. If not, check the data sources and Log collector configuration in the portal. <br /> &nbsp;&nbsp;&nbsp;&nbsp;a. In the Data source page, verify that the data source you are using is accurately configured. <br />&nbsp;&nbsp;&nbsp;&nbsp;b. In the Log collectors page, verify that the data source is linked to the right log collector. <br /> 3. Check the local configuration of the on-premises log collector machine.  <br />&nbsp;&nbsp;&nbsp;&nbsp;a. Log in to the log collector over SSH and run the collector_config utility.<br/>&nbsp;&nbsp;&nbsp;&nbsp;b. Confirm that your firewall or proxy is sending logs to the log collector using the protocol you defined (Syslog/TCP, Syslog/UDP or FTP) and that it is sending them to the correct port and directory.<br /> &nbsp;&nbsp;&nbsp;&nbsp;c. Run netstat on the machine and verify that it receives incoming connections from your firewall or proxy <br /> 4.   Verify that the log collector is allowed to initiate outbound traffic on port 443. |
|Log collector status: Created | The log collector deployment was not completed. Complete the on-premise deployment steps according to the deployment guide.|
|Log collector status: Disconnected | No data received in the last 24 hours from any of the linked data sources. |
|Failed pulling latest collector image| If you get this error during Docker deployment, it could be that you don't have enough memory ont he host machine. To check this, run this command on the host: `docker pull microsoft/caslogcollector`. If it returns this error: `failed to register layer: Error processing tar file(exist status 1): write /opt/jdk/jdk1.8.0_152/src.zip: no space left on device` contact your host machine administrator to provide more space.|

## Discovery dashboard errors

|Issue|Resolution|
|----|----|
|Discovery data was uploaded and parsed successfully but the Cloud Discovery dashboard looks empty|The Dashboard might be filtered on data your logs don't have so there's no data to show. Try changing the filters in the Cloud Discovery dashboard to show different types of data to see the results.|

## Next steps
  
[Daily activities to protect your cloud environment](daily-activities-to-protect-your-cloud-environment.md)   

[Premier customers can also create a new support request directly in the Premier Portal.](https://premier.microsoft.com/)  

