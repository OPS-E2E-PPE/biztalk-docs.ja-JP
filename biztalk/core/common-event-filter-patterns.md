---
title: 一般的なイベント フィルタ パターン |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fc80168b-25bd-4228-b84c-d38bf4e2fe4a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef90a4533b8b12929488d3a323dae47976eace0a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22234522"
---
# <a name="common-event-filter-patterns"></a><span data-ttu-id="ec3b2-102">一般的なイベント フィルタ パターン</span><span class="sxs-lookup"><span data-stu-id="ec3b2-102">Common Event Filter Patterns</span></span>
<span data-ttu-id="ec3b2-103">Windows Workflow Foundation (WF) 用の BAM インターセプタを使用すると、インターセプタ構成ファイル内で頻繁に使用する、一般的なフィルタ パターンがあることに気付きます。</span><span class="sxs-lookup"><span data-stu-id="ec3b2-103">As you work with the BAM Interceptor for Windows Workflow Foundation (WF), you will likely notice that there are a set of common filter patterns that you will use frequently in your interceptor configuration files.</span></span> <span data-ttu-id="ec3b2-104">これらのフィルタ パターンの一部はアプリケーションと環境に固有ですが、多くのパターンは、環境にまたがりさまざまなアプリケーションで使用できます。</span><span class="sxs-lookup"><span data-stu-id="ec3b2-104">While some of these filter patterns will be unique to your applications and environments, many patterns can be used across environments and in diverse applications.</span></span>  
  
 <span data-ttu-id="ec3b2-105">このトピックでは、WF アプリケーション用に記述されたインターセプタ構成ファイルで使用する、一般的なフィルタ パターンを多数示します。</span><span class="sxs-lookup"><span data-stu-id="ec3b2-105">This topic collects many of the common filter patterns used by interceptor configuration files written for WF applications.</span></span> <span data-ttu-id="ec3b2-106">各パターンは、以下の Windows Workflow Foundation 追跡イベントでグループ化されています。</span><span class="sxs-lookup"><span data-stu-id="ec3b2-106">Patterns are grouped by Windows Workflow Foundation tracking event:</span></span>  
  
-   <span data-ttu-id="ec3b2-107">アクティビティ状態イベント</span><span class="sxs-lookup"><span data-stu-id="ec3b2-107">Activity status events</span></span>  
  
-   <span data-ttu-id="ec3b2-108">ワークフロー状態イベント</span><span class="sxs-lookup"><span data-stu-id="ec3b2-108">Workflow status events</span></span>  
  
-   <span data-ttu-id="ec3b2-109">ユーザー イベント</span><span class="sxs-lookup"><span data-stu-id="ec3b2-109">User events</span></span>  
  
 <span data-ttu-id="ec3b2-110">各パターンをインターセプタ構成ファイルにコピーし、アプリケーションに合わせて変更することができます。</span><span class="sxs-lookup"><span data-stu-id="ec3b2-110">Each pattern can be copied into your interceptor configuration file and modified to suit your application.</span></span>  
  
## <a name="activity-status-event-filter-patterns"></a><span data-ttu-id="ec3b2-111">アクティビティ状態イベントのフィルタ パターン</span><span class="sxs-lookup"><span data-stu-id="ec3b2-111">Activity Status Event Filter Patterns</span></span>  
 <span data-ttu-id="ec3b2-112">アクティビティは、ワークフローの基本的なビルディング ブロックです。</span><span class="sxs-lookup"><span data-stu-id="ec3b2-112">Activities are the fundamental building blocks of workflows.</span></span> <span data-ttu-id="ec3b2-113">ワークフローは、ツリー状に階層化された一連のアクティビティです。</span><span class="sxs-lookup"><span data-stu-id="ec3b2-113">A workflow is a set of activities that are organized hierarchically in a tree structure.</span></span> <span data-ttu-id="ec3b2-114">1 つのアクティビティは、ワークフロー内の 1 つのアクションを表します。</span><span class="sxs-lookup"><span data-stu-id="ec3b2-114">An activity represents an action in a workflow.</span></span> <span data-ttu-id="ec3b2-115">遅延などの単純なアクションのこともあれば、複数の子アクティビティで構成される複合的なアクティビティの場合もあります。</span><span class="sxs-lookup"><span data-stu-id="ec3b2-115">It can be a simple action such as a delay, or it can be a composite activity that consists of several child activities.</span></span>  
  
 <span data-ttu-id="ec3b2-116">このセクションのフィルタは、アクティビティに対してフィルタを適用し、以下の BAM インターセプタの 1 つ以上を使用して、WF の操作をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="ec3b2-116">The filters in this section filter activities and use one or more of the following BAM Interceptor for WF custom operations:</span></span>  
  
