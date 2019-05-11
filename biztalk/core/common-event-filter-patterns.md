---
title: 一般的なイベント フィルタ パターン |Microsoft Docs
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
ms.openlocfilehash: 05a81dcac4e7bd43a0a60e042d285c56a9fcc35c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357131"
---
# <a name="common-event-filter-patterns"></a><span data-ttu-id="12ab9-102">一般的なイベント フィルタ パターン</span><span class="sxs-lookup"><span data-stu-id="12ab9-102">Common Event Filter Patterns</span></span>
<span data-ttu-id="12ab9-103">BAM インターセプターの Windows Workflow Foundation (WF) を操作するときは、するで、インターセプタ構成ファイルが頻繁に使用がパターンの一般的なフィルターのセットがある可能性がありますに注意してください。</span><span class="sxs-lookup"><span data-stu-id="12ab9-103">As you work with the BAM Interceptor for Windows Workflow Foundation (WF), you will likely notice that there are a set of common filter patterns that you will use frequently in your interceptor configuration files.</span></span> <span data-ttu-id="12ab9-104">これらのフィルタ パターンの一部は、アプリケーションと環境に対して一意では、中に、環境間で、さまざまなアプリケーションで多数のパターンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="12ab9-104">While some of these filter patterns will be unique to your applications and environments, many patterns can be used across environments and in diverse applications.</span></span>  
  
 <span data-ttu-id="12ab9-105">このトピックでは、WF アプリケーション用に記述されたインターセプタ構成ファイルで使用される一般的なフィルタ パターンの多くを収集します。</span><span class="sxs-lookup"><span data-stu-id="12ab9-105">This topic collects many of the common filter patterns used by interceptor configuration files written for WF applications.</span></span> <span data-ttu-id="12ab9-106">パターンは、Windows Workflow Foundation 追跡イベントでグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="12ab9-106">Patterns are grouped by Windows Workflow Foundation tracking event:</span></span>  
  
- <span data-ttu-id="12ab9-107">アクティビティ ステータス イベント</span><span class="sxs-lookup"><span data-stu-id="12ab9-107">Activity status events</span></span>  
  
- <span data-ttu-id="12ab9-108">ワークフロー ステータス イベント</span><span class="sxs-lookup"><span data-stu-id="12ab9-108">Workflow status events</span></span>  
  
- <span data-ttu-id="12ab9-109">ユーザー イベント</span><span class="sxs-lookup"><span data-stu-id="12ab9-109">User events</span></span>  
  
  <span data-ttu-id="12ab9-110">各パターンをインターセプタ構成ファイルにコピーし、アプリケーションに合うように変更できます。</span><span class="sxs-lookup"><span data-stu-id="12ab9-110">Each pattern can be copied into your interceptor configuration file and modified to suit your application.</span></span>  
  
## <a name="activity-status-event-filter-patterns"></a><span data-ttu-id="12ab9-111">アクティビティ ステータス イベントのフィルタ パターン</span><span class="sxs-lookup"><span data-stu-id="12ab9-111">Activity Status Event Filter Patterns</span></span>  
 <span data-ttu-id="12ab9-112">アクティビティは、ワークフローの基本的な構成要素です。</span><span class="sxs-lookup"><span data-stu-id="12ab9-112">Activities are the fundamental building blocks of workflows.</span></span> <span data-ttu-id="12ab9-113">ワークフローは、ツリー構造で階層的に編成されているアクティビティのセットです。</span><span class="sxs-lookup"><span data-stu-id="12ab9-113">A workflow is a set of activities that are organized hierarchically in a tree structure.</span></span> <span data-ttu-id="12ab9-114">アクティビティは、ワークフローのアクションを表します。</span><span class="sxs-lookup"><span data-stu-id="12ab9-114">An activity represents an action in a workflow.</span></span> <span data-ttu-id="12ab9-115">おくと、遅延などの単純な操作または複数の子アクティビティで構成される複合アクティビティであることができます。</span><span class="sxs-lookup"><span data-stu-id="12ab9-115">It can be a simple action such as a delay, or it can be a composite activity that consists of several child activities.</span></span>  
  
 <span data-ttu-id="12ab9-116">このセクションではフィルターには、活動と WF カスタム操作の 1 つ以上の次の BAM インターセプターの使用がフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="12ab9-116">The filters in this section filter activities and use one or more of the following BAM Interceptor for WF custom operations:</span></span>  
  
