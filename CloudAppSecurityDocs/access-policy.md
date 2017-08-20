---
# required metadata

title: Create access policies to monitor and block access to your cloud apps | Microsoft Docs
description: This topic describes the procedure for setting up an access policy to monitor and block access to your cloud apps.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 8/8/2017
ms.topic: article
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: ddeabd1d-f017-4756-94b2-194292e60c07

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Access policies  
Access policies allow you to monitor and block access to specific apps based on user, location or device.

Before you can create an access policy, it is necessary to [Deploy the Proxy](proxy-deployment.md). Access policies enable you to set rules that define how you manage and monitor your users' access to your cloud apps.
For example, you can set a policy to:
- Block access to all cloud apps from unmanaged devices.
- Block access from specific countries, such as all countries that are not England.
- Block access for all user groups that are not Sales and Admins to Salesforce.
- Allow access but monitor all login attempts and alert when someone tries to log in who isn't from a specific user group.

To create a new access policy, follow this procedure:  
  
1.  In the console, click on **Control** followed by **Policies**.  
  
2.  Click **Create policy** and select **Access policy**.  
  
3.  Give your policy a name and description, if you want you can base it on a template, for more information on policy templates, see [Control cloud apps with policies](control-cloud-apps-with-policies.md).  
  
3. Give your policy a **Policy severity**. If you have set Cloud App Security to send you notifications on policy matches for a specific policy severity level, this will be used to determine whether this policy's matches will trigger a notification.

4.  Within **Category**, link the policy to the most appropriate risk type. This field is informative only and helps you search for specific policies and alerts later, based on risk type.  The risk may already be preselected according to the category for which you chose to create the policy. By default, Access policies are set to **Access control**.  
  
5.  To set which discovered apps will trigger this policy, **Create a filter for the files this policy will act on**. 

 > [!NOTE] 
 > When using the policy filters, **Contains**  will search only for full words – separated by comas, dots, spaces or underscores. For example if you search for **malware** or **virus**, it will find virus_malware_file.exe but it will not find malwarevirusfile.exe. If you search for **malware.exe** then you will find ALL files with either malware or exe in their filename, whereas if you search for **“malware.exe”** (with the quotation marks) you will find only files that contain exactly “malware.exe”. **Equals** will search only for the complete string, for example if you search for **malware.exe** it will find malware.exe but not malware.exe.txt.  

6.   Under **Activity source**, select which apps the policy will apply to, either all apps or specific apps.

7. Use the filters to select which users, apps and devices you want to trigger a policy match. For a full list of filters, see [Access policy filters](#access-policy-filters).

8.  Choose the **Actions** you want Cloud App Security to take when a match is detected:
    - Allow and alert: If you select allow, the apps' access will be monitored but not blocked. By default, if **Allow** is selected, alerts are automatically sent to the Cloud App Security portal. 
    - Block: If you select **Block**, when the policy requirements are matched, the user or device will not be able to access the cloud app. The user will receive a message that they do not have access to the app.
  
>[!WARNING]
>It is highly recommended to first create the policy using the **Allow** action, and check the results and only after you have determined that the policy does not block anyone unintended, switch the policy to **Block** access.
  
9. Set the alerts you want to receive when the policy is matched. You can set a limit so that you won't receive too many alerts, and you can select whether to get the alerts as an email message or text message or both.

10. To view access policy matches, click **Control** and then **Policies**. Filter the results to display only the Access policies using the **Type** filter at the top. For more information about the matches for each policy, click on a policy. Click the **History** tab to see a history back to up to 6 months of policy matches.     
  
## Access policy reference  <a name="access-policy-filters"></a>

This section provides reference details about access policy filters. 

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
    
>[!NOTE]
> If at any point you want to clear the filters, you can do so by clicking the clear filters icon ![clear filters icon](./media/clear-filters.png).


## See Also  
[Daily activities to protect your cloud environment](daily-activities-to-protect-your-cloud-environment.md)   
[For technical support, please visit the Cloud App Security assisted support page.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  