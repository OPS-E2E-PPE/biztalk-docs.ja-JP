---
title: 例外のスロー図形を構成する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 07d156572484ba4fbe71533252ce4fe956136699
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248082"
---
# <a name="how-to-configure-the-throw-exception-shape"></a><span data-ttu-id="4f664-102">例外のスロー図形を構成する方法</span><span class="sxs-lookup"><span data-stu-id="4f664-102">How to Configure the Throw Exception Shape</span></span>
<span data-ttu-id="4f664-103">使用して、オーケストレーションで例外をスローすることが明示的に、**例外のスロー**図形です。</span><span class="sxs-lookup"><span data-stu-id="4f664-103">You can explicitly throw exceptions in an orchestration by using the **Throw Exception** shape.</span></span> <span data-ttu-id="4f664-104">スローが実行されると、ランタイム エンジンは、スローされた例外の種類を処理できる例外ハンドラーのうち最も近くにある例外ハンドラーを探します。</span><span class="sxs-lookup"><span data-stu-id="4f664-104">When the throw is performed, the runtime engine will search for the nearest exception handler that can handle the type of exception being thrown.</span></span>  
  
 <span data-ttu-id="4f664-105">最初に現在のオーケストレーションを囲んでいるスコープを検索し、そのスコープに関連付けられている例外ハンドラーを検討して、スローされた例外の種類に適したハンドラーを特定します。</span><span class="sxs-lookup"><span data-stu-id="4f664-105">First, the current orchestration is searched for an enclosing scope, and the associated exception handlers of the scope are considered in order to locate the appropriate handler for the type of exception that has been thrown.</span></span>  
  
 <span data-ttu-id="4f664-106">適切な例外ハンドラーを検出できない場合は、現在のオーケストレーションを呼び出したオーケストレーションから、現在のオーケストレーションへの呼び出しポイントを含むスコープを探します。</span><span class="sxs-lookup"><span data-stu-id="4f664-106">If no appropriate exception handler is found, the orchestration that called the current orchestration is searched for a scope that encloses the point of the call to the current orchestration.</span></span> <span data-ttu-id="4f664-107">この検索は、現在の例外を処理できる例外ハンドラーが見つかるまで継続されます。</span><span class="sxs-lookup"><span data-stu-id="4f664-107">This search continues until an exception handler is found that can handle the current exception.</span></span>  
  
 <span data-ttu-id="4f664-108">例外に完全に一致するのは、スローされた例外のランタイム型と同じクラスか、その基本クラスとなっている例外クラスです。</span><span class="sxs-lookup"><span data-stu-id="4f664-108">An exact match for the exception is an exception class that is of the same class as, or a base class of, the run-time type of the exception being thrown.</span></span>  
  
 <span data-ttu-id="4f664-109">一致する例外ハンドラーが見つかると、その例外ハンドラーの最初のステートメントに制御が移ります。</span><span class="sxs-lookup"><span data-stu-id="4f664-109">After a matching exception handler is found, control is transferred to the first statement of the exception handler.</span></span>  
  
 <span data-ttu-id="4f664-110">一致する例外ハンドラーの検索に失敗した場合は、オーケストレーションが停止します。</span><span class="sxs-lookup"><span data-stu-id="4f664-110">If the search for matching exception handlers fails, the orchestration halts.</span></span> <span data-ttu-id="4f664-111">トランザクションを使用すると、そのような場合の影響を最小限に抑えることができます。</span><span class="sxs-lookup"><span data-stu-id="4f664-111">Transactions can help you minimize the impact of such an occurrence.</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="4f664-112">手順</span><span class="sxs-lookup"><span data-stu-id="4f664-112">Procedure</span></span>  
  
#### <a name="to-configure-a-throw-exception-shape"></a><span data-ttu-id="4f664-113">例外のスロー図形を構成するには</span><span class="sxs-lookup"><span data-stu-id="4f664-113">To configure a Throw Exception shape</span></span>  
  
-   <span data-ttu-id="4f664-114">[プロパティ] ウィンドウで、使用可能なオブジェクトの種類を選択からスローする、**例外オブジェクト**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="4f664-114">In the Properties window, select an available object type to throw from the **Exception Object** drop-down list.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4f664-115">一般的な例外を選択して、**例外のスロー**場合にのみ、図形、**例外のスロー**図形が例外ハンドラー内にあり、現在の例外ハンドラーでキャッチされた例外を再スローします。</span><span class="sxs-lookup"><span data-stu-id="4f664-115">Select General Exception in the **Throw Exception** shape only if the **Throw Exception** shape is within an exception handler and you want to rethrow the exception caught in the current exception handler.</span></span> <span data-ttu-id="4f664-116">一般的な例外を使用する場合、コンパイル時に、エラーが表示されます、**例外のスロー**他のコンテキスト内の図形です。</span><span class="sxs-lookup"><span data-stu-id="4f664-116">You will receive an error during the compile if you use General Exception for a **Throw Exception** shape in any other context.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f664-117">参照</span><span class="sxs-lookup"><span data-stu-id="4f664-117">See Also</span></span>  
 [<span data-ttu-id="4f664-118">例外</span><span class="sxs-lookup"><span data-stu-id="4f664-118">Exceptions</span></span>](../core/exceptions.md)