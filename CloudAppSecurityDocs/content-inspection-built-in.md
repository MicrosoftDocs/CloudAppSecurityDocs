---
title: Built-in DLP content inspection
description: This article describes the process Microsoft Defender for Cloud Apps follows when running the built-in DLP content inspection on data in your cloud.
ms.date: 02/23/2023
ms.topic: how-to
---

# Built-in DLP content inspection in Microsoft Defender for Cloud Apps

[!INCLUDE [Banner for top of topics](includes/banner.md)]

> [!IMPORTANT]
> Effective March 2023, we're retiring the built-in DLP content inspection engine. To ensure a smooth transition, we highly recommend that you begin transitioning your policies to the Data Classification Services (DCS) Content Inspection Engine.  While the built-in DLP engine will continue to work, we strongly advise you to move your policies to the DCS engine to take advantage of its improved capabilities.  
>
> Here's how to migrate:
>
> Disable policies that include a content inspection condition with the built-in engine. This will ensure that all matched files remain unchanged until the specified transition date.
>
> Create a new policy that includes the following two conditions:
>
> - A metadata condition with a "starting date" to avoid scanning all files from the start.
> - A content inspection condition using the DCS engine.
>
>
> For more information, see [Microsoft Data Classification Services integration](dcs-inspection.md).

This article describes the process Microsoft Defender for Cloud Apps follows when running the built-in DLP content inspection on data in your cloud.

Defender for Cloud Apps content inspection works as follows:

1. First, Defender for Cloud Apps performs a Near Real-Time (NRT) scan of drives and events that are detected to be new or changed.
2. After that scan is complete, Defender for Cloud Apps performs a continuous scan of all relevant files in all drives.

Both the files in the NRT scan and the continuous scan are added to the queue for inspection. The order of the files in the scan queue is set per activity on files and on the scan of your drives. The file contents are scanned only if the file metadata shows it's a supported MIME type (documents, presentations, spreadsheets, text, and zip/archive files).

After a file is scanned, the following actions occur:

1. Defender for Cloud Apps applies all your custom policies that relate to metadata and not to the content itself. For example, a policy that alerts you when files are more than 20 MB or a policy that alerts you when docx files are saved to OneDrive.

2. If there's a policy that requires content inspection and the file qualifies for content inspection, the content is queued for inspection. The queue length depends on the size of the tenant and the number of files that require scan.

3. At this point, you can view the status of the content inspection by going to **Investigate** > **Files** and clicking on a file. In the file drawer that opens with the details of the file, the **Content Inspection status** displays either **Completed**, **Pending**, **Not applicable** (if the file type isn't supported or no policy requires content inspection for this file), or a failure message. For information about content scan failure messages, see [Troubleshooting content inspection](troubleshooting-content-inspection.md).

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

The Defender for Cloud Apps content inspection engine:

- Supports all Unicode characters
- Covers over 100 file types
- Multiple languages are supported, especially files that use Unicode character sets. Make sure to define your policies to account for those languages. For example if you're looking for keywords, you must put in the keywords across the languages you intend to use.
- In text-based file types that use non-Unicode encoding, for example Chinese GB2312, comparing against Unicode Chinese keywords doesn't work as expected.
- For file types that rely on third-party libraries, matching strings and words doesn't always work as expected. This is most common in files (such as binary file types) in which content inspection relies on third-party libraries that return Java strings for language and character sets.

## Next steps

> [!div class="nextstepaction"]
> [Control cloud apps with policies](control-cloud-apps-with-policies.md)

[!INCLUDE [Open support ticket](includes/support.md)]
