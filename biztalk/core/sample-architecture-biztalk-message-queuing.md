---
title: "BizTalk メッセージ キューのサンプル アーキテクチャ: |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- examples, security
- Message Queuing binary protocol
- architecture, examples
- security, examples
- security, architecture
- examples, architecture
- MSMQ adapters, security
- architecture, security
- MSMQ adapters, architecture examples
- servers, Windows Message Queuing
- Windows Message Queuing
- message queuing adapters
ms.assetid: a660c798-1c45-4759-a6c8-f11550683a31
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f38d373680fd1b47722fc1ac52c56b113ef59cc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="sample-architecture-biztalk-message-queuing"></a><span data-ttu-id="d3433-102">BizTalk メッセージ キューのサンプル アーキテクチャ:</span><span class="sxs-lookup"><span data-stu-id="d3433-102">Sample Architecture: BizTalk Message Queuing</span></span>
<span data-ttu-id="d3433-103">ここでは、BizTalk メッセージ キュー アダプターを使用してメッセージを送受信する場合のサンプル アーキテクチャについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d3433-103">This topic describes the sample architecture when you use the BizTalk Message Queuing adapter to send and receive messages.</span></span>  
  
 <span data-ttu-id="d3433-104">次の図は、BizTalk メッセージ キュー アダプタを使用する場合の BizTalk Server サンプル アーキテクチャのコンポーネントを示しています。</span><span class="sxs-lookup"><span data-stu-id="d3433-104">The following figure shows the components of the BizTalk Server sample architecture when you use the BizTalk Message Queuing adapter.</span></span>  
  
 <span data-ttu-id="d3433-105">**BizTalk メッセージ キュー アダプタを示すサンプル アーキテクチャを図 1**</span><span class="sxs-lookup"><span data-stu-id="d3433-105">**Figure 1 Sample architecture that shows BizTalk Message Queuing adapter**</span></span>  
  
 <span data-ttu-id="d3433-106">![サンプル アーキテクチャの BizTalk メッセージ キューの](../core/media/tdi-sec-refarch-msmq.gif "TDI_Sec_RefArch_MSMQ")</span><span class="sxs-lookup"><span data-stu-id="d3433-106">![Sample architecture for BizTalk Message Queuing](../core/media/tdi-sec-refarch-msmq.gif "TDI_Sec_RefArch_MSMQ")</span></span>  
  
 <span data-ttu-id="d3433-107">このサンプル アーキテクチャには、次のセクションに記載されているコンポーネントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d3433-107">This sample architecture contains the components as discussed in the following sections.</span></span>  
  
## <a name="perimeter-networkinternet"></a><span data-ttu-id="d3433-108">境界ネットワーク - インターネット</span><span class="sxs-lookup"><span data-stu-id="d3433-108">Perimeter network―Internet</span></span>  
 <span data-ttu-id="d3433-109">インターネット経由でメッセージ キュー バイナリ プロトコルを使用することはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="d3433-109">We do not recommend using the Message Queuing binary protocol over the Internet.</span></span> <span data-ttu-id="d3433-110">メッセージ キュー トラフィックがファイアウォール 1 経由することはできません。</span><span class="sxs-lookup"><span data-stu-id="d3433-110">You should not let any Message Queuing traffic through Firewall 1.</span></span> <span data-ttu-id="d3433-111">インターネット経由でメッセージを受信する BizTalk メッセージ キュー アダプタを使用する場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d3433-111">If you want to use the BizTalk Message Queuing adapter to receive messages over the Internet, do the following:</span></span>  
  
-   <span data-ttu-id="d3433-112">境界ネットワーク内でメッセージ キュー サーバーを使用します。</span><span class="sxs-lookup"><span data-stu-id="d3433-112">Use a Message Queuing server in the perimeter network.</span></span>  
  
-   <span data-ttu-id="d3433-113">インターネット経由でメッセージ キュー HTTP プロトコルを使用します。</span><span class="sxs-lookup"><span data-stu-id="d3433-113">Use the Message Queuing HTTP protocol over the Internet.</span></span>  
  
-   <span data-ttu-id="d3433-114">境界ネットワーク内に、メッセージ キュー サーバーからメッセージを取得し、バイナリ プロトコルを使用してそのメッセージを BizTalk メッセージ キュー アダプタに転送する転送アプリケーションを用意します。</span><span class="sxs-lookup"><span data-stu-id="d3433-114">Have a forwarding application in the perimeter network that picks up the messages from the Message Queuing server and forwards them to the BizTalk Message Queuing adapter by using a binary protocol.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="d3433-115">BizTalk メッセージ キューを使用してインターネットからメッセージを受信する場合でも、BizTalk メッセージ キューで使用するポートは、ファイアウォール 1 では閉じたままにしてください。</span><span class="sxs-lookup"><span data-stu-id="d3433-115">Even if you use BizTalk Message Queuing to receive messages from the Internet, the ports that BizTalk Message Queuing uses should remain closed in Firewall 1.</span></span>  
  
