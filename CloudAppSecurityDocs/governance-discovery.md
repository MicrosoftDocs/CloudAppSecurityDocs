---
# required metadata

title: Blocking discovered apps | Microsoft Docs
description: This topic describes the procedure for exporting block scripts for discovered apps. 
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/15/2018
ms.topic: article
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: e451031e-4764-411a-b366-73a49d4f25df

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

## Govern discovered apps

After you have reviewed the list of discovered apps in your environment, you can secure your environment against unwanted app use in the following ways.

### Sanctioning/unsanctioning an app 

You can unsanction a specific risky app by clicking the three dots at the end of the row and selecting **Unsanction**.
Unsanctioning an app doesn't block use, but enables you to more easily monitor its use with the Cloud Discovery filters. 
You can then notify users of the app that it has been unsanctioned and suggest an alternative, safe app for their use.

![Tag as unsanctioned](./media/tag-as-unsanctioned.png)  


If you have a list of apps you want to sanction or unsanction, you can use the checkbox to select all the apps you want to manage, and then select the action.


## Export a block script to govern discovered apps

Cloud App Security enables you to block access to unsanctioned apps by leveraging your existing on-prem security appliances. Generate a dedicated block script and import it to your appliance.
This solution does not require redirection of all of the organization's web traffic to a proxy.

1. In the Cloud Discovery dashboard, tag any apps you want to block as **Unsanctioned**.

   ![Tag as unsanctioned](./media/tag-as-unsanctioned.png)  

2. In the title bar, click on the three dots and select **Generate block script...**. 

   ![Generate block script](./media/generate-block-script.png)  

3. In **Generate block script**, select the appliance you want to generate the block script for. 

   ![Generate block script pop up](./media/generate-block-script-popup.png)  

4. Then, click the Generate script button. This will create a block script for all your unsanctioned apps. By default, the file will be named with the date on which it was exported and the appliance type you selected, for example *2017-02-19_CAS_Fortigate_block_script.txt* 

   ![Generate block script button](./media/generate-block-script-button.png)  

5. Import the file created to your appliance.



## See Also  
[Daily activities to protect your cloud environment](daily-activities-to-protect-your-cloud-environment.md)   

[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  