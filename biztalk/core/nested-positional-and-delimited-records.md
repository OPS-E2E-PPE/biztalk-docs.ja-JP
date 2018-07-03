---
title: 位置指定および区切り記号付きレコードを入れ子になった |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d1688f04-d3c7-492c-82f7-a734bec0e409
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3896eb41a52ee356021a6fcf7e7621267f8764f8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971219"
---
# <a name="nested-positional-and-delimited-records"></a><span data-ttu-id="b8ea8-102">入れ子になった位置指定および区切り記号付きレコード</span><span class="sxs-lookup"><span data-stu-id="b8ea8-102">Nested Positional and Delimited Records</span></span>
<span data-ttu-id="b8ea8-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でサポートされているフラット ファイル形式では、位置指定レコードと区切り記号付きレコードを組み合わせて使用できます (使用できない場合もあります)。</span><span class="sxs-lookup"><span data-stu-id="b8ea8-103">In the flat file formats supported by Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], some combinations of positional and delimited records are allowed and others are disallowed.</span></span> <span data-ttu-id="b8ea8-104">次の組み合わせが可能です。</span><span class="sxs-lookup"><span data-stu-id="b8ea8-104">The following combinations are allowed:</span></span>  
  
- <span data-ttu-id="b8ea8-105">区切り記号を使用してすべてのレコードとその下位レコードの相互の境界を設定しており、区切り記号 (境界の区切り記号とは異なる場合もある) を使用してそれらのレコード内のフィールドを分割しているフラット ファイル。</span><span class="sxs-lookup"><span data-stu-id="b8ea8-105">Flat files in which delimiters are used to determine the boundaries between all records and their subordinate records from each other, and in which (possibly different) delimiters are used to separate the fields within those records.</span></span>  
  
- <span data-ttu-id="b8ea8-106">あらかじめ定義されたレコード長およびフィールド長に応じたファイル内の位置に基づいて、すべてのレコード、下位レコード、およびフィールドの境界が決定されるフラット ファイル。</span><span class="sxs-lookup"><span data-stu-id="b8ea8-106">Flat files in which the boundaries between all records, their subordinate records, and their fields are determined based on their position within the file according to predefined record and field lengths.</span></span>  
  
- <span data-ttu-id="b8ea8-107">区切り記号を使用してファイルの最も外側のレコードセットの境界が設定されていて、下位の区切り記号付きレコードと下位の位置指定レコードが組み合わされているフラット ファイル。</span><span class="sxs-lookup"><span data-stu-id="b8ea8-107">Flat files in which delimiters are used to determine the boundaries between at least the outermost set of records in the file, and in which a mix of delimited and positional subordinate records are used.</span></span> <span data-ttu-id="b8ea8-108">下位の区切り記号付き (または位置指定) レコード内にあるフィールド間の境界では、区切り記号 (区切り記号付きレコード) またはフィールドの固定長 (位置指定レコード) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="b8ea8-108">Boundaries between the fields within a delimited or positional subordinate record are determined using either delimiters or fixed field lengths, respectively.</span></span> <span data-ttu-id="b8ea8-109">位置指定レコードの下に属しているレコードについては、位置の指定も行う必要があります。つまり、ファイルの一部が区切り記号付きレコードから位置指定レコードに切り替わると、そのファイルの下位部分の位置をすべて指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8ea8-109">The subordinate records of a positional (subordinate) record must also be positional; in other words, once a portion of the file switches from delimited to positional records, that entire subordinate portion of the file must be positional.</span></span>  
  
  <span data-ttu-id="b8ea8-110">解析があいまいになると、位置指定レコードは、どのような場合であっても、下位の区切り記号付きレコードを格納できなくなります。</span><span class="sxs-lookup"><span data-stu-id="b8ea8-110">Due to the parsing ambiguities that would result, positional records, wherever they occur, are prohibited from containing delimited subordinate records.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8ea8-111">参照</span><span class="sxs-lookup"><span data-stu-id="b8ea8-111">See Also</span></span>  
 [<span data-ttu-id="b8ea8-112">フラット ファイル メッセージ スキーマを作成する上での注意点</span><span class="sxs-lookup"><span data-stu-id="b8ea8-112">Considerations When Creating Flat File Message Schemas</span></span>](../core/considerations-when-creating-flat-file-message-schemas.md)