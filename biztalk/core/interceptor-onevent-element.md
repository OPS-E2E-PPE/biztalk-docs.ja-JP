---
title: インターセプタ OnEvent 要素 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d684ac8e-61bc-410b-97a2-6fd3549e0d97
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d6fb70b2536dbf5db5b0abc03bc194de154b4317
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257610"
---
# <a name="interceptor-onevent-element"></a><span data-ttu-id="903fa-102">インターセプタ OnEvent 要素</span><span class="sxs-lookup"><span data-stu-id="903fa-102">Interceptor OnEvent Element</span></span>
<span data-ttu-id="903fa-103">**OnEvent**要素が外側の BAM アクティビティにマップされている実際のイベントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="903fa-103">The **OnEvent** element describes one real event that is mapped to the enclosing BAM activity.</span></span>  
  
## <a name="format"></a><span data-ttu-id="903fa-104">Format</span><span class="sxs-lookup"><span data-stu-id="903fa-104">Format</span></span>  
 <span data-ttu-id="903fa-105">`OnEvent` 要素には、イベント フィルタ、関連付け ID を指定する子要素が含まれています。オプションで、更新するデータ、参照データ、継続トークンを指定する子要素が含まれていることもあります。</span><span class="sxs-lookup"><span data-stu-id="903fa-105">The `OnEvent` element contains child elements that specify an event filter, the correlation ID and optionally which data to update, reference data, and a continuation token.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="903fa-106">属性</span><span class="sxs-lookup"><span data-stu-id="903fa-106">Attributes</span></span>  
  
|<span data-ttu-id="903fa-107">属性名</span><span class="sxs-lookup"><span data-stu-id="903fa-107">Attribute name</span></span>|<span data-ttu-id="903fa-108">Description</span><span class="sxs-lookup"><span data-stu-id="903fa-108">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="903fa-109">名前</span><span class="sxs-lookup"><span data-stu-id="903fa-109">Name</span></span>|<span data-ttu-id="903fa-110">このイベントのユーザー定義の名前です。</span><span class="sxs-lookup"><span data-stu-id="903fa-110">User-defined name for this event.</span></span>|  
|<span data-ttu-id="903fa-111">ソース</span><span class="sxs-lookup"><span data-stu-id="903fa-111">Source</span></span>|<span data-ttu-id="903fa-112">イベントの名前に表示されるソース、 **EventSource**要素。</span><span class="sxs-lookup"><span data-stu-id="903fa-112">Name of the event source as it appears in an **EventSource** element.</span></span>|  
|<span data-ttu-id="903fa-113">IsBegin</span><span class="sxs-lookup"><span data-stu-id="903fa-113">IsBegin</span></span>|<span data-ttu-id="903fa-114">イベントが新しい BAM アクティビティを開始するか (`true`)、開始しないか (`false`) を示すブール値です。</span><span class="sxs-lookup"><span data-stu-id="903fa-114">Boolean value indicating whether the event is the beginning of a new BAM activity (`true`) or not (`false`).</span></span>|  
|<span data-ttu-id="903fa-115">IsEnd</span><span class="sxs-lookup"><span data-stu-id="903fa-115">IsEnd</span></span>|<span data-ttu-id="903fa-116">イベントが BAM アクティビティを終了するか (`true`)、終了しないか (`false`) を示すブール値です。</span><span class="sxs-lookup"><span data-stu-id="903fa-116">Boolean value indicating whether the event is the end of a BAM activity (`true`) or not (`false`).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="903fa-117">子要素</span><span class="sxs-lookup"><span data-stu-id="903fa-117">Child Elements</span></span>  
  
|<span data-ttu-id="903fa-118">実行状態</span><span class="sxs-lookup"><span data-stu-id="903fa-118">Execution status</span></span>|<span data-ttu-id="903fa-119">Description</span><span class="sxs-lookup"><span data-stu-id="903fa-119">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="903fa-120">[フィルター]</span><span class="sxs-lookup"><span data-stu-id="903fa-120">Filter</span></span>|<span data-ttu-id="903fa-121">イベントを特定の条件に限定する方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="903fa-121">Provides a way to limit the event to specific criteria.</span></span>|  
|<span data-ttu-id="903fa-122">CorrelationID</span><span class="sxs-lookup"><span data-stu-id="903fa-122">CorrelationID</span></span>|<span data-ttu-id="903fa-123">関連付け ID (アクティビティ インスタンス ID) を指定します。</span><span class="sxs-lookup"><span data-stu-id="903fa-123">Specifies the correlation ID (the activity instance ID).</span></span>|  
|<span data-ttu-id="903fa-124">ContinuationToken</span><span class="sxs-lookup"><span data-stu-id="903fa-124">ContinuationToken</span></span>|<span data-ttu-id="903fa-125">継続トークンを指定します。これは、将来のイベントにおいて、同じアクティビティ インスタンスに使用される関連付け ID です。</span><span class="sxs-lookup"><span data-stu-id="903fa-125">Specifies the continuation token, a correlation ID that is used by future events that will contribute to the same activity instance.</span></span>|  
|<span data-ttu-id="903fa-126">Update</span><span class="sxs-lookup"><span data-stu-id="903fa-126">Update</span></span>|<span data-ttu-id="903fa-127">イベントから抽出して BAM アクティビティにインポートするデータを指定します。</span><span class="sxs-lookup"><span data-stu-id="903fa-127">Specifies the data to extract from the event and import into the BAM activity.</span></span>|  
|<span data-ttu-id="903fa-128">リファレンス</span><span class="sxs-lookup"><span data-stu-id="903fa-128">Reference</span></span>|<span data-ttu-id="903fa-129">BAM アクティビティにリレーションシップを追加します。</span><span class="sxs-lookup"><span data-stu-id="903fa-129">Adds a relationship to a BAM activity.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="903fa-130">解説</span><span class="sxs-lookup"><span data-stu-id="903fa-130">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="903fa-131">例</span><span class="sxs-lookup"><span data-stu-id="903fa-131">Example</span></span>  
 <span data-ttu-id="903fa-132">次の例は、一般的な**OnEvent** WF のブロック。</span><span class="sxs-lookup"><span data-stu-id="903fa-132">The following example shows a typical **OnEvent** block for WF:</span></span>  
  
