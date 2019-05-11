---
title: および |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 80bd8f1f-edae-476d-b488-78e6c5ee70bf
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2da29c40091664112ee8b481f3feeba9d7463b5d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359710"
---
# <a name="and"></a><span data-ttu-id="92761-102">And</span><span class="sxs-lookup"><span data-stu-id="92761-102">And</span></span>
<span data-ttu-id="92761-103">スタックから上位 2 項目を削除しますが、ブール値を実行します**AND**の項目を 2 つと、結果をスタックにプッシュします。</span><span class="sxs-lookup"><span data-stu-id="92761-103">Removes the top two items from the stack, performs a Boolean **AND** of the two items, and then pushes the result onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92761-104">構文</span><span class="sxs-lookup"><span data-stu-id="92761-104">Syntax</span></span>  
  
```  
  
<ic:Operation Name="And" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="92761-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="92761-105">Parameters</span></span>  
 <span data-ttu-id="92761-106">スタックの上位 2 項目。</span><span class="sxs-lookup"><span data-stu-id="92761-106">Top two items on the stack.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="92761-107">プッシュされた値</span><span class="sxs-lookup"><span data-stu-id="92761-107">Pushed Value</span></span>  
 <span data-ttu-id="92761-108">結果のブール値の文字列**AND**操作。</span><span class="sxs-lookup"><span data-stu-id="92761-108">String result of the Boolean **AND** operation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="92761-109">コメント</span><span class="sxs-lookup"><span data-stu-id="92761-109">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="92761-110">例</span><span class="sxs-lookup"><span data-stu-id="92761-110">Example</span></span>  
 <span data-ttu-id="92761-111">**と**操作は、複数のステートメントを評価する必要がある場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="92761-111">The **And** operation is useful when you need to evaluate multiple statements.</span></span> <span data-ttu-id="92761-112">次のフィルター式の例では、アクティビティ名が"CheckPO"を使用してアクティビティ イベントが閉じられるかどうかを確認します。、**と**操作。</span><span class="sxs-lookup"><span data-stu-id="92761-112">The following example filter expression checks whether the activity name is "CheckPO" and the activity event is closed by using the **And** operation.</span></span>  
  
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
  
 <span data-ttu-id="92761-113">この例では**と**式の最後の操作は、比較の結果に依存しています (および、比較を実行するスタックからポップ) ためです。</span><span class="sxs-lookup"><span data-stu-id="92761-113">In this example **And** is the final operation in the expression because it relies on the results of the comparisons (and pops them from the stack to perform the comparison).</span></span> <span data-ttu-id="92761-114">実行するには、この考え方を拡張する**と**3 つ以上の項目に対して操作します。</span><span class="sxs-lookup"><span data-stu-id="92761-114">You can extend this idea to perform **And** operations on more than two items.</span></span> <span data-ttu-id="92761-115">たとえば、条件 A、条件 B、および条件 C が true かどうかを評価するには、次のような式を使用します。</span><span class="sxs-lookup"><span data-stu-id="92761-115">For example, to evaluate whether Condition A and Condition B and Condition C are true, you would use an expression like the following:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="92761-116">参照</span><span class="sxs-lookup"><span data-stu-id="92761-116">See Also</span></span>  
 [<span data-ttu-id="92761-117">インターセプターの操作</span><span class="sxs-lookup"><span data-stu-id="92761-117">Interceptor Operations</span></span>](../core/interceptor-operations.md)