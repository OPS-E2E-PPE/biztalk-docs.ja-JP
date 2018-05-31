---
title: 複数の注文のアイテムを使用して |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- JD Edwards OneWorld adapters, multiple calls
- JD Edwards OneWorld adapters, multi-order numbers
- multiple edit line calls [JD Edwards OneWorld adapters]
- adapters [JD Edwards OneWorld adapters], multi-order numbers
- multi-order numbers [JD Edwards OneWorld adapters]
- adapters [JD Edwards OneWorld adapters], multiple calls
ms.assetid: 207ea92c-03f7-4117-8414-eb174e659d26
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 389e73ede2d1062c9907bd8640f38ce74ad6f316
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287258"
---
# <a name="using-multi-order-items"></a><span data-ttu-id="ffbb3-102">複数の注文項目の使用</span><span class="sxs-lookup"><span data-stu-id="ffbb3-102">Using Multi-Order Items</span></span>
<span data-ttu-id="ffbb3-103">JD Edwards OneWorld API の構造により、BizTalk Server で複数の注文番号を使用する場合は、オーケストレーションで複数の編集行呼び出しを行い、それらの品目をオーケストレーションに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ffbb3-103">Due to the structure of the JD Edwards OneWorld API, if you want to use multi-order numbers with BizTalk Server, you must make multiple edit line calls in your orchestration to add those line items in an orchestration.</span></span> <span data-ttu-id="ffbb3-104">たとえば、複数の注文番号の品目には、1 つの注文番号のヘッダーと、複数品目の注文を含む詳細が含まれていることがあります (Toy 1EA、Gloves 2EA など)。</span><span class="sxs-lookup"><span data-stu-id="ffbb3-104">For example, a multi-order item might contain a header with a single order number, and detail that includes several items orders (like Toy 1EA, Gloves 2EA).</span></span>  
  
 <span data-ttu-id="ffbb3-105">複数の編集行呼び出しを使用するには、BizTalk Server の開発者がそれらを構造化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ffbb3-105">To use multiple edit line calls, it is the responsibility of the BizTalk Server developer to structure them.</span></span> <span data-ttu-id="ffbb3-106">開発者は、オーケストレーションで内部ループを作成して、この呼び出しを行います。</span><span class="sxs-lookup"><span data-stu-id="ffbb3-106">The developer should create an internal loop in the orchestration to make those calls.</span></span>  
  
 <span data-ttu-id="ffbb3-107">JD Edwards OneWorld システムでは、複数の編集行呼び出しがサポートされますが、API ではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="ffbb3-107">The JD Edwards OneWorld system supports multiple edit line calls, but the API does not.</span></span> <span data-ttu-id="ffbb3-108">編集行メソッドの構造を確認すると、シーケンス構造ではなくフラットな構造になっています。</span><span class="sxs-lookup"><span data-stu-id="ffbb3-108">If you look at the structure of the Edit Line method, it is a flat structure and not a sequence.</span></span> <span data-ttu-id="ffbb3-109">したがって、品目を挿入するたびに関数を呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="ffbb3-109">Therefore, you must call the function every time you want to insert a line item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffbb3-110">参照</span><span class="sxs-lookup"><span data-stu-id="ffbb3-110">See Also</span></span>  
 [<span data-ttu-id="ffbb3-111">計画とアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="ffbb3-111">Planning and Architecture</span></span>](../core/planning-and-architecture17.md)