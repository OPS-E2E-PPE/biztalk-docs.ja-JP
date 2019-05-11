---
title: BAM WCF インターセプションを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d85aa130-3219-4df1-8974-a44a51a15002
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 51eb7a1a5e7fc8ac6c94af3f16051d85dd8731b9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341231"
---
# <a name="how-to-configure-the-bam-wcf-interception"></a><span data-ttu-id="a5e77-102">BAM WCF インターセプションを構成する方法</span><span class="sxs-lookup"><span data-stu-id="a5e77-102">How to Configure the BAM WCF Interception</span></span>
<span data-ttu-id="a5e77-103">で BAM を WCF インターセプションを構成するには、イベント ソースに対する正しいアセンブリ マニフェストにアクセスするインターセプター構成ファイルを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5e77-103">To configure BAM for WCF interception, you must modify the interceptor configuration file to access the proper assembly manifest for your event sources.</span></span>  
  
 <span data-ttu-id="a5e77-104">正しく書式設定されたを指定する必要があります、イベントを構成するときに[XPath](../core/xpath.md)アクションの式。</span><span class="sxs-lookup"><span data-stu-id="a5e77-104">When you are configuring the events you must specify properly formatted [XPath](../core/xpath.md) expressions for the actions.</span></span>  
  
 <span data-ttu-id="a5e77-105">適切な形式を作成する[XPath](../core/xpath.md)メッセージが含まれるサンプル WCF ログを生成するために WCF トレースとアプリケーションの実行を有効にすると、インターセプター構成に使用する式。</span><span class="sxs-lookup"><span data-stu-id="a5e77-105">You can create properly formatted [XPath](../core/xpath.md) expressions to use in the interceptor configuration by enabling WCF tracing and running the application to produce a sample WCF log which contains the message.</span></span> <span data-ttu-id="a5e77-106">使用することができます、 **Microsoft Service Trace Viewer** (SvcTraceViewer.exe) をログを表示し、メッセージを抽出します。</span><span class="sxs-lookup"><span data-stu-id="a5e77-106">You can use the **Microsoft Service Trace Viewer** (SvcTraceViewer.exe) to view the log and extract the message.</span></span> <span data-ttu-id="a5e77-107">ビューアーは、WCF SDK に含まれています。</span><span class="sxs-lookup"><span data-stu-id="a5e77-107">The viewer is included with the WCF SDK.</span></span> <span data-ttu-id="a5e77-108">必要な[XPath](../core/xpath.md)式は、メッセージ ベースの形式し、インターセプター構成に適用します。</span><span class="sxs-lookup"><span data-stu-id="a5e77-108">The desired [XPath](../core/xpath.md) expression can then be formed based on the message and applied to the interceptor configuration.</span></span>  
  
 <span data-ttu-id="a5e77-109">BAM WCF インターセプションを構成する場合は、machine.config ファイルで使用されている動作拡張機能が、受信場所のカスタム動作構成で使用される拡張機能と一致することが重要です。</span><span class="sxs-lookup"><span data-stu-id="a5e77-109">When configuring the BAM WCF interception, it is essential that the behavior extension used in the machine.config file matches the extension used in the custom behavior configuration of the receive location.</span></span> <span data-ttu-id="a5e77-110">構成の拡張機能の名前を変更するメッセージが表示される場所、machine.config ファイルで読み込みに失敗します。</span><span class="sxs-lookup"><span data-stu-id="a5e77-110">Changing the extension name of a configured receive location in the machine.config file causes the behavior to fail to load.</span></span> <span data-ttu-id="a5e77-111">さらに、受信場所の構成 UI は失敗します。</span><span class="sxs-lookup"><span data-stu-id="a5e77-111">In addition, the configuration UI of the receive location will fail.</span></span>  
  
 <span data-ttu-id="a5e77-112">クラスタ化されたシナリオでは、することが必要に 1 回だけカスタム動作が構成されているために、クラスター内のコンピューター上のすべての machine.config ファイルは、同じファイル名拡張子を指定します。</span><span class="sxs-lookup"><span data-stu-id="a5e77-112">In case of a clustered scenario, since the custom behavior is configured only once, you must ensure that all the machine.config files on the computers in the cluster specify the same file name extension.</span></span>  
  
