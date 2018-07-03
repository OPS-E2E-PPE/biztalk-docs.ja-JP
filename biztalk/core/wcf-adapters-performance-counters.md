---
title: WCF アダプターのパフォーマンス カウンター |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performance, WCF adapters
- performance, performance counters
- WCF adapters, performance
ms.assetid: 9feb052f-5674-419f-84ab-9b5d312a04a5
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5b916b6212da18dcf4aa48d4ca941e23413513d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37016253"
---
# <a name="wcf-adapters-performance-counters"></a><span data-ttu-id="3ce61-102">WCF アダプタのパフォーマンス カウンタ</span><span class="sxs-lookup"><span data-stu-id="3ce61-102">WCF Adapters Performance Counters</span></span>
<span data-ttu-id="3ce61-103">パフォーマンス カウンタを使用すると、サービスによってサイトまたはシステムで実行されている作業の具体的な側面を監視できます。</span><span class="sxs-lookup"><span data-stu-id="3ce61-103">Performance counters enable you to monitor specific aspects of work performed on the site or system by a service.</span></span> <span data-ttu-id="3ce61-104">パフォーマンス カウンターは、サーバー パフォーマンスに関する問題を特定してトラブルシューティングする際に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3ce61-104">Performance counters can help you identify and troubleshoot server performance issues.</span></span> <span data-ttu-id="3ce61-105">WCF アダプタ自体のパフォーマンス カウンタはありません。</span><span class="sxs-lookup"><span data-stu-id="3ce61-105">The WCF adapters do not provide their own performance counters.</span></span> <span data-ttu-id="3ce61-106">しかし、Windows Communication Foundation (WCF) のパフォーマンス カウンタを監視して、WCF 受信場所のパフォーマンスを測定できます。</span><span class="sxs-lookup"><span data-stu-id="3ce61-106">However, you can monitor the performance counters of Windows Communication Foundation (WCF) to gauge the performance of the WCF receive locations.</span></span> <span data-ttu-id="3ce61-107">WCF 受信場所に対して WCF パフォーマンス カウンタを使用するには、受信場所を実行するホスト インスタンスのパフォーマンス カウンタを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ce61-107">To use the WCF performance counters for the WCF receive locations, you have to enable the performance counters for the host instances running the receive locations.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3ce61-108">WCF パフォーマンス カウンタは、WCF 送信ポートでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="3ce61-108">The WCF performance counters are not available for WCF send ports.</span></span>  
  
 <span data-ttu-id="3ce61-109">インプロセス WCF アダプターの場合、パフォーマンス カウンターは BTSNTSvc.exe.config ファイルを使用して有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="3ce61-109">For the in-process WCF adapters, you can enable the performance counters through the BTSNTSvc.exe.config file.</span></span> <span data-ttu-id="3ce61-110">分離 WCF アダプタの場合は、Web.config ファイルを変更してパフォーマンス カウンタを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="3ce61-110">For the isolated WCF adapters, you can modify the Web.config file to enable the performance counters.</span></span> <span data-ttu-id="3ce61-111">WCF パフォーマンス カウンタの詳細についてを参照してください「WCF Performance Counters」 [ http://go.microsoft.com/fwlink/?LinkID=87245](http://go.microsoft.com/fwlink/?LinkID=87245)します。</span><span class="sxs-lookup"><span data-stu-id="3ce61-111">For more information about the WCF performance counters, see "WCF Performance Counters" at [http://go.microsoft.com/fwlink/?LinkID=87245](http://go.microsoft.com/fwlink/?LinkID=87245).</span></span>  
  
## <a name="enabling-the-wcf-performance-counters-for-the-wcf-receive-locations"></a><span data-ttu-id="3ce61-112">WCF 受信場所に対する WCF パフォーマンス カウンタの有効化</span><span class="sxs-lookup"><span data-stu-id="3ce61-112">Enabling the WCF Performance Counters for the WCF Receive Locations</span></span>  
 <span data-ttu-id="3ce61-113">インプロセス WCF アダプターの場合、パフォーマンス カウンターは BTSNTSvc.exe.config ファイルを使用して有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="3ce61-113">For the in-process WCF adapters, you can enable the performance counters through the BTSNTSvc.exe.config file.</span></span>  
  
 <span data-ttu-id="3ce61-114">分離 WCF アダプタの場合は、BizTalk WCF サービス公開ウィザードによって Web アプリケーション フォルダに作成される Web.config ファイルを変更して、WCF 追跡を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="3ce61-114">For the isolated WCF adapters, you can enable WCF tracing by modifying the Web.config file that the BizTalk WCF Service Publishing Wizard creates in the Web application folder</span></span>  
  
 <span data-ttu-id="3ce61-115">BTSNtSvc.exe.config または Web.config を変更するには、構成ファイルを開き、次の構成例に示すように WCF 追跡を構成します。</span><span class="sxs-lookup"><span data-stu-id="3ce61-115">To modify BTSNtSvc.exe.config or Web.config, open the configuration file, and then configure WCF tracing, as indicated in the following configuration example:</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3ce61-116">BTSNTSvc.exe.config ファイルは常に BTSNTSvc.exe ファイルと同じディレクトリ (通常は [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]) に配置されます。</span><span class="sxs-lookup"><span data-stu-id="3ce61-116">The BTSNTSvc.exe.config file is always located in the same directory as the BTSNTSvc.exe file, which is usually [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)].</span></span>  
  
```  
<configuration>  
 <system.serviceModel>  
 <diagnostics performanceCounters="All" />  
 </system.serviceModel>  
 </configuration>  
```  
  
 <span data-ttu-id="3ce61-117">**PerformanceCounters**パフォーマンス カウンターの特定の種類を有効にする属性を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="3ce61-117">The **performanceCounters** attribute can be set to enable a specific type of performance counters.</span></span> <span data-ttu-id="3ce61-118">有効な値は</span><span class="sxs-lookup"><span data-stu-id="3ce61-118">Valid values are</span></span>  
  
- <span data-ttu-id="3ce61-119">**すべて**: すべてのカテゴリ カウンター (**ServiceModelService**、 **ServiceModelEndpoint**、および**ServiceModelOperation**) を有効にします。</span><span class="sxs-lookup"><span data-stu-id="3ce61-119">**All**: All category counters (**ServiceModelService**, **ServiceModelEndpoint**, and **ServiceModelOperation**) are enabled.</span></span>  
  
- <span data-ttu-id="3ce61-120">**ServiceOnly**: のみ**ServiceModelService**カテゴリのカウンターを有効にします。</span><span class="sxs-lookup"><span data-stu-id="3ce61-120">**ServiceOnly**: Only **ServiceModelService** category counters are enabled.</span></span>  
  
- <span data-ttu-id="3ce61-121">**オフ**: ServiceModel \* パフォーマンス カウンターが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="3ce61-121">**Off**: ServiceModel\* performance counters are disabled.</span></span> <span data-ttu-id="3ce61-122">これが既定値です。</span><span class="sxs-lookup"><span data-stu-id="3ce61-122">This is the default value.</span></span>  
  
  <span data-ttu-id="3ce61-123">BTSNTSvc.exe.config ファイルを変更した後、インプロセス WCF 受信場所を実行するホスト インスタンスを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ce61-123">After modifying the BTSNTSvc.exe.config file, you must restart the host instances running the in-process WCF receive locations.</span></span>  
  
## <a name="types-of-performance-counters"></a><span data-ttu-id="3ce61-124">パフォーマンス カウンタの種類</span><span class="sxs-lookup"><span data-stu-id="3ce61-124">Types of Performance Counters</span></span>  
 <span data-ttu-id="3ce61-125">WCF パフォーマンス カウンタには、サービス、エンドポイント、および操作の 3 つのレベルがあります。</span><span class="sxs-lookup"><span data-stu-id="3ce61-125">WCF performance counters are scoped to three different levels: service, endpoint, and operation.</span></span>  
  
 <span data-ttu-id="3ce61-126">**サービスのパフォーマンス カウンター**</span><span class="sxs-lookup"><span data-stu-id="3ce61-126">**Service performance counters**</span></span>  
  
 <span data-ttu-id="3ce61-127">サービス パフォーマンス カウンタは、サービス動作全体を測定し、サービス全体のパフォーマンスを診断するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="3ce61-127">Service performance counters measure the service behavior as a whole and can be used to diagnose the performance of the whole service.</span></span> <span data-ttu-id="3ce61-128">下にある、 **ServiceModelService 3.0.0.0**パフォーマンス モニターで表示するときにパフォーマンス オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="3ce61-128">They are found under the **ServiceModelService 3.0.0.0** performance object when viewing with Performance Monitor.</span></span> <span data-ttu-id="3ce61-129">インスタンスには、次のパターンの名前が付けられています。</span><span class="sxs-lookup"><span data-stu-id="3ce61-129">The instances are named using the following pattern:</span></span>  
  
```  
biztalkserviceinstance@<URI of a receive location>  
```  
  
 <span data-ttu-id="3ce61-130">WCF アダプタは受信場所ごとに個別のサービス ホストを作成するので、各受信場所に対して 1 つのパフォーマンス カウンタ インスタンスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="3ce61-130">Because the WCF adapters create a separate service host for each receive location, a performance counter instance is created for each receive location.</span></span> <span data-ttu-id="3ce61-131">WCF を実装するサービス クラスの詳細については、サービス コントラクトを参照してください、 **BizTalkServiceInstance クラス**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="3ce61-131">For more information about the service class implementing the WCF service contracts, see the **BizTalkServiceInstance Class** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span> 
  
 <span data-ttu-id="3ce61-132">**エンドポイントのパフォーマンス カウンター**</span><span class="sxs-lookup"><span data-stu-id="3ce61-132">**Endpoint performance counters**</span></span>  
  
 <span data-ttu-id="3ce61-133">エンドポイント パフォーマンス カウンタを使用すると、エンドポイントでのメッセージの受信状況を表すデータを参照できます。</span><span class="sxs-lookup"><span data-stu-id="3ce61-133">Endpoint performance counters enable you to look at data reflecting how an endpoint is accepting messages.</span></span> <span data-ttu-id="3ce61-134">下にある、 **ServiceModelEndpoint 3.0.0.0**パフォーマンス モニターで表示するときにパフォーマンス オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="3ce61-134">They are found under the **ServiceModelEndpoint 3.0.0.0** performance object when viewing with Performance Monitor.</span></span> <span data-ttu-id="3ce61-135">インスタンスには、次のパターンの名前が付けられています。</span><span class="sxs-lookup"><span data-stu-id="3ce61-135">The instances are named using the following pattern:</span></span>  
  
```  
biztalkserviceinstance.<WCF service contract>@<URI of a receive location>  
```  
  
 <span data-ttu-id="3ce61-136">各受信場所に対して 1 つのパフォーマンス カウンタ インスタンスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="3ce61-136">A performance counter instance is created for each receive location.</span></span> <span data-ttu-id="3ce61-137">上記のパターンでは、WCF サービス コントラクトの名前は、受信場所からメッセージを受信するために WCF アダプタで選択されたサービス コントラクトを表します。</span><span class="sxs-lookup"><span data-stu-id="3ce61-137">In the preceding pattern, the name of the WCF service contract represents the service contract that the WCF adapters choose to receive messages through the receive location.</span></span> <span data-ttu-id="3ce61-138">WCF アダプターが使用可能な WCF からサービス コントラクトを選択する方法の詳細については、サービス コントラクトを参照してください**WCF アダプタ サービス コントラクト参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="3ce61-138">For more information about how the WCF adapters choose a service contract from the available WCF service contracts, see **WCF Adapters Service Contract Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>  
  
 <span data-ttu-id="3ce61-139">**操作パフォーマンス カウンター**</span><span class="sxs-lookup"><span data-stu-id="3ce61-139">**Operation performance counters**</span></span>  
  
 <span data-ttu-id="3ce61-140">操作パフォーマンス カウンターは下にあります、 **ServiceModelOperation 3.0.0.0**パフォーマンス モニターで表示するときにパフォーマンス オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="3ce61-140">Operation performance counters are found under the **ServiceModelOperation 3.0.0.0** performance object when viewing with Performance Monitor.</span></span> <span data-ttu-id="3ce61-141">各受信場所に対して 2 つのパフォーマンス カウンタ インスタンスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="3ce61-141">Two performance counter instances are created for each receive location.</span></span> <span data-ttu-id="3ce61-142">オブジェクト インスタンスの 1 つには、次のパターンを使用した名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="3ce61-142">One of the object instances is named using the following pattern:</span></span>  
  
```  
biztalkserviceinstance.<WCF service contract>biztalksubmit@<URI of a receive location>  
```  
  
 <span data-ttu-id="3ce61-143">上記のパターンでは、WCF サービス コントラクトの名前は、受信場所からメッセージを受信するために WCF アダプタで選択されたサービス コントラクトを表します。</span><span class="sxs-lookup"><span data-stu-id="3ce61-143">In the preceding pattern, the name of the WCF service contract represents the service contract that the WCF adapters choose to receive messages through the receive location.</span></span> <span data-ttu-id="3ce61-144">**biztalksubmit**サービス コントラクトで宣言された操作名であり、ランタイムがメタデータに WSDL 操作が作成されます。</span><span class="sxs-lookup"><span data-stu-id="3ce61-144">**biztalksubmit** is an operation name declared in the service contract, and causes the runtime to create WSDL operations in the metadata.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3ce61-145">WCF アダプターが使用可能な WCF からサービス コントラクトを選択する方法の詳細については、サービス コントラクトを参照してください**WCF アダプタ サービス コントラクト参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="3ce61-145">For more information about how the WCF adapters choose a service contract from the available WCF service contracts, see **WCF Adapters Service Contract Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
 <span data-ttu-id="3ce61-146">もう 1 つのオブジェクト インスタンスには、次のパターンを使用した名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="3ce61-146">The other object instance is named using the following pattern:</span></span>  
  
```  
biztalkserviceinstance.<WCF service contract><twowaymethod|onewaymethod>@<URI of a receive location>  
```  
  
 <span data-ttu-id="3ce61-147">このパフォーマンス カウンタ インスタンスは、受信場所からの受信メッセージの非同期処理を行う操作を表します。</span><span class="sxs-lookup"><span data-stu-id="3ce61-147">This performance counter instance represents the operation that asynchronously processes messages incoming through the receive location.</span></span> <span data-ttu-id="3ce61-148">このインスタンスの操作名の部分を指定できます**twowaymethod**または**onewaymethod**受信場所で使用される WCF アダプターの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="3ce61-148">The operation name part of this instance can be **twowaymethod** or **onewaymethod** depending on the type of WCF adapter used in the receive location.</span></span> <span data-ttu-id="3ce61-149">Wcf-netmsmq アダプターを使用する場合、インスタンスが、 **onewaymethod**操作名が作成されます。</span><span class="sxs-lookup"><span data-stu-id="3ce61-149">If you use the WCF-NetMsmq adapter, an instance having the **onewaymethod** operation name is created.</span></span> <span data-ttu-id="3ce61-150">その他のアダプターの**twowaymethod**操作名要素として使用されます。</span><span class="sxs-lookup"><span data-stu-id="3ce61-150">For the other adapters, **twowaymethod** is used for the operation name part.</span></span>