---
# required metadata

title: Create session policies to gain deep visibility into user session activities and block downloads | Microsoft Docs
description: This topic describes the procedure for setting up a Cloud App Security Proxy session policy gain deep visibility into user session activities and block downloads.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 8/8/2017
ms.topic: article
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: 745df28a-654c-4abf-9c90-203841169f90

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Session policies  
Session policies allow you to monitor everything a user does inside a session and gives you control capabilities to block specific activities users perform within those sessions,such as downloading files.

Before you can create an session policy, it is necessary to [Deploy the Proxy](proxy-deployment.md). Session policies enable you to set rules that define how you control and monitor your users' sessions.
For example, you can set a policy to:
- Block downloads of any file with the Azure Information Protection classification label "classified" from unmanaged devices.
- Protect downloads of all files to unmanaged devices, with Azure RMS encryption.
- 

To create a new session policy, follow this procedure:  
  
1.  In the console, click on **Control** followed by **Policies**.  
  
2.  Click **Create policy** and select **Session policy**.  
  
3.  Give your policy a name and description, if you want you can base it on a template, for more information on policy templates, see [Control cloud apps with policies](control-cloud-apps-with-policies.md).  
  
3. Give your policy a **Policy severity**. If you have set Cloud App Security to send you notifications on policy matches for a specific policy severity level, this will be used to determine whether this policy's matches will trigger a notification.

4.  Within **Category**, link the policy to the most appropriate risk type. This field is informative only and helps you search for specific policies and alerts later, based on risk type.  The risk may already be preselected according to the category for which you chose to create the policy. By default, Session policies are set to **DLP**.  
  
5.  To set which discovered apps will trigger this policy, **Create a filter for the files this policy will act on**. 

 > [!NOTE] 
 > When using the policy filters, **Contains**  will search only for full words – separated by comas, dots, spaces or underscores. For example if you search for **malware** or **virus**, it will find virus_malware_file.exe but it will not find malwarevirusfile.exe. If you search for **malware.exe** then you will find ALL files with either malware or exe in their filename, whereas if you search for **“malware.exe”** (with the quotation marks) you will find only files that contain exactly “malware.exe”. **Equals** will search only for the complete string, for example if you search for **malware.exe** it will find malware.exe but not malware.exe.txt.  

6. Select the **Session control type**.
    - Monitor all activities: If you select Monitor, the apps' session activities will be monitored but not blocked. You will be able to monitor each specific internal page within the cloud app that was accessed and every download made in each specific app. By default, alerts are automatically sent to the Cloud App Security portal. This also enables you to [Export the entire audit log](#export-the-audit-log) for session activities from the Proxy tab.
    - Monitor all activities and control file download: Selecting Monitor and control will give you all the capabilities listed above under **Monitor all activities** with the added layer of control that enables you to block specific activities, such as downloading files, in real time. You will also be able to filter file content based on the Cloud App Security built-in DLP or an external DLP.
 
7. Under **Activity source**, select which apps the policy will apply to, either all apps or specific apps.

