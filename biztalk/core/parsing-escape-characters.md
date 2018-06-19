---
title: エスケープ文字の解析 |Microsoft ドキュメント
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
ms.openlocfilehash: f200e7c68a43360dc9edbae42ebea196b884f577
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25971976"
---
# <a name="parsing-escape-characters"></a><span data-ttu-id="5b22e-102">エスケープ文字の解析</span><span class="sxs-lookup"><span data-stu-id="5b22e-102">Parsing Escape Characters</span></span>
<span data-ttu-id="5b22e-103">パーサーは通常の文字 (区切り文字以外またはその他の特殊文字以外の文字) の前に付加されたエスケープ文字を見つけると、そのエスケープ文字を無視します。</span><span class="sxs-lookup"><span data-stu-id="5b22e-103">When the parser encounters an escape character that prefixes a regular character (that is, one that is not a delimiter or other special character), the escape character is ignored.</span></span> <span data-ttu-id="5b22e-104">たとえば、文字列を指定して"abc \d"、"\\"エスケープ文字は、出力は"abcd"です。</span><span class="sxs-lookup"><span data-stu-id="5b22e-104">For example, given a string "abc\d" where "\\" is the escape character, the output is "abcd".</span></span>  
  
 <span data-ttu-id="5b22e-105">パーサーには、ダブル エスケープ文字が検出された場合 (たとえば、"abc\\\d")、出力には、1 つのエスケープ文字 ("abc \d") が含まれています。</span><span class="sxs-lookup"><span data-stu-id="5b22e-105">If the parser encounters a double escape character (for example, "abc\\\d"), the output includes a single escape character ("abc\d").</span></span>  
  
 <span data-ttu-id="5b22e-106">パーサーが次の 3 つのエスケープ文字を検出する場合 (たとえば、abc\\\\\d)、最初の 2 つのエスケープ文字を解析しているために、出力は"abc \d""\\"と 3 番目のエスケープ文字は無視されます。</span><span class="sxs-lookup"><span data-stu-id="5b22e-106">If the parser encounters three escape characters (for example, abc\\\\\d), the output is "abc\d" because the first two escape characters are parsed to "\\" and the third escape character is ignored.</span></span>  
  
 <span data-ttu-id="5b22e-107">パーサーは、間違った位置にある区切り文字を通常の文字として扱います。</span><span class="sxs-lookup"><span data-stu-id="5b22e-107">The parser treats misplaced delimiters as regular characters.</span></span> <span data-ttu-id="5b22e-108">たとえば、"Record, Field1, Field, 2"を受信する場合、出力 XML は\<Field1\> \<Field, 2\>です。</span><span class="sxs-lookup"><span data-stu-id="5b22e-108">For example, if "Record, Field1, Field,2" is received, the output XML is \<Field1\> \<Field,2\>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b22e-109">参照</span><span class="sxs-lookup"><span data-stu-id="5b22e-109">See Also</span></span>  
 [<span data-ttu-id="5b22e-110">フラット ファイル解析エンジンの使用</span><span class="sxs-lookup"><span data-stu-id="5b22e-110">Using the Flat File Parsing Engine</span></span>](../core/using-the-flat-file-parsing-engine.md)