-   <span data-ttu-id="ec3b2-117">GetActivityName</span><span class="sxs-lookup"><span data-stu-id="ec3b2-117">GetActivityName</span></span>  
  
-   <span data-ttu-id="ec3b2-118">GetActivityEvent</span><span class="sxs-lookup"><span data-stu-id="ec3b2-118">GetActivityEvent</span></span>  
  
-   <span data-ttu-id="ec3b2-119">GetActivityType</span><span class="sxs-lookup"><span data-stu-id="ec3b2-119">GetActivityType</span></span>  
  
-   <span data-ttu-id="ec3b2-120">GetActivityProperty</span><span class="sxs-lookup"><span data-stu-id="ec3b2-120">GetActivityProperty</span></span>  
  
-   <span data-ttu-id="ec3b2-121">GetWorkflowProperty</span><span class="sxs-lookup"><span data-stu-id="ec3b2-121">GetWorkflowProperty</span></span>  
  
-   <span data-ttu-id="ec3b2-122">GetContextProperty</span><span class="sxs-lookup"><span data-stu-id="ec3b2-122">GetContextProperty</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ec3b2-123">フィルタ内で GetActivityEvent 操作を使用しない場合は、終了したアクティビティ イベントだけがフィルタの対象となります。</span><span class="sxs-lookup"><span data-stu-id="ec3b2-123">If you do not use the GetActivityEvent operation in your filter, your filter will look for Closed activity events only.</span></span>  
  
