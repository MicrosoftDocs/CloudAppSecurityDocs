---
# required metadata

title: Deploy Cloud App Security for cloud app use insight and control | Microsoft Docs
description: This topic outlines the process for getting Cloud App Security up and running.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 7/30/2017
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

# Deploy Cloud App Security
Cloud App Security can help you take advantage of the benefits of cloud applications while maintaining control of your corporate resources. It works by improving visibility of cloud activity, and helping to increase the protection of corporate data. In this topic, we walk you through the steps you take to set up and work with Cloud App Security.  

Your organization must have a license to use Cloud App Security. For more information, see the Licensing resources section in [How to buy Cloud App Security](https://www.microsoft.com/en-us/cloud-platform/cloud-app-security).  

>[!NOTE]
>You do not need an Office 365 license to use Cloud App Security.  

## Prerequisites  
  
-   Your organization must have a license for Cloud App Security in order to use the product. For more information see [How to buy Cloud App Security](https://www.microsoft.com/server-cloud/products/cloud-app-security/default.aspx) and check the [Licensing resources](https://www.microsoft.com/server-cloud/products/cloud-app-security/default.aspx).  
  
     For tenant activation support, see [Contact Office 365 for business support - Admin Help](https://support.office.com/article/Contact-Office-365-for-business-support-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).  
  
> [!NOTE] 
> An Office 365 license is not required for Cloud App Security.  
  
-   After you have procured a license for Cloud App Security, you will receive an email with activation information and a link to the Cloud App Security portal.  
  
-   To set up Cloud App Security, you must be a Global Administrator, a Compliance Administrator or a Security Administrator in Azure Active Directory or Office 365. It's important to understand that a user who is assigned an admin role will have the same permissions across all of the cloud apps that your organization has subscribed to, regardless of whether you assign the role in the Office 365 portal, or in the Azure classic portal, or by using the Azure AD module for [Windows PowerShell](https://technet.microsoft.com/library/mt736914.aspx). For more information, see [Assigning admin roles in Office 365](https://support.office.com/article/Assigning-admin-roles-in-Office-365-eac4d046-1afd-4f1a-85fc-8219c79e1504) and [Assigning administrator roles in Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-assign-admin-roles/).  
  
-   To run the Cloud App Security portal, use Internet Explorer 11, Microsoft Edge (latest), Google Chrome (latest), Mozilla Firefox (latest) or Apple Safari (latest).  

## To access the portal

To access the Cloud App Security portal, go to [https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com).  
  
Alternatively, you can access the portal through the **Office 365 Admin center** by clicking the Admin centers icon ![O365 admin centers icon](./media/o365-admin-centers-icon.png "O365 admin centers icon") followed by **Cloud App Security**.  
  
![Access from O365](./media/access-from-o365.png "Access from O365")  
  



## Get started quickly with Cloud App Security  

 

### Step 1. [Set up Cloud Discovery](set-up-cloud-discovery.md).
Required task: Upload traffic logs
**To create a continuous Cloud Discovery report**

 1. Go to **Settings** > **Cloud Discovery settings**.
 2. Choose **Upload log automatically**.
 3. On the **Data sources** tab, add your sources.
 4. On the **Log collectors** tab, configure the log collector.
 
**To create a snapshot Cloud Discovery report**

 1. Go to **Discover** > **Create new snapshot report** and follow the steps shown.

**Why should you configure Cloud Discovery reports?**
Having visibility into shadow IT in your organization is critical.
After your logs are analyzed, you can easily discover which cloud apps are being used, by which people, and on which devices.


### Step 2. [Set instant visibility, protection, and governance actions for your apps](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md).
Required task: Connect apps

1. Go to **Settings** > **App connectors**.
2. Choose **Connect app** and select an app.
3. Follow the configuration steps to connect the app.

**Why connect an app?**
After you connect an app, you can gain deeper visibility so you can investigate activities, files, and accounts for the apps in your cloud environment.


### Step 3. [Control cloud apps with policies](control-cloud-apps-with-policies.md).
Required task: Create policies

**To create policies**

1. Go to **Control** > **Templates**.
2. Select a policy template from the list, and then choose (+) **Create policy**.
3. Customize the policy (select filters, actions, and other settings), and then choose **Create**.
4. On the **Policies** tab, choose the policy to see the relevant matches (activities, files, alerts).
 Tip: To cover all your cloud environment security scenarios, create a policy for each **risk category**.

**How can policies help your organization?**
You can use policies to help you monitor trends, see security threats, and generate customized reports and alerts. With policies, you can create governance actions, and set data loss prevention and file-sharing controls.


### Step 4. [Personalize your experience](mail-settings.md).
Recommended task: Add your organization details

**To enter email settings**

1. Go to **Settings** > **Mail settings**.
2. Under **Email sender identity**, enter your email addresses and display name.
3. Under **Email design**, upload your organization's email template.

**To set admin notifications**

1. In the navigation bar, choose your user name, and then go to **User settings**.
2. Under **Notifications**, configure the methods you want to set for system notifications.
3. Choose **Save**.

**To customize the score metrics**

1. Go to **Settings** > **Cloud Discovery settings**.
2. Under **Score metric configuration**, configure the importance of various risk values.
3. Choose **Save**.

Now the risk scores given to discovered apps are configured precisely according to your organization needs and priorities.

**Why personalize your environment?**
Some features work best when they are customized to your needs. 
Provide a better experience for your users with your own email templates, decide what notifications you receive, and customize your risk score metric to fit your organization’s preferences.


### Step 5. [Organize the data according to your needs](ip-tags.md).
Recommended task: Configure important settings

**To create IP address tags**

1. Go to **Settings** > **IP address tags**.
2. Choose (+) **Add IP address range**.
3. Enter the IP range **details**, **location**, **tags**, and **category**.
4. Choose **Create**.

 Now you can use IP tags when you create policies, and when you filter and create continuous reports.

**To create continuous reports**

1. Go to **Settings** > **Cloud Discovery settings**.
2. Under **Manage continuous reports**, choose **Create report**.
3. Follow the configuration steps.
4. Choose **Create**.

Now you can view discovered data based on your own preferences, such as business units or IP ranges.

**To add domains**

1. Go to **Settings** > **General settings**.
2. Under **Organization details**, add your organization's internal domains.
3. Choose **Save**.

**Why should you configure these settings?**
These settings help give you better control of features in the console. With IP tags, it's easier to create policies that fit your needs, to accurately filter data, and more. Use Data views to group your data into logical categories.
  

## See Also

Set policies [Control cloud apps with policies](control-cloud-apps-with-policies.md).    
For technical support, go to the [Cloud App Security assisted support](http://support.microsoft.com/oas/default.aspx?prid=16031) page.   
Premier customers can also choose Cloud App Security directly from the [Premier portal](https://premier.microsoft.com/).   
