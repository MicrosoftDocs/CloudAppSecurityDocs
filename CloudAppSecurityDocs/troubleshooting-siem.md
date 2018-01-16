---
# required metadata

title: Troubleshooting SIEM integration with Cloud App Security | Microsoft Docs
description: This topic provides a list of possible issues when connecting your SIEM to Cloud App Security and provides resolutions for each.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/15/2018
ms.topic: article
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: de64d9ca-eaed-4243-bcf7-adca5aff18c8

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Troubleshooting the SIEM agent

Make sure the status of the SIEM agent in the Cloud App Security portal is not **Connection error** or **Disconnected** and there are no agent notifications. It will show up as **Connection error** if the connection is down for more than two hours and as **Disconnected** if the connection is down for over 12 hours.

If you see one of the following errors in the cmd prompt while running the agent, use the following steps to remediate the problem:

|Error|Description|Resolution|
|----|----|----|
|General error during bootstrap|Unexpected error during agent bootstrap.|Contact support.|
|Too many critical errors|Too many critical errors occurred while connecting the console. Shutting down.|Contact support.|
|Invalid token|The token provided is not valid.|Make sure you copied the right token. You can use the process above to regenerate the token.|
|Invalid proxy address|The proxy address provided is not valid.|Make sure you entered the right proxy and port.|


After creating the agent, if you see one of the following **Agent notifications** in the Cloud App Security portal on the SIEM agent page, use the following steps to remediate the problem:

|Error|Description|Resolution|
|----|----|----|
|**Internal error**|Something unknown went wrong with your SIEM agent.|Contact support.|
|**Data server send error**|You can get this error if you are working with a Syslog server over TCP. The SIEM agent cannot connect to your Syslog server.  If you get this error, the agent will stop pulling new activities until it’s fixed, so make sure to follow the remediation steps until the error stops appearing.|1. Make sure you properly defined your Syslog server: In the Cloud App Security UI, edit your SIEM agent as described above, and make sure you wrote the name of the server properly, and set the right port. </br>2. Check connectivity to your Syslog server: Make sure your firewall isn't blocking communication.| 
|**Data server connection error**| You can get this error if you are working with a Syslog server over TCP. The SIEM agent cannot connect to your Syslog server.  If you get this error, the agent will stop pulling new activities until it’s fixed, so make sure to follow the remediation steps until the error stops appearing.|1. Make sure you properly defined your Syslog server: In the Cloud App Security UI, edit your SIEM agent as described above, and make sure you wrote the name of the server properly, and set the right port. </br>2. Check connectivity to your Syslog server: Make sure your firewall isn't blocking communication.|
|**SIEM agent error**|The SIEM agent has been disconnected for more than X hours|Make sure that you didn't change the SIEM configuration in the Cloud App Security portal. Otherwise, this could indicate connectivity issues between Cloud App Security and the computer on which you are running the SIEM agent.|
|**SIEM agent notification error**|SIEM agent notification forward errors were received from a SIEM agent.|This indicates that you have received errors regarding the connection between the SIEM agent and your SIEM server. Make sure there isn't a firewall blocking your SIEM server or the computer on which you are running the SIEM agent. Also, check that the IP address of the SIEM server was not changed.|



## See Also  
[Daily activities to protect your cloud environment](daily-activities-to-protect-your-cloud-environment.md)   

[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  