### <a name="filter-by-activity-name-closed-activity"></a><span data-ttu-id="ec3b2-124">アクティビティ名によるフィルタ (終了したアクティビティ)</span><span class="sxs-lookup"><span data-stu-id="ec3b2-124">Filter by Activity Name (Closed Activity)</span></span>  
 <span data-ttu-id="ec3b2-125">終了したアクティビティ イベントに対し、アクティビティ名によってフィルタを適用する必要になることが頻繁にあります。</span><span class="sxs-lookup"><span data-stu-id="ec3b2-125">You will frequently need to filter for closed activity events by activity name.</span></span> <span data-ttu-id="ec3b2-126">これは、ファイルの受信やデータベースへのデータの書き込みなど、特定のアクティビティからのデータをキャプチャする必要があるときに便利です。</span><span class="sxs-lookup"><span data-stu-id="ec3b2-126">This is useful when you need to capture data from a specific activity such as receiving a file or writing data to a database.</span></span>  
  
 <span data-ttu-id="ec3b2-127">以下のコード例は、"MyActivity" という名前の終了したアクティビティをフィルタします。</span><span class="sxs-lookup"><span data-stu-id="ec3b2-127">The fragment below filters for a closed activity named "MyActivity".</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-type-closed-activity-event"></a><span data-ttu-id="ec3b2-128">アクティビティ タイプによるフィルタ (終了したアクティビティ イベント)</span><span class="sxs-lookup"><span data-stu-id="ec3b2-128">Filter by Activity Type (Closed Activity Event)</span></span>  
 <span data-ttu-id="ec3b2-129">名前ではなくタイプでアクティビティをフィルタしたい場合があります。</span><span class="sxs-lookup"><span data-stu-id="ec3b2-129">There will be times when you want to filter an activity by type rather than name.</span></span> <span data-ttu-id="ec3b2-130">たとえば、ワークフロー内のすべてのアクティビティに対して、アクティビティ名と日付/タイムスタンプを保存したいことがあります。</span><span class="sxs-lookup"><span data-stu-id="ec3b2-130">For example, you may want to save activity name and a date/time stamp for all activities in a workflow.</span></span> <span data-ttu-id="ec3b2-131">このために使用する、`GetActivityType`操作します。</span><span class="sxs-lookup"><span data-stu-id="ec3b2-131">To accomplish this, you use the `GetActivityType` operation.</span></span> <span data-ttu-id="ec3b2-132">`GetActivityType`一致を判断するには、基本データ型とすべての派生型に対して指定された型を比較します。</span><span class="sxs-lookup"><span data-stu-id="ec3b2-132">`GetActivityType` compares a supplied type against the base type and all derived types to determine a match.</span></span> <span data-ttu-id="ec3b2-133">`System.Workflow.ComponentModel.Activity` に対する比較は一致します。これは、すべてのワークフロー アクティビティがそこから派生する必要があるためです。</span><span class="sxs-lookup"><span data-stu-id="ec3b2-133">Comparing against `System.Workflow.ComponentModel.Activity` will match since all workflow activities must derive from it.</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-event-any-activity-type"></a><span data-ttu-id="ec3b2-134">アクティビティ イベントによるフィルタ (任意のアクティビティ タイプ)</span><span class="sxs-lookup"><span data-stu-id="ec3b2-134">Filter by Activity Event (Any Activity Type)</span></span>  
 <span data-ttu-id="ec3b2-135">このフィルタは GetActivityEvent 操作を使用して、終了したアクティビティを探します。</span><span class="sxs-lookup"><span data-stu-id="ec3b2-135">This filter uses the GetActivityEvent operation to find closed activities.</span></span> <span data-ttu-id="ec3b2-136">これは、すべての終了したイベントに関する情報をキャプチャするのに (名前やタイプでイベントをフィルタするよりも) 便利です。</span><span class="sxs-lookup"><span data-stu-id="ec3b2-136">It is useful for capturing information about all closed events (versus a specific event by name or type).</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityEvent" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>Closed</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-name-and-type-closed-activity-event"></a><span data-ttu-id="ec3b2-137">アクティビティ名とタイプによるフィルタ (終了したアクティビティ イベント)</span><span class="sxs-lookup"><span data-stu-id="ec3b2-137">Filter by Activity Name and Type (Closed Activity Event)</span></span>  
 <span data-ttu-id="ec3b2-138">対象とするアクティビティのタイプ (プロセッサ アーキテクチャを含む) を正確に指定したい場合は、アクティビティ名とアクティビティ タイプでアクティビティをフィルタすることができます。</span><span class="sxs-lookup"><span data-stu-id="ec3b2-138">You may choose to filter activities by activity name and activity type if you want to specify the exact type of activity (including processor architecture) that you are interested in finding.</span></span> <span data-ttu-id="ec3b2-139">以下の例は、`System.Workflow.ComponentModel.Activity` から派生した "MyActivity" を探します。派生タイプに変更すると、より条件を厳しくすることができます。</span><span class="sxs-lookup"><span data-stu-id="ec3b2-139">The sample below looks for "MyActivity" deriving from `System.Workflow.ComponentModel.Activity`; you can change this to a derived type to make it more restrictive.</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
<ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-name-and-event-any-activity-type"></a><span data-ttu-id="ec3b2-140">アクティビティ名とイベントによるフィルタ (任意のアクティビティ タイプ)</span><span class="sxs-lookup"><span data-stu-id="ec3b2-140">Filter by Activity Name and Event (Any Activity Type)</span></span>  
 <span data-ttu-id="ec3b2-141">この式は、アクティビティ名とアクティビティ イベントに基づいてフィルタを適用します。</span><span class="sxs-lookup"><span data-stu-id="ec3b2-141">This expression filters based on activity name and activity event.</span></span> <span data-ttu-id="ec3b2-142">これは、特定のアクティビティとイベントに対する情報をキャプチャする場合や、特定のアクティビティに対する複数のアクティビティ イベントからデータをキャプチャする場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="ec3b2-142">This is useful when you want to capture information for a specific activity and event or when capturing data from more than one activity event for a given activity.</span></span> <span data-ttu-id="ec3b2-143">たとえば、実行中の MyActivity に対する要素と、Closed に対する要素の、2 つの異なる OnEvent 要素が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="ec3b2-143">For example, you may want two different OnEvent elements, one for MyActivity when it is Executing and one for when it is Closed as shown below.</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetActivityEvent" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>Closed</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-type-and-event"></a><span data-ttu-id="ec3b2-144">アクティビティ タイプとイベントによるフィルタ</span><span class="sxs-lookup"><span data-stu-id="ec3b2-144">Filter by Activity Type and Event</span></span>  
 <span data-ttu-id="ec3b2-145">このフィルタは、単一のアクティビティ イベント中に特定のタイプから派生したすべてのアクティビティに関する情報をキャプチャするのに便利です。</span><span class="sxs-lookup"><span data-stu-id="ec3b2-145">This filter is useful for capturing information about all activities that derive from a specific type during a single activity event.</span></span> <span data-ttu-id="ec3b2-146">たとえば、ワークフロー内を流れる注文書から注文書 ID と日付/タイムスタンプを追跡したいことがあります。</span><span class="sxs-lookup"><span data-stu-id="ec3b2-146">For example, you may be interested in tracking a purchase order ID and date/time stamp from a purchase order as it flows through a workflow.</span></span> <span data-ttu-id="ec3b2-147">使用してこれを実現する、`GetActivityEvent`と`GetActivityType`操作します。</span><span class="sxs-lookup"><span data-stu-id="ec3b2-147">To accomplish this, you use the `GetActivityEvent` and the `GetActivityType` operations.</span></span> <span data-ttu-id="ec3b2-148">`GetActivityType`一致を判断するには、基本データ型とすべての派生型に対して指定された型を比較します。</span><span class="sxs-lookup"><span data-stu-id="ec3b2-148">`GetActivityType` compares a supplied type against the base type and all derived types to determine a match.</span></span> <span data-ttu-id="ec3b2-149">`System.Workflow.ComponentModel.Activity` に対する比較は一致します。これは、すべてのワークフロー アクティビティがそこから派生する必要があるためです。</span><span class="sxs-lookup"><span data-stu-id="ec3b2-149">Comparing against `System.Workflow.ComponentModel.Activity` will match since all workflow activities must derive from it.</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityEvent" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>Closed</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-name-type-and-event"></a><span data-ttu-id="ec3b2-150">アクティビティ名、タイプ、イベントによるフィルタ</span><span class="sxs-lookup"><span data-stu-id="ec3b2-150">Filter by Activity Name, Type, and Event</span></span>  
 <span data-ttu-id="ec3b2-151">名前、タイプ、イベントによるアクティビティのフィルタは、追跡したいアクティビティをさらに絞り込みたい場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="ec3b2-151">Filtering an activity by name, type and event can be useful when you want to better qualify the activity you are interested in tracking.</span></span> <span data-ttu-id="ec3b2-152">たとえば、以下のフィルタは、タイプが `System.Workflow.ComponentModel.Activity` と同じか、またはそこから派生した、終了したアクティビティ "MyActivity" を探します。</span><span class="sxs-lookup"><span data-stu-id="ec3b2-152">For example, the filter below looks for the closed activity "MyActivity" that has a type that is equal to or derives from `System.Workflow.ComponentModel.Activity`.</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetActivityEvent" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>Closed</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
## <a name="workflow-status-event-filter-patterns"></a><span data-ttu-id="ec3b2-153">ワークフロー状態イベントのフィルタ パターン</span><span class="sxs-lookup"><span data-stu-id="ec3b2-153">Workflow Status Event Filter Patterns</span></span>  
 <span data-ttu-id="ec3b2-154">このセクションのフィルタは、ワークフロー イベントをフィルタし、以下の BAM インターセプタの 1 つ以上を使用して、WF の操作をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="ec3b2-154">The filters in this section filter workflow events and use one or more of the following BAM Interceptor for WF custom operations:</span></span>  
  
-   <span data-ttu-id="ec3b2-155">GetWorkflowEvent</span><span class="sxs-lookup"><span data-stu-id="ec3b2-155">GetWorkflowEvent</span></span>  
  
-   <span data-ttu-id="ec3b2-156">GetContextProperty</span><span class="sxs-lookup"><span data-stu-id="ec3b2-156">GetContextProperty</span></span>  
  
### <a name="filter-by-workflow-event"></a><span data-ttu-id="ec3b2-157">ワークフロー イベントによるフィルタ</span><span class="sxs-lookup"><span data-stu-id="ec3b2-157">Filter by Workflow Event</span></span>  
 <span data-ttu-id="ec3b2-158">この式は、ワークフロー イベントによってフィルタを適用します。</span><span class="sxs-lookup"><span data-stu-id="ec3b2-158">This expression filters by workflow event.</span></span>  
  
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
  
