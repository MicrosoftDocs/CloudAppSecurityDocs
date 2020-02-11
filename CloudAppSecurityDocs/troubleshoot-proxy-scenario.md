---
# required metadata

title: Troubleshoot Conditional Access App Control issues
description: This article provides a list of possible Conditional Access App Control issues and provides possible resolutions.
keywords:
author: shsagir
ms.author: shsagir
manager: shsagir
ms.date: 6/30/2019
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.prod:
ms.service: cloud-app-security
ms.suite: ems
---
# Troubleshooting Conditional Access App Control issues

*Applies to: Microsoft Cloud App Security*

This article provides a list of possible Conditional Access App Control issues and provides possible resolutions.

## Our system flagged a new DNS entry or generated a certificate for *.cas.ms, but we don’t use Microsoft Cloud App Security

This is normal behavior and results from Cloud App Security protecting your environment. Even if your organization is not using Cloud App Security, when someone visits your site or service from an environment protected by Cloud App Security's Conditional Access App Control, their URLs are rewritten to protect their access.

For example, when a user at Contoso, a company protected by Cloud App Security, visits fabrikam.com, the user is automatically redirected to fabrikam.com.us.cas.ms. As a result, Fabrikam's phishing team will see a new DNS entry and certificate for fabrikam.com.us.cas.ms.

From this example you can see that even though Fabrikam does not actually use Cloud App Security, because Contoso does, the DNS entry and certificate are created.

**//TBD[ALEX]: ??? HOW TO RESOLVE? Contact MS? Add exceptions? ???**

## I see *.cas.ms in my URL. Have I been phished?

First of all, you have not been phished! This kind of URL is expected and indicates that your organization applies additional security controls to protect business-critical data.

They do this by ...

When you try accessing a cloud apps such as Salesforce, SharePoint Online, or AWS, you will notice that the URL is suffixed with `*.cas.ms`. For example, when using the XYZ app, the URL you're used to seeing will have changes  from `XYZ.com` to `XYZ.com.us.cas.ms`.

If the URL does not exactly match the replacement pattern (for example, redirecting *.com to *.com.*.cas.ms), or if you have additional concerns, please contact your IT department.
