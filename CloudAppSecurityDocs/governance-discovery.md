---
# required metadata

title: Blocking discovered apps | Microsoft Docs
description: This topic describes the procedure for exporting block scripts for discovered apps. 
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 2/21/2017
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
Cloud App Security enables you to block access to unsanctioned apps by leveraging your existing on-prem security appliances. Generate a dedicated block script and import it to your appliance.
This solution does not require redirection of all of the organization's web traffic to a proxy.


## Export a block script to govern discovered apps

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
[For technical support, please visit the Cloud App Security assisted support page.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  