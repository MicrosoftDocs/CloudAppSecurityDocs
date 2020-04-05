---
# required metadata

title: How Cloud App Security performs content inspection
description: This article describes the process Cloud App Security follows when performing DLP content inspection on data in your cloud.
keywords:
author: shsagir
ms.author: shsagir
manager: shsagir
ms.date: 12/10/2018
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
# Built-in content inspection

*Applies to: Microsoft Cloud App Security*

This article describes the process Microsoft Cloud App Security follows when running the built-in DLP content inspection on data in your cloud.

Cloud App Security content inspection works as follows:

1. First, Cloud App Security performs Near Real-Time (NRT) scan of drives and events that are detected to be new or changed.
2. After that scan is complete, Cloud App Security performs a continuous scan of all relevant files in all drives.

Both the files in the NRT scan and the continuous scan are added to the queue for inspection. The order of the files in the scan queue is set per activity on files and on the scan of your drives. Files are scanned only if the file metadata shows it's a supported MIME type. That this scan is for files that are relevant for data scan (documents, images, presentations, spreadsheets, text, and zip/archive files).

After a file is scanned, the following actions occur:

1. Cloud App Security applies all your custom policies that relate to metadata and not to the content itself. For example, a policy that alerts you when files are more than 20 MB or a policy that alerts you when docx files are saved to OneDrive.

2. If there's a policy that requires content inspection and the file qualifies for content inspection, the content is queued for inspection. The queue length depends on the size of the tenant and the number of files that require scan.

3. At this point, you can view the status of the content inspection by going to **Investigate** > **Files** and clicking on a file. In the file drawer that opens with the details of the file, the **Content Inspection status** will display either **Completed**, **Pending**, **Not applicable** (if the file type isn't supported), or a failure message. For information about content scan failure messages, see [Troubleshooting content inspection](troubleshooting-content-inspection.md).

> [!NOTE]
> If you see a dash in the scan status, this means that the file is not queued to be scanned. See [File policies](data-protection-policies.md) for information on setting content inspection policies.

Built-in content inspection scan policies can search for the following items:

- Email addresses
- Credit card numbers
  - All credit card companies (Visa, MasterCard, American Express, Diners Club, Discover, JCB, Dankort, UnionPay)
  - Delimiters- space, dot, or dash
  - This scan also includes the Luhn validation
- SWIFT codes
- International passport numbers
- Drivers' license numbers
- Dates
- Bank ABA routing transit numbers
- Bank identifier codes
- HIPAA HICN Health insurance claim numbers
- HIPAA NPI National provider identifier numbers
- PHI Full name and birth dates
- California ID or drivers' license numbers
- Drivers' license numbers
- Home addresses
- Passport cards
- Social security numbers

## Supported languages

The Cloud App Security content inspection engine:

- Supports all Unicode characters
- Covers over 100 file types
- Multiple languages are supported, especially files that use Unicode character sets. Make sure to define your policies to account for those languages. For example if you're looking for keywords, you must put in the keywords across the languages you intend to use.
- In text-based file types that use non-Unicode encoding, for example Chinese GB2312, comparing against Unicode Chinese keywords won't work as expected.
- For file types that rely on third-party libraries, matching strings and words may not always work as expected. This is most common in files (such as binary file types) in which content inspection relies on third-party libraries that return Java strings for language and character sets.

## Next steps

> [!div class="nextstepaction"]
> [Control cloud apps with policies](control-cloud-apps-with-policies.md)

[!INCLUDE [Open support ticket](includes/support.md)]
