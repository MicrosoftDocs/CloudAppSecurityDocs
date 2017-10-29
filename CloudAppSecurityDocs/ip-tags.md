---
# required metadata

title: Set IP ranges and tags | Microsoft Docs
description: This topic provides instructions for working with IP tags and IP categories.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 8/27/2017
ms.topic: get-started-article
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
  
#  <a name="IPtagsandRanges"></a> Working with IP ranges and tags

To easily identify known IP addresses, such as your physical office IP addresses, you need to set IP address ranges which allow you to tag and categorize appropriately and customize the way logs and alerts are displayed and investigated.   
Each group of IP ranges can be categorized based on a preset list of IP categories or tagged with your own created IP tags. In addition, this setting allows you to override public geo-location info based on your internal network knowledge.  
  
IPv4 and IPv6 are supported.  
  
Cloud App Security comes preconfigured with built-in tags for the following IP addresses: 
- Native client
- Outdated operating system
- Managed devices
- Anonymous proxy
- Botnet (when an activity was performed by a botnet, you will receive a link to learn more about the specific botnet)
- Tor
- Compliant device
- Verified device
- Impersonate

To use these built-in tags as part of a search, refer to their ID in the Cloud App Security API documentation. 

> [!NOTE]
> You can add IP ranges in bulk by creating a script using the [IP address ranges API](https://portal.cloudappsecurity.com/api-docs/)


Built-in IP address tags and custom IP tags are considered hierarchically, with custom IP tags taking precedence over built-in IP tags. For instance, if an IP address is tagged as **Risky** based on threat intelligence, but there is a custom IP tag that identifies it as **Corporate** the custom category and tags will take precedence.

In the menu bar, click the settings icon ![settings icon](./media/settings-icon.png "settings icon") and select **IP address ranges**. Click **+Add IP address range** and set the following:  
  
> [!NOTE]  
>  The Location and Registered ISP will override defaults.   
> IP tags, however, are added to the activity without overriding data.  
  
1.  **Name** your IP range. The name will not appear in the activities log, it is only used to manage your IP range.  
  
     To include the IP range in an IP category, select a category from the drop-down menu.  
  
2.  Enter the **IP address range** you wish to configure and then click on the "+" button. You can add as many IP addresses and subnets as you want using network prefix notation (also known as CIDR notation), for example 192.168.1.0/32.  
  
3.  To **Override the Location** or Organization (ISP) fields for these addresses, enter new value. For example, if you have an IP address that is considered publicly to be in Ireland, but you know it to be in the US, you can override this setting.  
  
4.  Enter a **Registered ISP**. This will override the data in your activities  
  
5.  To **Tag** the activities from these IP addresses enter a tag. Entering a word into the box creates the tag. After you already have a configured tag you can easily add it to additional IP ranges by choosing it from the list. You can add as many IP tags as you want for each range. IP tags can be used when building policies.  In addition to the IP tags you configure, Cloud App Security has built-in tags that are not configurable. You can see the list of tags under the [IP tags filter](activity-filters.md).  
  
6.  **IP categories** are used to easily recognize activities from interesting IP addresses. The categories are available in the portal yet require user configuration to determine which IP addresses are included in each category, except for the "Risky" category which includes two IP tags - Anonymous proxy and Tor.  
  
     The following IP categories are available:  
  
    -   **Administrative**: these should be all the IP addresses of your admins.  
  
    -  **Cloud provider**: these should be the IP addresses used by your cloud provider.
  
    -   **Corporate**: these should be all the IP addresses of your internal network, your branch offices and your Wi-Fi roaming addresses.  
  
    -   **Risky**: these should be any IP addresses that you consider risky. They can include suspicious IP addresses you've seen in the past, IP addresses in your competitors' networks, etc.  
  
    -   **VPN**: these should be any IP addresses you use for remote workers.  
 

7.  When you are done, click **Create**.  
  
     ![newipaddress range](./media/newipaddress-range.png "newipaddress range")  
  
  
    
## See Also  
[Set up Cloud Discovery](set-up-cloud-discovery.md)   
[For technical support, please visit the Cloud App Security assisted support page.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  