## <a name="user-event-filter-patterns"></a><span data-ttu-id="ec3b2-159">ユーザー イベントのフィルタ パターン</span><span class="sxs-lookup"><span data-stu-id="ec3b2-159">User Event Filter Patterns</span></span>  
 <span data-ttu-id="ec3b2-160">アプリケーションが、TrackData メソッドを使用してカスタム情報を追跡する場合、以下の BAM インターセプタを 1 つ以上使用して、WF のユーザー データ操作をカスタマイズするために、データの特性に基づいてフィルタをすることができます。</span><span class="sxs-lookup"><span data-stu-id="ec3b2-160">If your application tracks custom information using the TrackData method, you can filter based on the characteristics of the data using one or more of the following BAM Interceptor for WF custom user data operations:</span></span>  
  
-   <span data-ttu-id="ec3b2-161">GetUserDataType</span><span class="sxs-lookup"><span data-stu-id="ec3b2-161">GetUserDataType</span></span>  
  
-   <span data-ttu-id="ec3b2-162">GetUserKey</span><span class="sxs-lookup"><span data-stu-id="ec3b2-162">GetUserKey</span></span>  
  
-   <span data-ttu-id="ec3b2-163">GetUserData</span><span class="sxs-lookup"><span data-stu-id="ec3b2-163">GetUserData</span></span>  
  
 <span data-ttu-id="ec3b2-164">フィルタでは、これらの操作を以下の操作と組み合わせて、より複雑な式を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="ec3b2-164">The filter can combine these operations with the following to create a more complex expression:</span></span>  
  
-   <span data-ttu-id="ec3b2-165">GetActivityName</span><span class="sxs-lookup"><span data-stu-id="ec3b2-165">GetActivityName</span></span>  
  
-   <span data-ttu-id="ec3b2-166">GetActivityType</span><span class="sxs-lookup"><span data-stu-id="ec3b2-166">GetActivityType</span></span>  
  
-   <span data-ttu-id="ec3b2-167">GetActivityProperty</span><span class="sxs-lookup"><span data-stu-id="ec3b2-167">GetActivityProperty</span></span>  
  
-   <span data-ttu-id="ec3b2-168">GetWorkflowProperty</span><span class="sxs-lookup"><span data-stu-id="ec3b2-168">GetWorkflowProperty</span></span>  
  
-   <span data-ttu-id="ec3b2-169">GetContextProperty</span><span class="sxs-lookup"><span data-stu-id="ec3b2-169">GetContextProperty</span></span>  
  
 <span data-ttu-id="ec3b2-170">フィルタにユーザー データ操作が 1 つも含まれていない場合、フィルタはユーザー イベント フィルタではなく、それを含んでいる OnEvent はエラーになるか (ユーザー操作が対応する更新式に現れる場合)、ユーザー追跡点ではなくアクティビティ追跡点として識別されます。</span><span class="sxs-lookup"><span data-stu-id="ec3b2-170">If your filter does not include at least one user data operation, your filter will not be a user event filter and the enclosing OnEvent will cause an error (if a user operation appears in a corresponding update expression) or will be identified as an activity track point and not a user track point.</span></span>  
  