-   <span data-ttu-id="12ab9-117">GetActivityName</span><span class="sxs-lookup"><span data-stu-id="12ab9-117">GetActivityName</span></span>  
  
-   <span data-ttu-id="12ab9-118">GetActivityEvent</span><span class="sxs-lookup"><span data-stu-id="12ab9-118">GetActivityEvent</span></span>  
  
-   <span data-ttu-id="12ab9-119">GetActivityType</span><span class="sxs-lookup"><span data-stu-id="12ab9-119">GetActivityType</span></span>  
  
-   <span data-ttu-id="12ab9-120">GetActivityProperty</span><span class="sxs-lookup"><span data-stu-id="12ab9-120">GetActivityProperty</span></span>  
  
-   <span data-ttu-id="12ab9-121">GetWorkflowProperty</span><span class="sxs-lookup"><span data-stu-id="12ab9-121">GetWorkflowProperty</span></span>  
  
-   <span data-ttu-id="12ab9-122">GetContextProperty</span><span class="sxs-lookup"><span data-stu-id="12ab9-122">GetContextProperty</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="12ab9-123">フィルターで GetActivityEvent 操作を使用しない場合、フィルターは終了したアクティビティ イベントのみになります。</span><span class="sxs-lookup"><span data-stu-id="12ab9-123">If you do not use the GetActivityEvent operation in your filter, your filter will look for Closed activity events only.</span></span>  
  
### <a name="filter-by-activity-name-closed-activity"></a><span data-ttu-id="12ab9-124">アクティビティ名 (終了したアクティビティ) でフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="12ab9-124">Filter by Activity Name (Closed Activity)</span></span>  
 <span data-ttu-id="12ab9-125">頻繁に終了したアクティビティ イベントのアクティビティ名でフィルター処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="12ab9-125">You will frequently need to filter for closed activity events by activity name.</span></span> <span data-ttu-id="12ab9-126">これは、機能は、ファイルの受信やデータベースへのデータの書き込みなどの特定のアクティビティからデータをキャプチャする必要がある場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="12ab9-126">This is useful when you need to capture data from a specific activity such as receiving a file or writing data to a database.</span></span>  
  
 <span data-ttu-id="12ab9-127">終了したアクティビティのフィルターの下のフラグメントでは、"MyActivity"という名前です。</span><span class="sxs-lookup"><span data-stu-id="12ab9-127">The fragment below filters for a closed activity named "MyActivity".</span></span>  
  
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
  
### <a name="filter-by-activity-type-closed-activity-event"></a><span data-ttu-id="12ab9-128">アクティビティの種類 (終了したアクティビティ イベント) でフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="12ab9-128">Filter by Activity Type (Closed Activity Event)</span></span>  
 <span data-ttu-id="12ab9-129">名前ではなく型によるアクティビティをフィルター処理に必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="12ab9-129">There will be times when you want to filter an activity by type rather than name.</span></span> <span data-ttu-id="12ab9-130">たとえば、ワークフローでアクティビティ名とすべてのアクティビティの日付/時刻スタンプを保存する場合があります。</span><span class="sxs-lookup"><span data-stu-id="12ab9-130">For example, you may want to save activity name and a date/time stamp for all activities in a workflow.</span></span> <span data-ttu-id="12ab9-131">使用してこれを実現する、`GetActivityType`操作。</span><span class="sxs-lookup"><span data-stu-id="12ab9-131">To accomplish this, you use the `GetActivityType` operation.</span></span> <span data-ttu-id="12ab9-132">`GetActivityType` 一致を判断するには、基本データ型とすべての派生型に対して指定された型を比較します。</span><span class="sxs-lookup"><span data-stu-id="12ab9-132">`GetActivityType` compares a supplied type against the base type and all derived types to determine a match.</span></span> <span data-ttu-id="12ab9-133">比較対象`System.Workflow.ComponentModel.Activity`すべてのワークフロー アクティビティがそこから派生する必要がありますが、一致します。</span><span class="sxs-lookup"><span data-stu-id="12ab9-133">Comparing against `System.Workflow.ComponentModel.Activity` will match since all workflow activities must derive from it.</span></span>  
  
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
  
