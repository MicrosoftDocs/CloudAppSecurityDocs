---
# Required metadata 
# For more information, see https://review.learn.microsoft.com/en-us/help/platform/learn-editor-add-metadata?branch=main
# For valid values of ms.service, ms.prod, and ms.topic, see https://review.learn.microsoft.com/en-us/help/platform/metadata-taxonomies?branch=main

title: 		 Connect Workplace      # Add a title for the browser tab
description: This article provides information about how to connect your Workplace app to Defender for Cloud Apps using the API connector for visibility and control over use. # Add a meaningful description for search results
author:      NagarajVenkatesh # GitHub alias
ms.author:   naven # Microsoft alias
ms.service:  # Add the ms.service or ms.prod value
# ms.prod:   # To use ms.prod, uncomment it and delete ms.service
ms.topic:    how-to# Add the ms.topic value
ms.date:     02/28/2023
---

# Connect Workplace to Microsoft Defender for Cloud Apps

[!INCLUDE [Banner for top of topics](includes/banner.md)]

This article provides instructions for connecting Microsoft Defender for Cloud Apps to your existing Workplace account using the App Connector APIs. This connection gives you visibility into and control over your organization's Workplace use.

## Prerequisites

- You must be signed-in as a system admin to Workplace by Meta. 
   
   > [!NOTE]
   > - A Workplace account can be connected to a single instance of Defender for Cloud Apps. Please make sure that your Workplace account is not connected to any other Defender for Cloud Apps instance.
      
## How to connect Workplace to Defender for Cloud Apps

1. In the [Defender for Cloud Apps portal](https://portal.cloudappsecurity.com/), select **Investigate** and then **Connected apps**.
1. In the **App connectors** page, select the plus button followed by **Workplace by Meta**.
1. In the pop-up, give the connector a descriptive name, and press **Connect Workplace by Meta**.
   ![Connect-Workplace](media/protect-servicenow/connect-workplace.jpg)

1. In the next screen, click **Connect Workplace by Meta**:
   ![Connect-Workplace-2](media/protect-servicenow/connect-workplace-2.jpg)

1. You'll be redirected to Workplace by Meta page. 
   [!NOTE]
   - Make sure you are logged into Workplace as System admin.
      
1. On Workplace authorization page, make sure to choose the correct organization from the dropdown.
    
1. In the app consent page, make sure to choose **All groups** and then click **Add to Workplace.**
   
   > [!NOTE]
   > - The first connection can take up to 4 hours to get all users and their activities.
   > - The activities that will show are the activities that were generated from the moment the connector is connected. 
   > - After the connector's **Status** is marked as **Connected**, the connector is live and works.
   
## Next steps

> [!div class="nextstepaction"]
> [Control cloud apps with policies](control-cloud-apps-with-policies.md)

[!INCLUDE [Open support ticket](includes/support.md)]


