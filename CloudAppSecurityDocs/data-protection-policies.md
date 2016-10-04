---
title: "Data protection policies"
ms.custom: na
ms.date: "08/31/2016"
ms.prod: "identity-cas"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
applies_to: 
  - "Microsoft Cloud App Security"
ms.assetid: ac53fbd6-4d31-4bce-b2bc-9dc65ad83b3e
caps.latest.revision: 22
author: "Rkarlin"
ms.author: "rkarlin"
translation.priority.ht: 
  - "cs-cz"
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "hu-hu"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "nl-nl"
  - "pl-pl"
  - "pt-br"
  - "pt-pt"
  - "ru-ru"
  - "sv-se"
  - "tr-tr"
  - "zh-cn"
  - "zh-tw"
---
# Data protection policies
    
## File policies  
 File Policies allow you to enforce a wide range of automated processes leveraging the cloud provider’s APIs. Policies can be set to provide continuous compliance scans, legal eDiscovery tasks, DLP for sensitive content shared publicly and many more use cases.  
  Cloud App Security can monitor any file type based on more than 20 metadata filters (for example, access level, file type). 
 
**Supported file types** 

Cloud App Security's built in DLP engines perform content inspection by extracting text from all common file types (100+) including Office, Open Office, compressed files, various rich text formats, XML, HTML and more.

The engine combines three aspects under each policy:  
  
-   Content scan based on preset templates or custom expressions.  
  
-   Context filters including user roles, file metadata, sharing level, organizational group integration, collaboration context and additional customizable attributes.  
  
-   Automated actions for governance and remediation. For more information, see [Control](../migration/control.md).  
  
 Once enabled, the policy will continuously scan your cloud environment and identify files that match the content and context filters, and apply the requested automated actions. These policies will detect and remediate any violations for at-rest information or when new content is created. Policies can be monitored using real-time alerts or using console generated reports.  
  
 The following are examples of file policies that can be created:  
  
-   Publicly shared files:  
    Receive an alert about any file in your cloud that is publicly shared by selecting all files whose sharing level is public.  
  
-   Publicly shared filename contains the organization’s name:  
    Receive an alert about any file that contains your organization’s name and is publicly shared. Select files with a filename containing the name of your organization and which are publicly shared.  
  
-   Sharing with external domains:  
    Receive an alert about any file shared with accounts owned by specific external domains, for example, with a competitor’s domain. Select the external domain with which you want to limit sharing.  
  
-   Quarantine shared files not modified during the last period:  
    Receive an alert about shared files that no one modified recently, in order to quarantine them or choose to turn on an automated action. Exclude all the Private files that  weren’t modified during a specified date range. On Google Apps,  you can choose to quarantine these files, using the ‘quarantine file’ checkbox on the policy creation page.  
  
-   Sharing with unauthorized users:  
    Receive an alert about files being shared with unauthorized group of users in your organization. Select the users which whom sharing is forbidden.  
  
-   Sensitive file extension:  
    Receive an alert about files with specific extensions which are potentially highly-exposed. Select the specific extension (for example, crt for certificates) or filename and exclude those with private sharing level.  
  
 To create a new file policy, follow this procedure:  
  
1.  In the console, click on **Control** followed by **Policies**.  
  
2.  Click **Create policy** and select **File** policy.  
  
3.  Give your policy a name and description, if you want you can base it on a template, for more information on policy templates, see [Control cloud apps with policies](../migration/control-cloud-apps-with-policies.md).  
  
4.  Within **Risk type**, link the policy to the most appropriate risk type. This field is informative only and helps you search for specific policies and alerts later, based on risk type.  The risk may already be preselected according to the category for which you chose to create the policy. By default, File policies are set to DLP.  
  
