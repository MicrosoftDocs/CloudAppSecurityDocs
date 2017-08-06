---
# required metadata

title: Connect Azure to Cloud App Security for visibility and control over use | Microsoft Docs
description: This topic provides information about how to connect Azure to Cloud App Security using the API connector.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 8/6/2017
ms.topic: get-started-article
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: 3a677bc7-c8b7-4c6a-aada-82c8b3778352


# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Connect Azure to Microsoft Cloud App Security

This section provides instructions for connecting Cloud App Security to your existing Azure account using the app connector API.  
  
## Setting up Azure for connection to Cloud App Security

Cloud App Security connects to Azure via Event Hubs. This section provides instruction for streaming all your Activity Logs to a single Event Hub in your subscription. 

1.	Stream the Azure Activity Log of your Azure subscription to an Event Hub. Follow the official guide in the Azure documentation: https://docs.microsoft.com/en-us/azure/monitoring-and-diagnostics/monitoring-stream-activity-logs-event-hubs

Note: if you have more than one Azure subscription, repeat this for each subscription but use a single Event Hub that will be shared across your subscriptions

After completing the instructions, a new Event Hub will have been created in the Namespace you chose.

2.	Get a connection string to your Event Hub

a.	Go to the Event Hubs Blade


b.	Select your Event Hub Namespace


c.	Click on Event Hubs under the Entities s 

d.	Select the new Event Hub created by Azure Monitor. It will always have the name “insights-operational-logs”.


3.	Click on Shared access policies and then click on Add


4.	Create a new access policy. Enter a name for the new policy, and make sure to include at least the Listen claim. When done, click Create.


5.	Click on the new access policy you created in the previous steps


6.	Copy one of the connection strings. Click on the Copy button next to the primary or the secondary connection strings.


 
7.	Paste your connection string in Cloud App Security. 
8.	In the App connectors page, click the plus sign followed by Microsoft Azure.

9.	Click Connect Microsoft Azure, then paste your previously-copied connection string
10.	Use $Default as the Consumer group, unless you have reasons to create other consumer groups. When done, click Connect.




## See Also  
[Control cloud apps with policies](control-cloud-apps-with-policies.md)   
[For technical support, please visit the Cloud App Security assisted support page.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  