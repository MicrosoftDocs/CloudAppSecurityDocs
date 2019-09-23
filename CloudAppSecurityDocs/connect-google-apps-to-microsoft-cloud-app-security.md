---
# required metadata

title: Connect G Suite to Cloud App Security
description: This article provides information about how to connect your G Suite to Cloud App Security using the API connector for visibility and control over use.
keywords:
author: shsagir
ms.author: shsagir
manager: shsagir
ms.date: 6/17/2019
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: b938e1e0-356d-4cc6-ba4a-862c0c59d709

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: seodec18

---
# Connect G Suite to Microsoft Cloud App Security

*Applies to: Microsoft Cloud App Security*

This article provides instructions for connecting Microsoft Cloud App Security to your existing G Suite account using the connector APIs. This connection gives you visibility into and control over G Suite use. 
    
## Configure G Suite  
  
1. As a G Suite Super Admin, sign in to <a href="https://cloud.google.com/console/project" target="_blank">https://cloud.google.com/console/project</a>.  
  
2. Click **Create project** to start a new project.  
  
    ![google1](./media/google1.png "google1")  
  
3. In the **New project** screen, name your project as follows:</br>
   **Cloud App Security** and click **Create**.  
          ![google2](./media/google2.png "google2")  
  
4. After the project is created, in the tool bar, click on **Google Cloud Platform**. Make sure that the right project is selected in the drop-down at the top.
       
      ![google project](./media/googleverify-project.png "googleverify project")  

5. Under **APIs**, click **Go to API's overview**.  
  
     ![google3](./media/google3.png "google3")  
   