### <a name="filter-by-activity-event-any-activity-type"></a><span data-ttu-id="12ab9-134">(任意のアクティビティ タイプ) のアクティビティ イベントによるフィルタします。</span><span class="sxs-lookup"><span data-stu-id="12ab9-134">Filter by Activity Event (Any Activity Type)</span></span>  
 <span data-ttu-id="12ab9-135">このフィルターでは、GetActivityEvent 操作を使用して、閉じたアクティビティを検索します。</span><span class="sxs-lookup"><span data-stu-id="12ab9-135">This filter uses the GetActivityEvent operation to find closed activities.</span></span> <span data-ttu-id="12ab9-136">(名前や種類によって、特定のイベント) とすべての closed イベントに関する情報をキャプチャするため便利です。</span><span class="sxs-lookup"><span data-stu-id="12ab9-136">It is useful for capturing information about all closed events (versus a specific event by name or type).</span></span>  
  
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
  
### <a name="filter-by-activity-name-and-type-closed-activity-event"></a><span data-ttu-id="12ab9-137">アクティビティの名前でフィルター処理し、(終了したアクティビティ イベント) を入力</span><span class="sxs-lookup"><span data-stu-id="12ab9-137">Filter by Activity Name and Type (Closed Activity Event)</span></span>  
 <span data-ttu-id="12ab9-138">検索の関心をアクティビティ (プロセッサ アーキテクチャを含む) の正確な型を指定する場合は、アクティビティ名とアクティビティの種類別の活動をフィルター処理することができます。</span><span class="sxs-lookup"><span data-stu-id="12ab9-138">You may choose to filter activities by activity name and activity type if you want to specify the exact type of activity (including processor architecture) that you are interested in finding.</span></span> <span data-ttu-id="12ab9-139">次のサンプルでは"myactivity"から派生する`System.Workflow.ComponentModel.Activity`; より制限の厳しいする派生型に変更することができます。</span><span class="sxs-lookup"><span data-stu-id="12ab9-139">The sample below looks for "MyActivity" deriving from `System.Workflow.ComponentModel.Activity`; you can change this to a derived type to make it more restrictive.</span></span>  
  
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
  
### <a name="filter-by-activity-name-and-event-any-activity-type"></a><span data-ttu-id="12ab9-140">アクティビティ名とイベント (アクティビティの種類) でフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="12ab9-140">Filter by Activity Name and Event (Any Activity Type)</span></span>  
 <span data-ttu-id="12ab9-141">アクティビティ名とアクティビティ イベントに基づいて、この式のフィルター。</span><span class="sxs-lookup"><span data-stu-id="12ab9-141">This expression filters based on activity name and activity event.</span></span> <span data-ttu-id="12ab9-142">これは、機能は、特定のアクティビティとイベントの情報をキャプチャするとき、または、特定のアクティビティの 1 つ以上のアクティビティ イベントからのデータをキャプチャするときに便利です。</span><span class="sxs-lookup"><span data-stu-id="12ab9-142">This is useful when you want to capture information for a specific activity and event or when capturing data from more than one activity event for a given activity.</span></span> <span data-ttu-id="12ab9-143">たとえば、中の MyActivity Executing とに 1 つが閉じられる次のように 1 つずつ 2 つの異なる OnEvent 要素たい場合があります。</span><span class="sxs-lookup"><span data-stu-id="12ab9-143">For example, you may want two different OnEvent elements, one for MyActivity when it is Executing and one for when it is Closed as shown below.</span></span>  
  
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
  
