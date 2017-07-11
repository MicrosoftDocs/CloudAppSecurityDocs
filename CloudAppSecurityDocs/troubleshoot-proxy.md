---
# required metadata

title: Troubleshooting issues with the Cloud App Security Proxy | Microsoft Docs
description: This topic provides troubleshooting information about the Cloud App Security Proxy.
keywords:
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 7/10/2017
ms.topic: article
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: f5a67b0b-94e9-4f36-b1b4-dbe04b2d6f53

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Troubleshooting the Cloud App Security Proxy

## Users are complaining that they cannot access the app when they should be able to

**Resolution:**

If this is a Managed device related policy, instruct the users to perform the
following steps:

1.  Verify that the user has a client certificate installed on her device

2.  Verify that that users accepts the client certificates request

3.  If a client certificate request does not appear:

    1.  Close all instances of the browser, open a new one and try again

    2.  Clear all cookies – and try again

    3.  Try using different browsers

    4.  If this is a MAC device, go to the keychain manager … TODO

If all of the above does not work, or it is not a Managed device policy, and you
want to perform immediate action before investigating, do one of the following:

1.  If you know the relevant policies

    1.  Exclude the relevant users from the policies

    2.  Disable the relevant policies

        1.  Under **Control** choose **Policies**

        2.  Find the relevant policies, and under the more option menu – choose
            **Disable**

2.  If you don’t know the exact policies, or you want to disable everything in a
    single place, disable the proxy capabilities for the relevant app

    1.  Under the settings cog choose Proxy

    2.  Find the relevant app in the table and in the more options menu – choose
        **Suspend…**

To investigate the reasons why a policy does not work properly, try playing with
the different filters and on different devices and configuration in order to
find the optimal configuration.

## Some pages do not look the same when using session control

**Resolution:** Try disabling 3rd party apps and reconnect to Salesforce.

## Session control does not look the same from my browser

**Resolution:** Make sure you are using a supported browser.



## See Also  
[Working with the Cloud App Security Proxy](proxy-intro.md)   
[For technical support, please visit the Cloud App Security assisted support page.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  