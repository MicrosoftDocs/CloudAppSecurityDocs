---
# required metadata

title: Control which third-party cloud apps get permissions | Microsoft Docs
description: This article provides information about how you can control, ban and allow third-party app permissions.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/23/2017
ms.topic: article
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: 137e0630-5440-4c49-bfe4-48bbc64575e2

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Manage app permissions
Many third-party productivity apps that might be installed by business users in your organization request permission to access user information and data and sign in on behalf of the user in other cloud apps, such as Office 365.  When users install these apps, they often click accept without closely reviewing the details in the prompt, including granting permissions to the app.  This problem is compounded by the fact that IT may not have enough insight to weigh the security risk of an application against the productivity benefit that it provides. Because accepting third-party app permisssions is a potential security risk to your organization, monitoring the app permissions your users grant gives you the necessary visibility and control to protect your users and your applications. The Cloud App Security app permissions enable you to see which user-installed applications have access to Office 365 data, what permissions the apps have, and which users granted these apps access to their Office 365 accounts. App permissions help you decide which apps you allow your users access to, and which ones you want to ban.


## Working with the app permissions page

The **App permissions** tab displays information about app permissions in your Office 365 tenant.

To access the App permissions tab:

1. In the Cloud App Security portal, click **Investigate**, and under **Connected apps**, select **Office 365**. 
> [!Note]
> You have to first connect Cloud App Security to Office 365 to work with App permissions.

2. Then, in the Office 365 dashboard, click the **App permissions** tab.


 ![app permissions](./media/app-permissions.png)

The App permissions page provides the following information about each third-party app that was granted permissions:

|Item|What it means|
|-------|----------------|
|Basic icon in the app query bar  |Select this to switch to query in the basic view.|
|Advanced icon in the app query bar  |Select this to switch to query in the Advanced view.|
|Open or close all details icon in the app list  |Select this icon to view more or less details about each app.|
|Export icon in the app list  |Select this icon to export a CSV file that contains a list of apps, number of users for each app, permissions associated with the app, permissions level, app state, and community use level.|
|App|Name of the app. Select the name to view more information, including the description, publisher, app website and ID.|
|Authorized by|The number of users who authorized this app to access their Office 365 account, and granted the app permissions. Select the number to view more information, including a list of user emails, and whether or not an admin has consented the app previously.|
|Permissions Level  |The permissions level icon and text indicating either High, Medium or Low. The level indicates how much access this app has to Office 365 data. For example, Low might indicate that the app only accesses user profile and name. Select the level to view more information, including permissions granted to the app, community use, or related activity in [Governance log](governance-actions.md).|
|App state, Either Banned, Approved, or Undetermined.  |An admin can mark an app as approved, banned, or leave is as undetermined.|


## Ban or approve an app
1. On the App permissions page, click on the app to open the App drawer to view more information about the app and hte permissions it was granted. You can click on the Permissions link to view a full list of permissions that were granted to the app. Under Community use, you can view how common the app is in other organizations. You can also click the Relate activity link to view the activities that are listed in the governance log related to this app.
2. To ban the app, click on the ban icon at the end of the app row in the table. <br></br>
 ![ban app icon](./media/ban-app-icon.png) <br></br>
When you ban an app, you can choose whether you want to let users know that the app they previously installed and authorized has been banned and will be disabled and won't have access to Office 365. If you don't want them to know, unselect Notify users who granted access to this banned app in the Ban the app dialog.

    ![ban app](./media/ban-app.png)
> [!Note]
> It is recommended that you let the app users know their app is about to be banned from use.

3. To approve the app, click on the approve icon at the end of the row in the table. <br></br>
 ![approve app](./media/approve-app.png) <br></br>
The icon turns green, and the app is approved for all your Office 365 users.
> [!Note]
> When you mark an app as approved there is no effect on the end-user. This is just meant to help you visually mark the apps that you have approved to separate them from ones that you haven't reviewed yet.

3. Type the message you want to send to the app users in the Enter a custom notification message box, and update the Notification email 'reply to' address if necessary. 
 Click **Ban app** to send the mail, and ban the app from your Office 365 users.


## Query app permissions

### Query in the Advanced view 
1. In the advanced view, use the **Select a filter** dropdown to narrow your search. Add operators, equals or does not equal to a selected value to complete your query.
2. Choose the **Add a filter** icon  to add additional filters to further refine your query. The filters are be applied automatically and the apps list is updated accordingly.
3. Choose the **Remove a filter** icon  next to the filter to remove the filters.
The filters you can choose from are:
- App
Display third-party app or apps with the selected name or names that have been granted access to Office 365.

- User 
Display apps that this user(s) authorized.

- Permissions 
Display apps that require the selected permissions.

- App state 
Display apps based on their state, approved, banned, or undetermined.

- Permission level 
Display apps based on the selected permission level or levels.

- Community use 
Display apps based on community use levels, either rare, uncommon, or common.

### Query in the basic view 
In the basic view, select values from one or multiple dropdowns to display the specific apps. You can select multiple values in the dropdowns. The dropdown menus you can use for querying are: 
- App 
Display third-party app or apps with the selected name or names that have been granted access to Office 365.

- User 
Display apps that this user(s) authorized.

- Permissions 
Display apps that require the selected permissions.

- App state 
Display apps based on their state, approved, banned, or undetermined.

- Permission level 
Display apps based on the selected permission level or levels.

- Community use 
Display apps based on community use levels, either rare, uncommon, or common.
The filters are applied automatically and the apps list is updated accordingly. 

## See Also  
[Control cloud apps with policies](control-cloud-apps-with-policies.md)   
[For technical support, please visit the Cloud App Security assisted support page.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  