```  
<ic:OnEvent Name="BeginAct" IsBegin="true" Source="ResWF">  
  <ic:Filter>  
    <ic:Expression>  
      <wf:Operation Name="GetActivityName"/>  
      <ic:Operation Name="Constant">  
        <ic:Argument>FoodAndDrinksPolicy</ic:Argument>  
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
  <ic:CorrelationID>  
    <ic:Expression>  
      <wf:Operation Name="GetContextProperty">  
        <wf:Argument>InstanceId</wf:Argument>  
      </wf:Operation>  
    </ic:Expression>  
  </ic:CorrelationID>  
  <ic:Update DataItemName="StartOrderProcessing" Type="DATETIME">  
    <ic:Expression>  
      <wf:Operation Name="GetContextProperty">  
        <wf:Argument>EventTime</wf:Argument>  
      </wf:Operation>  
    </ic:Expression>  
  </ic:Update>  
  <ic:Update DataItemName="FoodItem" Type="NVARCHAR">  
    <ic:Expression>  
      <wf:Operation Name="GetWorkflowProperty">  
        <wf:Argument>foodItem</wf:Argument>  
      </wf:Operation>  
    </ic:Expression>  
  </ic:Update>  
</ic:OnEvent>  
```  
  
 <span data-ttu-id="903fa-133">この例は、一般的な**OnEvent** WCF サービスをブロックします。</span><span class="sxs-lookup"><span data-stu-id="903fa-133">This example shows a typical **OnEvent** block for WCF service:</span></span>  
  
```  
<ic:OnEvent IsBegin="true" IsEnd ="false" Name ="AuthorizationRequestService" Source="ESCreditCardService">  
  <ic:Filter>  
    <ic:Expression>  
      <wcf:Operation Name="GetServiceContractCallPoint"/>  
      <ic:Operation Name ="Constant">  
        <ic:Argument>ServiceRequest</ic:Argument>  
      </ic:Operation>  
      <ic:Operation Name ="Equals"/>  
      <wcf:Operation Name="GetOperationName" />  
      <ic:Operation Name="Constant">  
        <ic:Argument>AuthorizeWithDataContract</ic:Argument>  
      </ic:Operation>  
      <ic:Operation Name ="Equals" />  
      <ic:Operation Name ="And" />  
    </ic:Expression>  
  </ic:Filter>  
  <ic:CorrelationID>  
    <ic:Expression>  
      <ic:Operation Name="Constant">  
        <ic:Argument>ServiceRequest</ic:Argument>  
      </ic:Operation>  
    </ic:Expression>  
  </ic:CorrelationID>  
  <ic:Update DataItemName="Name" Type="NVARCHAR">  
    <ic:Expression>  
      <wcf:Operation Name="XPath">  
        <wcf:Argument>//s:Body/ccservice:*/ccservice:creditCard/creditcard:FirstName</wcf:Argument>  
      </wcf:Operation>  
      <wcf:Operation Name="XPath">  
        <wcf:Argument>//s:Body/ccservice:*/ccservice:creditCard/creditcard:LastName</wcf:Argument>  
      </wcf:Operation>  
      <ic:Operation Name ="Concatenate"/>  
    </ic:Expression>  
  </ic:Update>  
</ic:OnEvent>  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="903fa-134">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="903fa-134">In This Section</span></span>  
  
-   [<span data-ttu-id="903fa-135">Assert</span><span class="sxs-lookup"><span data-stu-id="903fa-135">Filter</span></span>](../core/filter.md)  
  
-   [<span data-ttu-id="903fa-136">関連付け Id</span><span class="sxs-lookup"><span data-stu-id="903fa-136">CorrelationID</span></span>](../core/correlationid.md)  
  
-   [<span data-ttu-id="903fa-137">ContinuationToken</span><span class="sxs-lookup"><span data-stu-id="903fa-137">ContinuationToken</span></span>](../core/continuationtoken.md)  
  
-   [<span data-ttu-id="903fa-138">リファレンス</span><span class="sxs-lookup"><span data-stu-id="903fa-138">Reference</span></span>](../core/reference.md)  
  
-   [<span data-ttu-id="903fa-139">Update</span><span class="sxs-lookup"><span data-stu-id="903fa-139">Update</span></span>](../core/update2.md)  
  
## <a name="see-also"></a><span data-ttu-id="903fa-140">参照</span><span class="sxs-lookup"><span data-stu-id="903fa-140">See Also</span></span>  
 [<span data-ttu-id="903fa-141">インターセプタ構成ファイルの構造</span><span class="sxs-lookup"><span data-stu-id="903fa-141">Structure of an Interceptor Configuration File</span></span>](../core/structure-of-an-interceptor-configuration-file.md)