### <a name="to-set-the-manifest"></a><span data-ttu-id="a5e77-113">マニフェストを設定するには</span><span class="sxs-lookup"><span data-stu-id="a5e77-113">To set the manifest</span></span>  
  
1.  <span data-ttu-id="a5e77-114">インターセプション構成内の EventSource のマニフェストを設定 ' Microsoft.BizTalk.Adapter.Wcf.Runtime.ITwoWayAsyncVoid、, Microsoft.BizTalk.Adapter.Wcf.Runtime, バージョン =, Culture = neutral, PublicKeyToken = 31bf3856ad364e35'</span><span class="sxs-lookup"><span data-stu-id="a5e77-114">Set the manifest in the EventSource in the Interception Configuration to 'Microsoft.BizTalk.Adapter.Wcf.Runtime.ITwoWayAsyncVoid, Microsoft.BizTalk.Adapter.Wcf.Runtime, Version=3.0.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35'</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a5e77-115">使用するサービス/受信ポートの種類に基づいてインターフェイスが変更されます。</span><span class="sxs-lookup"><span data-stu-id="a5e77-115">The interface changes based on the type of service/receive port used.</span></span> <span data-ttu-id="a5e77-116">次の表に従って、使用するポートの種類を反映するようにマニフェスト行を変更します。</span><span class="sxs-lookup"><span data-stu-id="a5e77-116">Change the manifest line to reflect the type of port you are using according to the table below.</span></span>  
  
    |<span data-ttu-id="a5e77-117">ポートの種類</span><span class="sxs-lookup"><span data-stu-id="a5e77-117">Port Type</span></span>|<span data-ttu-id="a5e77-118">新しく使用する機能</span><span class="sxs-lookup"><span data-stu-id="a5e77-118">Use</span></span>|  
    |---------------|---------|  
    |<span data-ttu-id="a5e77-119">双方向のポート</span><span class="sxs-lookup"><span data-stu-id="a5e77-119">Two-way ports</span></span>|<span data-ttu-id="a5e77-120">ITwoWayAsync</span><span class="sxs-lookup"><span data-stu-id="a5e77-120">ITwoWayAsync</span></span>|  
    |<span data-ttu-id="a5e77-121">バインドを持つ一方向のポートは、本質的に、2 の 2 つの方法 (HTTP など) です。</span><span class="sxs-lookup"><span data-stu-id="a5e77-121">One-way ports with binding that are inherently two 2 way (for example, HTTP).</span></span>|<span data-ttu-id="a5e77-122">ITwoWayAsyncVoid</span><span class="sxs-lookup"><span data-stu-id="a5e77-122">ITwoWayAsyncVoid</span></span>|  
    |<span data-ttu-id="a5e77-123">バインドを持つ一方向のポートは、本質的に 2 つのトランザクションで双方向です。</span><span class="sxs-lookup"><span data-stu-id="a5e77-123">One-way ports with binding that are inherently two two-way with transactions.</span></span>|<span data-ttu-id="a5e77-124">ITwoWayAsyncVoidTxn</span><span class="sxs-lookup"><span data-stu-id="a5e77-124">ITwoWayAsyncVoidTxn</span></span>|  
    |<span data-ttu-id="a5e77-125">1 つの方法 (たとえば、MSMQ) のバインド。</span><span class="sxs-lookup"><span data-stu-id="a5e77-125">Bindings that are one way (for example, MSMQ).</span></span>|<span data-ttu-id="a5e77-126">IOneWayAsync</span><span class="sxs-lookup"><span data-stu-id="a5e77-126">IOneWayAsync</span></span>|  
    |<span data-ttu-id="a5e77-127">トランザクションを使用する一方向のバインド。</span><span class="sxs-lookup"><span data-stu-id="a5e77-127">Bindings that are one way with transactions.</span></span>|<span data-ttu-id="a5e77-128">IOneWayAsyncTxn</span><span class="sxs-lookup"><span data-stu-id="a5e77-128">IOneWayAsyncTxn</span></span>|  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="a5e77-129">フィルターで使用する代わりに、 [GetOperationName](../core/getoperationname.md)操作では、次の例で強調表示されている XPath 操作を使用します。</span><span class="sxs-lookup"><span data-stu-id="a5e77-129">In the filter, instead of using the [GetOperationName](../core/getoperationname.md) operation, use XPath operation as highlighted in the following sample.</span></span> <span data-ttu-id="a5e77-130">汎用の契約は、すべてのメッセージはメッセージ自身 (Action 属性) に基づいて特定の操作にルーティングされますがこの時点で、汎用の操作に到着します。</span><span class="sxs-lookup"><span data-stu-id="a5e77-130">For generic contracts all messages arrive at some generic operation, at which point they get routed to specific operations based on the message itself (Action attribute).</span></span>  
  