### <a name="filter-by-activity-type-and-event"></a><span data-ttu-id="12ab9-144">アクティビティの種類とイベントによるフィルタします。</span><span class="sxs-lookup"><span data-stu-id="12ab9-144">Filter by Activity Type and Event</span></span>  
 <span data-ttu-id="12ab9-145">このフィルターは、1 つのアクティビティ イベント中に特定の型から派生するすべてのアクティビティに関する情報をキャプチャするために便利です。</span><span class="sxs-lookup"><span data-stu-id="12ab9-145">This filter is useful for capturing information about all activities that derive from a specific type during a single activity event.</span></span> <span data-ttu-id="12ab9-146">たとえば、注文書 ID を追跡したいしてワークフロー内を流れるに注文書からスタンプを日付/時刻。</span><span class="sxs-lookup"><span data-stu-id="12ab9-146">For example, you may be interested in tracking a purchase order ID and date/time stamp from a purchase order as it flows through a workflow.</span></span> <span data-ttu-id="12ab9-147">使用してこれを実現する、`GetActivityEvent`と`GetActivityType`操作。</span><span class="sxs-lookup"><span data-stu-id="12ab9-147">To accomplish this, you use the `GetActivityEvent` and the `GetActivityType` operations.</span></span> <span data-ttu-id="12ab9-148">`GetActivityType` 一致を判断するには、基本データ型とすべての派生型に対して指定された型を比較します。</span><span class="sxs-lookup"><span data-stu-id="12ab9-148">`GetActivityType` compares a supplied type against the base type and all derived types to determine a match.</span></span> <span data-ttu-id="12ab9-149">比較対象`System.Workflow.ComponentModel.Activity`すべてのワークフロー アクティビティがそこから派生する必要がありますが、一致します。</span><span class="sxs-lookup"><span data-stu-id="12ab9-149">Comparing against `System.Workflow.ComponentModel.Activity` will match since all workflow activities must derive from it.</span></span>  
  
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
  
### <a name="filter-by-activity-name-type-and-event"></a><span data-ttu-id="12ab9-150">アクティビティ名、型、イベントによるフィルタします。</span><span class="sxs-lookup"><span data-stu-id="12ab9-150">Filter by Activity Name, Type, and Event</span></span>  
 <span data-ttu-id="12ab9-151">アクティビティをフィルター処理、名前、タイプとイベントできます追跡興味のあるアクティビティをさらに絞り込みたい場合。</span><span class="sxs-lookup"><span data-stu-id="12ab9-151">Filtering an activity by name, type and event can be useful when you want to better qualify the activity you are interested in tracking.</span></span> <span data-ttu-id="12ab9-152">たとえば次のフィルターでは、終了したアクティビティ"MyActivity"に等しいかから派生する型を持つ`System.Workflow.ComponentModel.Activity`します。</span><span class="sxs-lookup"><span data-stu-id="12ab9-152">For example, the filter below looks for the closed activity "MyActivity" that has a type that is equal to or derives from `System.Workflow.ComponentModel.Activity`.</span></span>  
  
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
  
## <a name="workflow-status-event-filter-patterns"></a><span data-ttu-id="12ab9-153">ワークフロー ステータス イベントのフィルタ パターン</span><span class="sxs-lookup"><span data-stu-id="12ab9-153">Workflow Status Event Filter Patterns</span></span>  
 <span data-ttu-id="12ab9-154">このセクションでは、フィルターは、WF の操作をカスタムの使用を次の BAM インターセプタの 1 つ以上のワークフロー イベントとフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="12ab9-154">The filters in this section filter workflow events and use one or more of the following BAM Interceptor for WF custom operations:</span></span>  
  
-   <span data-ttu-id="12ab9-155">GetWorkflowEvent</span><span class="sxs-lookup"><span data-stu-id="12ab9-155">GetWorkflowEvent</span></span>  
  
-   <span data-ttu-id="12ab9-156">GetContextProperty</span><span class="sxs-lookup"><span data-stu-id="12ab9-156">GetContextProperty</span></span>  
  
### <a name="filter-by-workflow-event"></a><span data-ttu-id="12ab9-157">ワークフロー イベントによるフィルタします。</span><span class="sxs-lookup"><span data-stu-id="12ab9-157">Filter by Workflow Event</span></span>  
 <span data-ttu-id="12ab9-158">この式は、ワークフロー イベントをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="12ab9-158">This expression filters by workflow event.</span></span>  
  
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
  
