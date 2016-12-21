---
# required metadata

title: Cloud Discovery policies | Microsoft Docs
description: This topic provides information about working with Cloud Discovery policies.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 12/20/2016
ms.topic: article
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: 7de9ce83-a612-4956-8c17-5d8717ea5474

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# SIEM integration - - PUBLIC PREVIEW - - 
    
You can now integrate Cloud App Security with your SIEM server to enable centralized monitoring of alerts and activities. Integrating with a SIEM service allows you to better protect your cloud applications while maintaining your usual security workflow, automating security procedures and correlating between cloud-based and on-premises events. The Cloud App Security SIEM agent runs on your server and pulls alerts and activities from Cloud App Security and streams them into the SIEM server.



## Prerequisites

- A standard Windows or Linux server (can be a virtual machine).
- The server must be running Java 8; earlier versions are not supported.

## Integrating with your SIEM

To integrate Cloud App Security with your SIEM agent:

1. In the Cloud App Security portal, under the Settings cog, click **SIEM agents**.

2. Click Add SIEM agent to start the wizard.
3. In the wizard, click **Add SIEM agent**.	
4. In the wizard, fill in a name, and **Select your SIEM format**:
-	You can select **HP ArcSight** . Click **Advanced settings** to **Include system name** in the Syslog message header of the local system that is running the agent. 
-	You can select **Generic CEF** which enables you to add customized settings to the Syslog message header specifying a time format, PRI (priority code) and system name.
Click **Next**.

5. Type in the IP address of the **Remote syslog host** and the **Syslog port number**. Select TCP or UDP as the Remote Syslog protocol.
You can work with your security admin to get these details if you don't have them.
Click **Next**.

6. Select which data types, **Alerts** and **Activities** you want to export to your SIEM server. 
Use the slider to enable and disable them, by default, everything is selected. You can use the **Apply to** dropdown to set filters to send only specific alerts and activities to your SIEM server.
You can click **Edit and preview results** to check that the filter works as expected. 
Click **Next**. 

7. Copy the token and save it for later. 
After you do this, you will see the SIEM agent you added in the table. It will show that it's **Created** until it’s connected later.
If you lose the token, you can always regenerate it by clicking the three dots at the end of the row for the SIEM agent in the table, and selecting **Regenerate token**.

 ![SIEM - regenerate token](./media/siem-regenerate-token.png)

8. Download the .jar file from ????.

8. Run the .jar file on your SIEM server.
 After running the file, run the following:
    
    jar cas siemagent [--logsDirectory <DIRNAME>] [--proxy <ADDRESS[:PORT]>] --token <TOKEN>

Where DIRNAME is the path to the directory you want to use for local agent debug logs.
ADDRESS[:PORT] is the proxy server address and port that the server uses to connect to the Internet.
TOKEN is the SIEM agent token you copied in the previous step.

You can type -h at any time to get help.
The following SIEM agent logs are written to the local log file:

|----|----|
|General error during bootstrap|Unexpected error during agent bootstrap!|
|Startup|Initializing agent...|
|Startup finished, starting main loop|Initialization complete|
|Too many critical errors|Got too many critical errors connecting the console. Shutting down|
|Invalid token|The token provided is invalid|
|Invalid proxy address|The proxy address provided is invalid|

9. If you need to delete or edit the SIEM agent in the future, you can click on the three dots at the end of the row for the SIEM agent in the table, and select **Edit** or **Delete**. If you edit the SIEM agent, you do not need to rerun the .jar file, it updates automatically.

![SIEM - edit or delete](./media/siem-edit-delete.png)









## See Also  
[User activity policies](user-activity-policies.md)   
[For technical support, please visit the Cloud App Security assisted support page.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  