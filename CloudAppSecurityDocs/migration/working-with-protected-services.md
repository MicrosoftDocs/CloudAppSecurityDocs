---
title: "Working with protected services"
ms.custom: na
ms.date: "07/27/2016"
ms.prod: "identity-cas"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
applies_to: 
  - "Microsoft Cloud App Security"
ms.assetid: 3ff7fca2-db6a-4c06-ad5d-5ca125e6134e
caps.latest.revision: 10
author: "Rkarlin"
ms.author: "rkarlin"
robots: noindex,nofollow
---
# Working with protected services
  After deploying [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] and setting up your initial policies, the real work of [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] begins, providing you with deep visibility into what goes on in your cloud and enabling you to continuously fine-tune your policies to catch only incidents of interest, alerting you only when something of concern happens in your network. You can then respond to the detected events by investigating, notifying, running app-specific governance and always using them to further fine tune your policies for the future, as depicted here:  
  
 ![work process](../migration/media/work-process.png "work process")  
  
## Predict and Detect Risk  
 The first thing you want to do after [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] is all set up and running on your cloud apps, is to start monitoring what's going on in your cloud.  
  
 The main places to look to keep an eye on your cloud environment are:  
  
-   **The [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] Dashboard**  
  
     The dashboard provides an overview of everything happening in your cloud environment, including alert data and policy violations.  
  
     Try to keep your alerts cleared - that means clicking on each new alert, drilling down to investigate what happened and dismissing or resolving it.  
  
-   **The Policy center**  
  
     If you are concerned about a specific policy, and you want to make sure to monitor it, go to the Policy center and click on the policy of concern.  
  
     This opens the Alerts/policy matches page, filtered to that specific policy. You can then see all the matches for that policy and drill down into the specific violations to see which users or IP addresses or activities violated the policy.  
  
-   **The Alerts page**  
  
     In the alerts page, you can see the full list of open alerts in your environment. Clear your alerts by clicking on each, figuring out which policy they violate and deciding if they need to be dismissed or if you need to respond by taking action against the violation.  
  
-   **Built-in Reports**  
  
     Built-in reports help you gain insight into what's going on in your cloud environment. You can look at them to fine-tune your policies, or even before rolling out your initial policies to understand what kind of traffic is on your cloud.  
  
## Mitigating Risk  
  
-   The first thing you want to do to mitigate risk is take a look at the **Dashboard**.  The Dashboard provides you with an overview, alerts data and policy violations.  
  
     You should keep your alert list clear by going over the alerts on a daily basis and dismissing or resolving the alerts.  
  
-   Go to the **Policy center** and monitor any policies you are particularly interested in. Check to see what violations were triggered by these policies and what open alerts there are for these policies. Drill down by clicking on the policy and then for each match that was detected, you can click on the match content.  
  
-   Use the list of alerts you get to fine tune your policies and narrow the number of violations you get to ensure that only real violations are being considered policy matches.  
  
     If the policy is receiving too many false positives, and you want to modify the policy, this can be done by clicking on the settings icon next to the policy. You can also use the ![Sanction three dots](../migration/media/sanction-three-dots.png "Sanction three dots") icon to **Enable**/**Disable** or **Delete** a policy.  
  
 For example, if you receive an alert in which you see a log on by an unfamiliar IP address:  
  
1.  Go to **Investigate**, followed by **Built-in reports**.  
  
2.  Select **IP addresses** and in the report that opens, filter by the IP address and click on the IP address that is displayed to investigate further - who are the users? where are they located?  
  
3.  Click on the username to see an overview of the user's account.  
  
4.  Then if you want to take an action, you can resolve the alert by going back to the alert in the **Alerts** page, and clicking on the alert, and then selecting an action from the settings icon such as Suspend user, until you can determine exactly who logged in and if it was justified.  
  
     ![actions](../migration/media/actions.png "actions")  
  
### Predict and fine-tune using reports  
 When you start trying to gain control over your cloud environment, you make certain assumptions based on what you expect to find - you don't really know your cloud yet. And based on these assumptions, you create policies. Then, after [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] runs on your cloud environment, you can use the built-in reports (as well as custom reports) to see what's really going on in your cloud, and based on this, you adjust your policies again to include exceptions so that eventually your policy catches very few things that are false positives.  
  
 To work with Built-in Reports, go to **Investigate** and then **Built-in reports**. For more information about the various built-in reports, see the [Built-in report reference](../migration/built-in-report-reference.md).  
  
### Taking governance actions on risky apps  
 Once you find the apps and users of concern to your organization, you can take governance actions:  
  
-   You can contact the users or their managers to recommend alternative, safe and sanctioned apps.  
  
-   You can manage the risky app by going to the **Discovered Services** page and clicking the ![Sanction three dots](../migration/media/sanction-three-dots.png "Sanction three dots") icon next to the service and setting it as **Unsanctioned**.  
  
-   Then, you can block access to your Unsanctioned apps by clicking the  ![Sanction three dots](../migration/media/sanction-three-dots.png "Sanction three dots") icon and selecting **Export blocking script** for your firewall.  
  
### Example: Activity policy  
 For the sake of our example, let's say that you assume you don't have any access to your cloud environment by risky IP addresses (for example, Anonymous proxies and Tor). But you create a Risky IP policy just to make sure:  
  
1.  In the portal, go to **Control** and select **Policies**.  
  
2.  In the **Policy center**, click the **Templates** tab.  
  
3.  At the end of the **User logon from a non-categorized IP address** row, click the **+** to create a new policy.  
  
4.  Change the policy name so you'll be able to identify this policy.  
  
5.  Under **Activity filters**, click the **+** to add a filter. Scroll down to **IP tag** and then select **Anonymous** and **Tor**.  
  
     ![example policy risky ips](../migration/media/example-policy-risky-ips.png "example policy risky ips")  
  
 Now that you have the policy in place, you're surprised to see that you get an alert that the policy was violated.  
  
1.  Go to the **Alerts** page and view the alert about the policy violation.  
  
2.  If you see that it looks like a real violation, you want to contain risk or remediate.  
  
     To contain risk, you can send the user a notification to ask if the violation was intentional and if the user was aware of it.  
  
     You can also drill down into the alert and suspend the user until you can figure out what needs to be done.  
  
3.  You can also drill down into the alert manually and see if it was an allowed event.  
  
     If it's an allowed event that isn't likely to recur, you can dismiss the alert.  
  
     If it's allowed and you expect it to recur, you can modify the policy to avoid this type of event being considered a violation in the future.  
  
  