5.  To set which discovered apps will trigger this policy, **Create a filter for the files this policy will act on**. Narrow down the policy filters until you reach the most accurate set of files you wish to act upon. Be as restrictive as possible in order to avoid false positives. For example, if you wish to remove public permissions, remember to add the “Public” filter, if you wish to remove an external user, use the “External” filter etc.  
  
6.  For Box, SharePoint, Dropbox, OneDrive, you can enforce your file policy over all files on the app or on specific folders. Under **Apply to**, select **selected folders** or **all files excluding selected folders**, you will be redirected to log on to the cloud app, and then add the relevant folders.  
  
7.  Select the **Content inspection method**. The built-in DLP allows you to filter files by their content. In order to scan files  for content, next select **Built-in DLP**. Once content inspection is enabled, you can choose to use preset expressions or to search for other customized expressions, either as a substring or a regular expression of your own.  
    In addition, you can specify a regular expression to exclude a file from the results. This is highly useful if you have an inner classification keyword standard that you want to exclude from the policy.  
    In addition, you can decide what is the minimum number of content violations that you want to match before the file is considered a violation. For example, you can choose 10 if you want to be alerted on files with at least 10 credit card numbers found within its content.  
    When content is matched against the selected expression, you can choose to mask the match itself from the violation notification and logs. Once checked, violation text will be replaced with “X” characters. Remember, numbers are replaced with “#” characters and never stored within [!INCLUDE[Adallom](../migration/includes/adallom_md.md)].  
  
8.  Choose the **Governance** actions you want [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] to take when a match is detected.  
  
9. Once you’ve created your policy, you can view it in the **File policy** tab. You can always edit a policy, calibrate its filters or change the automated actions.  
    The policy is automatically enabled upon creation and will start scanning your cloud files immediately.  
  
> [!NOTE]  
>  Take extra care when you set governance actions, they could lead to irreversible loss of access permissions to your files.  
> It is recommended to narrow down the filters to exactly represent the files that you wish to act upon, using multiple search fields. The narrower the filters, the better.  
>   
>  For guidance, you can use the **Edit and preview results** button in the Filters section.  
  
 ![file policy edit and preview results](../migration/media/file-policy-edit-and-preview-results.png "file policy edit and preview results")  
  
 10. To view file policy matches, files that are suspected to violate the policy, click **Control** and then **Policies**. Filter the results to display only the file policies using the **Type** filter at the top. For more information about the matches for each policy, click on a policy. This displays the Matching now files for the policy. Click the **History** tab to see a history back to up to 6 months of files that matched the policy.     
  
## File policy reference  
  This section provides reference details about policies, providing explanations for each policy type and the fields that can be configured for each policy. 
  
  A **File policy** is an API-based policy that enables you to control your organization's content in the cloud, taking into account over 20 file metadata filters (including owner and sharing level) as well as content inspection results. Based on the policy results, governance actions can be applied. The content inspection engine can be extended via 3rd-party DLP engines as well as anti-malware solutions.  
  
 Each policy is composed of the following parts:  
  
-   File filters – Enable you to create very granular conditions based on metadata.  
  
-   Content inspection – Enable you to narrow down the policy, based on DLP engine results.  
  
-   Actions – The policy provides a set of governance actions that can be automatically applied when violations are found.  These are divided into collaboration actions, security actions and investigation actions.

![file governance drop down](../migration/media/file-governance-drop-down.png)
  
-   Extensions  
  
    > [!NOTE]  
    >  Extensions are only available with the [!INCLUDE[Adallom](../migration/includes/adallom_md.md)] Technical Preview version.  
  
    -   Content inspection can be performed via 3rd-party engines for improved DLP or anti-malware capabilities.  
  
    -   Governance actions can be performed via 3rd-party engines for enforcing custom encryption control or other types of file processing (for example, custom water marking).  
  
## See Also  
 [Daily activities to protect your cloud environment](../migration/daily-activities-to-protect-your-cloud-environment.md)   
 [For technical support, please visit the Cloud App Security assisted support page.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
 [Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  