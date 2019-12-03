---
# required metadata

title: How Cloud App Security performs content inspection
description: This article describes the process Cloud App Security follows when performing DLP content inspection on data in your cloud.
keywords:
author: shsagir
ms.author: shsagir
manager: shsagir
ms.date: 1/6/2019
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.prod:
ms.service: cloud-app-security
ms.technology:

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: seodec18

---
# Content inspection

*Applies to: Microsoft Cloud App Security*

If you enable content inspection, you can choose to use preset expressions or to search for other customized expressions.

You can specify a regular expression to exclude a file from the results. This option is highly useful if you have an inner classification keyword standard that you want to exclude from the policy.

You can decide set the minimum number of content violations that you want to match before the file is considered a violation. For example, you can choose 10 if you want to be alerted on files with at least 10 credit card numbers found within its content.

When content is matched against the selected expression, the violation text is replaced with "X" characters. By default, violations are masked and shown in their context displaying 100 characters before and after the violation. Numbers in the context of the expression are replaced with “#” characters and are never stored within Cloud App Security. You can select the option to **Unmask the last four characters of a violation** to unmask the last four characters of the violation itself. It's necessary to set which data types the regular expression searches: content, metadata and/or file name. By default it searches the content and the metadata.

## Content inspection for protected files

Cloud App Security allows admins to grant Cloud App Security permission to decrypt encrypted files and scan their content for violations.

In order to give Cloud app Security the necessary permissions:

1. Go to **Settings** and then **Azure Information Protection**.
2. Enable **Inspect protected files.**
3. Follow the prompt to allow the required permissions in Azure Active Directory.
4. You can configure the settings per file policy to determine which policies will scan protected files.

## Next steps

> [!div class="nextstepaction"]
> [Control cloud apps with policies](control-cloud-apps-with-policies.md)

[!INCLUDE [Open support ticket](includes/support.md)]