8. Use the filters to select which users, apps and devices you want to trigger a policy match. For a full list of filters, see [session policy filters](#session-policy-filters).
  
9. If you chose to **Monitor all activities and control file download**, you can also set [file filters](#session-file-filters)

10. If you chose to **Monitor all activities and control file download**, you can also set **Content inspection** options. The built-in DLP allows you to filter files by their content. In order to scan files for content, next select Built-in DLP. Once content inspection is enabled, you can choose to use preset expressions or to search for other customized expressions, either as a substring or a regular expression of your own.
In addition, you can specify a regular expression to exclude a file from the results. This is highly useful if you have an inner classification keyword standard that you want to exclude from the policy.
You can decide set the minimum number of content violations that you want to match before the file is considered a violation. For example, you can choose 10 if you want to be alerted on files with at least 10 credit card numbers found within its content.
When content is matched against the selected expression, the violation text will be replaced with "X" characters. By default, violations are completely masked and shown in their context displaying 40 characters before and after the violation. Numbers in the context of the expression are replaced with “#” characters and are never stored within Cloud App Security. You can select the option to Unmask the last 4 characters of a violation to unmask the last 4 characters of the violation itself.

10. If you chose to **Monitor all activities and control file download**, you can also set **Actions** to be taken when the policy is matched:
    - Allow: If you select allow, users will be allowed to download the files. 
    - Block: If you select **Block**, when the policy requirements are matched, the user will not be able to download the files. The user will receive a message that they do not have permission to download the files.
    - Protect: If you select **Protect**, the user will be able to download the files but they will be encrypted with Azure RMS. You can also set a default action to be taken if encryption fails (block or allow the download).
 >[!WARNING]
 >It is highly recommended to first create the policy using the **Allow** action, and check the results and only after you have determined that the policy does not block anyone unintended, switch the policy to **Block** downloads.
 
 9. Set the alerts you want to receive when the policy is matched. You can set a limit so that you won't receive too many alerts, and you can select whether to get the alerts as an email message or text message or both.

10. To view session policy matches, click **Control** and then **Policies**. Filter the results to display only the Session policies using the **Type** filter at the top. For more information about the matches for each policy, click on a policy. Click the **History** tab to see a history back to up to 6 months of policy matches.     
  
## session policy reference  

This section provides reference details about session policy filters. 

### Session filters <a name="session-policy-filters"></a>

- Device tag - Device tag lets you filter out managed devices by selecting **Compliant**, **Domain joined** and **Valid client certificate**.
- Device type: No value, PC, Mobile, Tablet, Other
-   IP address – The raw IP address, category or tag from which the activity was performed.  
    - Raw IP address - Enables you to search for activities that were performed on or by raw IP addresses that equal, don't equal or start with or don't start with a particular sequence, or raw IP addresses that are or are not set. 
    - IP category - The category of the IP address from which the activity was performed, for example, all activities from administrative IP address range. The categories need to be configured to include the relevant IP addresses, except for the "Risky" category which is pre-configured and includes two IP tags - Anonymous proxy and Tor. To learn how to configure the IP categories, see [Organize the data according to your needs](ip-tags.md).  
    - IP tag - The tag of the IP address from which the activity was performed, for example, all activities from anonymous proxy IP addresses. Cloud App Security creates a set of built-in IP tags that are not configurable. In addition, you can configure your own IP tags. For more information about configuring your own IP tags, see [Organize the data according to your needs](ip-tags.md).
   The built-in IP tags include:
    - Microsoft apps (14 of them)
    - Anonymous proxy
    - Botnet (you will see that the activity was performed by a botnet with a link to learn more about the specific botnet)
    - Darknet scanning IP
    - Malware C&C server
    - Remote Connectivity Analyzer
    - Satellite providers
    - Smart proxy and access proxy (left out on purpose)
    - Tor exit nodes
    - Zscaler

-   Location – The country from which the access request was made.    

- Registered ISP: 

-   User – The user who performed the activity, which can be filtered into domain, group, name or organization. In order to filter activities with no specific user, you can use the ‘is not set’ operator.  
    -   User organization – The organizational unit of the user who performed the activity, for example, all activities performed by EMEA_marketing users.  
    -   User group – Specific user groups that you can import from connected apps, for example, Office 365 administrators.  
    -   User name - Search for a specific username. To see a list of users in a specific user group, in the **Activity drawer**, click on the name of the user group. This will take you to the Accounts page which lists all the users in the group. From there you can drill down into the details of the accounts of specific users in the group.
       -  The **User group** and **User name** filters can be further filtered by using the **As** filter, and selecting the role of the user, which can be any of the following:
            - Activity object only - this means that the user or user group selected did not perform the activity in question, they were the object of the activity
            - Actor only - this means that the user or user group performed the activity
            - Any role - this means that the user or user group were involved in the activity, either as the person who performed the activity or as the object of the activity

-   User agent – The user agent of from with the activity was performed.  
  
-   User agent tag – Built-in user agent tag, for example, all activities from an outdated browser or outdated operating systems.  

### Session file filters <a name="session-file-filters"></a>

-   Classification label - Search for files with specific tags set. These are either:
    - Azure Information Protection tags. This requires integration with Azure Information Protection.
    - Cloud App Security tags. now provides more insight into the files it scans. For each file scanned by Cloud App Security DLP, you can now know if the files were blocked from being inspected because they were encrypted or corrupted. For instance, you can set up policies to alert and quarantine password protected files that are shared externally, as follows: 
        - Azure RMS encrypted – files whose content was not inspected because they have an Azure RMS encryption set.
        - Password encrypted – files whose content was not inspected because they are password protected by the user.
        - Corrupt file – files whose content was not inspected because their content could not be read.

-   File type – Cloud App Security takes both the MIME type received from the service and scans the file to determine the true file type. Note that this scan is for files that are relevant for data scan (documents, images, presentations, spreadsheets, text and zip/archive files). The filter works per file/folder type, for example, All folders that are ... or All spreadsheet files that are...
-   Extension – Focus on specific file extensions, for example, all files that are executables (exe).  
  
-   File name – File name or sub string of the name as defined in the cloud app, for example, All files with a password in their name.   
  
-   File size – File size in MB - greater than a certain size, samller than a certain size or between a range.    


>[!NOTE]
> If at any point you want to clear the filters, you can do so by clicking the clear filters icon ![clear filters icon](./media/clear-filters.png).

  
## See Also  
[Daily activities to protect your cloud environment](daily-activities-to-protect-your-cloud-environment.md)   
[For technical support, please visit the Cloud App Security assisted support page.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  