2.  <span data-ttu-id="a5e77-131">操作名が必ず同じこの時点でします。</span><span class="sxs-lookup"><span data-stu-id="a5e77-131">The operation name will always be the same at this point.</span></span> <span data-ttu-id="a5e77-132">WCF アダプタ (汎用の契約を使用) する場合は、使用されるメソッドは、BizTalkSubmit を示します。</span><span class="sxs-lookup"><span data-stu-id="a5e77-132">In case of WCF adapters (which uses generic contracts) the method used is BizTalkSubmit.</span></span> <span data-ttu-id="a5e77-133">GetOperationName の代わりにアクション ノードの XPath を使用すると、操作名を取得します。</span><span class="sxs-lookup"><span data-stu-id="a5e77-133">You can use an XPath for the Action node instead of GetOperationName to retrieve the operation name.</span></span> <span data-ttu-id="a5e77-134">操作名でフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="a5e77-134">You can then filter on the operation name.</span></span>  
  
## <a name="sample-interceptor-configurations"></a><span data-ttu-id="a5e77-135">インターセプタ構成のサンプル</span><span class="sxs-lookup"><span data-stu-id="a5e77-135">Sample Interceptor Configurations</span></span>  
 <span data-ttu-id="a5e77-136">このサンプルでは、WCF アダプタの ServiceRequest と ServiceReply の使用状況を示します。</span><span class="sxs-lookup"><span data-stu-id="a5e77-136">This sample shows the usage of ServiceRequest and ServiceReply for the WCF adapter.</span></span> <span data-ttu-id="a5e77-137">強調表示されたセクションでは、 [XPath](../core/xpath.md)アクションに式を使用して、操作を使用する代わりにフィルター処理を[GetOperationName](../core/getoperationname.md)します。</span><span class="sxs-lookup"><span data-stu-id="a5e77-137">In the highlighted section an [XPath](../core/xpath.md) expression on the Action is used to filter on the operation instead of using [GetOperationName](../core/getoperationname.md).</span></span> <span data-ttu-id="a5e77-138">同様に、応答が、ITwoWayAsync の場合だけをフィルター処理することができます。</span><span class="sxs-lookup"><span data-stu-id="a5e77-138">You can filter on the reply as well, but only in the case of ITwoWayAsync.</span></span> <span data-ttu-id="a5e77-139">その他のすべてのインターフェイスは、何も返しませんまたはを無効にします。</span><span class="sxs-lookup"><span data-stu-id="a5e77-139">All other interfaces return nothing or void.</span></span>  
  
### <a name="servicerequest"></a><span data-ttu-id="a5e77-140">ServiceRequest</span><span class="sxs-lookup"><span data-stu-id="a5e77-140">ServiceRequest</span></span>  
  
