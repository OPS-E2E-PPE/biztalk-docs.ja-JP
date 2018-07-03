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
ms.openlocfilehash: 618d5475842a9e5844f289a7ca77e4d9a725b130
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990219"
---
# <a name="nested-positional-records"></a><span data-ttu-id="c44b2-102">入れ子になった位置指定レコード</span><span class="sxs-lookup"><span data-stu-id="c44b2-102">Nested Positional Records</span></span>
<span data-ttu-id="c44b2-103">入れ子になった位置指定レコードは許可されている場合、 **Max Occurs**子レコードのプロパティが正の整数に設定します。</span><span class="sxs-lookup"><span data-stu-id="c44b2-103">Nested positional records are allowed if the **Max Occurs** property of child records is set to a positive integer.</span></span> <span data-ttu-id="c44b2-104">フィールドの自動計算で、新しい深さを処理できることが必要となります。</span><span class="sxs-lookup"><span data-stu-id="c44b2-104">Field autocalculation should be able to handle the new depth.</span></span> <span data-ttu-id="c44b2-105">ただし、この動作が正しく行われるためには、いくつかの条件があります。</span><span class="sxs-lookup"><span data-stu-id="c44b2-105">However, there is a modification to the way this behaves.</span></span> <span data-ttu-id="c44b2-106">特に、区切り記号が null である可能性があるため、フィールド位置の自動計算は、次のいずれかの条件が満たされた場合にしか機能しません。</span><span class="sxs-lookup"><span data-stu-id="c44b2-106">Specifically, because of the possibility for null delimiters, autocalculation of field positions will function only if one of the following conditions is met:</span></span>  
  
- <span data-ttu-id="c44b2-107">選択されたノードに、挿入辞で区切られた親が存在する。</span><span class="sxs-lookup"><span data-stu-id="c44b2-107">The selected node has a parent that is infix delimited.</span></span>  
  
- <span data-ttu-id="c44b2-108">選択されたノードに、開始位置が指定されている。</span><span class="sxs-lookup"><span data-stu-id="c44b2-108">The selected node has a specified starting position.</span></span>  
  
  <span data-ttu-id="c44b2-109">入れ子になった位置指定レコードは、親が null で区切られたコンテナーとなっている位置指定レコードとは異なる点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="c44b2-109">Note that there is a distinction between nested positional records and positional records whose parent is a delimited container where the delimiter is null.</span></span> <span data-ttu-id="c44b2-110">構造を位置に基づいて入れ子にする場合、長さを判断するときに、あいまいさは許可されません。</span><span class="sxs-lookup"><span data-stu-id="c44b2-110">For structures to be truly nested positionally, there must not be any ambiguity in determining their length.</span></span> <span data-ttu-id="c44b2-111">たとえば、区切り記号付きのループ ノードは、0 ～ N 個の連続して出現する位置指定レコードを含むことができます。</span><span class="sxs-lookup"><span data-stu-id="c44b2-111">For example, a delimited loop node can contain a repeating positional record that occurs 0 to N times.</span></span> <span data-ttu-id="c44b2-112">しかし、ループ ノード自体を位置指定レコードとし、連続する位置指定レコードのピアとしてフィールドを含むためには、連続する位置指定レコードの出現回数 (正の整数) が確定している必要があります。</span><span class="sxs-lookup"><span data-stu-id="c44b2-112">However, for that loop node itself to be positional, and possibly also contain fields as peers to the repeating positional record, the occurrence of the repeating positional record must be deterministic (a positive integer).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c44b2-113">参照</span><span class="sxs-lookup"><span data-stu-id="c44b2-113">See Also</span></span>  
 [<span data-ttu-id="c44b2-114">位置指定レコードに関する注意</span><span class="sxs-lookup"><span data-stu-id="c44b2-114">Positional Record Considerations</span></span>](../core/positional-record-considerations.md)