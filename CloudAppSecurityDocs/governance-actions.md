---
title: "Governance log"
ms.custom: na
ms.date: "10/11/2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
ms.assetid: 3536c0a5-fa56-4931-9534-cc7cc4b4dfb0
caps.latest.revision: 8
author: "Rkarlin"
ms.author: "rkarlin"
---
# Governance log
The Governance log provides a status record of each task that you set Cloud App Security to run, including both manual and automatic tasks. These tasks include tasks that you set in policies, governance actions that you set on files and users, and any other action you set Cloud App Security to take. The Governance log also provides information about the success or failure of these actions. You can choose to retry or revert some of the governance actions from the Governance log. 

The following is the full list of actions the Cloud App Security portal enables you to take. These are enabled in various places throughout the console as described in the **Location** column. Each governance action taken is listed in the Governance Log.
For information about how governance actions are treated when there are policy conflicts, see [Policy Conflicts](Control%20cloud%20apps%20with%20policies.md) 

**Location**|**Target object type**|**Governance action**|**Description**|**Related connectors** 
---------|---------|---------|---------|---------
|File Policy|File|Restrict to collaborators only|Only named collaborators can access the file.|Box|
|Settings> Cloud discovery settings |Cloud Discovery|Re-calculate Cloud Discovery scores|Recalculates the scores in the Cloud app catalog after a score metric change.|Discovery|
|Settings> Cloud discovery settings > Manage data views|Cloud Discovery|Create custom Cloud Discovery filter data view|Creates a new data view for a more granular view of the discovery results. For example, specific IP ranges.|Discovery|
|Discover > Discovered Apps/IP addresses/Users|Cloud Discovery|Export discovery data|Creates a CSV from the discovery data.|Discovery|
|Settings> Cloud discovery settings > Delete data|Cloud Discovery|Delete Cloud Discovery data|Deletes all the data collected from discovery sources.|Discovery|
|Settings> Cloud discovery settings > Upload logs manually/Upload logs automatically|Cloud Discovery|Parse Cloud Discovery data|Notification that all the log data was parsed.|Discovery|
|Investigate >Files and File policy|File|Grant read permission to domain|Grants read permissions for the file to the specified domain for your entire domain or a specific domain. This would be useful if you want to remove public access after granting access to the domain of people who need to work on it.|Google Apps|
|Investigate > Files|File|Grant read permissions to myself|Grants read permissions for the file for yourself so you can access the file and understand if it has a violation or not.|Google Apps|
|File policy and Activity policy|File, Activity|Notify user|Sends an email to users to notify them that something they did or a file they own violates a policy. You can add a custom notification to let them know what the violation was.|All|
|File policy and Investigate > Files|File|Remove editors' ability to share|In Google Drive, the default editor permissions of a file allow sharing as well. This governance action restricts this option and restricts file sharing to the owner.|Google Apps|
|Investigate > Files and File policy|File|Put in user quarantine|Removes all permissions from the file and moves the file to a quarantine folder under the user's root drive. This permits the user to review the file and move it. If it is manually moved back, the file sharing is not restored.|Box, One Drive, SharePoint|
|File policy and Investigate > Files|File|Put in admin quarantine|Removes any permissions from the file and moves the file to a quarantine folder under the user's root drive. This permits the admin to review the file and move it.|Box|
|Investigate > Files and File policy|File|Remove a collaborator|Removes a specific collaborator from a file.|Google Apps, Box, One Drive, SharePoint|
|Investigate >Files and File policy|File|Make private|Make the file private - no more collaborators or public links, not shared with anyone.|Google Apps, One Drive, SharePoint|
|Investigate >Files and File policy|File|Remove external users|Removes all external collaborators - outside the domains configured as internal in Settings.|Google Apps, Box |
|Accounts|File|Remove user's collaborations|Remove all the collaborations of a specific user for any files - good for people leaving the company.|Box, Google Apps|
|Investigate >Files and File policy|File|Remove public access|If a file was yours and you put it in public access, it becomes accessible only to anyone else configured with access to the file - depending on what kind of access the file had. |Google Apps|
|Investigate >Files and File policy|File|Remove direct shared link|Removes a link that is created for the file that is public but is only shared with specific people.|Box|
|App dashboard > App permissions|Permissions|Revoke app|This performs the same action that occurs when you go into Google Apps or Salesforce and under App Permissions, you revoke a third-party app's permissions to Google or Salesforce.|Google Apps, Salesforce, Office|
|Activity policy and Investigate > Accounts|File|Revoke password|Revokes the password for a user's account - for example,  setting an activity policy that revokes a password after 10 failed login attempts.|Google Apps|
|Activity policy and Investigate > Accounts|File|Revoke admin privileges|Revokes privileges for an admin account - for example, setting an activity policy that revokes admin privileges after 10 failed login attempts.|Google Apps|
|App dashboard > App permissions|Account|Revoke user from app|You can revoke specific users when clicking on the number under Users. The screen will display the specific users and you have can use the X to delete permissions for any user.|Google Apps, Office|
|Investigate > Files|File|Revoke read permissions form myself|Revokes read permissions for the file for yourself, useful after granting yourself permission to understand if a file has a violation or not.|Google Apps|
|Investigate >Accounts and Policies|Account|Suspend user|Sets user to have no access and no ability to log in - if they are logged in when you set this, they are immediately locked out.|Google Apps, Box, Office|
|Files page and Policies|File|Transfer file ownership|Changes the owner - in the policy you choose a specific owner.|Google Apps|
|Investigate >Accounts |File|Transfer all files ownership|On an account, you transfer one user's files to all be owned by a new person you select. The previous owner becomes an editor. After you transfer ownership, admin@gtest1.adallom.com will become an editor and will no longer be able to change sharing settings. The new owner will receive an email notification about the change of ownership.|Google Apps|
|File policy|File|Trash|Puts the file in the user's trash.|One Drive, SharePoint|
|Investigate >Accounts|Account|Unsuspend user|Unsuspends the user|Google Apps, Box, Office|
|Investigate > Files|File|Restore from user quarantine|Restores a user from being quarantined.|Box|
|Investigate >Accounts|Account|Account settings|Takes you to the account settings page in the specific app (for example, inside Salesforce).|All apps -One Drive and SharePoint settings are configured from within Office.|
|Investigate > Files|File|Allow editors to share|In Google Drive, the default editor permissions of a file allows sharing as well. This governance action is the opposite of Remove editor’s ability to share and enables the editor to share the file.|Google Apps|
|File Policy, Activity Policy|File, Activity|Notify last file editor|Sends an email to notify the last person who edited the file that it violates a policy.|Google Apps, Box|
|File Policy, Activity Policy|File, Activity|Notify file owner|Sends an email to the file owner with the option to cc their manager, when a file violates a policy. In Dropbox, if no owner is associated with a file, the notification will be sent to the specific user you set.|All apps|
|File Policy, Activity Policy|File, Activity|cc the owners manager|When the file owner receives an email notification that their file is in violation of a policy, this optionally notifies the manager of the file owner.|All apps except Service Now|
|File Policy, Activity Policy|File, Activity|Notify specific users|Sends an email to notify specific users about a file that violates a policy.|All apps|

