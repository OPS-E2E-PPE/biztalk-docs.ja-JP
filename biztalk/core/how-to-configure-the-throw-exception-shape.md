---
title: 例外のスロー図形を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Throw Exception shape [Orchestration Designer]
- orchestrations, errors
- Orchestration Designer, errors
ms.assetid: d3190f1b-db5e-4988-bff6-f7a276760ece
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee24b5a6fab36e7a865f26a04e8c040141835735
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385935"
---
# <a name="how-to-configure-the-throw-exception-shape"></a><span data-ttu-id="a7c8b-102">例外のスロー図形を構成する方法</span><span class="sxs-lookup"><span data-stu-id="a7c8b-102">How to Configure the Throw Exception Shape</span></span>
<span data-ttu-id="a7c8b-103">使用して、オーケストレーションで例外をスローすることが明示的に、**例外のスロー**図形。</span><span class="sxs-lookup"><span data-stu-id="a7c8b-103">You can explicitly throw exceptions in an orchestration by using the **Throw Exception** shape.</span></span> <span data-ttu-id="a7c8b-104">スローが実行されると、ランタイム エンジンは、スローされる例外の種類を処理できる最も近い例外ハンドラーが検索されます。</span><span class="sxs-lookup"><span data-stu-id="a7c8b-104">When the throw is performed, the runtime engine will search for the nearest exception handler that can handle the type of exception being thrown.</span></span>  
  
 <span data-ttu-id="a7c8b-105">最初に、外側のスコープ、現在のオーケストレーションが検索されがスローされた例外の種類に対応するハンドラーを見つけるには、スコープの関連付けられている例外ハンドラーと見なされます。</span><span class="sxs-lookup"><span data-stu-id="a7c8b-105">First, the current orchestration is searched for an enclosing scope, and the associated exception handlers of the scope are considered in order to locate the appropriate handler for the type of exception that has been thrown.</span></span>  
  
 <span data-ttu-id="a7c8b-106">適切な例外ハンドラーが見つからない場合、現在のオーケストレーションを呼び出したオーケストレーションを現在のオーケストレーションへの呼び出しのポイントを囲むスコープが検索されます。</span><span class="sxs-lookup"><span data-stu-id="a7c8b-106">If no appropriate exception handler is found, the orchestration that called the current orchestration is searched for a scope that encloses the point of the call to the current orchestration.</span></span> <span data-ttu-id="a7c8b-107">この検索は、現在の例外を処理できる例外ハンドラーが見つかるまで続けられます。</span><span class="sxs-lookup"><span data-stu-id="a7c8b-107">This search continues until an exception handler is found that can handle the current exception.</span></span>  
  
 <span data-ttu-id="a7c8b-108">例外の完全に一致すると、同じクラスの例外クラス、スローされる例外の実行時の型の基本クラス。</span><span class="sxs-lookup"><span data-stu-id="a7c8b-108">An exact match for the exception is an exception class that is of the same class as, or a base class of, the run-time type of the exception being thrown.</span></span>  
  
 <span data-ttu-id="a7c8b-109">一致する例外ハンドラーが見つかると後、は、例外ハンドラーの最初のステートメントに制御が移ります。</span><span class="sxs-lookup"><span data-stu-id="a7c8b-109">After a matching exception handler is found, control is transferred to the first statement of the exception handler.</span></span>  
  
 <span data-ttu-id="a7c8b-110">一致する例外ハンドラーの検索に失敗した場合、オーケストレーションを停止します。</span><span class="sxs-lookup"><span data-stu-id="a7c8b-110">If the search for matching exception handlers fails, the orchestration halts.</span></span> <span data-ttu-id="a7c8b-111">トランザクションは、このような出来事の影響を最小限に抑えるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a7c8b-111">Transactions can help you minimize the impact of such an occurrence.</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="a7c8b-112">手順</span><span class="sxs-lookup"><span data-stu-id="a7c8b-112">Procedure</span></span>  
  
#### <a name="to-configure-a-throw-exception-shape"></a><span data-ttu-id="a7c8b-113">例外のスロー図形を構成するには</span><span class="sxs-lookup"><span data-stu-id="a7c8b-113">To configure a Throw Exception shape</span></span>  
  
-   <span data-ttu-id="a7c8b-114">[プロパティ] ウィンドウからスローに使用可能なオブジェクトの種類を選択します。、**例外オブジェクト**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="a7c8b-114">In the Properties window, select an available object type to throw from the **Exception Object** drop-down list.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a7c8b-115">一般的な例外の選択、**例外のスロー**場合にのみ、図形、**例外のスロー**図形が例外ハンドラー内にあり、現在の例外ハンドラーでキャッチされた例外を再スローします。</span><span class="sxs-lookup"><span data-stu-id="a7c8b-115">Select General Exception in the **Throw Exception** shape only if the **Throw Exception** shape is within an exception handler and you want to rethrow the exception caught in the current exception handler.</span></span> <span data-ttu-id="a7c8b-116">一般的な例外を使用する場合、コンパイル時にエラーが表示されます、**例外のスロー**他のコンテキストでの図形。</span><span class="sxs-lookup"><span data-stu-id="a7c8b-116">You will receive an error during the compile if you use General Exception for a **Throw Exception** shape in any other context.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7c8b-117">参照</span><span class="sxs-lookup"><span data-stu-id="a7c8b-117">See Also</span></span>  
 [<span data-ttu-id="a7c8b-118">例外</span><span class="sxs-lookup"><span data-stu-id="a7c8b-118">Exceptions</span></span>](../core/exceptions.md)