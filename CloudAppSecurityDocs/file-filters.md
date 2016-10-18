---
# required metadata

title: Files | Microsoft Docs
description: This reference topic provides information about the types of files and file filters used by Cloud App Security.
keywords:
author: rkarlin
manager: mbaldwin
ms.date: 10/15/2016
ms.topic: article
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

# Files

###  <a name="Filefilters"></a> File filters 
 
 Cloud App Security can monitor any file type based on more than 20 metadata filters (for example, access level, file type). 
 
Cloud App Security's built in DLP engines perform content inspection by extracting text from common file types (PDF, Office files, RTF, HTML, code files, etc.).

Below is a list of the file filters that can be applied. Most filters support multiple values as well as NOT, in order to provide you with a very powerful tool for policy creation.  
> [!NOTE] When using the policy filters, **Contains**  will search only for full words – separated by comas, dots, spaces or underscores. For example if you search for **malware** or **virus**, it will find virus_malware_file.exe but it will not find malwarevirusfile.exe. If you search for **malware.exe** then you will find ALL files with either malware or exe in their filename, whereas if you search for **“malware.exe”** (with the quotation marks) you will find only files that contain exactly “malware.exe”.  **Equals** will search only for the complete string, for example if you search for **malware.exe** it will find malware.exe but not malware.exe.txt. 

   
 ![policy_file type filters](./media/policy_file-type-filters.png "policy_file type filters")  
  
-   Access level – Sharing access level; public, external, internal or private.  For more information about External files, see [General Setup, Set up the portal](Getting%20started%20with%20Cloud%20App%20Security.md)
Internal are any files within the Internal domains you set in [General setup](General%20setup.md)/. External are any files saved in locations that are not within the internal domains you set. Shared are files that have a sharing level above private, this includes internal sharing (files shared within your internal domains), external sharing (files shared in domains that are not listed in your internal domains, public with a link (files that can be shared with anyone via a link) and public (files that can be found by searching the Internet). 

     **NOTE:**  Files shared into your connected storage apps by external users are handled as follows by Cloud App Security:
    - **OneDrive:** OneDrive assigns an internal user as the owner of any file placed into your OneDrive by an external user. Because these files are then considered owned by your organization, Cloud App Security scans these files and applies policies as it does to any other file in your OneDrive.
     - **Google Drive:** Google Drive considers these as being owned by the external user, and because of legal restrictions on files and data that your organization does not own, Cloud App Security does not have access to these files.
    - **Box:** Because Box considers externally owned files to be private information, Box Global Admins cannot see the content of the files. For this reason, Cloud App Security does not have access to these files. 
    - **Dropbox:** Because Dropbox considers externally owned files to be private information, Box Global Admins cannot see the content of the files. For this reason, Cloud App Security does not have access to these files.

-   App – Search only for files within these apps.  
  
-   Collaborators – Include/exclude specific collaborator groups.  
  
    -   Any from domain – If any user from this domain has access to the file.  
  
    -   Entire domain – If the entire domain has access to the file.  
  
    -   Groups – If a specific group has access to the file. Groups can be imported from Active Directory, cloud apps or manually created in the service.  
  
    -   Users – Certain set of users that may have access to the file.  
  
-   Created  – File creation time. Filter supports before/after dates as well as date range.  
  
-   Last modified – File modification time. Filter supports before/after dates, date range and relative time expressions, for example, All files that were not modified in the last 6 months.  
  
-   Extension – Focus on specific file extensions, for example, all files that are executables (exe).  
  
-   File ID – Search for specific file IDs, this is an advanced feature that allows you to track certain high-value files without depending on their owner/location/name.  
  
-   File name – File name or sub string of the name as defined in the cloud app, for example, All files with a password in their name.  
  
-   File type – Cloud App Security takes both the MIME type received from the service and scans the file to determine the true file type. Note that this scan is for files that are relevant for data scan (documents, images, presentations, spreadsheets, text and zip/archive files). The filter works per file/folder type, for example, All folders that are ... or All spreadsheet files that are...


     ![policy_file filters trash](./media/policy_file-filters-trash.png "policy_file filters trash")  
  
-   In trash – Exclude/include files in the trash folder. These files may still be shared and pose a risk.  
  
-   MIME type – File MIME type check, accepts free text.  
  
-   Owner -Include/exclude specific file owners, for example, Track all files shared by rogue_employee_#100.  
  
-   Owner OU – Include/exclude file owners that belong to certain organizational group, for example, All public files except those shared by EMEA_marketing.  
  
-   Parent folder – Include/exclude based on parent folder, for example, All publicly shared files except for files in this folder.  
  
-   Quarantined – Is the file quarantined by the service, for example, Show me all files that are quarantined.  
  
 You can also set the policy to run on specific files by setting the **Apply to** filter to either All files, Selected folders or All files excluding selected folders, and then select the files or folders that are relevant.  
  
 ![apply to filter](./media/apply-to-filter.png "apply to filter")  
  
### Governance actions  
  
-   Notifications  
  
    -   Alerts – Alerts can be triggered in the system and propagated via email and text message, based on severity level.  
  
    -   User email notification – Email messages can be customized and will be sent to all violating file owners.  
  
    -   CC manager – Based on user directory integration, email notifications can also be sent to the manager of the person found to violate a policy.  
  
-   Notify specific users – Specific list of email addresses that will receive these notifications.  
  
-   Notify last file editor – Send notifications to the last person who modified the file.  
  
-   Governance actions in apps  
  
     Granular actions can be enforced per app, specific actions vary depending on app terminology.  
  
    -   Change sharing  
  
        -   Remove public sharing –  Allow access only to named collaborators, for example: Remove public access for Google Apps and Remove direct shared link for Box.  
  
        -   Remove external users – Allow access only to company users.  
  
        -   Make private – Only the owner can access the file, all shares are removed.  
  
        -   Remove a collaborator – Remove a specific collaborator from the file.  
  
    -   Quarantine  
  
        -   Put in user quarantine – Allow self-service by moving the file to a user controlled quarantine folder  
  
        -   Put in admin quarantine – File is moved to quarantine in the admin drive, and the admin has to approve it.  
  
-   Trash – Move the file to the trash folder.
  
 ![policy_create alerts](./media/policy_create-alerts.png "policy_create alerts")  
  
 
## See Also  
 [Daily activities to protect your cloud environment](daily-activities-to-protect-your-cloud-environment.md)   
 [For technical support, please visit the Cloud App Security assisted support page.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
 [Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  