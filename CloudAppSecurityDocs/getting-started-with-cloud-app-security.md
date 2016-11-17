---
# required metadata

title: Getting started with Cloud App Security | Microsoft Docs
description: This topic outlines the process for getting Cloud App Security up and running.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/15/2016
ms.topic: get-started-article
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: cf040b18-93d1-41e8-a26a-647c56afb00f

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Getting started with Cloud App Security
Cloud App Security can help you take advantage of the benefits of cloud applications, but maintain control of corporate resources. It works by improving visibility of cloud activity, and helping to increase the protection of corporate data. In this topic, we walk you through the steps you take to set up and work with Cloud App Security.  

Your organization must have a license to use Cloud App Security. For more information, see the Licensing resources section in [How to buy Cloud App Security](https://www.microsoft.com/en-us/cloud-platform/cloud-app-security).  

>[!NOTE]
>You do not need an Office 365 license to use Cloud App Security.  

## Get started quickly with Cloud App Security  

|What you should do|Task|Required?|How|Description|  
|-------------------------|----------|---------------|-------------|-----------------|  
|Step 1. [Set up Cloud Discovery](set-up-cloud-discovery.md).|Upload traffic logs|Required|**To create a continuous Cloud Discovery report**<br /><br /> 1. Go to **Settings** > **Cloud Discovery settings**.<br /><br /> 2. Choose **Upload log automatically**.<br /><br /> 3. On the **Data sources** tab, add your sources.<br /><br /> 4. On the **Log collectors** tab, configure the log collector.<br /><br /> **To create a snapshot Cloud Discovery report**<br /><br /> 1. Go to **Discover** > **Create new snapshot report** and follow the steps shown.|**Why should you configure Cloud Discovery reports?**<br /> Having visibility into shadow IT in your organization is critical. <br />After your logs are analyzed, you can easily discover which cloud apps are being used, by which people, and on which devices.|
|Step 2. [Set instant visibility, protection, and governance actions for your apps](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md).|Connect apps|Required|1. Go to **Settings** > **Sanctioned apps**.<br /><br /> 2. Choose **Connect app** and select an app.<br /><br /> 3. Follow the configuration steps to connect the app.|**Why connect an app?**<br />After you connect an app, you can gain deeper visibility so you can investigate activities, files, and accounts for the apps in your cloud environment.|
|Step 3. [Control cloud apps with policies](control-cloud-apps-with-policies.md).|Create policies|Required|**To create policies**<br /><br /> 1. Go to **Control** > **Templates**.<br /><br /> 2. Select a policy template from the list, and then choose (+) **Create policy**.<br /><br /> 3. Customize the policy (select filters, actions, and other settings), and then choose **Create**.<br /><br /> 4. On the **Policies** tab, choose the policy to see the relevant matches (activities, files, alerts).<br /><br /> Tip: To cover all your cloud environment security scenarios, create a policy for each **risk category**.|**How can policies help your organization?**<br />You can use policies to help you monitor trends, see security threats, and generate customized reports and alerts. With policies, you can create governance actions, and set data loss prevention and file-sharing controls.|
|Step 4. [Personalize your experience](general-setup.md#Adallom_mailsettings).|Add your organization details|Recommended|**To enter email settings**<br /><br /> 1. Go to **Settings** > **Mail settings**.<br /><br /> 2. Under **Email sender identity**, enter your email addresses and display name.<br /><br /> 3. Under **Email design**, upload your organization's email template.<br /><br /> **To set admin notifications**<br /><br /> 1. In the navigation bar, choose your user name, and then go to **User settings**.<br /><br /> 2. Under **Notifications**, configure the methods you want to set for system notifications.<br /><br /> 3. Choose **Save**.<br /><br /> **To customize the score metrics**<br /><br /> 1. Go to **Settings** > **Cloud Discovery settings**.<br /><br /> 2. Under **Score metric configuration**, configure the importance of various risk values.<br /><br /> 3. Choose **Save**.<br /><br /> Now the risk scores given to discovered apps are configured precisely according to your organization needs and priorities.|**Why personalize your environment?**<br />Some features work best when they are customized to your needs. <br />Provide a better experience for your users with your own email templates, decide what notifications you receive, and customize your risk score metric to fit your organization’s preferences.|
|Step 5. [Organize the data according to your needs](general-setup.md#IPtagsandRanges).|Configure important settings|Recommended|**To create IP address tags**<br /><br /> 1. Go to **Settings** > **IP address tags**.<br /><br /> 2. Choose (+) **Add IP address range**.<br /><br /> 3. Enter the IP range **details**, **location**, **tags**, and **category**.<br /><br /> 4. Choose **Create**.<br /><br /> Now you can use IP tags when you create policies, and when you filter and create data views.<br /><br /> **To create views**<br /><br /> 1. Go to **Settings** > **Cloud Discovery settings**.<br /><br /> 2. Under **Data views**, choose (+) **Add data view**.<br /><br /> 3. Follow the configuration steps.<br /><br /> 4. Choose **Create**.<br /><br /> Now you can view discovered data based on your own preferences, such as business units or IP ranges.<br /><br /> **To add domains**<br /><br /> 1. Go to **Settings** > **General settings**.<br /><br /> 2. Under **Organization details**, add your organization's internal domains.<br /><br /> 3. Choose **Save**.|**Why should you configure these settings?**<br />These settings help give you better control of features in the console. With IP tags, it's easier to create policies that fit your needs, to accurately filter data, and more. Use Data views to group your data into logical categories.|  

## See Also

Read about the basics in [Getting started with Cloud App Security](getting-started-with-cloud-app-security.md).    
For technical support, go to the [Cloud App Security assisted support](http://support.microsoft.com/oas/default.aspx?prid=16031) page.   
Premier customers can also choose Cloud App Security directly from the [Premier portal](https://premier.microsoft.com/).   
