---
# required metadata

title: SIEM integration | Microsoft Docs
description: This topic provides information integrating your SIEM with Cloud App Security.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/8/2017
ms.topic: article
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: 4649423b-9289-49b7-8b60-04b61eca1364


# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# SIEM integration -PUBLIC PREVIEW- 
    
You can now integrate Cloud App Security with your SIEM server to enable centralized monitoring of alerts and activities. Integrating with a SIEM service allows you to better protect your cloud applications while maintaining your usual security workflow, automating security procedures and correlating between cloud-based and on-premises events. The Cloud App Security SIEM agent runs on your server and pulls alerts and activities from Cloud App Security and streams them into the SIEM server.
When you first integrate your SIEM with Cloud App Security, activities and alerts from the last two days will be forwarded to the SIEM and all activities and alerts from then on. Additionally, if you disable this feature for an extended period, when you enable it again it will forward the past two days of alerts and activities and then all alerts and activities from then on.

Integrating with your SIEM is accomplished in three steps:
1. Set it up in the Cloud App Security portal. 
2. Download the JAR file and run it on your server.
3. Validate that the SIEM agent is working

## Prerequisites

- A standard Windows or Linux server (can be a virtual machine).
- The server must be running Java 8; earlier versions are not supported.

## Integrating with your SIEM

### Step 1: Set it up in the Cloud App Security portal

1. In the Cloud App Security portal, under the Settings cog, click **SIEM agents**.

2. Click Add SIEM agent to start the wizard.
3. In the wizard, click **Add SIEM agent**.	
4. In the wizard, fill in a name, and **Select your SIEM format** and set any **Advanced settings** that are relevant to that format. 
Click **Next**.

   ![General SIEM settings](./media/siem1.png)

5. Type in the IP address of the **Remote syslog host** and the **Syslog port number**. Select TCP or UDP as the Remote Syslog protocol.
You can work with your security admin to get these details if you don't have them.
Click **Next**.
  ![Remote Syslog settings](./media/siem2.png)

6. Select which data types, **Alerts** and **Activities** you want to export to your SIEM server. 
Use the slider to enable and disable them, by default, everything is selected. You can use the **Apply to** dropdown to set filters to send only specific alerts and activities to your SIEM server.
You can click **Edit and preview results** to check that the filter works as expected. 
Click **Next**. 

  ![Data types settings](./media/siem3.png)

7. Copy the token and save it for later. 
After you click Finish and leave the Wizard, back in the SIEM page, you can see the SIEM agent you added in the table. It will show that it's **Created** until it’s connected later.

### Step 2: Download the JAR file and run it on your server

1. [Download the .zip file from the Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=838596) and unzip it.

2. Extract the .jar file from the zip file and run it on your server.
 After running the file, run the following:
    
      java -jar mcas-siemagent-0.87.20-signed.jar [--logsDirectory DIRNAME] [--proxy ADDRESS[:PORT]] --token TOKEN
> [!NOTE]
> - The file name may differ depending on the version of the SIEM agent.
> - Parameters in brackets [] are optional, and should be used only if relevant.

Where DIRNAME is the path to the directory you want to use for local agent debug logs.
ADDRESS[:PORT] is the proxy server address and port that the server uses to connect to the Internet.
TOKEN is the SIEM agent token you copied in the previous step.

You can type -h at any time to get help.



### Step 3: Validate that the SIEM agent is working

1. Make sure the status of the SIEM agent in the Cloud App Security portal is not Disconnected and there are no agent notifications. 
 ![SIEM disconnected](./media/siem-not-connected.png)
 
   Instead, the status should be connected, as seen here:
    ![SIEM connected](./media/siem-connected.png)

2. In your Syslog/SIEM server, make sure you see activities and alerts arriving from Cloud App Security.


## Regenerating your token
If you lose the token, you can always regenerate it by clicking the three dots at the end of the row for the SIEM agent in the table, and selecting **Regenerate token**.

 ![SIEM - regenerate token](./media/siem-regenerate-token.png)

## Editing your SIEM agent 
If you need to edit the SIEM agent in the future, you can click on the three dots at the end of the row for the SIEM agent in the table, and select **Edit**. If you edit the SIEM agent, you do not need to rerun the .jar file, it updates automatically.

![SIEM - edit](./media/siem-edit.png)

## Deleting your SIEM agent
If you need to delete the SIEM agent in the future, you can click on the three dots at the end of the row for the SIEM agent in the table, and select **Delete**.

![SIEM - delete](./media/siem-delete.png)


## Troubleshooting the SIEM agent

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

## See Also  
[User activity policies](user-activity-policies.md)   
[For technical support, please visit the Cloud App Security assisted support page.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  