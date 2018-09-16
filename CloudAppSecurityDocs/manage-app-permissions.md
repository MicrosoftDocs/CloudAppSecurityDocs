---
# required metadata

title: Control which third-party cloud apps get permissions | Microsoft Docs
description: This article provides information about how you can control, ban and allow third-party app permissions.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 8/22/2018
ms.topic: conceptual
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
*Applies to: Microsoft Cloud App Security*


# Manage app permissions
Many third-party productivity apps that might be installed by business users in your organization request permission to access user information and data and sign in on behalf of the user in other cloud apps, such as Office 365, G Suite and Salesforce.  When users install these apps, they often click accept without closely reviewing the details in the prompt, including granting permissions to the app.  This problem is compounded by the fact that IT may not have enough insight to weigh the security risk of an application against the productivity benefit that it provides. Because accepting third-party app permissions is a potential security risk to your organization, monitoring the app permissions your users grant gives you the necessary visibility and control to protect your users and your applications. The Microsoft Cloud App Security app permissions enable you to see which user-installed applications have access to Office 365 data, G Suite data and Salesforce data, what permissions the apps have, and which users granted these apps access to their Office 365, G Suite and Salesforce accounts. App permissions help you decide which apps you allow your users access to, and which ones you want to ban.


## Working with the app permissions page

The **App permissions** page displays information about app permissions in your connected apps.

To access the App permissions tab:

In the Cloud App Security portal, click **Investigate**, and then **App permissions**.


 ![app permissions](./media/app-permissions.png)

The App permissions page provides the following information about each third-party app that was granted permissions:

|Item|What it means|Applies to|
|-------|-------|-------|
|Basic icon in the app query bar  |Select this to switch to query in the basic view.|Office 365, G Suite, Salesforce|
|Advanced icon in the app query bar  |Select this to switch to query in the Advanced view.|Office 365, G Suite, Salesforce|
|Open or close all details icon in the app list  |Select this icon to view more or less details about each app.|
|Export icon in the app list  |Select this icon to export a CSV file that contains a list of apps, number of users for each app, permissions associated with the app, permissions level, app state, and community use level.|Office 365, G Suite, Salesforce|
|App|Name of the app. Select the name to view more information, including the description, publisher (for Office 365), app website and ID.|Office 365, G Suite, Salesforce|
|Authorized by|The number of users who authorized this app to access their app's account, and granted the app permissions. Select the number to view more information, including a list of user emails, and whether or not an admin has consented the app previously.|Office 365, G Suite, Salesforce|
|Permissions Level  |The permissions level icon and text indicating either High, Medium or Low. The level indicates how much access this app has to app's data. For example, Low might indicate that the app only accesses user profile and name. Select the level to view more information, including permissions granted to the app, community use, or related activity in the [Governance log](governance-actions.md).|Office 365, G Suite|
|App state|An admin can mark an app as approved, banned, or leave is as undetermined.|Office 365, G Suite, Salesforce|
|Community use|Select this if you want to know how popular the app is across all your users (common, uncommon, rare)|Office 365, G Suite, Salesforce|
|Last authorized|The most recent date on which a user granted permissions to this app.|Office 365, Salesforce|
|Publisher|The name of the vendor who provides the app.|Office 365|
|Last used|The most recent date on which this app was used by anyone in your organization.|Salesforce|


## Ban or approve an app
1. On the App permissions page, click on the app to open the App drawer to view more information about the app and the permissions it was granted. You can click on the Permissions link to view a full list of permissions that were granted to the app. Under Community use, you can view how common the app is in other organizations. You can also click the Relate activity link to view the activities that are listed in the governance log related to this app.
2. To ban the app, click on the ban icon at the end of the app row in the table. <br></br>
   ![ban app icon](./media/ban-app-icon.png) <br></br>
   When you ban an app, you can choose whether you want to let users know that the app they previously installed and authorized has been banned and will be disabled and won't have access to the connected app. If you don't want them to know, unselect Notify users who granted access to this banned app in the Ban the app dialog.

    ![ban app](./media/ban-app.png)
   > [!Note]
   > It is recommended that you let the app users know their app is about to be banned from use.

3. To approve the app, click on the approve icon at the end of the row in the table. <br></br>
   ![approve app](./media/approve-app.png) <br></br>
   The icon turns green, and the app is approved for all your connected app users.
   > [!Note]
   > When you mark an app as approved there is no effect on the end-user. This is just meant to help you visually mark the apps that you have approved to separate them from ones that you haven't reviewed yet.

4. Type the message you want to send to the app users in the Enter a custom notification message box, and update the Notification email 'reply to' address if necessary. 
   Click **Ban app** to send the mail, and ban the app from your connected app users.

## Revoke app and notify user

For G Suite and Salesforce, it is possible to revoke permission to an app or to notify the user that this should been done. 

1. On the **App permissions** page, click on three dots at the end of the app row and select **Notify user**. By default, the user will be notified as follows: *You authorized the app Adallom Google Protector to access your G Suite account.
   This app conflicts with your organization's security policy. Reconsider giving or revoking the permissions you gave this app in your G Suite account. To revoke app access, go to: https://security.google.com/settings/security/permissions?hl=en&pli=1  Select the app and click 'Revoke access' on the right menu bar.* You can customize the message that is sent.
2. You can also revoke permissions to use the app for the user by click on the  icon at the end of the app row in the table and selecting **Revoke app**. 

   ![revoke app](./media/revoke-app.png)

## Query app permissions

You can query app permissions in either the **Basic** view or the **Advanced** view. In the Basic view, select values from one or multiple drop-downs to display the specific apps. In the advanced view, use the **Select a filter** drop-down to narrow your search. Add operators, equals or does not equal to a selected value to complete your query.

- Choose the **Add a filter** icon  to add additional filters to further refine your query. The filters are be applied automatically and the apps list is updated accordingly.

- Choose the **Remove a filter** icon  next to the filter to remove the filters.

## Send feedback

If there’s an OAuth app discovered in your organization that seems malicious, you can send the Cloud App Security team feedback to let us know. This new feature enables you to be part of our security community and enhance OAuth app risk score and analysis.
1. On the **App permissions** page, click on three dots at the end of the app row and select **Report app**.  

   ![report app](./media/report-app.png)
2. In the **Report this app** screen, you can select whether to report the app as malicious or to report some other issue with the way Cloud App Security perceives the app, for example, **Incorrect publisher** or **Incorrect permissions**. The data you submit will be used to update the app's risk score as well as other analytics about the app.

 
## See Also  
[Control cloud apps with policies](control-cloud-apps-with-policies.md)   

[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  