### <a name="filter-by-activity-name-and-user-data-type"></a><span data-ttu-id="ec3b2-171">アクティビティ名とユーザー データ型によるフィルタ</span><span class="sxs-lookup"><span data-stu-id="ec3b2-171">Filter by Activity Name and User Data Type</span></span>  
 <span data-ttu-id="ec3b2-172">アクティビティ名とユーザー データ型でイベントを識別することが頻繁にあります。</span><span class="sxs-lookup"><span data-stu-id="ec3b2-172">Frequently you can identify an event by activity name and user data type.</span></span> <span data-ttu-id="ec3b2-173">以下の式は、"MyActivity" という名前と、`System.Object` から派生するユーザー データ型でアクティビティをフィルタします。</span><span class="sxs-lookup"><span data-stu-id="ec3b2-173">The following expression filters for an activity named "MyActivity" and a user data type that derives from `System.Object`.</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetUserDataType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Object</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-type-and-user-data-type"></a><span data-ttu-id="ec3b2-174">アクティビティ タイプとユーザー データ型によるフィルタ</span><span class="sxs-lookup"><span data-stu-id="ec3b2-174">Filter by Activity Type and User Data Type</span></span>  
 <span data-ttu-id="ec3b2-175">アクティビティ タイプとユーザー データ型に基づいてフィルタすることができます。</span><span class="sxs-lookup"><span data-stu-id="ec3b2-175">You can filter based on activity type and user data type.</span></span> <span data-ttu-id="ec3b2-176">`GetActivityType` と `GetUserDataType` はどちらも指定されたタイプとすべての派生タイプに対して比較を行うため、これにより、派生元のタイプに基づいてイベントをフィルタするための自由度が得られます。</span><span class="sxs-lookup"><span data-stu-id="ec3b2-176">This grants you the latitude to filter events based on the type the derive from because both `GetActivityType` and `GetUserDataType` compare against the type specified and all derived types.</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetUserDataType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Object</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-name-activity-type-and-user-data-type"></a><span data-ttu-id="ec3b2-177">アクティビティ名、アクティビティ タイプ、ユーザー データ型によるフィルタ</span><span class="sxs-lookup"><span data-stu-id="ec3b2-177">Filter by Activity Name, Activity Type, and User Data Type</span></span>  
 <span data-ttu-id="ec3b2-178">このフィルターは、アクティビティ名を含めることで、アクティビティ タイプとユーザー データ型のフィルター パターンの条件をさらに絞り込みます。</span><span class="sxs-lookup"><span data-stu-id="ec3b2-178">This filter further restricts the activity type and user data type filter pattern by including activity name.</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
    <wf:Operation Name="GetUserDataType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Object</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-name-and-user-key"></a><span data-ttu-id="ec3b2-179">アクティビティ名とユーザー キーによるフィルタ</span><span class="sxs-lookup"><span data-stu-id="ec3b2-179">Filter by Activity Name and User Key</span></span>  
 <span data-ttu-id="ec3b2-180">アプリケーションに、実行時に決定されるキーを使用して `TrackData` を呼び出すアクティビティがある場合は、アクティビティ名とユーザー キーでフィルタしたいことがあります。</span><span class="sxs-lookup"><span data-stu-id="ec3b2-180">If your application has an activity that calls `TrackData` with a key determined at run time, you may want to filter by activity name and user key.</span></span> <span data-ttu-id="ec3b2-181">これにより、特定のキー値に基づいて `OnEvent` をトリガできます。</span><span class="sxs-lookup"><span data-stu-id="ec3b2-181">This will enable you to trigger an `OnEvent` based on a specific key value.</span></span> <span data-ttu-id="ec3b2-182">たとえば、アプリケーションで複数のキーが定義され、アクティビティ内で動的に 1 つを選択することがあります。</span><span class="sxs-lookup"><span data-stu-id="ec3b2-182">For example, your application might define multiple keys and dynamically select one within an activity.</span></span>  
  
 <span data-ttu-id="ec3b2-183">以下の式は、ユーザー キー "ItemKey" を含む "MyActivity" をフィルタします。</span><span class="sxs-lookup"><span data-stu-id="ec3b2-183">The expression below filters for "MyActivity" containing a user key named "ItemKey".</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetUserKey" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>ItemKey</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-type-and-user-key"></a><span data-ttu-id="ec3b2-184">アクティビティ タイプとユーザー キーによるフィルタ</span><span class="sxs-lookup"><span data-stu-id="ec3b2-184">Filter by Activity Type and User Key</span></span>  
 <span data-ttu-id="ec3b2-185">アプリケーションに、実行時に決定されるキーを使用して `TrackData` を呼び出すアクティビティが複数ある場合は、アクティビティ名とユーザー キーでフィルタしたいことがあります。</span><span class="sxs-lookup"><span data-stu-id="ec3b2-185">If your application contain multiple activities that call `TrackData` with a key determined at run time, you may want to filter by activity name and user key.</span></span> <span data-ttu-id="ec3b2-186">これにより、特定のキー値に基づいて `OnEvent` をトリガできます。</span><span class="sxs-lookup"><span data-stu-id="ec3b2-186">This will enable you to trigger an `OnEvent` based on a specific key value.</span></span> <span data-ttu-id="ec3b2-187">たとえば、アプリケーションで複数のキーが定義され、アクティビティ内で動的に 1 つを選択することがあります。</span><span class="sxs-lookup"><span data-stu-id="ec3b2-187">For example, your application might define multiple keys and dynamically select one within an activity.</span></span>  
  
 <span data-ttu-id="ec3b2-188">以下の式は、ユーザー キー "ItemKey" を含む、`System.Workflow.ComponentModel.Activity` から派生したすべてのアクティビティをフィルタします。</span><span class="sxs-lookup"><span data-stu-id="ec3b2-188">The expression below filters for any activity deriving from `System.Workflow.ComponentModel.Activity` containing a user key named "ItemKey".</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetUserKey" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>ItemKey</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-name-activity-type-and-user-key"></a><span data-ttu-id="ec3b2-189">アクティビティ名、アクティビティ タイプ、ユーザー キーによるフィルタ</span><span class="sxs-lookup"><span data-stu-id="ec3b2-189">Filter by Activity Name, Activity Type, and User Key</span></span>  
 <span data-ttu-id="ec3b2-190">このフィルタ パターンは、アクティビティ名をフィルタに含めることで、アクティビティ タイプとユーザー キーのフィルタ パターンの条件をさらに絞込みます。</span><span class="sxs-lookup"><span data-stu-id="ec3b2-190">This filter pattern further refines the activity type and user key filter pattern by including the activity name in the filter.</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
    <wf:Operation Name="GetUserKey" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>key</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-name-user-data-type-and-user-key"></a><span data-ttu-id="ec3b2-191">アクティビティ名、ユーザー データ型、ユーザー キーによるフィルタ</span><span class="sxs-lookup"><span data-stu-id="ec3b2-191">Filter by Activity Name, User Data Type, and User Key</span></span>  
 <span data-ttu-id="ec3b2-192">このフィルタは、特定のユーザー キーを持ち、特定のデータ型から派生した、指定した名前のアクティビティのフィルタ条件を絞り込む場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="ec3b2-192">This filter is useful when you want to restrict your filter to a named activity with a specific user key and deriving from a specific data type.</span></span> <span data-ttu-id="ec3b2-193">たとえば、アクティビティがキー "Item" と、項目の種類に応じて文字列または整数のデータ値を使用して TrackData を呼び出すことがあります。</span><span class="sxs-lookup"><span data-stu-id="ec3b2-193">For example, your activity may call TrackData using the key "Item" and a data value of string or integer depending upon the item type.</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetUserDataType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Object</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
    <wf:Operation Name="GetUserKey" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>key</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-type-user-data-type-and-user-key"></a><span data-ttu-id="ec3b2-194">アクティビティ タイプ、ユーザー データ型、ユーザー キーによるフィルタ</span><span class="sxs-lookup"><span data-stu-id="ec3b2-194">Filter by Activity Type, User Data Type, and User Key</span></span>  
 <span data-ttu-id="ec3b2-195">このフィルタは、特定のユーザー キーを持ち、特定のデータ型から派生した、アクティビティ タイプのフィルタ条件を絞り込む場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="ec3b2-195">This filter is useful when you want to restrict your filter to an activity type with a specific user key and deriving from a specific data type.</span></span> <span data-ttu-id="ec3b2-196">使用するタイプに応じて、アクティビティ名、ユーザー データ型、ユーザー キーを使用した場合よりも条件が厳しくなることも緩くなることもあります。</span><span class="sxs-lookup"><span data-stu-id="ec3b2-196">It can be more restrictive or less restrictive than using activity name, user data type, and user key based on the type used.</span></span> <span data-ttu-id="ec3b2-197">最も派生したタイプを指定するとより条件が厳しくなり、ルート ベース タイプを指定すると条件が緩くなります。</span><span class="sxs-lookup"><span data-stu-id="ec3b2-197">If you specify the most-derived type, it could be more restrictive; if you specify the root base type, it could be less restrictive.</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetUserDataType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Object</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
    <wf:Operation Name="GetUserKey" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>key</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-name-activity-type-user-data-type-and-user-key"></a><span data-ttu-id="ec3b2-198">アクティビティ名、アクティビティ タイプ、ユーザー データ型、ユーザー キーによるフィルタ</span><span class="sxs-lookup"><span data-stu-id="ec3b2-198">Filter by Activity Name, Activity Type, User Data Type, and User Key</span></span>  
 <span data-ttu-id="ec3b2-199">このフィルタは、アクティビティ名を追加することで、アクティビティ タイプとユーザー データ型、ユーザー キーのパターンの条件をさらに絞り込みます。</span><span class="sxs-lookup"><span data-stu-id="ec3b2-199">This filter further restricts the activity type, user data type, and user key pattern by the addition of activity name.</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
    <wf:Operation Name="GetUserDataType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Object</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
    <wf:Operation Name="GetUserKey" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>key</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>   
```