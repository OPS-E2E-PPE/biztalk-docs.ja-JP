---
title: "WCF アダプタのパフォーマンス カウンタ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- performance, WCF adapters
- performance, performance counters
- WCF adapters, performance
ms.assetid: 9feb052f-5674-419f-84ab-9b5d312a04a5
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 236eaed7401c79540274e0419b99d14d0f128332
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="wcf-adapters-performance-counters"></a><span data-ttu-id="a2be0-102">WCF アダプタのパフォーマンス カウンタ</span><span class="sxs-lookup"><span data-stu-id="a2be0-102">WCF Adapters Performance Counters</span></span>
<span data-ttu-id="a2be0-103">パフォーマンス カウンタを使用すると、サービスによってサイトまたはシステムで実行されている作業の具体的な側面を監視できます。</span><span class="sxs-lookup"><span data-stu-id="a2be0-103">Performance counters enable you to monitor specific aspects of work performed on the site or system by a service.</span></span> <span data-ttu-id="a2be0-104">パフォーマンス カウンターは、サーバー パフォーマンスに関する問題を特定してトラブルシューティングする際に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a2be0-104">Performance counters can help you identify and troubleshoot server performance issues.</span></span> <span data-ttu-id="a2be0-105">WCF アダプタ自体のパフォーマンス カウンタはありません。</span><span class="sxs-lookup"><span data-stu-id="a2be0-105">The WCF adapters do not provide their own performance counters.</span></span> <span data-ttu-id="a2be0-106">しかし、Windows Communication Foundation (WCF) のパフォーマンス カウンタを監視して、WCF 受信場所のパフォーマンスを測定できます。</span><span class="sxs-lookup"><span data-stu-id="a2be0-106">However, you can monitor the performance counters of Windows Communication Foundation (WCF) to gauge the performance of the WCF receive locations.</span></span> <span data-ttu-id="a2be0-107">WCF 受信場所に対して WCF パフォーマンス カウンタを使用するには、受信場所を実行するホスト インスタンスのパフォーマンス カウンタを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2be0-107">To use the WCF performance counters for the WCF receive locations, you have to enable the performance counters for the host instances running the receive locations.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a2be0-108">WCF パフォーマンス カウンタは、WCF 送信ポートでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="a2be0-108">The WCF performance counters are not available for WCF send ports.</span></span>  
  
 <span data-ttu-id="a2be0-109">インプロセス WCF アダプターの場合、パフォーマンス カウンターは BTSNTSvc.exe.config ファイルを使用して有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="a2be0-109">For the in-process WCF adapters, you can enable the performance counters through the BTSNTSvc.exe.config file.</span></span> <span data-ttu-id="a2be0-110">分離 WCF アダプタの場合は、Web.config ファイルを変更してパフォーマンス カウンタを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="a2be0-110">For the isolated WCF adapters, you can modify the Web.config file to enable the performance counters.</span></span> <span data-ttu-id="a2be0-111">WCF パフォーマンス カウンタの詳細についてにある「WCF Performance Counters」を参照してください。 [http://go.microsoft.com/fwlink/?LinkID=87245](http://go.microsoft.com/fwlink/?LinkID=87245)です。</span><span class="sxs-lookup"><span data-stu-id="a2be0-111">For more information about the WCF performance counters, see "WCF Performance Counters" at [http://go.microsoft.com/fwlink/?LinkID=87245](http://go.microsoft.com/fwlink/?LinkID=87245).</span></span>  
  
## <a name="enabling-the-wcf-performance-counters-for-the-wcf-receive-locations"></a><span data-ttu-id="a2be0-112">WCF 受信場所に対する WCF パフォーマンス カウンタの有効化</span><span class="sxs-lookup"><span data-stu-id="a2be0-112">Enabling the WCF Performance Counters for the WCF Receive Locations</span></span>  
 <span data-ttu-id="a2be0-113">インプロセス WCF アダプターの場合、パフォーマンス カウンターは BTSNTSvc.exe.config ファイルを使用して有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="a2be0-113">For the in-process WCF adapters, you can enable the performance counters through the BTSNTSvc.exe.config file.</span></span>  
  
 <span data-ttu-id="a2be0-114">分離 WCF アダプタの場合は、BizTalk WCF サービス公開ウィザードによって Web アプリケーション フォルダに作成される Web.config ファイルを変更して、WCF 追跡を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="a2be0-114">For the isolated WCF adapters, you can enable WCF tracing by modifying the Web.config file that the BizTalk WCF Service Publishing Wizard creates in the Web application folder</span></span>  
  
 <span data-ttu-id="a2be0-115">BTSNtSvc.exe.config または Web.config を変更するには、構成ファイルを開き、次の構成例に示すように WCF 追跡を構成します。</span><span class="sxs-lookup"><span data-stu-id="a2be0-115">To modify BTSNtSvc.exe.config or Web.config, open the configuration file, and then configure WCF tracing, as indicated in the following configuration example:</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a2be0-116">BTSNTSvc.exe.config ファイルは常に BTSNTSvc.exe ファイルと同じディレクトリ (通常は [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]) に配置されます。</span><span class="sxs-lookup"><span data-stu-id="a2be0-116">The BTSNTSvc.exe.config file is always located in the same directory as the BTSNTSvc.exe file, which is usually [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)].</span></span>  
  
```  
<configuration>  
 <system.serviceModel>  
 <diagnostics performanceCounters="All" />  
 </system.serviceModel>  
 </configuration>  
```  
  
 <span data-ttu-id="a2be0-117">**PerformanceCounters**パフォーマンス カウンターの特定の種類を有効にする属性を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="a2be0-117">The **performanceCounters** attribute can be set to enable a specific type of performance counters.</span></span> <span data-ttu-id="a2be0-118">有効な値は</span><span class="sxs-lookup"><span data-stu-id="a2be0-118">Valid values are</span></span>  
  
-   <span data-ttu-id="a2be0-119">**すべて**: すべてのカテゴリ カウンタ (**ServiceModelService**、 **ServiceModelEndpoint**、および**ServiceModelOperation**) を有効にします。</span><span class="sxs-lookup"><span data-stu-id="a2be0-119">**All**: All category counters (**ServiceModelService**, **ServiceModelEndpoint**, and **ServiceModelOperation**) are enabled.</span></span>  
  
-   <span data-ttu-id="a2be0-120">**ServiceOnly**: のみ**ServiceModelService**カテゴリ カウンターを有効にします。</span><span class="sxs-lookup"><span data-stu-id="a2be0-120">**ServiceOnly**: Only **ServiceModelService** category counters are enabled.</span></span>  
  
-   <span data-ttu-id="a2be0-121">**オフ**: ServiceModel * パフォーマンス カウンターが無効です。</span><span class="sxs-lookup"><span data-stu-id="a2be0-121">**Off**: ServiceModel* performance counters are disabled.</span></span> <span data-ttu-id="a2be0-122">これが既定値です。</span><span class="sxs-lookup"><span data-stu-id="a2be0-122">This is the default value.</span></span>  
  
 <span data-ttu-id="a2be0-123">BTSNTSvc.exe.config ファイルを変更した後、インプロセス WCF 受信場所を実行するホスト インスタンスを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2be0-123">After modifying the BTSNTSvc.exe.config file, you must restart the host instances running the in-process WCF receive locations.</span></span>  
  
## <a name="types-of-performance-counters"></a><span data-ttu-id="a2be0-124">パフォーマンス カウンタの種類</span><span class="sxs-lookup"><span data-stu-id="a2be0-124">Types of Performance Counters</span></span>  
 <span data-ttu-id="a2be0-125">WCF パフォーマンス カウンタには、サービス、エンドポイント、および操作の 3 つのレベルがあります。</span><span class="sxs-lookup"><span data-stu-id="a2be0-125">WCF performance counters are scoped to three different levels: service, endpoint, and operation.</span></span>  
  
 <span data-ttu-id="a2be0-126">**サービスのパフォーマンス カウンター**</span><span class="sxs-lookup"><span data-stu-id="a2be0-126">**Service performance counters**</span></span>  
  
 <span data-ttu-id="a2be0-127">サービス パフォーマンス カウンタは、サービス動作全体を測定し、サービス全体のパフォーマンスを診断するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="a2be0-127">Service performance counters measure the service behavior as a whole and can be used to diagnose the performance of the whole service.</span></span> <span data-ttu-id="a2be0-128">下にある、 **ServiceModelService 3.0.0.0**パフォーマンス オブジェクトとパフォーマンス モニターを使用して表示します。</span><span class="sxs-lookup"><span data-stu-id="a2be0-128">They are found under the **ServiceModelService 3.0.0.0** performance object when viewing with Performance Monitor.</span></span> <span data-ttu-id="a2be0-129">インスタンスには、次のパターンの名前が付けられています。</span><span class="sxs-lookup"><span data-stu-id="a2be0-129">The instances are named using the following pattern:</span></span>  
  
```  
biztalkserviceinstance@<URI of a receive location>  
```  
  
 <span data-ttu-id="a2be0-130">WCF アダプタは受信場所ごとに個別のサービス ホストを作成するので、各受信場所に対して 1 つのパフォーマンス カウンタ インスタンスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="a2be0-130">Because the WCF adapters create a separate service host for each receive location, a performance counter instance is created for each receive location.</span></span> <span data-ttu-id="a2be0-131">WCF を実装するサービス クラスの詳細については、サービス コントラクトを参照してください、 **BizTalkServiceInstance クラス**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。</span><span class="sxs-lookup"><span data-stu-id="a2be0-131">For more information about the service class implementing the WCF service contracts, see the **BizTalkServiceInstance Class** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span> 
  
 <span data-ttu-id="a2be0-132">**エンドポイントのパフォーマンス カウンター**</span><span class="sxs-lookup"><span data-stu-id="a2be0-132">**Endpoint performance counters**</span></span>  
  
 <span data-ttu-id="a2be0-133">エンドポイント パフォーマンス カウンタを使用すると、エンドポイントでのメッセージの受信状況を表すデータを参照できます。</span><span class="sxs-lookup"><span data-stu-id="a2be0-133">Endpoint performance counters enable you to look at data reflecting how an endpoint is accepting messages.</span></span> <span data-ttu-id="a2be0-134">下にある、 **ServiceModelEndpoint 3.0.0.0**パフォーマンス オブジェクトとパフォーマンス モニターを使用して表示します。</span><span class="sxs-lookup"><span data-stu-id="a2be0-134">They are found under the **ServiceModelEndpoint 3.0.0.0** performance object when viewing with Performance Monitor.</span></span> <span data-ttu-id="a2be0-135">インスタンスには、次のパターンの名前が付けられています。</span><span class="sxs-lookup"><span data-stu-id="a2be0-135">The instances are named using the following pattern:</span></span>  
  
```  
biztalkserviceinstance.<WCF service contract>@<URI of a receive location>  
```  
  
 <span data-ttu-id="a2be0-136">各受信場所に対して 1 つのパフォーマンス カウンタ インスタンスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="a2be0-136">A performance counter instance is created for each receive location.</span></span> <span data-ttu-id="a2be0-137">上記のパターンでは、WCF サービス コントラクトの名前は、受信場所からメッセージを受信するために WCF アダプタで選択されたサービス コントラクトを表します。</span><span class="sxs-lookup"><span data-stu-id="a2be0-137">In the preceding pattern, the name of the WCF service contract represents the service contract that the WCF adapters choose to receive messages through the receive location.</span></span> <span data-ttu-id="a2be0-138">WCF アダプタが使用可能な WCF からサービス コントラクトを選択する方法の詳細については、サービス コントラクトを参照してください**WCF アダプタ サービス コントラクト参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。</span><span class="sxs-lookup"><span data-stu-id="a2be0-138">For more information about how the WCF adapters choose a service contract from the available WCF service contracts, see **WCF Adapters Service Contract Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>  
  
 <span data-ttu-id="a2be0-139">**操作パフォーマンス カウンター**</span><span class="sxs-lookup"><span data-stu-id="a2be0-139">**Operation performance counters**</span></span>  
  
 <span data-ttu-id="a2be0-140">操作パフォーマンス カウンターは下にあります、 **ServiceModelOperation 3.0.0.0**パフォーマンス オブジェクトとパフォーマンス モニターを使用して表示します。</span><span class="sxs-lookup"><span data-stu-id="a2be0-140">Operation performance counters are found under the **ServiceModelOperation 3.0.0.0** performance object when viewing with Performance Monitor.</span></span> <span data-ttu-id="a2be0-141">各受信場所に対して 2 つのパフォーマンス カウンタ インスタンスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="a2be0-141">Two performance counter instances are created for each receive location.</span></span> <span data-ttu-id="a2be0-142">オブジェクト インスタンスの 1 つには、次のパターンを使用した名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="a2be0-142">One of the object instances is named using the following pattern:</span></span>  
  
```  
biztalkserviceinstance.<WCF service contract>biztalksubmit@<URI of a receive location>  
```  
  
 <span data-ttu-id="a2be0-143">上記のパターンでは、WCF サービス コントラクトの名前は、受信場所からメッセージを受信するために WCF アダプタで選択されたサービス コントラクトを表します。</span><span class="sxs-lookup"><span data-stu-id="a2be0-143">In the preceding pattern, the name of the WCF service contract represents the service contract that the WCF adapters choose to receive messages through the receive location.</span></span> <span data-ttu-id="a2be0-144">**biztalksubmit**サービス コントラクトで宣言されている操作名であり、メタデータに WSDL 操作を作成するランタイム。</span><span class="sxs-lookup"><span data-stu-id="a2be0-144">**biztalksubmit** is an operation name declared in the service contract, and causes the runtime to create WSDL operations in the metadata.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a2be0-145">WCF アダプタが使用可能な WCF からサービス コントラクトを選択する方法の詳細については、サービス コントラクトを参照してください**WCF アダプタ サービス コントラクト参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。</span><span class="sxs-lookup"><span data-stu-id="a2be0-145">For more information about how the WCF adapters choose a service contract from the available WCF service contracts, see **WCF Adapters Service Contract Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
 <span data-ttu-id="a2be0-146">もう 1 つのオブジェクト インスタンスには、次のパターンを使用した名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="a2be0-146">The other object instance is named using the following pattern:</span></span>  
  
```  
biztalkserviceinstance.<WCF service contract><twowaymethod|onewaymethod>@<URI of a receive location>  
```  
  
 <span data-ttu-id="a2be0-147">このパフォーマンス カウンタ インスタンスは、受信場所からの受信メッセージの非同期処理を行う操作を表します。</span><span class="sxs-lookup"><span data-stu-id="a2be0-147">This performance counter instance represents the operation that asynchronously processes messages incoming through the receive location.</span></span> <span data-ttu-id="a2be0-148">このインスタンスの操作名の部分を指定できます**twowaymethod**または**onewaymethod**受信場所で使用される WCF アダプターの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="a2be0-148">The operation name part of this instance can be **twowaymethod** or **onewaymethod** depending on the type of WCF adapter used in the receive location.</span></span> <span data-ttu-id="a2be0-149">Wcf-netmsmq アダプターを使用する場合、インスタンスを持つ、 **onewaymethod**操作名を作成します。</span><span class="sxs-lookup"><span data-stu-id="a2be0-149">If you use the WCF-NetMsmq adapter, an instance having the **onewaymethod** operation name is created.</span></span> <span data-ttu-id="a2be0-150">他のアダプターの**twowaymethod**操作名の部分を使用します。</span><span class="sxs-lookup"><span data-stu-id="a2be0-150">For the other adapters, **twowaymethod** is used for the operation name part.</span></span>