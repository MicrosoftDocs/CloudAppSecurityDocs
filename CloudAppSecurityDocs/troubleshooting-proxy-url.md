---
# required metadata

title: Troubleshooting - What is cas.ms?
description: This article provides information about the cas.ms URL suffix used by Conditional Access App Control.
keywords:
author: shsagir
ms.author: shsagir
manager: shsagir
ms.date: 03/08/2020
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.prod:
ms.service: cloud-app-security
ms.suite: ems
---
# Troubleshooting - What is cas.ms?

*Applies to: Microsoft Cloud App Security*

This article provides information about the `cas.ms` URL suffix used by Conditional Access App Control.

## Our system flagged a new DNS entry or generated certificate for *.cas.ms, but we don't use Cloud App Security

This is normal behavior and results from Cloud App Security protecting your environment. Even if your organization does not use Cloud App Security, when someone visits your site or service from an environment that does, their URLs are rewritten to protect their access.

For example, Contoso protects its environment using Conditional Access App Control provided by Cloud App Security. When a Contoso user visits `fabrikam.com`, the user is automatically redirected to `fabrikam.com.<region>.cas.ms`. As a result, Fabrikam's phishing team will see a new DNS entry and certificate for `fabrikam.com.<region>.cas.ms`.

So even though Fabrikam does not actually use Cloud App Security, they see the DNS entry or certificate because Contoso does.

## Here's why you see *.cas.ms in your URL

First of all, you have not been phished! This kind of URL is expected and indicates that your organization applies additional security controls to protect business-critical data.

They do this by using Cloud App Security, a solution for protecting your organization's cloud environment, to replace all relevant URLs and cookies relating to cloud apps that your use.

So when you try accessing a cloud app such as Salesforce, SharePoint Online, or AWS, you will notice that its URL is suffixed with `*.cas.ms`. For example, when using the XYZ app, the URL you're used to seeing changes from `XYZ.com` to `XYZ.com.us.cas.ms`.

If the URL does not exactly match the replacement pattern (for example, `<app_site>.com` is not replaced with `<app_site>.com.*.cas.ms`), or if you have additional concerns, contact your IT department.
