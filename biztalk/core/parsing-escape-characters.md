---
title: エスケープ文字の解析 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], code samples
- pipeline components [custom], escape characters
- pipeline components [custom], parsing
ms.assetid: 2b33f436-3c29-4ff5-8dfa-26d6591713bc
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f16ddf0225c2b8ebaa1a934955a1a05f45f64ee0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395052"
---
# <a name="parsing-escape-characters"></a><span data-ttu-id="8cf4a-102">エスケープ文字の解析</span><span class="sxs-lookup"><span data-stu-id="8cf4a-102">Parsing Escape Characters</span></span>
<span data-ttu-id="8cf4a-103">パーサーには、プレフィックス (つまり、1 つの区切り記号またはその他の特殊文字はない) 通常の文字をエスケープ文字が検出されると、エスケープ文字は無視されます。</span><span class="sxs-lookup"><span data-stu-id="8cf4a-103">When the parser encounters an escape character that prefixes a regular character (that is, one that is not a delimiter or other special character), the escape character is ignored.</span></span> <span data-ttu-id="8cf4a-104">たとえば、指定された文字列"abc \d"を"\\"エスケープ文字では、出力は"abcd"。</span><span class="sxs-lookup"><span data-stu-id="8cf4a-104">For example, given a string "abc\d" where "\\" is the escape character, the output is "abcd".</span></span>  
  
 <span data-ttu-id="8cf4a-105">パーサーがエスケープ文字を検出する場合 (たとえば、"abc\\\d")、出力には、1 つのエスケープ文字 ("abc \d") が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8cf4a-105">If the parser encounters a double escape character (for example, "abc\\\d"), the output includes a single escape character ("abc\d").</span></span>  
  
 <span data-ttu-id="8cf4a-106">パーサーが次の 3 つのエスケープ文字を検出する場合 (たとえば、abc\\\\\d)、最初の 2 つのエスケープ文字を解析しているために、出力は"abc \d""\\"と 3 番目のエスケープ文字は無視されます。</span><span class="sxs-lookup"><span data-stu-id="8cf4a-106">If the parser encounters three escape characters (for example, abc\\\\\d), the output is "abc\d" because the first two escape characters are parsed to "\\" and the third escape character is ignored.</span></span>  
  
 <span data-ttu-id="8cf4a-107">間違っている区切り記号は、パーサーは、標準の文字として扱います。</span><span class="sxs-lookup"><span data-stu-id="8cf4a-107">The parser treats misplaced delimiters as regular characters.</span></span> <span data-ttu-id="8cf4a-108">たとえば、"Record, Field1, Field, 2"を受信した場合、出力 XML は\<Field1\> \<Field, 2\>します。</span><span class="sxs-lookup"><span data-stu-id="8cf4a-108">For example, if "Record, Field1, Field,2" is received, the output XML is \<Field1\> \<Field,2\>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cf4a-109">参照</span><span class="sxs-lookup"><span data-stu-id="8cf4a-109">See Also</span></span>  
 [<span data-ttu-id="8cf4a-110">フラット ファイル解析エンジンの使用</span><span class="sxs-lookup"><span data-stu-id="8cf4a-110">Using the Flat File Parsing Engine</span></span>](../core/using-the-flat-file-parsing-engine.md)