## <a name="perimeter-networkintranet"></a><span data-ttu-id="d3433-116">境界ネットワーク - イントラネット</span><span class="sxs-lookup"><span data-stu-id="d3433-116">Perimeter network―intranet</span></span>  
 <span data-ttu-id="d3433-117">BizTalk メッセージ キュー アダプタを使用してイントラネットからメッセージを受信する場合、BizTalk メッセージ キュー アダプタのホスト インスタンスを実行する BizTalk Server にメッセージ キュー トラフィックを転送する Windows メッセージ キュー サーバーがあります。</span><span class="sxs-lookup"><span data-stu-id="d3433-117">When you use the BizTalk Message Queuing adapter to receive messages from the intranet, there is a Windows Message Queuing server that forwards the Message Queuing traffic to the BizTalk Server that runs a host instance of the BizTalk Message Queuing adapter.</span></span>  
  
 <span data-ttu-id="d3433-118">イントラネットおよび E ビジネス ドメインで共通の Active Directory を共有する場合、メッセージは適切な送信先 (BizTalk メッセージ キューの受信アダプタのホスト インスタンスが実行されている BizTalk Server) に到達するまで、一連のメッセージ キュー ルーターを介して移動します。</span><span class="sxs-lookup"><span data-stu-id="d3433-118">If the intranet and the E-Business domain share a common Active Directory, a message goes through a series of Message Queuing routers until it reaches the right destination (the BizTalk Server that runs a host instance of the BizTalk Message Queuing receive adapter).</span></span> <span data-ttu-id="d3433-119">このオプションは、最初のオプションよりセキュリティの強度が劣るため、この図では示していません。</span><span class="sxs-lookup"><span data-stu-id="d3433-119">This option is not represented in the diagram because it is less secure than the first one.</span></span>  
  
## <a name="e-business-domain"></a><span data-ttu-id="d3433-120">E ビジネス ドメイン</span><span class="sxs-lookup"><span data-stu-id="d3433-120">E-Business domain</span></span>  
 <span data-ttu-id="d3433-121">このドメイン内のサーバーは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d3433-121">The servers in this domain are:</span></span>  
  
-   <span data-ttu-id="d3433-122">**BizTalk Server (処理、BizTalk メッセージ キュー アダプター、および追跡ホスト)。**</span><span class="sxs-lookup"><span data-stu-id="d3433-122">**BizTalk Server (processing, BizTalk Message Queuing adapter, and Tracking hosts).**</span></span> <span data-ttu-id="d3433-123">このサーバーには、BizTalk Server ランタイムがインストールされており、BizTalk オーケストレーション、パイプライン、ビジネス ルール エンジン、およびその他のビジネス プロセスを含むホストのインスタンスが格納されています。</span><span class="sxs-lookup"><span data-stu-id="d3433-123">This server has an installation of the BizTalk Server runtime, and has instances of the hosts that contain the BizTalk orchestrations, pipelines, Business Rule Engine, and other business processes.</span></span> <span data-ttu-id="d3433-124">ここには、BizTalk Server のポート、受信場所、パイプライン、マップ、スキーマ、およびアセンブリがメッセージを受信、ルーティング、処理、および送信するために配置されています。</span><span class="sxs-lookup"><span data-stu-id="d3433-124">This is where the BizTalk Server ports, receive locations, pipelines, maps, schemas, and assemblies are located to receive, route, process, and send messages.</span></span> <span data-ttu-id="d3433-125">このサーバーでは、正常性監視とビジネスの監視データの追跡をサポートするホストのホスト インスタンスもあります。</span><span class="sxs-lookup"><span data-stu-id="d3433-125">This server also has a host instance of a host that supports tracking of health monitoring and business monitoring data.</span></span> <span data-ttu-id="d3433-126">さらに、このホストには、BizTalk メッセージ キューの送信アダプタと受信アダプタを実行するホストのインスタンスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d3433-126">Additionally, this host contains instances of the host that runs the BizTalk Message Queuing send and receive adapters.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d3433-127">パフォーマンスを向上させる必要がある場合、処理ホストのホスト インスタンス用の環境に BizTalk Server をさらに追加できます。</span><span class="sxs-lookup"><span data-stu-id="d3433-127">As your performance needs increase, you can add more BizTalk Servers to your environment for host instances of your processing hosts.</span></span>  
  
-   <span data-ttu-id="d3433-128">**マスター シークレット サーバーです。**</span><span class="sxs-lookup"><span data-stu-id="d3433-128">**Master secret server.**</span></span> <span data-ttu-id="d3433-129">同じように、[サンプル アーキテクチャ: 基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="d3433-129">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="d3433-130">**SQL Server。**</span><span class="sxs-lookup"><span data-stu-id="d3433-130">**SQL Server.**</span></span> <span data-ttu-id="d3433-131">同じように、[サンプル アーキテクチャ: 基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="d3433-131">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="d3433-132">**ドメイン コント ローラー。**</span><span class="sxs-lookup"><span data-stu-id="d3433-132">**Domain controller.**</span></span> <span data-ttu-id="d3433-133">同じように、[サンプル アーキテクチャ: 基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="d3433-133">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="d3433-134">**管理ツールです。**</span><span class="sxs-lookup"><span data-stu-id="d3433-134">**Administration tools.**</span></span> <span data-ttu-id="d3433-135">同じように、[サンプル アーキテクチャ: 基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="d3433-135">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3433-136">参照</span><span class="sxs-lookup"><span data-stu-id="d3433-136">See Also</span></span>  
 <span data-ttu-id="d3433-137">[小規模および中規模企業向けのサンプル アーキテクチャ](../core/sample-architectures-for-small-medium-sized-companies.md) </span><span class="sxs-lookup"><span data-stu-id="d3433-137">[Sample Architectures for Small & Medium-Sized Companies](../core/sample-architectures-for-small-medium-sized-companies.md) </span></span>  
 [<span data-ttu-id="d3433-138">脅威モデル分析のサンプル シナリオ</span><span class="sxs-lookup"><span data-stu-id="d3433-138">Sample Scenarios for Threat Model Analysis</span></span>](../core/sample-scenarios-for-threat-model-analysis.md)