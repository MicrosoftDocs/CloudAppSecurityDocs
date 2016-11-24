---
# required metadata

title: Investigate | Microsoft Docs
description: This topic provides an outline of the process for investigating alerts, issues, and suspicious activities by using Cloud App Security.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 11/21/2016
ms.topic: article
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: a9b00c2a-2f71-499e-8f57-67e560daedc1

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Investigate
After Cloud App Security runs in your cloud environment, you'll need a stage of learning and investigating how to use the tools in Cloud App Security to gain a deeper understanding of what's happening in your cloud environment. Then, based on your particular environment and how it's being used, you can identify the requirements for protecting your organization from risk.  

This topic describes how to perform an investigation to get a better understanding of your cloud environment.  

## Dashboards  
The following dashboards are available to help you investigate apps in your cloud environment:  

|Dashboard|Description|  
|---------------|-----------------|  
|Main dashboard|Overview of cloud status (users, files, activities) and required actions (alerts, activity violations and content violations)|  
|Application dashboard: overall|Overview of application usage per location, usage graphs per number of users|  
|Application dashboard: insights|Analysis of data stored in the app, broken down by file type and file-sharing level|  
|Application dashboard: files|Drill-down into files; ability to filter according to owner, sharing level, etc., as well as perform governance actions (like quarantine)|  
|Application dashboard: third-party apps|Drill-down into third-party apps currently deployed, like Google Apps, and defining policies for them|  
|User dashboard|A complete overview of the user profile in the cloud, including groups, locations, recent activities, related alerts, and browsers used|  

##  <a name="sanctionapp"></a> Tag apps as sanctioned or unsanctioned  
An important step to understanding your cloud is to tag apps as sanctioned or unsanctioned. After you sanction an app, you can filter for apps that aren't sanctioned and start migration to sanctioned apps of the same type.  

-   In the Cloud App Security console, go to the App catalog or Discovered apps.  

-   In the list of apps, on the row in which the app you want to tag as sanctioned appears, choose the three dots at the end of the row ![Tag as sanctioned dots](./media/sanction-three-dots.png "Tag as sanctioned dots") and choose **Mark as sanctioned**.  

     ![Tag as sanctioned](./media/mark-as-sanctioned.png "tag as sanctioned")  


## Use the investigation tools  

1.  In the Cloud App Security portal, go to **Investigate** and then look at the **Activity log** and filter by a specific app. Check the following:  

    -   Who is accessing your cloud environment?  

    -   From what IP ranges?  

    -   What is the admin activity?  

    -   From what locations are admins connecting?  

    -   Are any outdated devices connecting to your cloud environment?  

    -   Are failed logins coming from expected IP addresses?  

2.  Go to **Investigate** and then **Files**, and check the following:  

    -   How many files are shared publicly so that anyone can access them without a link?  

    -   With which partners are you sharing files (outbound sharing)?  

    -   Do any files have a sensitive name?  

    -   Are any of the files being shared with someone's personal account?  

3.  Go to **Investigate** and then **Accounts**, and check the following:  

    -   Have any accounts been inactive in a particular service for a long time? (Maybe you can revoke the license for that user to that service?)  

    -   Do you want to know which users have a specific role?  

    -   Was someone fired but they still have access to an app and can use that access to steal information?  

    -   Do you want to revoke a user's permission to a specific app or require a specific user to perform multi-factor authentication?  

4.  Go to **Investigate** and then select an app. The app dashboard opens and gives you information and insights. You can use the tabs across the top to check the following:  

     ![App dashboard](./media/investigate-app.png "investigate app")  

    -   What kind of devices are your users using to connect to the app?  

    -   What types of files are they saving in the cloud?  

    -   What activity is happening in the app right now?  

    -   Are there any connected third-party apps to your environment?  

    -   Are you familiar with these apps?  

    -   Are they authorized for the level of access they are permitted to?  

    -   How many users have deployed them? How common are these apps in general?  

5.  Go to the **Cloud Discovery dashboard** and check the following:  

    -   What cloud apps are being used, to what extent, and by whom?  

    -   For what purposes are they being used?  

    -   How much data is being uploaded to these cloud apps?  

    -   In which categories do you have sanctioned cloud apps, and yet, users are using alternative solutions?  

    -   For the alternative solutions, do you want to unsanction any cloud apps in your organization?  

    -   Are there cloud apps that are used but not in compliance with your organization’s policy?  

## Use reports to investigate risk  
When you start trying to gain control over your cloud environment, you make certain assumptions based on what you expect to find—you don't really know your cloud yet. Based on these assumptions, you create policies.

After Cloud App Security runs on your cloud environment, you use the built-in reports (and custom reports) to see what's going on in your cloud. Based on this, you adjust your policies again to include exceptions so that eventually your policy catches very few false positives.  

Built-in reports offer you aggregated views for investigation. To work with built-in reports, go to **Investigate** and then **Built-in reports**. For more information about the different built-in reports, see the [Built-in report reference](built-in-report-reference.md).  

## Sample investigation  
Let's say that you assume you don't have any access to your cloud environment by risky IP addresses (for example, anonymous proxies and Tor). But you create a policy for risk IPs just to make sure:  

1.  In the portal, go to **Control** and choose **Policies**.  

2.  In the **Policy center**, choose the **Templates** tab.  

3.  At the end of the **User logon from a non-categorized IP address** row, choose the plus sign (**+**) to create a new policy.  

4.  Change the policy name so you'll be able to identify this policy.  

5.  Under **Activity filters**, choose **+** to add a filter. Scroll down to **IP tag**, and then choose **Anonymous** and **Tor**.  

     ![Example policy for risky IPs](./media/example-policy-risky-ips.png "example policy risky ips")  

Now that you have the policy in place, you're surprised to see that you get an alert that the policy was violated.  

1.  Go to the **Alerts** page and view the alert about the policy violation.  

2.  If you see that it looks like a real violation, you want to contain risk or remediate.  

     To contain risk, you can send the user a notification to ask if the violation was intentional and if the user was aware of it.  

     You can also drill down into the alert and suspend the user until you can figure out what needs to be done.  

3.  If it's an allowed event that isn't likely to recur, you can dismiss the alert.  

     If it's allowed and you expect it to recur, you can change the policy so that this type of event won't be considered a violation in the future.  

## See also  
To learn how to control your organization's cloud app, see [Control](control.md).   
For technical support, go to the [Cloud App Security assisted support](http://support.microsoft.com/oas/default.aspx?prid=16031) page.  
Premier customers can also choose Cloud App Security directly from the [Premier portal](https://premier.microsoft.com/).  
