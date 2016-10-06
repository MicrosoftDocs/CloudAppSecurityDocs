---
title: "Control"
ms.custom: na
ms.date: "07/31/2016"
ms.prod: "identity-cas"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"

ms.assetid: bc11bbfe-ec6c-458c-8302-8112c383199d
caps.latest.revision: 10
author: "Rkarlin"
ms.author: "rkarlin"
---
# Control
  Governance actions can be applied to users' files across your cloud environment. After you have thoroughly investigated and learned about your cloud, you can use governance actions to protect your organization.  
  
## Applying governance actions  
 Governance actions can be applied from within policies, from inside alerts and from the **File** log.  
  
 At any point, you can review and see the status of all previously applied governance actions by going to the **Settings** cog ![settings icon](./media/settings-icon.png "settings icon") and clicking **Governance log**.  
  
 For any governance action that failed, click on the retry icon ![retry icon](./media/retry-icon.png "retry icon") to apply it again.  
  
 Depending on the type of policy, violation, and app, different governance actions are available.  
  
## Moving from detection to automatic remediation  
 After defining and customizing your policy filters, you can  select automated-governance actions that will be taken upon every violation of your policy.  
Since remediation actions leverage the cloud provider APIs, actions may vary from one app to another.  
  
> [!NOTE]  
>  Take extra care when you set governance actions, they could lead to irreversible loss of access permissions to your files.  
> It is recommended to narrow down the filters to exactly represent the files that you wish to act upon, using multiple search fields. The narrower the filters, the better.  
>   
>  For guidance, you can use the **Edit and preview results** button in the Filters section.  
  
 ![file policy edit and preview results](./media/file-policy-edit-and-preview-results.png "file policy edit and preview results")  
  
## Migration  
 [!INCLUDE[Adallom](./includes/adallom_md.md)] helps you roll out your migrations by letting you know who in your organization is using which apps and giving you the tools to monitor new app adoption. It can also help you figure out which types of apps you should offer in your organization, by providing you the tools to see what everyone is already using.  
  
### How to migrate your users to a new app  
 Imagine this scenario: you recently bought Office 365 and you want all the users in your organization to stop using all other cloud storage apps, and start using OneDrive. Here's what you might want to do:  
  
-   Go to your **Cloud Discovery Dashboard** and under **Categories**, filter apps by **Cloud Storage**. Then sort the results by **Users** or **IP addresses**, and check to see which app is most popular.  
  
-   You can see which users are using other apps.  
  
     You can also drill-down into those apps, and notify people using them that you want them to migrate to OneDrive, as follows:  
  
    1.  In your **Cloud Discovery Dashboard**, click Dropbox and then click the **IP address** or **Users** tab.  
  
    2.  Click the arrow ![arrow icon](./media/arrow-icon.png "arrow icon") and select **Export**.  
  
### Find more secure alternatives  
 The [!INCLUDE[Adallom](./includes/adallom_md.md)] service catalog can help you find alternatives that work for your organization instead of risky apps your users may be using.  
  
 Imagine this scenario: You're considering buying a productivity too and you aren't sure if your users would make use of it or not.  
  
-   Go to the **Cloud Discovery Dashboard**.  
  
-   Under **Categories**, filter apps by **Productivity**.  
  
-   For each app in use, check out the **Score** to see if it's safe and if not, why not.  
  
-   If you decide that you want to buy an enterprise license for the whole organization, you might also want to look at the **Users** column to see what's already most popular among your users, see if it's trusted and see what security features it has before making your decision.  
  
## See Also  
 [Control cloud apps with policies](../migration/control-cloud-apps-with-policies.md)   
 [For technical support, please visit the Cloud App Security assisted support page.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
 [Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  