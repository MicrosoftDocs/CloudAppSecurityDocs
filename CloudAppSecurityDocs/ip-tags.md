---
# required metadata

title: Set IP ranges and tags | Microsoft Docs
description: This topic provides instructions for working with IP tags and IP categories.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 4/22/2018
ms.topic: conceptual
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: bbf54f66-4ce2-428c-afc8-b5a64277014f

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
 
 
#  <a name="IPtagsandRanges"></a> Working with IP ranges and tags

To easily identify known IP addresses, such as your physical office IP addresses, you need to set IP address ranges, which allow you to tag and categorize appropriately and customize the way logs and alerts are displayed and investigated. <br></br>  
Each group of IP ranges can be categorized based on a preset list of IP categories or tagged with your own created IP tags. In addition, this setting allows you to override public geo-location info based on your internal network knowledge.  
  
IPv4 and IPv6 are supported.  
  
Cloud App Security comes preconfigured with built-in IP ranges for popular cloud providers such as Azure and Office 365. In addition we have built-in tagging based on Microsoft threat intelligence including Anonymous proxy, Botnet and Tor. You can see the full list in the drop down on the IP address ranges page.

To use these built-in tags as part of a search, refer to their ID in the Cloud App Security API documentation. 

> [!NOTE]
> You can add IP ranges in bulk by creating a script using the **IP address ranges API**, which can be found from the Cloud App Security portal menu bar, by clicking the question mark and then **API documentation**.


Built-in IP address tags and custom IP tags are considered hierarchically, with custom IP tags taking precedence over built-in IP tags. For instance, if an IP address is tagged as **Risky** based on threat intelligence, but there is a custom IP tag that identifies it as **Corporate** the custom category and tags take precedence.

In the menu bar, click the settings icon ![the settings icon](./media/settings-icon.png "settings icon") and select **IP address ranges**. Click the plus sign to add IP address ranges and set the following fields:  
  
> [!NOTE]  
> - The Location and Registered ISP override defaults.   
> - IP tags, however, are added to the activity without overriding data.  
  
1.  **Name** your IP range. The name does not appear in the activities log, it is only used to manage your IP range.  
  
     To include the IP range in an IP category, select a category from the drop-down menu.  
  
2.  Enter the **IP address range** you wish to configure and then click on the "+" button. You can add as many IP addresses and subnets as you want using network prefix notation (also known as CIDR notation), for example 192.168.1.0/32.  
  
3.  **Categories** are used to easily recognize activities from interesting IP addresses. The categories are available in the portal yet require user configuration to determine which IP addresses are included in each category, except for the "Risky" category, which includes two IP tags - Anonymous proxy and Tor.  
  
     The following IP categories are available:  
  
    -   **Administrative**: these should be all the IP addresses of your admins.  
  
    -  **Cloud provider**: these should be the IP addresses used by your cloud provider.
  
    -   **Corporate**: these should be all the IP addresses of your internal network, your branch offices, and your Wi-Fi roaming addresses.  
  
    -   **Risky**: these should be any IP addresses that you consider risky. They can include suspicious IP addresses you've seen in the past, IP addresses in your competitors' networks, etc.  
  
    -   **VPN**: these should be any IP addresses you use for remote workers.  
4.  To **Tag** the activities from these IP addresses enter a tag. Entering a word into the box creates the tag. After you already have a configured tag, you can easily add it to additional IP ranges by choosing it from the list. You can add as many IP tags as you want for each range. IP tags can be used when building policies.  In addition to the IP tags you configure, Cloud App Security has built-in tags that are not configurable. You can see the list of tags under the [IP tags filter](activity-filters.md).  
  
5.  To **Override the Location** or Organization (ISP) fields for these addresses, enter new value. For example, if you have an IP address that is considered publicly to be in Ireland, but you know it to be in the US, you can override this setting.  
  
6.  Enter a **Registered ISP**. This overrides the data in your activities  
 
7.   When you are done, click **Create**.  
  
     ![newipaddress range](./media/newipaddress-range.png "newipaddress range")  
  
  
    
## See Also  
[Set up Cloud Discovery](set-up-cloud-discovery.md)   

[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  