6. Click on **Library** and enable the following APIs (use the search line if the API isn't listed in the **Popular APIs** list):  

   -   Admin SDK  
  
   -   Audit API
  
   -   Google Drive API
  
   -   G Suite Marketplace SDK

   ![google apis](./media/google4.png "google4")  
  
   > [!NOTE]  
   >  Ignore the **Credentials** warning for now.  

7. Click on Enable for each API.
     ![enable Google APPI](./media/google-api.png "google-api")  
8. Make sure you have the following APIs enabled:
  
     ![google enabled apis](./media/google5.png "google5")  
  
9. Click **Credentials** and then select the **OAuth consent screen** tab.
  
    - In **Product name shown to users**, type **Microsoft Cloud App Security**.  
  
    - All other fields are optional.  
  
    - Click **Save**.  
  
      ![Google oauth consent](./media/google-oauth-consent.png "google oauth conesent")  
  
10. In the **Credentials** tab, click the arrow next to **Create credentials**.  
  
     ![Google credentials](./media/google7.png "google7")  

11. Select **Service account key**.

     ![Google service account key](./media/google8.png "google8")  
  
12. Under **Create service account key**, choose **New service account**, and type any name, for example **Service account 1**. Under **Role**, choose **Project** and then **Editor**. Under **Key type**, choose **P12** and click **Create**. A P12 certificate file is saved to your computer.
 
     ![Create service account key in Google](./media/google9.png "google9")  
  
13. Copy the **Service account ID** assigned to your service - you need it later.
        
14. In the **Credentials** screen, click **Manage service accounts** in the far right.  
     
    ![G Suite credentials service account](./media/google10.png "G Suite credentials service account")  
  
15. Click the three dots to the right of the service account you created and select **Edit**.  
  
     ![google edit](./media/google11.png "google edit")  
  
16. Click **VIEW DOMAIN WIDE DELEGATION CLIENT ID**.
  
     ![google client ID](./media/google12.png "google12") 

    -   Copy the **Client ID** - you need it later.

    -   Go to [admin.google.com](https://admin.google.com/) and then choose **Security**.

    -   Select **Show more** and then choose **Advanced settings**.

    -   In the **Authentication** section, select **Manage API client access**.

    -   In the **Client Name** box, enter the **Client ID** that you copied earlier.

          ![manage api client access](./media/google12-2.png "google12-2")

    -   In the **One or More API Scopes** box, enter the following list of required scopes (copy the text and paste it in the box):

        `https://www.googleapis.com/auth/admin.reports.audit.readonly,https://www.googleapis.com/auth/admin.reports.usage.readonly,https://www.googleapis.com/auth/drive,https://www.googleapis.com/auth/drive.appdata,https://www.googleapis.com/auth/drive.apps.readonly,https://www.googleapis.com/auth/drive.file,https://www.googleapis.com/auth/drive.metadata.readonly,https://www.googleapis.com/auth/drive.readonly,https://www.googleapis.com/auth/drive.scripts,https://www.googleapis.com/auth/admin.directory.user.readonly,https://www.googleapis.com/auth/admin.directory.user.security,https://www.googleapis.com/auth/admin.directory.user.alias,https://www.googleapis.com/auth/admin.directory.orgunit,https://www.googleapis.com/auth/admin.directory.notifications,https://www.googleapis.com/auth/admin.directory.group.member,https://www.googleapis.com/auth/admin.directory.group,https://www.googleapis.com/auth/admin.directory.device.mobile.action,https://www.googleapis.com/auth/admin.directory.device.mobile,https://www.googleapis.com/auth/admin.directory.user`

    -    Click **Authorize**.

17. Open the Google menu by clicking the three horizontal lines next to Google Cloud Platform in the title bar. Click on **Google Cloud Platform** and then click the **APIs and services** tab in the left-menu.  

18. In the Dashboard that opens, scroll down to the list of enabled APIs and click on **Google Drive API**.
       ![Select Google Drive](./media/google14.png "google14")  

19. Click on the **Drive UI Integration** tab and fill in the following information:

    - **Application Name**: Microsoft Cloud App Security.  
  
    - **Short Description & Long Description** (optional): Microsoft Cloud App Security provides you with visibility into cloud applications, helping you control, investigate, and govern cloud application use; secure corporate data; and detect suspicious activities for any cloud application.  
  
    - Google requires you to upload at least one application Icon. Go to [https://go.microsoft.com/fwlink/?linkid=862826](https://go.microsoft.com/fwlink/?linkid=862826) to download a zip file containing Cloud App Security icons. Then, under **Application icon**, click **Select** next to the 128x128 image and drag it to the popup screen. Click **Select** next to the 32x32 image and drag it to the popup screen.  
  
    - Scroll down and in the **Drive Integration** section, type the following URL under **Open URL:**  
  
       https://portal.cloudappsecurity.com/#/services/11770?tab=files  
    
      ![Edit Google Drive](./media/google15.png "google15")  

20. Click **Save changes**.

21. Go back to the **Enabled APIs** list. Click **G Suite Marketplace SDK**. 
      
22. Select the **Configuration** tab. 
  
    -   Copy the **Project number (App ID)** that appears at the top to use later.  
  
    -   Under **Application Name** type **Microsoft Cloud App Security**.
  
         In **Application description** type "Microsoft Cloud App Security provides visibility into cloud apps, helping you control, investigate, and govern cloud app use; secure corporate data; and detect suspicious activities for any cloud app." 
    - Make sure to click **Done** in the **New item** window.      
     
       ![google new item](./media/google-new-item.png "google new item")  

    -   Uncheck the **Enable individual install** check box.  
  
    -   Configure the four required images under **Application icons**.  
  
         The images can be found at:  [https://go.microsoft.com/fwlink/?linkid=862826](https://go.microsoft.com/fwlink/?linkid=862826)  
  
    -   Fill in the following **Support URLs**:  
  
        -   **Terms of service URL**: https://go.microsoft.com/fwlink/?LinkID=733268  
  
        -   **Privacy policy URL**: https://go.microsoft.com/fwlink/?LinkId=512132  
  
    -   Under **OAuth 2.0 scopes**, copy and paste the following URLs (copy them one at a time and press Enter after each one):  
  
           https://www.googleapis.com/auth/admin.reports.audit.readonly  
  
           https://www.googleapis.com/auth/admin.reports.usage.readonly  
  
           https://www.googleapis.com/auth/drive  
  
           https://www.googleapis.com/auth/drive.appdata  
  
           https://www.googleapis.com/auth/drive.apps.readonly  
  
           https://www.googleapis.com/auth/drive.file  
  
           https://www.googleapis.com/auth/drive.metadata.readonly  
  
           https://www.googleapis.com/auth/drive.readonly  
  
           https://www.googleapis.com/auth/drive.scripts  
  
           https://www.googleapis.com/auth/admin.directory.user.readonly  
  
           https://www.googleapis.com/auth/admin.directory.user.security  
  
           https://www.googleapis.com/auth/admin.directory.user.alias  
  
           https://www.googleapis.com/auth/admin.directory.orgunit  
  
           https://www.googleapis.com/auth/admin.directory.notifications  
  
           https://www.googleapis.com/auth/admin.directory.group.member  
  
           https://www.googleapis.com/auth/admin.directory.group  
  
           https://www.googleapis.com/auth/admin.directory.device.mobile.action  
  
           https://www.googleapis.com/auth/admin.directory.device.mobile  
  
           https://www.googleapis.com/auth/admin.directory.user  

    -   Under **Visibility**, select **My domain** (not public). 
    -   Click on **Save Changes**.  
        ![google visibility](./media/google-visibility.png "google visibility")  
23. Go to [admin.google.com](https://admin.google.com/) and then choose **Security**.
   
      ![google security](./media/googlesec.png "google security")  
 
24. Choose **API reference**.  
       ![google api enable](./media/googleapi.png "google api")  
      
25. Select **Enable API Access** and click **Save changes**.  
  
    ![google api reference](./media/googleapiref.png "google8")  

  
## Configure Cloud App Security  
  
1.  In the Cloud App Security portal, click **Investigate** and then **Connected apps**.  
  
2.  In the **Connected apps** page, click the plus sign and select **G Suite**.  
       
  
3.  In the pop-up, fill in the following information:  
  
     ![G Suite Configuration in Cloud App Security](./media/gsuite-config-cas.png "G Suite Configuration in Cloud App Security")  
  
    1.  **Service account ID** that you copied in step 13.  
  
    2.  **Project number (App ID)** that you copied in step 22.  
  
    3.  Upload the **Certificate** P12 that you saved in step 12. You need the password you saved to do this.  
  
    4.  Enter one **admin account email** of your G Suite admin.  
  
    5.  If you have a G Suite Business or Enterprise account, check this check box. For information about which features are available in Cloud App Security for G Suite Business or Enterprise, see [Enable instant visibility, protection, and governance actions for your apps](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md).  
  
    6.  Click **Save settings**.  
  
    7.  **Follow the link** to connect to G Suite. This opens G Suite and you're asked to authorize access for Cloud App Security.  
         
    8.  Make sure the connection succeeded by clicking **Test now**.  
  
         Testing may take a couple of minutes.  
  
         After receiving a success notice, click **Done** and close the G Suite page.  
  
  
After connecting G Suite, you'll receive events for 60 days prior to connection.
  
After connecting G Suite, Cloud App Security performs a full scan. Depending on how many files and users you have, completing the full scan can take awhile. To enable near real-time scanning, files on which activity is detected are moved to the beginning of the scan queue. For example, a file that is edited, updated, or shared is scanned right away. This doesn't apply to files that aren't inherently modified. For example, files that are viewed, previewed, printed, or exported are scanned during the regular scan.
  
  
## Next steps 
[Control cloud apps with policies](control-cloud-apps-with-policies.md)   

[Premier customers can also create a new support request directly in the Premier Portal.](https://premier.microsoft.com/)  
  
  
