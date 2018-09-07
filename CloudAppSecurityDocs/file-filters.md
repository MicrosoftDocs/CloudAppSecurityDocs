---
# required metadata

title: Understanding file data and filters available in Cloud App Security | Microsoft Docs
description: This reference topic provides information about the types of files and file filters used by Cloud App Security.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 7/2/2018
ms.topic: conceptual
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: cadcd6db-05b2-4974-91fe-cfac3d57aecd

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

# Files


To provide data protection, Microsoft Cloud App Security gives you visibility into all the files from your connected apps. After you connect Microsoft Cloud App Security to an app using the App connector, Microsoft Cloud App Security scans all the files, for example all the files stored in OneDrive and Salesforce. Then, Cloud App Security rescans each file every time it’s modified – the modification can be to content, metadata or sharing permissions. Scanning times depend on the number of files stored in your app. You can also use the **Files** page to filter files to investigate what kind of data is saved in your cloud apps. 

For example, you can use the **Files** page to secure externally shared files labeled as **confidential**, as follows:
After you connect an app to Cloud App Security, you can integrate with Azure Information Protection. Then, in the **Files** page, filter for files labeled **confidential**. If you see that there are **confidential** files that are shared outside your organization by filtering the **Collaborators** filter to exclude your domain, you can create a file policy that detects **confidential** files that have incorrect access levels applied to them and apply automatic governance actions to them, such as **Remove external collaborators** and **Send policy-match digest to file owner** to prevent data loss to your organization.

 ![File filter confidential](media/file-filter-confidential.png)

Here's another example of how you can utilize the **Files** page. To make sure you no one in your organization is publicly or externally sharing files that haven't been modified in the last 6 months:
After you connect an app to Cloud App Security, in the **Files** page, filter for files whose access level is **External** or **Public** and set the **Last modified** date to 6 months ago. You can create a file policy that detects thest stale public files by clicking **New policy from search** and apply automatic governance actions to them, such as **Remove external users** to prevent data loss to your organization.

 ![File filter stale external](media/file-example-stale-external.png)

The basic filter provides you with great tools to get started filtering your files.

 ![basic file log filter](media/file-log-filter-basic.png)

To drill down into more specific files, you can expand the basic filter by clicking Advanced.

 ![advanced file log filter](media/file-log-filter-advanced.png)
 
###  <a name="Filefilters"></a> File filters 
 
Cloud App Security can monitor any file type based on more than 20 metadata filters (for example, access level, file type). 
 
Cloud App Security's built in DLP engines perform content inspection by extracting text from common file types (PDF, Office files, RTF, HTML, code files, etc.).

Below is a list of the file filters that can be applied. Most filters support multiple values as well as NOT, in order to provide you with a very powerful tool for policy creation.  
> [!NOTE]
> When using the file policy filters, **Contains**  will search only for **full words** – separated by comas, dots, spaces or underscores to search. 
> - Spaces between words function like OR, for example, if you search for **malware** **virus** it will find all files with either malware or virus in the name, so it will find both malware-virus.exe and virus.exe.  
> - If you want to search for a string, enclose the words in quotation marks. This functions like AND, for example: if you search for **"malware"** **"virus"**, it will find virus_malware_file.exe but it will not find malwarevirusfile.exe and it will not find malware.exe. However, it will search for the exact string. If you search for **"malware virus"** it will not find **"virus"** or **"virus_malware"**.
> 
> **Equals** will search only for the complete string, for example if you search for **malware.exe** it will find malware.exe but not malware.exe.txt. 

