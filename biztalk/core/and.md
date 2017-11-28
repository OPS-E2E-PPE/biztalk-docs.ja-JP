---
title: "|Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 80bd8f1f-edae-476d-b488-78e6c5ee70bf
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 676940dfa5cbc23d0c8127923d292e382a4e3cad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="and"></a><span data-ttu-id="82425-102">And</span><span class="sxs-lookup"><span data-stu-id="82425-102">And</span></span>
<span data-ttu-id="82425-103">ブール値を実行する、スタックから上位 2 項目を削除**AND**の項目、および結果をスタックにプッシュし、2 つです。</span><span class="sxs-lookup"><span data-stu-id="82425-103">Removes the top two items from the stack, performs a Boolean **AND** of the two items, and then pushes the result onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82425-104">構文</span><span class="sxs-lookup"><span data-stu-id="82425-104">Syntax</span></span>  
  
```  
  
<ic:Operation Name="And" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="82425-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="82425-105">Parameters</span></span>  
 <span data-ttu-id="82425-106">スタックの上位 2 項目。</span><span class="sxs-lookup"><span data-stu-id="82425-106">Top two items on the stack.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="82425-107">プッシュされた値</span><span class="sxs-lookup"><span data-stu-id="82425-107">Pushed Value</span></span>  
 <span data-ttu-id="82425-108">ブール型の結果の文字列**AND**操作します。</span><span class="sxs-lookup"><span data-stu-id="82425-108">String result of the Boolean **AND** operation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="82425-109">解説</span><span class="sxs-lookup"><span data-stu-id="82425-109">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="82425-110">例</span><span class="sxs-lookup"><span data-stu-id="82425-110">Example</span></span>  
 <span data-ttu-id="82425-111">**と**操作は、複数のステートメントを評価する必要がある場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="82425-111">The **And** operation is useful when you need to evaluate multiple statements.</span></span> <span data-ttu-id="82425-112">次の例のフィルタ式を確認するかどうか、アクティビティ名が"CheckPO"を使用してアクティビティ イベントが閉じられる、**と**操作します。</span><span class="sxs-lookup"><span data-stu-id="82425-112">The following example filter expression checks whether the activity name is "CheckPO" and the activity event is closed by using the **And** operation.</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>CheckPO</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
    <wf:Operation Name="GetActivityEvent"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>Closed</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
    <ic:Operation Name="And"/>  
  </ic:Expression>  
</ic:Filter>  
```  
  
 <span data-ttu-id="82425-113">この例では**と**式の最後の操作は、比較の結果に依存しています (および比較の実行にスタックからポップ) ためです。</span><span class="sxs-lookup"><span data-stu-id="82425-113">In this example **And** is the final operation in the expression because it relies on the results of the comparisons (and pops them from the stack to perform the comparison).</span></span> <span data-ttu-id="82425-114">実行するには、この概念を拡張する**と**3 つ以上のアイテムに対して操作します。</span><span class="sxs-lookup"><span data-stu-id="82425-114">You can extend this idea to perform **And** operations on more than two items.</span></span> <span data-ttu-id="82425-115">たとえば、条件 A、条件 B、および条件 C が True の場合、次のような式を使用します。</span><span class="sxs-lookup"><span data-stu-id="82425-115">For example, to evaluate whether Condition A and Condition B and Condition C are true, you would use an expression like the following:</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>CheckPO</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
    <wf:Operation Name="GetActivityEvent"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>Closed</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
    <wf:Operation Name="GetActivityType"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyType</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
    <ic:Operation Name="And"/>  
    <ic:Operation Name="And"/>  
  </ic:Expression>  
</ic:Filter>   
```  
  
## <a name="see-also"></a><span data-ttu-id="82425-116">参照</span><span class="sxs-lookup"><span data-stu-id="82425-116">See Also</span></span>  
 [<span data-ttu-id="82425-117">インターセプタの操作</span><span class="sxs-lookup"><span data-stu-id="82425-117">Interceptor Operations</span></span>](../core/interceptor-operations.md)