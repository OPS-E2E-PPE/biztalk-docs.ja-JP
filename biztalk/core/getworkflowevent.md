---
title: GetWorkflowEvent |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2534e0b8-26df-4554-b0df-742014deb64d
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 68cf89a168606ae64a83c67b29eb058770b67f44
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387645"
---
# <a name="getworkflowevent"></a><span data-ttu-id="3c447-102">GetWorkflowEvent</span><span class="sxs-lookup"><span data-stu-id="3c447-102">GetWorkflowEvent</span></span>
<span data-ttu-id="3c447-103">スタックには、現在のワークフロー イベントの名前をプッシュします。</span><span class="sxs-lookup"><span data-stu-id="3c447-103">Pushes the name of the current workflow event onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c447-104">構文</span><span class="sxs-lookup"><span data-stu-id="3c447-104">Syntax</span></span>  
  
```  
  
<wf:Operation Name="GetWorkflowEvent" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3c447-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3c447-105">Parameters</span></span>  
 <span data-ttu-id="3c447-106">[なし] :</span><span class="sxs-lookup"><span data-stu-id="3c447-106">None.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="3c447-107">プッシュされた値</span><span class="sxs-lookup"><span data-stu-id="3c447-107">Pushed Value</span></span>  
 <span data-ttu-id="3c447-108">現在のワークフロー イベントを表す文字列です。</span><span class="sxs-lookup"><span data-stu-id="3c447-108">String containing the current workflow event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c447-109">コメント</span><span class="sxs-lookup"><span data-stu-id="3c447-109">Remarks</span></span>  
 <span data-ttu-id="3c447-110">ワークフロー インスタンスは、その実行の進行中にいくつかの状態を通過できます。</span><span class="sxs-lookup"><span data-stu-id="3c447-110">A workflow instance can pass through several states during the course of its execution.</span></span> <span data-ttu-id="3c447-111">たとえば、ワークフロー インスタンスがアイドル状態になる可能性があります。 または、中断する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3c447-111">For example, a workflow instance may become idle, or it may be suspended.</span></span> <span data-ttu-id="3c447-112">ワークフロー インスタンス状態が変わるたびに、ランタイム追跡インフラストラクチャにワークフロー ステータス イベントを出力します。</span><span class="sxs-lookup"><span data-stu-id="3c447-112">Every time the workflow instance changes state, it emits a workflow status event to the runtime tracking infrastructure.</span></span> <span data-ttu-id="3c447-113">Windows Workflow Foundation BAM インターセプタは、によって定義されたイベントのほとんどをサポートしています、`System.Workflow.Runtime.Tracking.TrackingWorkflowEvent`列挙体では、次の表に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="3c447-113">The Windows Workflow Foundation BAM interceptor supports most of the events defined by the `System.Workflow.Runtime.Tracking.TrackingWorkflowEvent` enumeration, as shown in the following table.</span></span>  
  
|<span data-ttu-id="3c447-114">アクティビティ イベント</span><span class="sxs-lookup"><span data-stu-id="3c447-114">Activity event</span></span>|<span data-ttu-id="3c447-115">説明</span><span class="sxs-lookup"><span data-stu-id="3c447-115">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="3c447-116">変更</span><span class="sxs-lookup"><span data-stu-id="3c447-116">Changed</span></span>|<span data-ttu-id="3c447-117">ワークフロー インスタンスのワークフローの変更が発生しました。</span><span class="sxs-lookup"><span data-stu-id="3c447-117">A workflow change has occurred on the workflow instance.</span></span>|  
|<span data-ttu-id="3c447-118">[完了]</span><span class="sxs-lookup"><span data-stu-id="3c447-118">Completed</span></span>|<span data-ttu-id="3c447-119">ワークフロー インスタンスが完了しました。</span><span class="sxs-lookup"><span data-stu-id="3c447-119">The workflow instance has completed.</span></span>|  
|<span data-ttu-id="3c447-120">Created</span><span class="sxs-lookup"><span data-stu-id="3c447-120">Created</span></span>|<span data-ttu-id="3c447-121">ワークフロー インスタンスが作成されました。</span><span class="sxs-lookup"><span data-stu-id="3c447-121">The workflow instance has been created.</span></span>|  
|<span data-ttu-id="3c447-122">例外</span><span class="sxs-lookup"><span data-stu-id="3c447-122">Exception</span></span>|<span data-ttu-id="3c447-123">ハンドルされない例外が発生しました。</span><span class="sxs-lookup"><span data-stu-id="3c447-123">An unhandled exception has occurred.</span></span>|  
|<span data-ttu-id="3c447-124">Idle</span><span class="sxs-lookup"><span data-stu-id="3c447-124">Idle</span></span>|<span data-ttu-id="3c447-125">ワークフロー インスタンスがアイドル状態です。</span><span class="sxs-lookup"><span data-stu-id="3c447-125">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="3c447-126">読み込まれました。</span><span class="sxs-lookup"><span data-stu-id="3c447-126">Loaded</span></span>|<span data-ttu-id="3c447-127">ワークフロー インスタンスがメモリに読み込まれました。</span><span class="sxs-lookup"><span data-stu-id="3c447-127">The workflow instance has been loaded into memory.</span></span>|  
|<span data-ttu-id="3c447-128">永続化</span><span class="sxs-lookup"><span data-stu-id="3c447-128">Persisted</span></span>|<span data-ttu-id="3c447-129">ワークフロー インスタンスが永続化されています。</span><span class="sxs-lookup"><span data-stu-id="3c447-129">The workflow instance has been persisted.</span></span>|  
|<span data-ttu-id="3c447-130">再開</span><span class="sxs-lookup"><span data-stu-id="3c447-130">Resumed</span></span>|<span data-ttu-id="3c447-131">中断状態のワークフロー インスタンスが再開を実行します。</span><span class="sxs-lookup"><span data-stu-id="3c447-131">A previously suspended workflow instance has resumed running.</span></span>|  
|<span data-ttu-id="3c447-132">Started</span><span class="sxs-lookup"><span data-stu-id="3c447-132">Started</span></span>|<span data-ttu-id="3c447-133">ワークフロー インスタンスが開始されました。</span><span class="sxs-lookup"><span data-stu-id="3c447-133">The workflow instance has been started.</span></span>|  
|<span data-ttu-id="3c447-134">中断</span><span class="sxs-lookup"><span data-stu-id="3c447-134">Suspended</span></span>|<span data-ttu-id="3c447-135">ワークフロー インスタンスが中断されました。</span><span class="sxs-lookup"><span data-stu-id="3c447-135">The workflow instance has been suspended.</span></span>|  
|<span data-ttu-id="3c447-136">終了</span><span class="sxs-lookup"><span data-stu-id="3c447-136">Terminated</span></span>|<span data-ttu-id="3c447-137">ワークフロー インスタンスを終了しました。</span><span class="sxs-lookup"><span data-stu-id="3c447-137">The workflow instance has been terminated.</span></span>|  
|<span data-ttu-id="3c447-138">アンロード</span><span class="sxs-lookup"><span data-stu-id="3c447-138">Unloaded</span></span>|<span data-ttu-id="3c447-139">ワークフロー インスタンスがメモリからアンロードされました。</span><span class="sxs-lookup"><span data-stu-id="3c447-139">The workflow instance has been unloaded from memory.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="3c447-140">同じ OnEvent 要素で `GetWorkflowEvent` と `GetActivityEvent` の両方を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="3c447-140">You cannot use both `GetWorkflowEvent` and `GetActivityEvent` in the same OnEvent element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3c447-141">例</span><span class="sxs-lookup"><span data-stu-id="3c447-141">Example</span></span>  
 <span data-ttu-id="3c447-142">次のサンプルには、特定のアクティビティを検出するように構成するフィルターが含まれています:"FoodAndDrinksPolicy": ワークフロー内で。</span><span class="sxs-lookup"><span data-stu-id="3c447-142">The following sample contains a filter that is configured to find a specific activity—"FoodAndDrinksPolicy"—in a workflow.</span></span> <span data-ttu-id="3c447-143">サンプルでは、closed ワークフロー内の"FoodAndDrinksPolicy"をという名前のアクティビティを検索するフィルターを構成します。</span><span class="sxs-lookup"><span data-stu-id="3c447-143">In the sample, a filter is configured to find the activity named "FoodAndDrinksPolicy" in a closed workflow.</span></span> <span data-ttu-id="3c447-144">によって返される値を比較することによってこれは、`GetWorkflowEvent`定数「作成」します。</span><span class="sxs-lookup"><span data-stu-id="3c447-144">This is done by comparing the value returned by `GetWorkflowEvent` to the constant "Created".</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetWorkflowEvent" />   
      <ic:Operation Name="Constant">  
        <ic:Argument>Created</ic:Argument>   
      </ic:Operation>  
    <ic:Operation Name="Equals" />   
  </ic:Expression>  
</ic:Filter>  
```  
  
 <span data-ttu-id="3c447-145">この操作は、ワークフローの有効期間を追跡するため、例外、またはワークフローとその他の問題を検出するために便利です。</span><span class="sxs-lookup"><span data-stu-id="3c447-145">This operation is useful for tracking the lifetime of a workflow and for detecting exceptions or other problems with the workflow.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c447-146">参照</span><span class="sxs-lookup"><span data-stu-id="3c447-146">See Also</span></span>  
 [<span data-ttu-id="3c447-147">System.Workflow.Runtime.Tracking.TrackingWorkflowEvent 列挙体</span><span class="sxs-lookup"><span data-stu-id="3c447-147">System.Workflow.Runtime.Tracking.TrackingWorkflowEvent enumeration</span></span>](http://go.microsoft.com/fwlink/?LinkId=119568)