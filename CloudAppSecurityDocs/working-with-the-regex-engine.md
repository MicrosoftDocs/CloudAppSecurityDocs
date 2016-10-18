---
# required metadata

title: Working with the RegEx engine | Microsoft Docs
description: This topic provides instructions for using RegEx for pattern matching in Cloud App Security policies.
keywords:
author: rkarlin
manager: mbaldwin
ms.date: 10/15/2016
ms.topic: article
ms.prod:
ms.service: cloud-app-security
ms.technology:
ms.assetid: dc8b87e5-e6c1-4a65-ab8c-067fb527fce4

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: reutam
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Working with the RegEx engine
 
 Cloud App Security's content inspection policies leverage RegEx for pattern matching. Content inspection may be applied as part of file policies. In order to test regular expressions, you can use the following websites:  
  
-   [http://regexpal.com/](http://regexpal.com/)  
  
     (Make sure you select **Case insensitive**.  
  
-   [https://regex101.com/](https://regex101.com/)  
  
     Provides detailed analysis of the RegEx.  
  
 The following limitations are imposed on custom regular expressions:  
  
-   The search is always case-insensitive  
   
-   Allowed quantifiers: {n,m} where n, m < 10  
  
-   All groups must be non-capturing, for example: (?:xxx)  
  
     Instead of (group) use (?:group)  
  
-   Disallowed quantifiers: *, +, {n,}  
  
     Instead of * use {0,9}  
  
     Instead of + use {1,9}  
  
-   Disallowed back-references: \\<number\> or \k\<name>  
  
 Example expressions  
  
||||  
|-|-|-|  
|**Regular expression**|**Data**|**Matches**|  
|Colou?r (?:black&#124;blue&#124;white)|Color black<br /><br /> Color white<br /><br /> Color red|Yes<br /><br /> Yes<br /><br /> No|  
|[a-z0-9]{1,9}@[a-z0-9]{1,9}\\.[a-z]{2,3}|Some1@abc.com<br /><br /> user@host.org<br /><br /> @bad.com|Yes<br /><br /> Yes<br /><br /> No|  
|20\d{2}-(?:0[1-9]&#124;1[0-2])-(?:[0-2][0-9]&#124;30&#124;31)|2015-12-31<br /><br /> 2015-01-09<br /><br /> 1999-12-31|Yes<br /><br /> Yes<br /><br /> No|  
|d.n't\s{0,10}c.r.|Don't     care<br /><br /> D!n'tcor0<br /><br /> Doesn't care|Yes<br /><br /> Yes<br /><br /> No|  
 