---
title: オーケストレーションにおける変数のスコープ |Microsoft Docs
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
ms.openlocfilehash: ebe6e3e4116a2b5c250e642d5bc78d828b07656c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292576"
---
# <a name="variable-scope-in-orchestrations"></a><span data-ttu-id="54c21-102">オーケストレーションにおける変数のスコープ</span><span class="sxs-lookup"><span data-stu-id="54c21-102">Variable Scope in Orchestrations</span></span>
<span data-ttu-id="54c21-103">可視性と変数と、例外ハンドラーや補正ブロックをも含め、オーケストレーション内のさまざまな場所でオーケストレーション パラメーターの状態を理解するために、いくつかの重要なポイントがあります。</span><span class="sxs-lookup"><span data-stu-id="54c21-103">There are a few important points to understand about the visibility and state of variables and orchestration parameters in various places within your orchestration, including exception handlers and compensation blocks.</span></span>  
  
-   <span data-ttu-id="54c21-104">オーケストレーション パラメーターは、その補正ブロックのようにも、オーケストレーションの本文全体で表示されます。</span><span class="sxs-lookup"><span data-stu-id="54c21-104">Orchestration parameters are visible throughout the body of the orchestration as well as in its compensation block.</span></span>  
  
-   <span data-ttu-id="54c21-105">およびすべての例外ハンドラーと補正ブロックのスコープの本体で、スコープ レベルの変数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="54c21-105">Scope-level variables are visible in the body of the scope as well as in all of its exception handlers and compensation block.</span></span> <span data-ttu-id="54c21-106">例外のハンドラー内で、変数と見なされる初期化されていない前に、または本文に、初期化された後に、特定のハンドラーの原因となった例外がかどうか実施不確定ではないためです。</span><span class="sxs-lookup"><span data-stu-id="54c21-106">Inside exception handlers, the variables are considered un-initialized since it is indeterminate whether the exception that led to a given handler took place before or after any initialization in the body.</span></span> <span data-ttu-id="54c21-107">このため、スコープで変数を宣言し、本文内で初期化し、例外ハンドラーでそこから読み取ることができませんまたはコンパイラ エラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="54c21-107">For this reason, if you declare a variable in a scope and initialize it in the body, you cannot read from it in an exception handler, or you will get a compiler error.</span></span> <span data-ttu-id="54c21-108">実行時間の長いトランザクションの場合、その回避策が存在します。</span><span class="sxs-lookup"><span data-stu-id="54c21-108">A workaround for that exists in the case of long running transactions.</span></span> <span data-ttu-id="54c21-109">次の例では、succeeded() 演算子を使用して、適切なランタイムの動作を確保する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="54c21-109">The following example shows how the succeeded() operator can be used to ensure proper runtime behavior:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="54c21-110">次のコードは、;、論理的なプロセスを説明する擬似コードこのコードは、オーケストレーションの式図形内で使用できません。</span><span class="sxs-lookup"><span data-stu-id="54c21-110">The code below is pseudo code that describes a logical process; this code cannot be used within an Orchestration Expression shape.</span></span>  
  
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
  
-   <span data-ttu-id="54c21-111">補正ブロック内では、すべての変数には、スコープの本体がコミットされたときの値が想定しています。</span><span class="sxs-lookup"><span data-stu-id="54c21-111">Inside a compensation block, all variables assume the values they had when the body of the scope committed.</span></span> <span data-ttu-id="54c21-112">スコープの補正ブロックが本体内の完了直後後に実行されないことに注意してください。介在するコードは常にします。</span><span class="sxs-lookup"><span data-stu-id="54c21-112">Note that the compensation block of a scope never runs immediately after its body completes; there is always intervening code.</span></span> <span data-ttu-id="54c21-113">介在するコードのいくつかの外側のスコープの変数が更新され、補正ブロックが実行する場合、補正ブロック内でこれらの更新プログラムが表示されません。</span><span class="sxs-lookup"><span data-stu-id="54c21-113">If any of that intervening code updates some outer-scope variables, and then the compensation block runs, those updates will not be seen inside the compensation block.</span></span> <span data-ttu-id="54c21-114">代わりに、変数は、一時的にその報酬を所有するスコープがコミット時に保持していた値に戻ります。</span><span class="sxs-lookup"><span data-stu-id="54c21-114">Instead the variables will temporarily revert to the values they had at the time the scope which owns that compensation had committed.</span></span>  
  
-   <span data-ttu-id="54c21-115">トランザクションは、ループ内で入れ子になっている、ときに、ループが実行される回数だけ、トランザクションが補正されます。</span><span class="sxs-lookup"><span data-stu-id="54c21-115">When a transaction is nested inside a loop, the transaction will be compensated as many times as the loop executes.</span></span> <span data-ttu-id="54c21-116">各イテレーションの補正ブロック内では、外側のスコープの変数には、トランザクションのコミットのイテレーション時の値が想定しています。</span><span class="sxs-lookup"><span data-stu-id="54c21-116">Inside the compensation block for each iteration, outer-scope variables assume the values they had at the time of the iteration of the transaction committed.</span></span>  
  
-   <span data-ttu-id="54c21-117">外側のスコープの変数にすべての更新が行われたか、補正ブロックが完了したら、内側のスコープの補正ブロック内でのオーケストレーション パラメーターは表示されません。</span><span class="sxs-lookup"><span data-stu-id="54c21-117">Any updates made to outer-scope variables or orchestration parameters inside compensation blocks of inner scopes will not be visible after the compensation block completes.</span></span> <span data-ttu-id="54c21-118">つまり、補正ブロックを使用して、外側のスコープの変数の値を直接変更できません。</span><span class="sxs-lookup"><span data-stu-id="54c21-118">In other words, the compensation block cannot be used to directly modify the values of outer-scope variables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54c21-119">参照</span><span class="sxs-lookup"><span data-stu-id="54c21-119">See Also</span></span>  
 [<span data-ttu-id="54c21-120">XLANG-s データ型</span><span class="sxs-lookup"><span data-stu-id="54c21-120">XLANG-s Data Types</span></span>](../core/xlang-s-data-types.md)