-   Access level – Sharing access level; public, external, internal or private.  For more information about External files, see [General Setup, Set up the portal](getting-started-with-cloud-app-security.md)
    - Internal are any files within the Internal domains you set in [General setup](General-setup.md). 
    - External are any files saved in locations that are not within the internal domains you set. 
    - Shared are files that have a sharing level above private, this includes internal sharing (files shared within your internal domains), external sharing (files shared in domains that are not listed in your internal domains, public with a link (files that can be shared with anyone via a link) and public (files that can be found by searching the Internet). 

> [!NOTE]
>  Files shared into your connected storage apps by external users are handled as follows by Cloud App Security:
> - **OneDrive:** OneDrive assigns an internal user as the owner of any file placed into your OneDrive by an external user. Because these files are then considered owned by your organization, Cloud App Security scans these files and applies policies as it does to any other file in your OneDrive.
> - **Google Drive:** Google Drive considers these as being owned by the external user, and because of legal restrictions on files and data that your organization does not own, Cloud App Security does not have access to these files.
> - **Box:** Because Box considers externally owned files to be private information, Box Global Admins cannot see the content of the files. For this reason, Cloud App Security does not have access to these files. 
> - **Dropbox:** Because Dropbox considers externally owned files to be private information, Dropbox Global Admins cannot see the content of the files. For this reason, Cloud App Security does not have access to these files.

-   App – Search only for files within these apps.  
  
-   Collaborators – Include/exclude specific collaborator groups.  
  
    -   Any from domain – If any user from this domain has access to the file.  
  
    -   Entire domain – If the entire domain has access to the file.  
  
    -   Groups – If a specific group has access to the file. Groups can be imported from Active Directory, cloud apps or manually created in the service.  
  
    -   Users – Certain set of users that may have access to the file.  
  
-   Created  – File creation time. Filter supports before/after dates as well as date range.  
  
-   Extension – Focus on specific file extensions, for example, all files that are executables (exe).  
  
-   File ID – Search for specific file IDs, this is an advanced feature that allows you to track certain high-value files without depending on their owner/location/name.  
  
-   File name – File name or sub string of the name as defined in the cloud app, for example, all files with a password in their name.   
  
-   Classification label - Search for files with specific tags set. These are either:
    - Azure Information Protection tags. This requires integration with Azure Information Protection.
    - Cloud App Security tags. now provides more insight into the files it scans. For each file scanned by Cloud App Security DLP, you can now know if the files were blocked from being inspected because they were encrypted or corrupted. For instance, you can set up policies to alert and quarantine password protected files that are shared externally, as follows: 
        - Azure RMS encrypted – files whose content was not inspected because they have an Azure RMS encryption set.
        - Password encrypted – files whose content was not inspected because they are password protected by the user.
        - Corrupt file – files whose content was not inspected because their content could not be read.

-   File type – Cloud App Security takes both the MIME type received from the service and scans the file to determine the true file type. Note that this scan is for files that are relevant for data scan (documents, images, presentations, spreadsheets, text and zip/archive files). The filter works per file/folder type, for example, All folders that are ... or All spreadsheet files that are...


 ![policy_file filters trash](./media/policy_file-filters-trash.png "policy_file filters trash")  

  
-   In trash – Exclude/include files in the trash folder. These files may still be shared and pose a risk.  
  
-   Last modified – File modification time. Filter supports before/after dates, date range and relative time expressions, for example, all files that were not modified in the last 6 months.  

-   Matched policy - Files that are matched by an active Cloud App Security policy.

-   MIME type – File MIME type check, accepts free text.  
  
-   Owner -Include/exclude specific file owners, for example, Track all files shared by rogue_employee_#100.  
  
-   Owner OU – Include/exclude file owners that belong to certain organizational group, for example, All public files except those shared by EMEA_marketing.  
  
-   Parent folder – Include/exclude based on parent folder, for example, All publicly shared files except for files in this folder.  
  
-   Quarantined – Is the file quarantined by the service, for example, Show me all files that are quarantined.  
  
You can also set the policy to run on specific files by setting the **Apply to** filter to either All files, Selected folders or All files excluding selected folders, and then select the files or folders that are relevant.  
  
![apply to filter](./media/apply-to-filter.png "apply to filter")  
  
>[!NOTE]
> If at any point you want to clear the filters, you can do so by clicking the clear filters icon ![clear filters icon](./media/clear-filters.png).

## Working with the File drawer

You can view more information about each file, by clicking on the File itself in the File log. This opens the File drawer which provides the following additional actions you can take on the file:

- URL: Takes you to the file location.
- File identifiers: Clicking on File identifiers opens a pop-up with raw data details about the file including file ID and encryption keys.
- Owner:  Click on the owner to view the user page for the owner of this file.
- Matched policies: Click on the Matched policies link to see a list of policies this file matched.
- Classification label: Click on the Classification label to view the list of Azure Information Protection classification labels found in this file. You can then filter by all files matching this label.    

The fields in the File drawer provide contextual links to additional files and drill downs you may want to perform from the drawer directly. For example, if you move your cursor next to the **Owner** field, you can use the add to filter icon ![add to filter](./media/add-to-filter-icon.png) to add the owner immediately to the filter of the current page. You can also use the settings cog icon ![settings icon](./media/contextual-settings-icon.png) that pops up to arrive directly at the settings page necessary to modify the configuration of one of the fields, such as **Classification labels**.


![File drawer](./media/file-drawer.png "File drawer")  
  
For a list of governance actions available, see [File governance actions](governance-actions.md#file-governance-actions).

## See Also  
[Daily activities to protect your cloud environment](daily-activities-to-protect-your-cloud-environment.md)   

[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  
