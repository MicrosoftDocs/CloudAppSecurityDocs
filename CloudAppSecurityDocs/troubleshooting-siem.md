---
# required metadata

title: Troubleshooting SIEM integration - Cloud App Security | Microsoft Docs
description: This article provides a list of possible issues when connecting your SIEM to Cloud App Security and provides resolutions for each.
keywords:
author: rkarlin
ms.author: rkarlin
manager: rkarlin
ms.date: 12/10/2018
ms.topic: conceptual
ms.collection: M365-security-compliance
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
ms.custom: seodec18

---
# Troubleshooting the SIEM agent

*Applies to: Microsoft Cloud App Security*

This article provides a list of possible issues when connecting your SIEM to Cloud App Security and provides possible resolutions.

## Troubleshooting

Make sure the status of the SIEM agent in the Microsoft Cloud App Security portal isn't **Connection error** or **Disconnected** and there are no agent notifications. The status shows as **Connection error** if the connection is down for more than two hours. The status changes to **Disconnected** if the connection is down for over 12 hours.

If you see one of the following errors in the cmd prompt while running the agent, use the following steps to remediate the problem:

|Error|Description|Resolution|
|----|----|----|
|General error during bootstrap|Unexpected error during agent bootstrap.|Contact support.|
|Too many critical errors|Too many critical errors occurred while connecting the console. Shutting down.|Contact support.|
|Invalid token|The token provided isn't valid.|Make sure you copied the right token. You can use the process above to regenerate the token.|
|Invalid proxy address|The proxy address provided isn't valid.|Make sure you entered the right proxy and port.|


After creating the agent, check the SIEM agent page in the Cloud App Security portal. If you see one of the following **Agent notifications**, use the following steps to remediate the problem:

|Error|Description|Resolution|
|----|----|----|
|**Internal error**|Something unknown went wrong with your SIEM agent.|Contact support.|
|**Data server send error**|You can get this error if you're working with a Syslog server over TCP. The SIEM agent can't connect to your Syslog server.  If you get this error, the agent will stop pulling new activities until it’s fixed. Make sure to follow the remediation steps until the error stops appearing.|1. Make sure you properly defined your Syslog server: In the Cloud App Security UI, edit your SIEM agent as described above. Make sure you wrote the name of the server properly and set the right port. </br>2. Check connectivity to your Syslog server: Make sure your firewall isn't blocking communication.| 
|**Data server connection error**| You can get this error if you're working with a Syslog server over TCP. The SIEM agent can't connect to your Syslog server.  If you get this error, the agent will stop pulling new activities until it’s fixed. Make sure to follow the remediation steps until the error stops appearing.|1. Make sure you properly defined your Syslog server: In the Cloud App Security UI, edit your SIEM agent as described above. Make sure you wrote the name of the server properly and set the right port. </br>2. Check connectivity to your Syslog server: Make sure your firewall isn't blocking communication.|
|**SIEM agent error**|The SIEM agent has been disconnected for more than X hours|Make sure that you didn't change the SIEM configuration in the Cloud App Security portal. Otherwise, this error could indicate connectivity issues between Cloud App Security and the computer on which you're running the SIEM agent.|
|**SIEM agent notification error**|SIEM agent notification forward errors were received from a SIEM agent.|This error indicates that you have received errors about the connection between the SIEM agent and your SIEM server. Make sure there isn't a firewall blocking your SIEM server or the computer on which you're running the SIEM agent. Also, check that the IP address of the SIEM server wasn't changed.|


## Next steps
  
[Daily activities to protect your cloud environment](daily-activities-to-protect-your-cloud-environment.md)   

[Premier customers can also create a new support request directly in the Premier Portal.](https://premier.microsoft.com/)  
  
