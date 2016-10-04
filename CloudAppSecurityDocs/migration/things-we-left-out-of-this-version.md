---
title: "things we left out of this version"
ms.custom: na
ms.date: "07/26/2016"
ms.prod: "identity-cas"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
applies_to: 
  - "Microsoft Cloud App Security"
ms.assetid: 06dc1fb7-b00a-4b17-b408-c01d6e1c8d0c
caps.latest.revision: 12
author: "Rkarlin"
ms.author: "rkarlin"
manager: "stevenpo"
robots: noindex,nofollow
---
# things we left out of this version
  Insert introduction here.  
  
## Section Heading  
  
|Governance action|Description|  
|-----------------------|-----------------|  
|Active Directory auto import||  
|Active Directory import||  
|Link/unlink file from user's drive||  
|Put in admin quarantine||  
|Restrict to collaborators only||  
|Permanently delete file from app||  
|Scan for advanced threats||  
|Re-calculate Cloud Discovery scores||  
|Create custom Cloud Discovery filter data view||  
|Export discovery data||  
|Delete Cloud Discovery data||  
|Parse Cloud Discovery data||  
|Encrypt||  
|Run Box folder invites notification||  
|Grant read permission to domain||  
|Grant read permissions to myself||  
|Notify user||  
|Remove editors' ability to share||  
|Run file ownership user notification||  
|Put user in quarantine||  
|Remove a collaborator||  
|Make private||  
|Remove external users||  
|Remove user's collaborations||  
|Remove public access||  
|Remove direct shared link||  
|Require multi-factor authentication||  
|Revoke app||  
|Revoke password||  
|Revoke admin privileges||  
|Revoke user from app||  
|Revoke read permissions form myself||  
|Suspend user||  
|Transfer file ownership||  
|Transfer all files ownership||  
|Trash||  
|Unsuspend user||  
|Restore from user quarantine||  
|Account settings||  
|Allow editors to share||  
  
### Subsection Heading  
  
-   **Single sign-on**  
  
     If you want your administrators to avoid having to sign in separately to [!INCLUDE[Adallom](../migration/includes/adallom_md.md)], provide SSO information as follows.  
  
     Configuring an SSO authentication in the [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] console is highly recommended.  
  
    1.  Select the **Enable single sign-on** checkbox and copy the **Assertion consumer URL and service provider entity ID**:  
  
    2.  Go to your identity provider and add [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] as a SAML 2.0 application.  
  
        > [!NOTE]  
        >  [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] supports service-initiated login flows, which occur when a user navigates directly to sub-domain.console.[!INCLUDE[Adallom](../migration/includes/adallom_md.md)].com/login, provides a username and no password. When this happens, [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] initiates a login request to the identity provider. Some identity providers will require you to configure a compressed request for this to properly function.  
        >   
        >  All users in the console are stored with lower-case characters. Therefore, in order to make sure the users you assign to [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] match the console users, add their email addresses with all lower-case characters.  
  
    3.  Copy the following parameters form your identity provider's console:  
  
        -   Identity Provider Single Sign-On URL  
  
        -   Identity Provider Issuer  
  
        -   3.X.509 Certificate  
  
    4.  In the [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] console, add the parameters you copied from your identity provider into the relevant fields in the single sign-on configuration screen.  
  
    5.  Cick **Save**.  
  
    6.  Test the integration  
        by attempting to log on to the console using your identity provider. If the log on attempt failed, you can see the error by hovering over the information icon, and  download the assertion to make sure the information that was sent by your identity provider was the expected information.  
  
    7.  If the log on attempt was successful,  
        you can select the **Allow tenant access through single sign-on only (lockdown)** checkbox to prevent direct log on to the console. When this is enabled,  [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] only accepts authenticated identity provider accounts and will no longer accept log on attempts directly to the console with your [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] credentials.  
  
        > [!IMPORTANT]  
        >  Make sure  you do not select the checkbox until you have verified that the single sign-on integration is working properly.  
  
