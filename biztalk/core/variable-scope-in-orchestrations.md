---
title: オーケストレーションにおける変数のスコープ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, variables
ms.assetid: 5856cdca-0ebd-4e16-8739-7bd50753b9f9
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 82803cd7f2b0beb8349e978fdd7b9e453dca31ce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="variable-scope-in-orchestrations"></a><span data-ttu-id="4088c-102">オーケストレーションにおける変数のスコープ</span><span class="sxs-lookup"><span data-stu-id="4088c-102">Variable Scope in Orchestrations</span></span>
<span data-ttu-id="4088c-103">オーケストレーション内のさまざまな場所で使用されている変数やパラメーターの可視性と状態については、例外ハンドラーや補正ブロックなど、理解しておくべき重要な点がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="4088c-103">There are a few important points to understand about the visibility and state of variables and orchestration parameters in various places within your orchestration, including exception handlers and compensation blocks.</span></span>  
  
-   <span data-ttu-id="4088c-104">オーケストレーション パラメーターは、補正ブロックを含め、オーケストレーション本体のどの場所からでも参照できます。</span><span class="sxs-lookup"><span data-stu-id="4088c-104">Orchestration parameters are visible throughout the body of the orchestration as well as in its compensation block.</span></span>  
  
-   <span data-ttu-id="4088c-105">スコープ レベルの変数は、該当スコープの本体と、そのすべての例外ハンドラーおよび補正ブロックから参照できます。</span><span class="sxs-lookup"><span data-stu-id="4088c-105">Scope-level variables are visible in the body of the scope as well as in all of its exception handlers and compensation block.</span></span> <span data-ttu-id="4088c-106">例外ハンドラー内では、変数は初期化されていないものとして見なされます。特定のハンドラーを呼び出した例外が、本体で初期化される前に発生したのか、初期化された後に発生したのかが確定しないためです。</span><span class="sxs-lookup"><span data-stu-id="4088c-106">Inside exception handlers, the variables are considered un-initialized since it is indeterminate whether the exception that led to a given handler took place before or after any initialization in the body.</span></span> <span data-ttu-id="4088c-107">したがって、スコープ内で変数を宣言し、本体でそれを初期化した場合、例外ハンドラーからその変数を読み取ることはできません。読み取ろうとした場合は、コンパイラ エラーになります。</span><span class="sxs-lookup"><span data-stu-id="4088c-107">For this reason, if you declare a variable in a scope and initialize it in the body, you cannot read from it in an exception handler, or you will get a compiler error.</span></span> <span data-ttu-id="4088c-108">長時間実行されるトランザクションの場合は、これを回避する方法があります。</span><span class="sxs-lookup"><span data-stu-id="4088c-108">A workaround for that exists in the case of long running transactions.</span></span> <span data-ttu-id="4088c-109">次の例は、succeeded() 演算子を使って、実行時に適切な動作が行われるようにする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="4088c-109">The following example shows how the succeeded() operator can be used to ensure proper runtime behavior:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4088c-110">以下のコードは、論理的なプロセスを説明するための疑似コードです。オーケストレーションの式図形でこのコードを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="4088c-110">The code below is pseudo code that describes a logical process; this code cannot be used within an Orchestration Expression shape.</span></span>  
  
    ```  
    scope longrunning transaction L  
    {  
       System.Int32 i;  
       System.Int32 v;  
       body  
       {  
          i = 3;  
          scope longrunning transaction T  
          {  
             body  
             {  
                i = 5;  
             }  
          }  
       }  
       exceptions  
       {  
          catch  
          {  
             if(succeeded(T))  
             {  
                v = i;  // OK to read from it here — no compiler errors!  
             }  
          }  
       }  
    }  
    ```  
  
-   <span data-ttu-id="4088c-111">補正ブロック内では、すべての変数は、そのスコープの本体が実行されたときの値が想定されます。</span><span class="sxs-lookup"><span data-stu-id="4088c-111">Inside a compensation block, all variables assume the values they had when the body of the scope committed.</span></span> <span data-ttu-id="4088c-112">スコープの補正ブロックは、本体の実行が完了した直後に実行されることはない、つまり、常に、介入コードが存在するという点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="4088c-112">Note that the compensation block of a scope never runs immediately after its body completes; there is always intervening code.</span></span> <span data-ttu-id="4088c-113">何らかの介入コードによって外側のスコープの変数が更新された後、補正ブロックが実行された場合、更新の内容は補正ブロックからは見えないことになります。</span><span class="sxs-lookup"><span data-stu-id="4088c-113">If any of that intervening code updates some outer-scope variables, and then the compensation block runs, those updates will not be seen inside the compensation block.</span></span> <span data-ttu-id="4088c-114">そのため、変数は、補正ブロックの属するスコープがコミットされたときに保持していた値へと一時的に戻されます。</span><span class="sxs-lookup"><span data-stu-id="4088c-114">Instead the variables will temporarily revert to the values they had at the time the scope which owns that compensation had committed.</span></span>  
  
-   <span data-ttu-id="4088c-115">トランザクションがループ内で入れ子になっている場合、トランザクションはループの実行回数と同じだけ補正されます。</span><span class="sxs-lookup"><span data-stu-id="4088c-115">When a transaction is nested inside a loop, the transaction will be compensated as many times as the loop executes.</span></span> <span data-ttu-id="4088c-116">各繰り返し処理の補正ブロック内では、外側のスコープの変数は、コミットされたトランザクションの繰り返し処理時に保持していた値が想定されます。</span><span class="sxs-lookup"><span data-stu-id="4088c-116">Inside the compensation block for each iteration, outer-scope variables assume the values they had at the time of the iteration of the transaction committed.</span></span>  
  
-   <span data-ttu-id="4088c-117">外側のスコープに属する変数またはオーケストレーション パラメーターに対して、内側のスコープの補正ブロック内で行った変更は、補正ブロックが完了した後には見えなくなります。</span><span class="sxs-lookup"><span data-stu-id="4088c-117">Any updates made to outer-scope variables or orchestration parameters inside compensation blocks of inner scopes will not be visible after the compensation block completes.</span></span> <span data-ttu-id="4088c-118">つまり、外側のスコープに属する変数の値を、補正ブロックで直接変更することはできないということになります。</span><span class="sxs-lookup"><span data-stu-id="4088c-118">In other words, the compensation block cannot be used to directly modify the values of outer-scope variables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4088c-119">参照</span><span class="sxs-lookup"><span data-stu-id="4088c-119">See Also</span></span>  
 [<span data-ttu-id="4088c-120">XLANG のデータ型</span><span class="sxs-lookup"><span data-stu-id="4088c-120">XLANG-s Data Types</span></span>](../core/xlang-s-data-types.md)