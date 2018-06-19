---
title: フィールドの値の一部として特殊文字を解釈する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9e19a202-4e4d-42e0-ba1e-fddc52792b21
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b96a3c7502a47541e8e58ec3df3eccf6098e3abc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288386"
---
# <a name="ways-to-interpret-special-characters-as-part-of-a-field-value"></a><span data-ttu-id="f89ab-102">フィールドの値の一部として特殊文字を解釈する方法</span><span class="sxs-lookup"><span data-stu-id="f89ab-102">Ways to Interpret Special Characters as Part of a Field Value</span></span>
<span data-ttu-id="f89ab-103">位置指定レコードおよび区切り記号付きレコードのフィールドには、いずれも、埋め込み文字、囲み文字、エスケープ文字など、さまざまな種類の特殊文字が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f89ab-103">Fields in both positional and delimited records can contain special characters of different types, such as pad, wrap, and escape characters.</span></span> <span data-ttu-id="f89ab-104">区切り記号ベースのレコードには、さらに、レコード間の区切りや、レコード内のフィールド間の区切りを表す記号が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f89ab-104">Delimited records can also contain one or more different delimiter characters that are used to separate the fields within a record and one record from another record.</span></span> <span data-ttu-id="f89ab-105">これらの特殊文字がデータとして含まれている場合もあり、その場合は、特殊な文字として解釈されないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f89ab-105">Sometimes these special characters are part of the data itself, and are not meant to be interpreted as special in those cases.</span></span>  
  
 <span data-ttu-id="f89ab-106">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で使用されるフラット ファイル スキーマでは、特殊文字をフィールド データの一部として解釈させるための 2 とおりの方法がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f89ab-106">The flat file schemas used by Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] support two different techniques for flagging occurrences of otherwise special characters as simply part of the data contained by a field.</span></span> <span data-ttu-id="f89ab-107">これらの方法には、それぞれエスケープ文字と囲み文字が使用されます。</span><span class="sxs-lookup"><span data-stu-id="f89ab-107">These two techniques employ escape characters and wrap characters, respectively.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f89ab-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="f89ab-108">In This Section</span></span>  
  
-   [<span data-ttu-id="f89ab-109">エスケープ文字</span><span class="sxs-lookup"><span data-stu-id="f89ab-109">Escape Characters</span></span>](../core/escape-characters.md)  
  
-   [<span data-ttu-id="f89ab-110">囲み文字</span><span class="sxs-lookup"><span data-stu-id="f89ab-110">Wrap Characters</span></span>](../core/wrap-characters.md)