-  
  
 Insert subsection body here.  
  
### Step 6: Forward logs to your SIEM (Preview Feature)  
 Integrating with a SIEM service allows you to better protect your cloud applications while maintaining your usual security workflow, automating security procedures and correlating between cloud-based and on-premises events. The [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] SIEM agent which is installed on the SIEM server pulls the logs from the [!INCLUDE[Adallom](../migration/includes/adallom_md.md)]API and streams them in CEF format into the SIEM logger to enable you to include your [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] logs in your SIEM. To integrate [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] with your SIEM, you must perform the following to take the [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] logs from the and send them to your SIEM service using Syslog TCP.  
  
> [!NOTE]  
>  [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] uses TCP Syslog to assure reliability of SIEM integration. TCP Syslog listener is installed by default on SIEM, however, if your SIEM instance does not support TCP Syslog, contact support.  
  
1.  Prerequisites:  
  
    -   A standard UNIX server  
  
    -   A virtual machine running Java 8  
  
2.  In the [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] console, click your name in the console menu bar, and select **User settings** and then click on the API Token tab. Name your SIEM integration token and click **Generate new token**. In the Created API token window, copy the token value.  
  
3.  On your XXX computer, download the [SIEMAgent.jar file here](https://app.box.com/s/y1y4kedctgcjcckl2b6i3bw8kcf2cd31) and save it in `/etc/adallom/siemagent/siemagent.jar`  
  
    > [!NOTE]  
    >  -   [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] supports multiple concurrent SIEM agents for different variations of logs and filters. You can create several configuration files and repeat these steps.  
    > -   The [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] SIEM agent uses the system clock to make the initial events synchronization. Make sure its accurate before running the agent. Events will be downloaded from the initial run and onward. If you want to download all events, contact support.  
  
4.  Configure your SIEM agent as follows:  
  
    1.  On your XXX computer, create the file `/etc/adallom/siemagent/cfg/[CFGNAME].xml` and fill in the following:  
  
        ```  
        <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
  
        <config>  
  
           <logDirectory>/var/log/adallom/siemagent/[CFGNAME]</logDirectory>  
  
           <stateFilePath>/etc/adallom/siemagent/state/[CFGNAME].dat</stateFilePath>  
  
           <rerunDelay>[RUN INTERVAL]</rerunDelay>  
  
           <url>https://[CONSOLE SUB-DOMAIN]console.adallom.com/api/</url>  
  
           <token>[TOKEN]</token>  
  
           <api>[LOG TYPE]</api>  
  
           <filters>  
  
               <filter>[FILTER]</filter>  
  
               <filter>[FILTER]</filter>  
  
                          ...  
  
           </filters>  
  
           <syslogHost>[SIEM HOST]</syslogHost>  
  
           <syslogPort>[SIEM PORT]</syslogPort>  
  
           <proxyHost>[OPTIONAL - PROXY HOST]</proxyHost>  
  
           <proxyPort>[OPTIONAL - PROXY PORT]</proxyPort>  
  
           <loggingEnable>[OPTIONAL - LOGGING ENABLE]</loggingEnable>  
  
           <siemLoggingEnable>[OPTIONAL - SIEM LOGGING ENABLE]</siemLoggingEnable>  
  
           <formatSet>[OPTIONAL – FORMAT SET]</formatSet>  
  
           <outputFormat>[OPTIONAL – CUSTOM FORMAT]</outputFormat>  
  
        </config>  
  
        ```  
  
         Using the following values:  
  
        |Value|Description|Example|  
        |-----------|-----------------|-------------|  
        |CFGNAME|A unique name that describes this instance of SIEMAgent|auditsgrabber|  
        |RUN INTERVAL|The interval for synchronization in milliseconds<br /><br /> Recommended value is 20 seconds|20000|  
        |CONSOLE SUB-DOMAIN|The sub-domain you have when you login to the  console|[!INCLUDE[Adallom](../migration/includes/adallom_md.md)]|  
        |LOG TYPE|Type of logs to retrieve. Supported values:<br /><br /> -   Audits- Activity log entries<br />-   Alerts - Alert entries|audits|  
        |FILTER|Optional<br /><br /> List of filters. Only entries that conform to all the filters are processed (AND filter).<br />Different filter options are specified below.|service=google-apps|  
        |SIEM HOST|The IP address of the SIEM|10.0.0.120|  
        |SIEM PORT|The port number for TCP Syslog listener|1111|  
        |PROXY HOST|Optional<br />The IP address of the proxy.|10.0.0.250|  
        |PROXY PORT|Optional<br />The TCP port of the proxy.|8080|  
        |LOGGING ENABLE|Optional<br />Set to true in order to activate the logs|true|  
        |SIEM LOGGING ENABLE|Optional<br />Set to true in order to send internal logs of the SIEM Agent to the syslog server|true|  
        |FORMAT SET|**Optional**<br /><br /> ADALLOM_CEF_V1 - (Default) the default SIEMagent output format.<br /><br /> ARCSIGHT_CEF_V1 - Output format compatible with ArcSight system.<br /><br /> CUSTOM - configure a custom format of your own (should be set in outputFormat) - see CUSTOM FORMAT below.|ADALLOM_CEF_V1|  
        |CUSTOM FORMAT|**Optional** Write your own output format - contact support for more information.||  
  
         Activity Filters:  
  
        |Parameter name|Type|Description|  
        |--------------------|----------|-----------------|  
        |Action|Multi-value strings, supports negation|List of action names (returned from /api/audits/type/|  
        |Service|Multi-value strings, supports negation|List of service “slugs” (safe url strings) of service names to filter the results|  
        |User|Multi-value strings, supports negation|List of users to filter the results|  
  
         Alert Filters:  
  
        |Parameter name|Type|Description|  
        |--------------------|----------|-----------------|  
        |Users|Comma separated list, supports negation|List of users to filter the results|  
  
5.  Run the SIEM agent in one of the following modes:  
  
    -   Run the following in command line mode: `java -jar SIEMAgent.jar /etc/adallom/siemagent/cfg/[CFGNAME].xml`  
  
    -   Recommended - Custom SystemV/Upstart service files can be provided upon request.  
  
#### Data privacy  
 When scanning and analyzing all your cloud app data, [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] saves only activity logs and metadata for your cloud app activity. Customer data (for example, file content and records) will never be found or kept anywhere on our servers. [!INCLUDE[Adallom](../migration/includes/adallom_md.md)]'s alerting and reporting is based only on activity logs and static lists of metadata that are retrieved from the services (for example, lists of attachments in Salesforce or  lists of users from Okta). Additionally, if any of these metadata lists are considered sensitive to you, the relevant module can be turned off so that those lists will not be retrieved from your cloud app account.  
  
 The only data that is directly inspected by [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] is data on which you set a file policy with a content inspection. In this case, files are scanned in-memory and when a policy is violated, the only data sent to [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] is the metadata of the file that was matched along with  the obfuscated violation from the file (the match is obfuscated as well as any other digit in the violation text).  
  
 [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] provides controls to mitigate risks and control cloud apps such as data scanning capabilities, auditing of activities and anomaly detection. [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] also monitors itself and enforces these same controls to provide security for [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] access as well.  
  
 Setting up an [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] API connector is similar for each supported cloud app you want to monitor. The process entails sanctioning the app and then gaining an access token to the app for the [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] API. Using the access token, [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] integrates with the cloud app API, gets all the relevant information about users and activities and enforces policies as needed.  
  
## Content inspection  
 Content inspection is performed utilizing the built-in DLP engine that can scan for pre-built data types as well as customer regular expressions.  
  
> [!NOTE]  
>  The files are downloaded from the cloud service and scanned, without ever storing them in [!INCLUDE[Adallom](../migration/includes/adallom_md.md)].  
  
 ![policy_dlp](../migration/media/policy_dlp.png "policy_dlp")  
  
-   Preset expression – Search for one of the preset sensitive data types, for example, All files with PII data.  
  
-   High sensitivity matching – Increase sensitivity of the filter, providing more results but increasing the number of false positives, for example, All files with credit card data, even with low certainty.  
  
-   Custom expression  
  
    -   Case sensitive – Perform a case-sensitive text-based search.  
  
    -   Substring – Search for a specific substring in all files, for example, All files with the substring PROJECT_SCOLA_.  
  
    -   Exact match – Search for an exact match, for example, All files that are publicly shared and contain the phrase ‘company confidential'.  
  
    -   Custom regular expression – Define a custom regular expression based on company-specific data types.  
  
-   Exclusion based on regular expression – Exclude files with certain content, for example, Look for files with PII information except for <TRIAL_PII_INFO_USED_IN_COMPANY>.  
  
-   Violations threshold – Look for files with a more than X violations.  
  
-   Mask DLP match – Configure if DLP matches should be stored in reports and logs. Default is to mask violations.  
  
    > [!IMPORTANT]  
    >  Numbers are replaced with “#” characters and never stored within [!INCLUDE[Adallom](../migration/includes/adallom_md.md)].  
  
 Content inspection extensions:  
  
 As depicted in the diagram below, the architecture can be extended to leverage 3rd-party DLP solutions such Symantec Vontu and Secure Islands. The service can integrate with existing on prem services as well as via cloud-to-cloud integrations.  
  
 ![policy engine](../migration/media/policy-engine.jpg "policy engine")  
  
-   Connectors:  
  
     The API connector scans files upon download as well as periodically. Each file is sent to the policy engine.  
  
     The Proxy connector scans files in real time as they are uploaded/downloaded.  
  
-   Data classification point:  
  
     The built-in DLP engine provides basic DLP scans and classification.  
  
     Integration with external, third-party DLP systems uses REST API to customize integrations. Common protocols such as ICAP can usually used out-of-the-box.  
  
-   Data processing point:  
  
     Built-in governance engine provides powerful governance tools for automating remediation actions like removing permissions of a file or user.  
  
     REST API can be used for custom integrations with third-party DRM systems to provide content processing such as water marking documents upon download.  
  
-   3rd party DLP – On-premises DLP solutions such as Symantec Vontu can be used to perform content inspection.  
  
-   Anti-malware – Anti-malware and sandboxing services can be leveraged to scan cloud data and protect from threats.  
  
 Governance action extensions  
  
 As shown in the diagram above, additional governance actions can be added by integrating with a 3rd-party file processing service, for example, Secure Islands for file encryption or a custom company solution for water marking.  
  
## User notifications reference  
 User notifications can be configured to periodically send reminders for violations, with an attached list of file violations. This can be used as reminder as well as for user approvals, for example, once a quarter all users need to approve that the list of publicly shared files is appropriate.  
  
-   File notifications – configurations include the following:  
  
    -   File filters – See [File filters](#Filefilters).  
  
    -   Email details:  
  
        -   Subject  
  
        -   CC  
  
        -   BCC  
  
        -   Body  
  
    -   Notification configuration  
  
        -   Include file details – Configure the optional attachment which contains the list of violations. A maximum size can be set as well.  
  
        -   Periodic configuration – Notifications can be sent every X days automatically.  
  
-   Folder invite notifications – The second type of notifications focuses on folder invite management. Allowing admins to track stale folder invites and notify users of these. Currently available for Box only.  
  
    -   Most filters are identical to general user notifications  
  
    -   Notify the inviter after more than X days – Allows the notification to search for stale invitations, that haven't been touched for over X days.  
  
|Risk category|Policy type|Use case|Automatic remediation|  
|-------------------|-----------------|--------------|---------------------------|  
|Access control||||  
|Compliance||||  
|Configuration control||||  
|Cloud discovery||||  
|DLP|File policy|Highly sensitive data that isn't meant to be shared on the cloud|Quarantine file|  
|Privileged accounts||||  
|Sharing control|File policy|Sharing control: public files containing sensitive data|Remove publish sharing or direct link|  
|Threat detection|Activity policy|Access from risky IP addresses|Suspend account|  
  
## Mitigating Risk  
  
-   The first thing you want to do to mitigate risk is take a look at the **Discovery Dashboard** and focus on your risky apps.  
  
-   Click on **Risky apps**. You can filter them by low risk score to see the worst offenders. You can also filter them by upload. If it's a risky app with significant upload, it may be one of the first things you want to take care of.  
  
-   You can click on the app to open the App information drawer to see why its score is so low - is it ranking low on compliance? or maybe the location of the app provider is suspect? If you find that the score is low because of a factor that is of particular concern to your organization, you might want to take care of that app right away.  
  
### Investigating risky apps  
 The best way to investigate risky apps is to deep dive into the app, its score, and the users and IP addresses using the app:  
  
-   In the **Discovery Dashboard**, double-click to open the app. You can check to see how many people use it, or how many uploads are happening in that app. You can check trends over time and you can also see transactions by top users or top IP addresses.  
  
-   It could be interesting to go to the users and IP addresses to see who's using the app. Click on the amount of upload or traffic to figure out who the most dominant user of the app is.  
  
-   You can drill down by clicking on the user to see how many apps they use or how many risky apps they use.  
  
### Taking governance actions on risky apps  
 Once you find the apps and users of concern to your organization, you can take governance actions:  
  
-   You can contact the users or their managers to recommend alternative, safe and sanctioned apps.  
  
-   You can manage the risky app by going to the **Discovered Services** page and clicking the ![Sanction three dots](../migration/media/sanction-three-dots.png "Sanction three dots") icon next to the service and setting it as **Unsanctioned**.  
  
-   Then, you can block access to your Unsanctioned apps by clicking the  ![Sanction three dots](../migration/media/sanction-three-dots.png "Sanction three dots") icon and selecting **Export blocking script** for your firewall.  
  
### Manage alerts  
 Change alerts and policies depending on what is being caught that you don't want considered Risky.  
  
-   In the console, click **Alerts**. For each alert you can do the following:  
  
-   1.  **Dismiss** the alert by clicking the X at the end of the alert row.  
  
    2.  Click on the alert to enable deep investigation. From inside the alert you can Resolve or take desired actions to resolve the alert. The actions listed will be determined by the type of policy violated by the alert.  
  
## Investigating risk  
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
  
## Forward logs to your SIEM (Preview Feature)  
 Integrating with a SIEM service allows you to better protect your cloud applications while maintaining your usual security workflow, automating security procedures and correlating between cloud-based and on-premises events. The [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] SIEM agent pulls the logs using the [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] API and streams them in CEF format into the SIEM logger to enable you to include your [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] logs in your SIEM. To integrate [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] with your SIEM, you must perform the following to take the [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] logs from the and send them to your SIEM service using Syslog TCP.  
  
> [!NOTE]  
>  [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] uses TCP to assure reliability of the SIEM integration.  
  
1.  Prerequisites:  
  
    -   A standard Linux or Windows server (can be a virtual machine).  
  
    -   The server should run Java 8.  
  
2.  In the [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] console, click your name in the console menu bar, and select **User settings** and then click on the API Token tab. Name your SIEM integration token and click **Generate new token**. In the Created API token window, copy the token value.  
  
3.  Create the following folders on your server:  
  
     `/etc/mcas/siemagent` (Linux) or `C:\MCAS\siemagent` (Windows)  
  
     `/etc/mcas/siemagent/cfg` (Linux) or `C:\MCAS\siemagent\cfg (Windows)`.  
  
4.  Download [SIEMAgent.jar](https://app.box.com/s/y1y4kedctgcjcckl2b6i3bw8kcf2cd31) and save it to your server in:  
  
     For Linux: `/etc/mcas/siemagent/`  
  
     For Windows: `C:\MCAS\siemagent`  
  
    > [!NOTE]  
    >  It is recommended to keep the version number as part of the filename, for easier identification of the installed version.  
  
    > [!NOTE]  
    >  -   [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] supports multiple concurrent SIEM agents for different variations of logs and filters. You can create several configuration files and repeat these steps.  
    > -   The [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] SIEM agent uses the system clock to make the initial events synchronization. Make sure its accurate before running the agent. Events will be downloaded from the initial run and onward. If you want to download all events, contact support.  
  
5.  Configure your SIEM agent as follows:  
  
    1.  Choose a name for your configuration and create a new file in the **cfg** folder and name it [CFGNAME].xml.  
  
         Where CFGNAME is the name of your configuration (do not include the brackets [ ] in your code).  
  
         Start with a letter, and do not use spaces or special symbols (the use of numbers, dashes and underscores is allowed). Paste the following into the file you created, and edit the parameters within (instructions on the next step).  
  
        > [!NOTE]  
        >  If you are an existing Adallom customer, and your console URL is for Adallom and not [!INCLUDE[Adallom](../migration/includes/adallom_md.md)], use [SUB DOMAIN].console.adallom.com instead of [SUB DOMAIN].portal.cloudappsecurity.com.  
  
         For Linux:  
  
        ```  
        <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
        <config>  
           <logDirectory>/var/log/mcas/siemagent/[CFGNAME]</logDirectory>  
           <stateFilePath>/etc/mcas/siemagent/state/[CFGNAME].dat</stateFilePath>  
           <rerunDelay>[RUN INTERVAL]</rerunDelay>  
           <url>https://[PORTAL SUB-DOMAIN].portal.cloudappsecurity.com/api/</url>  
           <token>[TOKEN]</token>  
           <api>[LOG TYPE]</api>  
           <filters>  
               <filter>[FILTER]</filter>  
               <filter>[FILTER]</filter>  
           </filters>  
           <syslogHost>[SIEM HOST]</syslogHost>  
           <syslogPort>[SIEM PORT]</syslogPort>  
           <proxyHost>[OPTIONAL - PROXY HOST]</proxyHost>  
           <proxyPort>[OPTIONAL - PROXY PORT]</proxyPort>  
           <loggingEnable>[OPTIONAL - LOGGING ENABLE]</loggingEnable>  
           <siemLoggingEnable>[OPTIONAL - SIEM LOGGING ENABLE]</siemLoggingEnable>  
           <formatSet>[OPTIONAL – FORMAT SET]</formatSet>  
           <outputFormat>[OPTIONAL – CUSTOM FORMAT]</outputFormat>  
        </config>  
  
        ```  
  
         For Windows:  
  
        ```  
        <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
        <config>  
           <logDirectory>C:\MCAS\siemagent\log\[CFGNAME]</logDirectory>  
           <stateFilePath>c:\MCAS\siemagent\state\[CFGNAME].dat</stateFilePath>  
           <rerunDelay>[RUN INTERVAL]</rerunDelay>  
           <url>https://[PORTAL SUB-DOMAIN].portal.cloudappsecurity.com/api/</url>  
           <token>[TOKEN]</token>  
           <api>[LOG TYPE]</api>  
           <filters>  
               <filter>[FILTER]</filter>  
               <filter>[FILTER]</filter>  
           </filters>  
           <syslogHost>[SIEM HOST]</syslogHost>  
           <syslogPort>[SIEM PORT]</syslogPort>  
           <proxyHost>[OPTIONAL - PROXY HOST]</proxyHost>  
           <proxyPort>[OPTIONAL - PROXY PORT]</proxyPort>  
           <loggingEnable>[OPTIONAL - LOGGING ENABLE]</loggingEnable>  
           <siemLoggingEnable>[OPTIONAL - SIEM LOGGING ENABLE]</siemLoggingEnable>  
           <formatSet>[OPTIONAL – FORMAT SET]</formatSet>  
           <outputFormat>[OPTIONAL – CUSTOM FORMAT]</outputFormat>  
        </config>  
  
        ```  
  
         Parameters table:  
  
        > [!NOTE]  
        >  Omit any lines of the optional parameters that you are not using.  
  
        |Value|Description|Example|  
        |-----------|-----------------|-------------|  
        |CFGNAME|A unique name that describes this instance of the SIEM agent. Use the same name you chose for the file name.|audits|  
        |RUN INTERVAL|The interval for synchronization in milliseconds.<br /><br /> Recommended value is 20 seconds.|20000|  
        |PORTAL SUB-DOMAIN|The sub-domain you have when you login to the portal.|cloudappsecurity|  
        |LOG TYPE|Type of logs to retrieve. Supported values:<br /><br /> -   audits- Activity log entries<br />-   alerts - Alert entries|audits|  
        |FILTER|**Optional**<br /><br /> List of filters. Only entries that match all the filters are returned (AND).<br />See usage, below.|service=google-apps|  
        |SIEM HOST|The IP address of the SIEM server.|10.0.0.120|  
        |SIEM PORT|The port number of the TCP Syslog listener.|1111|  
        |PROXY HOST|**Optional**<br /><br /> The IP address of your HTTP proxy.|10.0.0.250|  
        |PROXY PORT|**Optional**<br /><br /> The TCP port of your HTTP proxy.|8080|  
        |LOGGING ENABLE|**Optional**<br /><br /> Set to true in order to activate the logs.|true|  
        |SIEM LOGGING ENABLE|**Optional**<br /><br /> Set to true in order to send internal logs of the SIEM agent to the Syslog server.|true|  
        |FORMAT SET|**Optional**<br /><br /> ADALLOM_CEF_V1 - (Default) the default SIEM agent output format.<br /><br /> ARCSIGHT_CEF_V1 - Output format compatible with ArcSight system.|ADALLOM_CEF_V1|  
  
         Activity Filters:  
  
        |Parameter name|Type|Description|  
        |--------------------|----------|-----------------|  
        |action|Multi-value strings, supports negation, comma separated list.|List of actions|  
        |service|Multi-value strings, supports negation, comma separated list.|List of apps in the following format:<br /><br /> -   Take the application name as listed in the portal.<br />-   Convert all characters to lower case.<br />-   Replace spaces with a hyphen -.<br />-   Remove all non-numeric and non-alphabetical characters.<br />-   Replace multiple hyphens - with a single hyphen -.<br />-   Remove any hyphens  - from the start and end.<br />-   For example:<br />     Google Apps: google-apps<br />     Office 365: office-365<br />     Microsoft SharePoint Online: microsoft-sharepoint-online<br />     Salesforce: salesforce|  
        |user|Multi-value strings, supports negation, comma separated list.|List of users|  
  
         Alert Filters:  
  
        |Parameter name|Type|Description|  
        |--------------------|----------|-----------------|  
        |users|Multi-value strings, supports negation, comma separated list.|List of users|  
  
6.  Run the SIEM agent in one of the following modes:  
  
    -   Manual run:  
  
        -   Linux: `java -jar /etc/mcas/siemagent/siemagent.jar /etc/mcas/siemagent/cfg/[CFGNAME].xml`  
  
        -   Windows: `java -jar C:\MCAS\siemagent\siemagent.jar C:\MCAS\siemagent\cfg\[CFGNAME].xml`  
  
            > [!NOTE]  
            >  Replace CFGNAME.xml with the configuration file name.  
            >   
            >  Your jar file may have different name (if you kept the version number).  
  
    -   Automated run: Create a startup script to run the agent on system startup.  
  
  