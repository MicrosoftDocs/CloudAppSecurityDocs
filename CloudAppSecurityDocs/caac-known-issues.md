---
title: Conditional Access app control known limitations | Microsoft Defender for Cloud Apps
description: Learn about known limitations for working with Microsoft Defender for Cloud Apps Conditional Access app control.
ms.date: 01/23/2024
ms.topic: how-to
---

# Conditional Access app control known limitations

This article describes known limitations for working with Microsoft Defender for Cloud Apps Conditional Access app control.

To learn more about security limitations, contact our support team.

## Maximum file size for session policies

Session policies can be applied on files with a maximum size of 50 MB. For example, this maximum file size is relevant when you're defining policies to monitor file downloads from OneDrive, block file updates, or block downloads or uploads of malware files.

In cases such as these, make sure to cover files that are larger than 50 MB using the tenant settings to determine whether the file is allowed or blocked, regardless of any matching policies.

In Microsoft Defender XDR, select **Settings > Conditional Access App Control > Default behavior** to manage settings for files of over 50 MB.

## Maximum file size for session policies based on information protection content inspection

When a session policy to block file uploads or downloads based on information protection content inspection is applied, inspection is performed on only files smaller than 30 MB and with fewer than 1 million characters.

For example, you might define one of the following session policies:

  - Block file upload for files containing Social Security Number (SSN)
  - Protect file download for files containing PHI (Protected Health Information)
  - Block file download for with sensitivity label “very sensitive”

In such cases, files larger than 30 MB or with more than 1 million characters aren't scanned. These files are treated according to the **Always apply the selected action even if the data cannot be scanned** policy setting.

The following table lists more examples of files that are and aren't scanned:

|File description  |Scanned / Not scanned  |
|---------|---------|
|**A TXT file**, 1-MB size and 1 million characters     |  Scanned       |
|**A TXT file**, 2-MB size and 2 million characters     |   Not scanned      |
|**A Word file** composed of images and text, 4-MB size and 400-K characters     |  Scanned       |
|**A Word file** composed of images and text, 4-MB size and 2 million characters     |  Not scanned        |
|**A Word file** composed of images and text, 40-MB size and 400-K characters     |  Not scanned         |

## Files encrypted by sensitivity labels are not supported
For tenants that enable co-authoring for files encrypted with sensitivity labels:
A session policy to block file uploads\download that relies on label filters or file content will operate based on the policy settings of ‘Always apply the selected action even if data cannot be scanned’, in case of file with encrypted sensitivity label.

For example:
When a session policy is configured to prevent downloading files that contain credit card numbers and set to ‘Always apply the selected action even if data cannot be scanned’:
Any file with an encrypted sensitivity label will be blocked from downloading, regardless of its content. 

## External B2B users in Teams

External B2B collaboration users are not protected by session policies in Teams application.

## Limitations for sessions served by reverse proxy

This section lists limitations that apply only on sessions that are served by the reverse proxy. Users of Microsoft Edge can benefit from in-browser protection instead of using the reverse proxy, and therefore aren't affected by these limitations.

### Built-in app and browser plug-in limitations

Defender for Cloud Apps Conditional Access app control modifies underlying application code and therefore doesn't currently support built-in apps or browser extensions.

As an administrator, you might want to define default system behavior for when a policy can't be enforced, choosing to either allow access or totally block it.

### Context loss limitations

In the following applications, we encountered scenarios where navigating to a link might result in loss of the full path of the link and typically the user lands on the home page of the app:

- ArcGIS
- GitHub
- Microsoft Power Automate
- Microsoft Power Apps
- Workplace from Meta
- ServiceNow
- Workday

### File upload limitations

If a session policy to block or monitor the upload of sensitive files is applied, then in the following scenarios the user's attempts to upload files or folders using **drag & drop** blocks the complete list of files and folders:

- A folder that contains at least one file and at least one subfolder
- A folder that contains multiple subfolders
- A selection of at least one file and at least one folder
- A selection of multiple folders

The following table lists example results when the *Block upload of files containing PII to OneDrive* policy is defined:

|Scenario  |Result  |
|---------|---------|
|A user tries to upload a selection of 200 nonsensitive files using drag and drop.     |   Files are blocked       |
|A user tries to upload a selection of 200 files, some are sensitive, and some aren't, using the file upload dialog.     |   Mon-sensitive files are uploaded <br><br>Sensitive files are blocked      |
|A user tries to upload a selection of 200 files, some are sensitive, and some aren't, using drag and drop.     |   The full set of files is blocked      |

## Related content

- [Microsoft Defender for Cloud Apps Conditional Access app control](proxy-intro-aad.md)
