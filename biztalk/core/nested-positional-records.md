---
title: 位置指定レコードを入れ子になった |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e205e9d-f740-4177-b45a-5e1baadae99a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d0eddb7925a34e79c1da45a6ec6e2670f9632695
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65323623"
---
# <a name="nested-positional-records"></a><span data-ttu-id="ed37d-102">入れ子になった位置指定レコード</span><span class="sxs-lookup"><span data-stu-id="ed37d-102">Nested Positional Records</span></span>
<span data-ttu-id="ed37d-103">入れ子になった位置指定レコードは許可されている場合、 **Max Occurs**子レコードのプロパティが正の整数に設定します。</span><span class="sxs-lookup"><span data-stu-id="ed37d-103">Nested positional records are allowed if the **Max Occurs** property of child records is set to a positive integer.</span></span> <span data-ttu-id="ed37d-104">フィールドの自動計算は、新しい深さを処理できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed37d-104">Field autocalculation should be able to handle the new depth.</span></span> <span data-ttu-id="ed37d-105">ただし、この動作は方法が変更されます。</span><span class="sxs-lookup"><span data-stu-id="ed37d-105">However, there is a modification to the way this behaves.</span></span> <span data-ttu-id="ed37d-106">具体的には、区切り記号が null の可能性をフィールド位置の自動計算が、次の条件のいずれかが満たされた場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="ed37d-106">Specifically, because of the possibility for null delimiters, autocalculation of field positions will function only if one of the following conditions is met:</span></span>  
  
- <span data-ttu-id="ed37d-107">選択したノードには、区切られた挿入辞である親があります。</span><span class="sxs-lookup"><span data-stu-id="ed37d-107">The selected node has a parent that is infix delimited.</span></span>  
  
- <span data-ttu-id="ed37d-108">選択したノードには、指定された開始位置があります。</span><span class="sxs-lookup"><span data-stu-id="ed37d-108">The selected node has a specified starting position.</span></span>  
  
  <span data-ttu-id="ed37d-109">入れ子になった位置指定レコードと位置指定レコードの親は、区切り記号が null で区切られたコンテナーとの間の違いがあることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ed37d-109">Note that there is a distinction between nested positional records and positional records whose parent is a delimited container where the delimiter is null.</span></span> <span data-ttu-id="ed37d-110">構造を位置に、入れ子にする真にあってはいけません。 あいまいさの長さを決定します。</span><span class="sxs-lookup"><span data-stu-id="ed37d-110">For structures to be truly nested positionally, there must not be any ambiguity in determining their length.</span></span> <span data-ttu-id="ed37d-111">たとえば、区切られたループ ノードは、0 ~ N 個に発生する繰り返しの位置指定レコードを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="ed37d-111">For example, a delimited loop node can contain a repeating positional record that occurs 0 to N times.</span></span> <span data-ttu-id="ed37d-112">ただし、ループ ノード自体としてフィールドを含むと位置を指定すると、ピアに繰り返しの位置指定レコード内で見つかったの繰り返しの位置指定レコードは、決定的である必要があります (正の整数)。</span><span class="sxs-lookup"><span data-stu-id="ed37d-112">However, for that loop node itself to be positional, and possibly also contain fields as peers to the repeating positional record, the occurrence of the repeating positional record must be deterministic (a positive integer).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed37d-113">参照</span><span class="sxs-lookup"><span data-stu-id="ed37d-113">See Also</span></span>  
 [<span data-ttu-id="ed37d-114">位置指定レコードに関する注意</span><span class="sxs-lookup"><span data-stu-id="ed37d-114">Positional Record Considerations</span></span>](../core/positional-record-considerations.md)