---
# required metadata

title: Getting started with Cloud App Security | Microsoft Docs
description:
keywords:
author: rkarlin
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
  [!INCLUDE[Adallom1](./includes/adallom1_md.md)] helps customers take advantage of the benefits of cloud applications while maintaining control through improved visibility of activity and increased protection over critical company data.  This documentation walks you through the following steps to work with Cloud App Security.  
  
 Your organization must have a license for Cloud App Security in order to use the product. For more information see [How to buy Cloud App Security](https://www.microsoft.com/en-us/server-cloud/products/cloud-app-security/default.aspx) and check the [Licensing resources](https://www.microsoft.com/en-us/server-cloud/products/cloud-app-security/default.aspx).  
  
> [!NOTE]An Office 365 license is not required for Cloud App Security.  
  
## Get started quickly with Cloud App Security  
  
|What you should do:|Task|Required?|How to:|Description|  
|-------------------------|----------|---------------|-------------|-----------------|  
|STEP 1. [Set up Cloud Discovery](set-up-cloud-discovery.md).|Upload traffic logs|Required|**Create a continuous Cloud Discovery report**<br /><br /> 1.   Go to **Settings** -> **Cloud Discovery settings**.<br /><br /> 2.    Click on **Upload log automatically**.<br /><br /> 3.   Add your data sources under **Data sources** tab.<br /><br /> 4.    Configure the log collector under the **Log collectors** tab.<br /><br /> Create a snapshot Cloud Discovery report<br /><br /> 1.    Go to **Discover** -> **Create new snapshot report** and follow the steps|**Why should you configure Cloud Discovery reports?** Gaining visibility into Shadow IT in your organization is critical.  <br />After your logs are analyzed, you can easily discover which cloud apps are used, by which people, on which devices.|  
|STEP 2. [Enable instant visibility, protection and governance actions for your apps](enable-instant-visibility--protection-and-governance-actions-for-your-apps.md).|Connect apps|Required|1.   Go to **Settings** -> **Sanctioned apps**.<br /><br /> 2. Click **Connect app** and choose an app.<br /><br /> 3. Follow the configuration steps to connect the app.|**Why connect an app?**<br /><br /> Only after connecting an app will you be able to gain deeper visibility to investigate activities, files and accounts in your cloud environment for your cloud apps.|  
|STEP 3. [Control cloud apps with policies](control-cloud-apps-with-policies.md).|Create policies|Required|**Create policies**<br /><br /> 1.  Go to **Control** -> **Templates**.<br /><br /> 2.    Select a policy template from the list and click  (+) **Create policy**.<br /><br /> 3.  Customize the policy for your needs (select filters, actions and other configurations)  and  then click **Create**.<br /><br /> 4.    In the **Policies** tab, click on the policy you created to see the relevant matches (activities, files, alerts, etc.).<br /><br /> Tip - Create a policy for each **Risk category** to cover all your cloud environment security scenarios.|**How can policies help your organization?**<br /><br /> Policies provide you with the tools to monitor  trends, see security threats, and generate customized reports and alerts. With policies you can create various governance actions, DLP, and file sharing controls.|  
|STEP 4. [Personalize your experience](general-setup.md#Adallom_mailsettings).|Add your organization details|Recommended|**Enter email settings**<br /><br /> 1. Go to **Settings** -> **Mail settings**.<br /><br /> 2.   Under **Email sender identity** enter your email addresses and display name.<br /><br /> 3. Under **Email design** upload your organization's email template.<br /><br /> **Set admin notifications**<br /><br /> 1.    Click on your username in the navigation bar and go to **User settings**.<br /><br /> 2.    Under **Notifications** configure the methods you want to set for system notifications.<br /><br /> 3.  Click **Save**.<br /><br /> **Customize the score metrics**<br /><br /> 1.  Go to **Settings** -> **Cloud Discovery settings**.<br /><br /> 2.    Under **Score metric configuration** configure the importance of various risk values.<br /><br /> 3.    Click **Save**.<br /><br /> Now the risk scores given to discovered apps are configured precisely according to your organization needs and priorities.|**Why personalize your environment?**<br /><br /> Some features work best when customized to your needs.  <br />Provide a better experience for your users with your own email templates, decide what notifications you receive, and customize your risk score metric to fit your organization’s preferences.|  
|STEP 5. [Organize the data according to your needs](general-setup.md#IPtagsandRanges).|Configure important settings|Recommended|**Create IP address tags**<br /><br /> 1.   Go to **Settings** -> **IP address tags**.<br /><br /> 2. Click on (+) **Add IP address range**.<br /><br /> 3.    Enter the IP range **details**, **location**, **tags** and **category**.<br /><br /> 4. Click **Create**.<br /><br /> Now you can use IP tags when creating policies, when filtering and when creating data views.<br /><br /> **Create views**<br /><br /> 1.  Go to **Settings** -> **Cloud Discovery settings**.<br /><br /> 2.    Under **Data views** click on (+) **Add data view**.<br /><br /> 3.  Follow the configuration steps.<br /><br /> 4.  Click **Create**.<br /><br /> Now you can view discovered data based on your own preferences such as business units or IP ranges.<br /><br /> **Add domains**<br /><br /> 1.    Go to **Settings** -> **General settings**.<br /><br /> 2.    Under **Organization details** add your organization's internal domains.<br /><br /> 3. Click **Save**.|**Why should you configure these settings?**<br /><br /> These settings lead to better and easier control of various features in the console. With IP tags it's easier to create policies that fit your needs, accurately filter data and more. Use Data views to group your data into logical categories.|  
  
## See Also  
 [General setup](general-setup.md)   
 [For technical support, please visit the Cloud App Security assisted support page.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
 [Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  