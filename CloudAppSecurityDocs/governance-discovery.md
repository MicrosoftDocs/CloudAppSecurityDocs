---
# required metadata

title: Blocking discovered apps | Microsoft Docs
description: This topic describes the procedure for exporting block scripts for discovered apps. 
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 2/19/2017
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

# Governing discovered apps
Governance enables you to control what your users do, in real time, across apps. 
For discovered apps, you can govern users by exporting a block script to your firewall or third-party DLP solution.
For connected apps, you can apply governance actions to files or activities.

## Export a block script to govern discovered apps

Use the following procedure to export a block script from Cloud App Security to you to block use of discovered apps from your firewall or third-party DLP solution:

1. In the Cloud Discovery dashboard, tag any apps you want to block as **Unsanctioned**.

   ![Tag as unsanctioned](./media/tag-as-unsanctioned.png)  

2. In the title bar, click on the three dots and select **Generate block script...**. 

   ![Generate block script](./media/generate-block-script.png)  

3. In **Generate block script**, select the appliance you want to generate the block script for. 

   ![Generate block script pop up](./media/generate-block-script-popup.png)  

4. Then, click the Generate script button. This will create a block script for all your unsanctioned apps. By default, the file will be named with the date on which it was exported and the appliance type you selected, for example *2017-02-19_CAS_Fortigate_block_script.txt* 

   ![Generate block script button](./media/generate-block-script-button.png)  

5. Import the file created to your relevant firewall or DLP solution.



## See Also  
[Daily activities to protect your cloud environment](daily-activities-to-protect-your-cloud-environment.md)   
[For technical support, please visit the Cloud App Security assisted support page.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  