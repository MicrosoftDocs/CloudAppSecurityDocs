---
# required metadata

title: Set email notification preferences | Microsoft Docs
description: This article provides information about how to personalize the email notifications sent by Cloud App Security.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 5/29/2018
ms.topic: conceptual
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: 8402cdc9-4969-4150-b567-ccc9d75e5370

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


##  <a name="mailsettings"></a> Set email notification preferences  

To set parameters for email notifications sent from Microsoft Cloud App Security to administrators requesting alerts, and notifications sent to end users about breaches in which they are involved, follow this procedure. For information about the Microsoft Cloud App Security email server IP address that you should whitelist in your anti-spam service, see [Network requirements](network-requirements.md). 


1. In the menu bar, click the settings cog ![settings icon](./media/settings-icon.png "settings icon") and select **Settings**, and then select the **Mail settings** tab.  

   ![mail settings](./media/mail-settings-config.png)

2. Under **Email sender identity**: If you are planning to use the default email settings, you don't need to change anything in this section. If you want to customize the email sender identity, you can set any of the settings here to customize the field you want to change. You can change any or all of the following: **From display name**, **From email address**, **Reply-to email address**. Microsoft Cloud App Security accomplishes this for you by using a third-party mail service called MailChimp®. Make sure you review and accept MailChimp's Terms of Service and Privacy Statement in order to enable this - otherwise Microsoft Cloud App Security will send the notifications using the default settings.
   
   > [!NOTE]
   > Only unicode characters are supported in the display name and the email address according to the [rfc822 standard](http://www.rfc-editor.org/rfc/rfc822.txt).

  
3. For the **Email design**, you can use an html file to customize and design the email messages sent from the system. The html file used for your template should include the following:  
  
   -   All template CSS files should be inline in the template.  
  
   -   The template should have three un-editable placeholders:  
  
        %%logo%% - a URL to your company's logo that was uploaded in the General setting page  
  
        %%title%% - a placeholder for the title of the email, as set by the policy.  

        %%content%% - a placeholder for the content that will be included for end users, as set by the policy.  
     
4. Click **Upload a template...** and select the file you created. 

5. Then, click **Send a test email** to send yourself a test email to see an example of the template you created. The email will be sent to the account you used to log into the portal. In the test email you will be able to see the metadata fields, the template, the email subject, the title in the email body and the content.  The following is a sample email template: 



```html
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
  <html>  
       <head>  
            <meta http-equiv="Content-Type" content="text/html; charset=UTF-8"/>  
            <meta name="viewport" content="width=device-width, initial-scale=1.0"/>  
          </head>  
          <body class="end-user">  
          <table border="0" cellpadding="20%" cellspacing="0" width="100%" id="background-table">  
            <tr>  
              <td align="center">  
                <!--[if (gte mso 9)|(IE)]>  
                <table width="600" align="center" cellpadding="0" cellspacing="0" border="0">  
                  <tr>  
                    <td>  
                <![endif]-->  
                <table bgcolor="#ffffff" align="center" border="0" cellpadding="0" cellspacing="0" style="padding-bottom: 40px;" id="container-table">  
                  <tr>  
                    <td align="right" id="header-table-cell">  
                      <img src="%%logo%%" alt="Microsoft Cloud App Security" id="org-logo" />  
                    </td>  
                  </tr>  
                  <tr>  
                    <td style="padding-top: 58px;" align="center" valign="top">  
                      <table width="100%" cellpadding="12">  
                        <tr>  
                          <td align="center" class="round-title">  
                            %%title%%  
                          </td>  
                        </tr>  
                      </table>  
                    </td>  
                  </tr>  
                  <tr>  
                    <td style="padding: 0 40px 79px 40px;" class="content-table-cell" align="left" valign="top">  
                        %%content%%  
                    </td>  
                  </tr>  
                  <tr>  
                    <td class="last-row"></td>  
                  </tr>  
                </table>  
                <!--[if (gte mso 9)|(IE)]>  
                </td>  
                </tr>  
                </table>  
                  <![endif]-->  
              </td>  
              </tr>  
          </table>  
            </body>  
          </html>  
   ```
  

  
  

  
    
## See Also  
[Set up Cloud Discovery](set-up-cloud-discovery.md)   

[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  