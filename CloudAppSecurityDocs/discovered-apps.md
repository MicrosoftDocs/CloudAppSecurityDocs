---
# required metadata

title: Working with discovered apps in Cloud App Security | Microsoft Docs
description: This topic describes the process for identifying and remediating risky cloud discovery apps in Cloud App Security.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 6/4/2017
ms.topic: get-started-article
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: 645fd8c7-06d0-4f93-a85c-2976e7b3766d

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Working with discovered apps
If you want to deep dive into the data provided by Cloud Discovery, you can review which apps were discovered and determine if they are risky or not. To do this, it's helpful to use the filters to review the apps that were discovered as being used in your environment.
For example, if you want to unsanction and block risky cloud storage and collaboration apps, you can use the Discovered apps page to filter for the apps you want and then bulk unsanction them, as follows. In the **Discovered apps** page, under **Browse by category** select both **Cloud storage** and **Collaboration**. Then, use the Advanced filters and set **Compliance risk factor** to **SOC 2** equals **False**; **Usage** > **Users** to greater than 50 users; and **Usage** > **Transactions** to greater than 100; **Security risk factor** > **Data at rest encryption** equals **False** and then set **Risk score** equals less than 6.
Once the results are filtered for these risky apps, you can use the bulk action checkbox to unsanction them all in one action. After they are unsanctioned you can use a blocking script to block them from being used in your environment.

## Discovered app filters

![Discovered apps](./media/discovered-apps.png)  


- **App tag**: select whether the app was sanctioned or unsanctioned or not.
- **Apps and domains**: enables you to search for specific apps or apps used in specific domains 
- **Compliance risk factor**: lets you search for a specific compliance factor (HIPAA, ISO 27001, SOC 2, PCI-DSS, etc.)
- **General risk factor**: lets you search for apps by Consumer popularity, Data center locale, Domain, Domain registration (before or after date), Founded during a specific year, Headquarters in a specific locale, Holding (private or public), Hosting company, Logon URL, Vendor
- **Risk score**: lets you filter apps by risk score so that you can focus on, for example, reviewing only very risky apps.
- **Security risk factor**: enables you to filter based on
- **Usage**: Lets you filter based on apps used by specific IP addresses or apps Last seen being used before a specific date (to enable you to weed out apps that are stale and no longer in use), apps with less than a specified amount of **Traffic**, apps with fewer than a specified amount of **Transactions**, apps with less than or more than a specified amount of data uploads, apps with more than or less than a specified amount of **Users**.

>[!NOTE]
> If at any point you want to clear the filters, you can do so by clicking the clear filters icon ![clear filters icon](./media/clear-filters.png).

## Remediate

After you have reviewed the list of discovered apps in your environment, you can secure your environment against unwanted app use in the following ways.

## Governing discovered apps
Cloud App Security enables you to block access to unsanctioned apps by leveraging your existing on-prem security appliances. Generate a dedicated block script and import it to your appliance.
This solution does not require redirection of all of the organization's web traffic to a proxy.


### Sanctioning/unsanctioning an app 

You can unsanction a specific risky app by clicking the three dots at the end of the row and selecting **Unsanction**.
Unsanctioning an app doesn't block use, but enables you to more easily monitor its use with the Cloud Discovery filters. 
You can then notify users of the app that it has been unsanctioned and suggest an alternative, safe app for their use.

![Tag as unsanctioned](./media/tag-as-unsanctioned.png)  


If you have a list of apps you want to sanction or unsanction, you can use the checkbox to select all the apps you want to manage, and then select the action.

### Exporting a block script to govern discovered apps

1. In the Cloud Discovery dashboard, for any app that is **Unsanctioned**, in the title bar, click on the three dots and select **Generate block script...**. 

   ![Generate block script](./media/generate-block-script.png)  

3. In **Generate block script**, select the appliance you want to generate the block script for. 

   ![Generate block script pop up](./media/generate-block-script-popup.png)  

4. Then, click the Generate script button. This will create a block script for all your unsanctioned apps. By default, the file will be named with the date on which it was exported and the appliance type you selected, for example *2017-02-19_CAS_Fortigate_block_script.txt* 

   ![Generate block script button](./media/generate-block-script-button.png)  

5. Import the file created to your appliance.

### Creating a new policy from search
After you have search results filtered for specific apps you want to apply specific actions to, you can create a new policy from your filtered search results.
At the top of the Discovered apps page, click the three dots and then select **Create new policy**. This will automatically open a new Discovery Policy template filtered using the filters currently applied.


## See also
 
[Create snapshot Cloud Discovery reports](create-snapshot-cloud-discovery-reports.md)

[Configure automatic log upload for continuous reports](configure-automatic-log-upload-for-continuous-reports.md)

[Working with Cloud Discovery data](working-with-cloud-discovery-data.md)

