---
title: Troubleshooting - What is cas.ms, mcas.ms, or mcas-gov.us?
description: This article provides information about the cas.ms, mcas.ms, or mcas-gov.us URL suffix used by Conditional Access App Control.
ms.date: 11/09/2021
ms.topic: conceptual
---
# Troubleshooting - What is `*.cas.ms`, `*.mcas.ms`, or `*.mcas-gov.us`?

[!INCLUDE [Banner for top of topics](includes/banner.md)]

This article provides information about the `cas.ms`, `mcas.ms`, and `mcas-gov.us` URL suffixes used by Conditional Access App Control.

## Our system flagged a new DNS entry or generated certificate for `*.cas.ms`, `*.mcas.ms`, or `*.mcas-gov.us`, but we don't use Defender for Cloud Apps

This is normal behavior and results from Defender for Cloud Apps protecting your environment. Even if your organization does not use Defender for Cloud Apps, when someone visits your site or service from an environment that does, their URLs are rewritten to protect their access.

For example, Contoso protects its environment using Conditional Access App Control provided by Defender for Cloud Apps. When a Contoso user visits `fabrikam.com`, the user is automatically redirected to `fabrikam.com.cas.ms`. As a result, Fabrikam's phishing team will see a new DNS entry and certificate for `fabrikam.com.cas.ms`.

So even though Fabrikam does not actually use Defender for Cloud Apps, they see the DNS entry or certificate because Contoso does.

> [!NOTE]
> You may also see the following domains in the transparency logs:
>
> - `*.admin-rs-mcas.ms`
> - `*.rs-mcas.ms`
> - `*.admin-rs2-mcas.ms`
> - `*.rs2-mcas.ms`
> - `*.admin-mcas.ms`
> - `*.mcas.ms`
> - `*.admin-mcas-gov.us`
> - `*.mcas-df.ms`
> - `*.admin-mcas-df.ms`

## Here's why you see `*.cas.ms`, `*.mcas.ms`, or `*.mcas-gov.us` in your URL

First of all, you have not been phished! This kind of URL is expected and indicates that your organization applies additional security controls to protect business-critical data.

They do this by using Defender for Cloud Apps, a solution for protecting your organization's cloud environment, to replace all relevant URLs and cookies relating to cloud apps that you use.

So when you try accessing a cloud app such as Salesforce, SharePoint Online, or AWS, you will notice that its URL is suffixed with `.cas.ms`, `.mcas.ms`, or `.mcas-gov.us`. For example, when using the XYZ app, the URL you're used to seeing changes from `XYZ.com` to `XYZ.com.cas.ms`.

If the URL does not exactly match one of the replacement patterns (for example, `<app_site>.com` is not replaced with `<app_site>.com.cas.ms`), or if you have additional concerns, contact your IT department.
