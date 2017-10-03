---
title: "GetWorkflowEvent |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2534e0b8-26df-4554-b0df-742014deb64d
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8dc753bd45452af6ab586a11f216bc65f9539fb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="getworkflowevent"></a><span data-ttu-id="8ecda-102">GetWorkflowEvent</span><span class="sxs-lookup"><span data-stu-id="8ecda-102">GetWorkflowEvent</span></span>
<span data-ttu-id="8ecda-103">現在のワークフロー イベントの名前をスタックにプッシュします。</span><span class="sxs-lookup"><span data-stu-id="8ecda-103">Pushes the name of the current workflow event onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ecda-104">構文</span><span class="sxs-lookup"><span data-stu-id="8ecda-104">Syntax</span></span>  
  
```  
  
<wf:Operation Name="GetWorkflowEvent" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8ecda-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8ecda-105">Parameters</span></span>  
 <span data-ttu-id="8ecda-106">[なし] :</span><span class="sxs-lookup"><span data-stu-id="8ecda-106">None.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="8ecda-107">プッシュされた値</span><span class="sxs-lookup"><span data-stu-id="8ecda-107">Pushed Value</span></span>  
 <span data-ttu-id="8ecda-108">現在のワークフロー イベントを表す文字列です。</span><span class="sxs-lookup"><span data-stu-id="8ecda-108">String containing the current workflow event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8ecda-109">解説</span><span class="sxs-lookup"><span data-stu-id="8ecda-109">Remarks</span></span>  
 <span data-ttu-id="8ecda-110">ワークフロー インスタンスは、その実行の過程でいくつかの状態の段階を経る場合があります。</span><span class="sxs-lookup"><span data-stu-id="8ecda-110">A workflow instance can pass through several states during the course of its execution.</span></span> <span data-ttu-id="8ecda-111">たとえば、ワークフロー インスタンスはアイドル状態になったり、中断されたりします。</span><span class="sxs-lookup"><span data-stu-id="8ecda-111">For example, a workflow instance may become idle, or it may be suspended.</span></span> <span data-ttu-id="8ecda-112">ワークフロー インスタンスの状態が変化するたびに、ワークフロー ステータス イベントがランタイム追跡インフラストラクチャに送信されます。</span><span class="sxs-lookup"><span data-stu-id="8ecda-112">Every time the workflow instance changes state, it emits a workflow status event to the runtime tracking infrastructure.</span></span> <span data-ttu-id="8ecda-113">Windows Workflow Foundation BAM インターセプターは、`System.Workflow.Runtime.Tracking.TrackingWorkflowEvent` 列挙体に定義された、次の表に示すような大部分のイベントをサポートします。</span><span class="sxs-lookup"><span data-stu-id="8ecda-113">The Windows Workflow Foundation BAM interceptor supports most of the events defined by the `System.Workflow.Runtime.Tracking.TrackingWorkflowEvent` enumeration, as shown in the following table.</span></span>  
  
|<span data-ttu-id="8ecda-114">アクティビティ イベント</span><span class="sxs-lookup"><span data-stu-id="8ecda-114">Activity event</span></span>|<span data-ttu-id="8ecda-115">Description</span><span class="sxs-lookup"><span data-stu-id="8ecda-115">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="8ecda-116">変更</span><span class="sxs-lookup"><span data-stu-id="8ecda-116">Changed</span></span>|<span data-ttu-id="8ecda-117">ワークフロー インスタンスでは、ワークフローの変更が発生しました。</span><span class="sxs-lookup"><span data-stu-id="8ecda-117">A workflow change has occurred on the workflow instance.</span></span>|  
|<span data-ttu-id="8ecda-118">[完了]</span><span class="sxs-lookup"><span data-stu-id="8ecda-118">Completed</span></span>|<span data-ttu-id="8ecda-119">ワークフロー インスタンスが完了しました。</span><span class="sxs-lookup"><span data-stu-id="8ecda-119">The workflow instance has completed.</span></span>|  
|<span data-ttu-id="8ecda-120">Created</span><span class="sxs-lookup"><span data-stu-id="8ecda-120">Created</span></span>|<span data-ttu-id="8ecda-121">ワークフロー インスタンスが作成されました。</span><span class="sxs-lookup"><span data-stu-id="8ecda-121">The workflow instance has been created.</span></span>|  
|<span data-ttu-id="8ecda-122">例外</span><span class="sxs-lookup"><span data-stu-id="8ecda-122">Exception</span></span>|<span data-ttu-id="8ecda-123">処理されない例外が発生しました。</span><span class="sxs-lookup"><span data-stu-id="8ecda-123">An unhandled exception has occurred.</span></span>|  
|<span data-ttu-id="8ecda-124">Idle</span><span class="sxs-lookup"><span data-stu-id="8ecda-124">Idle</span></span>|<span data-ttu-id="8ecda-125">ワークフロー インスタンスがアイドル状態です。</span><span class="sxs-lookup"><span data-stu-id="8ecda-125">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="8ecda-126">読み込まれました。</span><span class="sxs-lookup"><span data-stu-id="8ecda-126">Loaded</span></span>|<span data-ttu-id="8ecda-127">ワークフロー インスタンスがメモリに読み込まれました。</span><span class="sxs-lookup"><span data-stu-id="8ecda-127">The workflow instance has been loaded into memory.</span></span>|  
|<span data-ttu-id="8ecda-128">永続化</span><span class="sxs-lookup"><span data-stu-id="8ecda-128">Persisted</span></span>|<span data-ttu-id="8ecda-129">ワークフロー インスタンスが保存されました。</span><span class="sxs-lookup"><span data-stu-id="8ecda-129">The workflow instance has been persisted.</span></span>|  
|<span data-ttu-id="8ecda-130">再開</span><span class="sxs-lookup"><span data-stu-id="8ecda-130">Resumed</span></span>|<span data-ttu-id="8ecda-131">以前に中断されているワークフロー インスタンスの実行が再開されました。</span><span class="sxs-lookup"><span data-stu-id="8ecda-131">A previously suspended workflow instance has resumed running.</span></span>|  
|<span data-ttu-id="8ecda-132">Started</span><span class="sxs-lookup"><span data-stu-id="8ecda-132">Started</span></span>|<span data-ttu-id="8ecda-133">ワークフロー インスタンスが開始されました。</span><span class="sxs-lookup"><span data-stu-id="8ecda-133">The workflow instance has been started.</span></span>|  
|<span data-ttu-id="8ecda-134">中断</span><span class="sxs-lookup"><span data-stu-id="8ecda-134">Suspended</span></span>|<span data-ttu-id="8ecda-135">ワークフロー インスタンスが中断されました。</span><span class="sxs-lookup"><span data-stu-id="8ecda-135">The workflow instance has been suspended.</span></span>|  
|<span data-ttu-id="8ecda-136">終了</span><span class="sxs-lookup"><span data-stu-id="8ecda-136">Terminated</span></span>|<span data-ttu-id="8ecda-137">ワークフロー インスタンスが終了されました。</span><span class="sxs-lookup"><span data-stu-id="8ecda-137">The workflow instance has been terminated.</span></span>|  
|<span data-ttu-id="8ecda-138">アンロード</span><span class="sxs-lookup"><span data-stu-id="8ecda-138">Unloaded</span></span>|<span data-ttu-id="8ecda-139">ワークフロー インスタンスがメモリからアンロードされました。</span><span class="sxs-lookup"><span data-stu-id="8ecda-139">The workflow instance has been unloaded from memory.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="8ecda-140">同じ OnEvent 要素で `GetWorkflowEvent` と `GetActivityEvent` の両方を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="8ecda-140">You cannot use both `GetWorkflowEvent` and `GetActivityEvent` in the same OnEvent element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ecda-141">例</span><span class="sxs-lookup"><span data-stu-id="8ecda-141">Example</span></span>  
 <span data-ttu-id="8ecda-142">次の例には、特定のアクティビティを検索するように構成するフィルターが含まれています:"FoodAndDrinksPolicy": ワークフロー内で。</span><span class="sxs-lookup"><span data-stu-id="8ecda-142">The following sample contains a filter that is configured to find a specific activity—"FoodAndDrinksPolicy"—in a workflow.</span></span> <span data-ttu-id="8ecda-143">このサンプルでは、閉じたワークフロー内で "FoodAndDrinksPolicy" という名前のアクティビティを検出するようにフィルターが構成されています。</span><span class="sxs-lookup"><span data-stu-id="8ecda-143">In the sample, a filter is configured to find the activity named "FoodAndDrinksPolicy" in a closed workflow.</span></span> <span data-ttu-id="8ecda-144">この処理は、`GetWorkflowEvent` によって返された値を定数 "作成" と比較することにより実行されます。</span><span class="sxs-lookup"><span data-stu-id="8ecda-144">This is done by comparing the value returned by `GetWorkflowEvent` to the constant "Created".</span></span>  
  
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
  
 <span data-ttu-id="8ecda-145">この操作は、ワークフローの有効期間を追跡する場合、およびワークフローで発生する例外またはその他の問題を検出する場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8ecda-145">This operation is useful for tracking the lifetime of a workflow and for detecting exceptions or other problems with the workflow.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ecda-146">参照</span><span class="sxs-lookup"><span data-stu-id="8ecda-146">See Also</span></span>  
 [<span data-ttu-id="8ecda-147">System.Workflow.Runtime.Tracking.TrackingWorkflowEvent 列挙体</span><span class="sxs-lookup"><span data-stu-id="8ecda-147">System.Workflow.Runtime.Tracking.TrackingWorkflowEvent enumeration</span></span>](http://go.microsoft.com/fwlink/?LinkId=119568)