## <a name="user-event-filter-patterns"></a><span data-ttu-id="12ab9-159">ユーザー イベントのフィルタ パターン</span><span class="sxs-lookup"><span data-stu-id="12ab9-159">User Event Filter Patterns</span></span>  
 <span data-ttu-id="12ab9-160">フィルター処理できるアプリケーションでは、TrackData メソッドを使用してカスタム情報を追跡している場合、次の BAM インターセプタの 1 つ以上を使用して、WF カスタム ユーザー データの操作のデータの特性に基づき。</span><span class="sxs-lookup"><span data-stu-id="12ab9-160">If your application tracks custom information using the TrackData method, you can filter based on the characteristics of the data using one or more of the following BAM Interceptor for WF custom user data operations:</span></span>  
  
- <span data-ttu-id="12ab9-161">GetUserDataType</span><span class="sxs-lookup"><span data-stu-id="12ab9-161">GetUserDataType</span></span>  
  
- <span data-ttu-id="12ab9-162">GetUserKey</span><span class="sxs-lookup"><span data-stu-id="12ab9-162">GetUserKey</span></span>  
  
- <span data-ttu-id="12ab9-163">GetUserData</span><span class="sxs-lookup"><span data-stu-id="12ab9-163">GetUserData</span></span>  
  
  <span data-ttu-id="12ab9-164">フィルターより複雑な式を作成するには、次のようにこれらの操作を組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="12ab9-164">The filter can combine these operations with the following to create a more complex expression:</span></span>  
  
- <span data-ttu-id="12ab9-165">GetActivityName</span><span class="sxs-lookup"><span data-stu-id="12ab9-165">GetActivityName</span></span>  
  
- <span data-ttu-id="12ab9-166">GetActivityType</span><span class="sxs-lookup"><span data-stu-id="12ab9-166">GetActivityType</span></span>  
  
- <span data-ttu-id="12ab9-167">GetActivityProperty</span><span class="sxs-lookup"><span data-stu-id="12ab9-167">GetActivityProperty</span></span>  
  
- <span data-ttu-id="12ab9-168">GetWorkflowProperty</span><span class="sxs-lookup"><span data-stu-id="12ab9-168">GetWorkflowProperty</span></span>  
  
- <span data-ttu-id="12ab9-169">GetContextProperty</span><span class="sxs-lookup"><span data-stu-id="12ab9-169">GetContextProperty</span></span>  
  
  <span data-ttu-id="12ab9-170">フィルターには少なくとも 1 人のユーザー データの操作は含まれません場合は、フィルターには、ユーザー イベントのフィルターはできませんユーザー操作は、対応する更新式に表示されます) であれば、それを囲む OnEvent のエラーが発生するか、アクティビティ追跡ポイントとして識別されます。およびユーザー追跡ポイントではありません。</span><span class="sxs-lookup"><span data-stu-id="12ab9-170">If your filter does not include at least one user data operation, your filter will not be a user event filter and the enclosing OnEvent will cause an error (if a user operation appears in a corresponding update expression) or will be identified as an activity track point and not a user track point.</span></span>  
  
### <a name="filter-by-activity-name-and-user-data-type"></a><span data-ttu-id="12ab9-171">アクティビティ名とユーザー データ型によるフィルタします。</span><span class="sxs-lookup"><span data-stu-id="12ab9-171">Filter by Activity Name and User Data Type</span></span>  
 <span data-ttu-id="12ab9-172">頻繁にアクティビティ名とユーザー データ型でイベントを識別できます。</span><span class="sxs-lookup"><span data-stu-id="12ab9-172">Frequently you can identify an event by activity name and user data type.</span></span> <span data-ttu-id="12ab9-173">"MyActivity"という名前のユーザーのデータ型から派生したアクティビティの次の式フィルター`System.Object`します。</span><span class="sxs-lookup"><span data-stu-id="12ab9-173">The following expression filters for an activity named "MyActivity" and a user data type that derives from `System.Object`.</span></span>  
  
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
  
### <a name="filter-by-activity-type-and-user-data-type"></a><span data-ttu-id="12ab9-174">アクティビティ タイプとユーザー データ型によるフィルタします。</span><span class="sxs-lookup"><span data-stu-id="12ab9-174">Filter by Activity Type and User Data Type</span></span>  
 <span data-ttu-id="12ab9-175">フィルター処理できますアクティビティ タイプとユーザー データ型に基づいています。</span><span class="sxs-lookup"><span data-stu-id="12ab9-175">You can filter based on activity type and user data type.</span></span> <span data-ttu-id="12ab9-176">イベントをフィルター処理の緯度の種類に基づいて、派生元ため、これを許可両方`GetActivityType`と`GetUserDataType`指定された型とすべての派生型を比較します。</span><span class="sxs-lookup"><span data-stu-id="12ab9-176">This grants you the latitude to filter events based on the type the derive from because both `GetActivityType` and `GetUserDataType` compare against the type specified and all derived types.</span></span>  
  
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
  