```  
<ic:OnEvent IsBegin="true" IsEnd ="false" Name ="WCFServiceRequest" Source="WCFService">  
      <ic:Filter>  
        <ic:Expression>  
          <wcf:Operation Name="GetServiceContractCallPoint"/>  
          <ic:Operation Name ="Constant">  
            <ic:Argument>ServiceRequest</ic:Argument>  
          </ic:Operation>  
          <ic:Operation Name ="Equals" />  
          <wcf:Operation Name ="XPath">  
            <wcf:Argument>//s:Header/a:Action</wcf:Argument>  
          </wcf:Operation>  
          <ic:Operation Name ="Constant">  
            <ic:Argument>Operation1</ic:Argument>  
          </ic:Operation>  
          <ic:Operation Name ="Equals" />  
          <ic:Operation Name ="And" />  
        </ic:Expression>  
      </ic:Filter>  
  
      <ic:CorrelationID>  
        <ic:Expression>  
          <wcf:Operation Name="AutoGenerateCorrelationToken"/>  
        </ic:Expression>  
      </ic:CorrelationID>  
  
      <ic:Update DataItemName ="Activity Date" Type ="DATETIME">  
        <ic:Expression>  
          <wcf:Operation Name ="GetContextProperty">  
            <wcf:Argument>EventTime</wcf:Argument>  
          </wcf:Operation>  
        </ic:Expression>  
      </ic:Update>  
  
      <ic:Update DataItemName ="Source" Type ="NVARCHAR">  
        <ic:Expression>  
          <ic:Operation Name="Constant">  
            <ic:Argument>WcfAdapter_ServiceRequest</ic:Argument>  
          </ic:Operation>  
        </ic:Expression>  
      </ic:Update>  
  
    </ic:OnEvent>  
```  
  
### <a name="servicereply"></a><span data-ttu-id="a5e77-141">ServiceReply</span><span class="sxs-lookup"><span data-stu-id="a5e77-141">ServiceReply</span></span>  
  
```  
<ic:OnEvent IsBegin="true" IsEnd ="false" Name ="WCFServiceReply" Source="WCFService">  
      <ic:Filter>  
        <ic:Expression>  
          <wcf:Operation Name="GetServiceContractCallPoint"/>  
          <ic:Operation Name ="Constant">  
            <ic:Argument>ServiceReply</ic:Argument>  
          </ic:Operation>  
          <ic:Operation Name ="Equals" />  
        </ic:Expression>  
      </ic:Filter>  
  
      <ic:CorrelationID>  
        <ic:Expression>  
          <wcf:Operation Name="AutoGenerateCorrelationToken"/>  
        </ic:Expression>  
      </ic:CorrelationID>  
  
      <ic:Update DataItemName ="Activity Date" Type ="DATETIME">  
        <ic:Expression>  
          <wcf:Operation Name ="GetContextProperty">  
            <wcf:Argument>EventTime</wcf:Argument>  
          </wcf:Operation>  
        </ic:Expression>  
      </ic:Update>  
  
      <ic:Update DataItemName ="Name" Type ="NVARCHAR">  
        <ic:Expression>  
          <ic:Operation Name="Constant">  
            <ic:Argument>WcfAdapter_ServiceReply</ic:Argument>  
          </ic:Operation>  
        </ic:Expression>  
      </ic:Update>  
  
    </ic:OnEvent>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a5e77-142">参照</span><span class="sxs-lookup"><span data-stu-id="a5e77-142">See Also</span></span>  
 [<span data-ttu-id="a5e77-143">BAM データを受信するための WCF アダプターの構成</span><span class="sxs-lookup"><span data-stu-id="a5e77-143">Configuring the WCF Adapter to Intercept BAM Data</span></span>](../core/configuring-the-wcf-adapter-to-intercept-bam-data.md)