### <a name="filter-by-activity-name-activity-type-and-user-data-type"></a><span data-ttu-id="12ab9-177">アクティビティ名、アクティビティの種類、ユーザー データ型によるフィルタします。</span><span class="sxs-lookup"><span data-stu-id="12ab9-177">Filter by Activity Name, Activity Type, and User Data Type</span></span>  
 <span data-ttu-id="12ab9-178">さらに、このフィルターは、アクティビティ名を含めることによって、アクティビティ タイプとユーザー データ型のフィルター パターンを制限します。</span><span class="sxs-lookup"><span data-stu-id="12ab9-178">This filter further restricts the activity type and user data type filter pattern by including activity name.</span></span>  
  
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
  
### <a name="filter-by-activity-name-and-user-key"></a><span data-ttu-id="12ab9-179">アクティビティ名とユーザー キーによるフィルタします。</span><span class="sxs-lookup"><span data-stu-id="12ab9-179">Filter by Activity Name and User Key</span></span>  
 <span data-ttu-id="12ab9-180">アプリケーションにアクティビティを呼び出す場合`TrackData`実行時に決定するキーを持つアクティビティ名とユーザー キーでフィルター処理することがあります。</span><span class="sxs-lookup"><span data-stu-id="12ab9-180">If your application has an activity that calls `TrackData` with a key determined at run time, you may want to filter by activity name and user key.</span></span> <span data-ttu-id="12ab9-181">これはトリガーすることにより、`OnEvent`特定のキー値に基づいて。</span><span class="sxs-lookup"><span data-stu-id="12ab9-181">This will enable you to trigger an `OnEvent` based on a specific key value.</span></span> <span data-ttu-id="12ab9-182">たとえば、アプリケーションは、複数のキーを定義し、アクティビティ内で 1 つを動的に選択します。</span><span class="sxs-lookup"><span data-stu-id="12ab9-182">For example, your application might define multiple keys and dynamically select one within an activity.</span></span>  
  
 <span data-ttu-id="12ab9-183">ユーザー キーを含む"myactivity"は、以下のフィルターの式では、"ItemKey"という名前です。</span><span class="sxs-lookup"><span data-stu-id="12ab9-183">The expression below filters for "MyActivity" containing a user key named "ItemKey".</span></span>  
  
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
  
### <a name="filter-by-activity-type-and-user-key"></a><span data-ttu-id="12ab9-184">アクティビティ タイプとユーザー キーによるフィルタします。</span><span class="sxs-lookup"><span data-stu-id="12ab9-184">Filter by Activity Type and User Key</span></span>  
 <span data-ttu-id="12ab9-185">アプリケーションには、複数のアクティビティを呼び出すことが含まれている場合`TrackData`実行時に決定するキーを持つアクティビティ名とユーザー キーでフィルター処理することがあります。</span><span class="sxs-lookup"><span data-stu-id="12ab9-185">If your application contain multiple activities that call `TrackData` with a key determined at run time, you may want to filter by activity name and user key.</span></span> <span data-ttu-id="12ab9-186">これはトリガーすることにより、`OnEvent`特定のキー値に基づいて。</span><span class="sxs-lookup"><span data-stu-id="12ab9-186">This will enable you to trigger an `OnEvent` based on a specific key value.</span></span> <span data-ttu-id="12ab9-187">たとえば、アプリケーションは、複数のキーを定義し、アクティビティ内で 1 つを動的に選択します。</span><span class="sxs-lookup"><span data-stu-id="12ab9-187">For example, your application might define multiple keys and dynamically select one within an activity.</span></span>  
  
 <span data-ttu-id="12ab9-188">フィルターから派生する任意のアクティビティを以下の式`System.Workflow.ComponentModel.Activity`"ItemKey"をという名前のユーザー キーを格納します。</span><span class="sxs-lookup"><span data-stu-id="12ab9-188">The expression below filters for any activity deriving from `System.Workflow.ComponentModel.Activity` containing a user key named "ItemKey".</span></span>  
  
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
  
### <a name="filter-by-activity-name-activity-type-and-user-key"></a><span data-ttu-id="12ab9-189">アクティビティ名、アクティビティの種類、ユーザー キーによるフィルタします。</span><span class="sxs-lookup"><span data-stu-id="12ab9-189">Filter by Activity Name, Activity Type, and User Key</span></span>  
 <span data-ttu-id="12ab9-190">さらに、このフィルタ パターンは、フィルターにアクティビティ名を含めることでアクティビティ タイプとユーザー キーのフィルタ パターンを細分化します。</span><span class="sxs-lookup"><span data-stu-id="12ab9-190">This filter pattern further refines the activity type and user key filter pattern by including the activity name in the filter.</span></span>  
  
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
  
### <a name="filter-by-activity-name-user-data-type-and-user-key"></a><span data-ttu-id="12ab9-191">アクティビティ名、ユーザー データ型、ユーザー キーによるフィルタします。</span><span class="sxs-lookup"><span data-stu-id="12ab9-191">Filter by Activity Name, User Data Type, and User Key</span></span>  
 <span data-ttu-id="12ab9-192">このフィルターは、特定のユーザー キーを持つ名前付きのアクティビティに、フィルターを制限する場合に有用と特定のデータ型から派生します。</span><span class="sxs-lookup"><span data-stu-id="12ab9-192">This filter is useful when you want to restrict your filter to a named activity with a specific user key and deriving from a specific data type.</span></span> <span data-ttu-id="12ab9-193">たとえば、アクティビティは、キー"Item"と、データの文字列または整数の項目の種類に応じて値を使用して TrackData を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="12ab9-193">For example, your activity may call TrackData using the key "Item" and a data value of string or integer depending upon the item type.</span></span>  
  
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
  
### <a name="filter-by-activity-type-user-data-type-and-user-key"></a><span data-ttu-id="12ab9-194">アクティビティの種類、ユーザー データ型、ユーザー キーによるフィルタします。</span><span class="sxs-lookup"><span data-stu-id="12ab9-194">Filter by Activity Type, User Data Type, and User Key</span></span>  
 <span data-ttu-id="12ab9-195">このフィルターは、特定のユーザー キーを使用して、フィルターをアクティビティの種類に制限する場合に有用と特定のデータ型から派生します。</span><span class="sxs-lookup"><span data-stu-id="12ab9-195">This filter is useful when you want to restrict your filter to an activity type with a specific user key and deriving from a specific data type.</span></span> <span data-ttu-id="12ab9-196">制限の厳しいまたはアクティビティ名、ユーザー データ型、および使用の種類に基づくユーザー キーを使用するよりも少ないを使用できます。</span><span class="sxs-lookup"><span data-stu-id="12ab9-196">It can be more restrictive or less restrictive than using activity name, user data type, and user key based on the type used.</span></span> <span data-ttu-id="12ab9-197">最も多く派生された型を指定する場合が考えられます。 より制限の厳しいルートの基本型を指定する場合より制限の少ないが考えられます。</span><span class="sxs-lookup"><span data-stu-id="12ab9-197">If you specify the most-derived type, it could be more restrictive; if you specify the root base type, it could be less restrictive.</span></span>  
  
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
  
### <a name="filter-by-activity-name-activity-type-user-data-type-and-user-key"></a><span data-ttu-id="12ab9-198">アクティビティ名、アクティビティの種類、ユーザー データ型、ユーザー キーによるフィルタします。</span><span class="sxs-lookup"><span data-stu-id="12ab9-198">Filter by Activity Name, Activity Type, User Data Type, and User Key</span></span>  
 <span data-ttu-id="12ab9-199">さらに、このフィルターは、アクティビティ名を追加して、アクティビティの種類、ユーザー データ型、およびユーザー キーのパターンを制限します。</span><span class="sxs-lookup"><span data-stu-id="12ab9-199">This filter further restricts the activity type, user data type, and user key pattern by the addition of activity name.</span></span>  
  
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