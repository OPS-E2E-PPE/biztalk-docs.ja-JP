---
title: サンプル アーキテクチャ:BizTalk メッセージ キュー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9424562425854dba532e0c1650c6c9070469be0f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393951"
---
# <a name="sample-architecture-biztalk-message-queuing"></a><span data-ttu-id="f5909-102">サンプル アーキテクチャ:BizTalk メッセージ キュー</span><span class="sxs-lookup"><span data-stu-id="f5909-102">Sample Architecture: BizTalk Message Queuing</span></span>
<span data-ttu-id="f5909-103">このトピックでは、BizTalk メッセージ キュー アダプタを使用してメッセージを送受信するときに、サンプル アーキテクチャについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f5909-103">This topic describes the sample architecture when you use the BizTalk Message Queuing adapter to send and receive messages.</span></span>  
  
 <span data-ttu-id="f5909-104">次の図は、BizTalk メッセージ キュー アダプタを使用する場合に、BizTalk Server のコンポーネントのサンプル アーキテクチャを示します。</span><span class="sxs-lookup"><span data-stu-id="f5909-104">The following figure shows the components of the BizTalk Server sample architecture when you use the BizTalk Message Queuing adapter.</span></span>  
  
 <span data-ttu-id="f5909-105">**BizTalk メッセージ キュー アダプタを示す図 1 サンプル アーキテクチャ**</span><span class="sxs-lookup"><span data-stu-id="f5909-105">**Figure 1 Sample architecture that shows BizTalk Message Queuing adapter**</span></span>  
  
 <span data-ttu-id="f5909-106">![BizTalk メッセージ キューのアーキテクチャのサンプル](../core/media/tdi-sec-refarch-msmq.gif "TDI_Sec_RefArch_MSMQ")</span><span class="sxs-lookup"><span data-stu-id="f5909-106">![Sample architecture for BizTalk Message Queuing](../core/media/tdi-sec-refarch-msmq.gif "TDI_Sec_RefArch_MSMQ")</span></span>  
  
 <span data-ttu-id="f5909-107">このサンプル アーキテクチャには、次のセクションで説明したように、コンポーネントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f5909-107">This sample architecture contains the components as discussed in the following sections.</span></span>  
  
## <a name="perimeter-networkinternet"></a><span data-ttu-id="f5909-108">境界ネットワーク-インターネット</span><span class="sxs-lookup"><span data-stu-id="f5909-108">Perimeter network―Internet</span></span>  
 <span data-ttu-id="f5909-109">メッセージ キュー バイナリ プロトコルを使用して、インターネット経由で勧めできません。</span><span class="sxs-lookup"><span data-stu-id="f5909-109">We do not recommend using the Message Queuing binary protocol over the Internet.</span></span> <span data-ttu-id="f5909-110">メッセージ キュー トラフィックがファイアウォール 1 経由しないようにします。</span><span class="sxs-lookup"><span data-stu-id="f5909-110">You should not let any Message Queuing traffic through Firewall 1.</span></span> <span data-ttu-id="f5909-111">インターネット経由でメッセージを受信する BizTalk メッセージ キュー アダプタを使用する場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f5909-111">If you want to use the BizTalk Message Queuing adapter to receive messages over the Internet, do the following:</span></span>  
  
-   <span data-ttu-id="f5909-112">境界ネットワーク内のメッセージ キュー サーバーを使用します。</span><span class="sxs-lookup"><span data-stu-id="f5909-112">Use a Message Queuing server in the perimeter network.</span></span>  
  
-   <span data-ttu-id="f5909-113">インターネット経由でメッセージ キュー HTTP プロトコルを使用します。</span><span class="sxs-lookup"><span data-stu-id="f5909-113">Use the Message Queuing HTTP protocol over the Internet.</span></span>  
  
-   <span data-ttu-id="f5909-114">メッセージ キュー サーバーからメッセージを取得し、バイナリ プロトコルを使用して、BizTalk メッセージ キュー アダプタに転送を境界ネットワークで転送アプリケーションがあります。</span><span class="sxs-lookup"><span data-stu-id="f5909-114">Have a forwarding application in the perimeter network that picks up the messages from the Message Queuing server and forwards them to the BizTalk Message Queuing adapter by using a binary protocol.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="f5909-115">インターネットからメッセージを受信 BizTalk メッセージ キューを使用する場合でも、ファイアウォール 1 で BizTalk メッセージ キューで使用する必要があります残っているポートが閉じられます。</span><span class="sxs-lookup"><span data-stu-id="f5909-115">Even if you use BizTalk Message Queuing to receive messages from the Internet, the ports that BizTalk Message Queuing uses should remain closed in Firewall 1.</span></span>  
  
## <a name="perimeter-networkintranet"></a><span data-ttu-id="f5909-116">境界ネットワーク-イントラネット</span><span class="sxs-lookup"><span data-stu-id="f5909-116">Perimeter network―intranet</span></span>  
 <span data-ttu-id="f5909-117">イントラネットからメッセージを受信 BizTalk メッセージ キュー アダプタを使用すると、BizTalk メッセージ キュー アダプタのホスト インスタンスが実行されている BizTalk Server にメッセージ キュー トラフィックを転送する Windows メッセージ キュー サーバーがあります。</span><span class="sxs-lookup"><span data-stu-id="f5909-117">When you use the BizTalk Message Queuing adapter to receive messages from the intranet, there is a Windows Message Queuing server that forwards the Message Queuing traffic to the BizTalk Server that runs a host instance of the BizTalk Message Queuing adapter.</span></span>  
  
 <span data-ttu-id="f5909-118">イントラネットおよび E ビジネス ドメインは、一般的な Active Directory を共有している場合は、適切な送信先 (BizTalk メッセージ キューのホスト インスタンスが実行されている BizTalk Server 受信アダプター) に達するまで、メッセージは一連のメッセージ キュー ルーターを通過します。</span><span class="sxs-lookup"><span data-stu-id="f5909-118">If the intranet and the E-Business domain share a common Active Directory, a message goes through a series of Message Queuing routers until it reaches the right destination (the BizTalk Server that runs a host instance of the BizTalk Message Queuing receive adapter).</span></span> <span data-ttu-id="f5909-119">1 つ目の安全性が低いために、このオプションは、図で表されません。</span><span class="sxs-lookup"><span data-stu-id="f5909-119">This option is not represented in the diagram because it is less secure than the first one.</span></span>  
  
## <a name="e-business-domain"></a><span data-ttu-id="f5909-120">E ビジネス ドメイン</span><span class="sxs-lookup"><span data-stu-id="f5909-120">E-Business domain</span></span>  
 <span data-ttu-id="f5909-121">このドメイン内のサーバーは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f5909-121">The servers in this domain are:</span></span>  
  
-   <span data-ttu-id="f5909-122">**BizTalk Server (処理、BizTalk メッセージ キュー アダプタ、および追跡ホスト)。**</span><span class="sxs-lookup"><span data-stu-id="f5909-122">**BizTalk Server (processing, BizTalk Message Queuing adapter, and Tracking hosts).**</span></span> <span data-ttu-id="f5909-123">このサーバーは、BizTalk Server ランタイムのインストールされてし、BizTalk オーケストレーション、パイプライン、ビジネス ルール エンジン、および他のビジネス プロセスが含まれているホストのインスタンスが存在します。</span><span class="sxs-lookup"><span data-stu-id="f5909-123">This server has an installation of the BizTalk Server runtime, and has instances of the hosts that contain the BizTalk orchestrations, pipelines, Business Rule Engine, and other business processes.</span></span> <span data-ttu-id="f5909-124">これは、BizTalk Server のポート、受信場所、パイプライン、マップ、スキーマ、およびアセンブリが存在する受信、ルーティング、処理、およびメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="f5909-124">This is where the BizTalk Server ports, receive locations, pipelines, maps, schemas, and assemblies are located to receive, route, process, and send messages.</span></span> <span data-ttu-id="f5909-125">このサーバーでは、正常性の監視とビジネスの監視データの追跡をサポートするホストのホスト インスタンスもあります。</span><span class="sxs-lookup"><span data-stu-id="f5909-125">This server also has a host instance of a host that supports tracking of health monitoring and business monitoring data.</span></span> <span data-ttu-id="f5909-126">さらに、このホストには、BizTalk メッセージ キューの実行を送信し、受信アダプター、ホストのインスタンスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f5909-126">Additionally, this host contains instances of the host that runs the BizTalk Message Queuing send and receive adapters.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f5909-127">パフォーマンス ニーズの増加に応じて、処理ホストのホスト インスタンスの環境に BizTalk Server を追加できます。</span><span class="sxs-lookup"><span data-stu-id="f5909-127">As your performance needs increase, you can add more BizTalk Servers to your environment for host instances of your processing hosts.</span></span>  
  
-   <span data-ttu-id="f5909-128">**マスター シークレット サーバーです。**</span><span class="sxs-lookup"><span data-stu-id="f5909-128">**Master secret server.**</span></span> <span data-ttu-id="f5909-129">同じように、[サンプル アーキテクチャ。基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="f5909-129">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="f5909-130">**SQL Server。**</span><span class="sxs-lookup"><span data-stu-id="f5909-130">**SQL Server.**</span></span> <span data-ttu-id="f5909-131">同じように、[サンプル アーキテクチャ。基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="f5909-131">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="f5909-132">**ドメイン コント ローラー。**</span><span class="sxs-lookup"><span data-stu-id="f5909-132">**Domain controller.**</span></span> <span data-ttu-id="f5909-133">同じように、[サンプル アーキテクチャ。基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="f5909-133">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="f5909-134">**管理ツールです。**</span><span class="sxs-lookup"><span data-stu-id="f5909-134">**Administration tools.**</span></span> <span data-ttu-id="f5909-135">同じように、[サンプル アーキテクチャ。基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="f5909-135">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5909-136">参照</span><span class="sxs-lookup"><span data-stu-id="f5909-136">See Also</span></span>  
 <span data-ttu-id="f5909-137">[中小規模の企業向けのサンプル アーキテクチャ](../core/sample-architectures-for-small-medium-sized-companies.md) </span><span class="sxs-lookup"><span data-stu-id="f5909-137">[Sample Architectures for Small & Medium-Sized Companies](../core/sample-architectures-for-small-medium-sized-companies.md) </span></span>  
 [<span data-ttu-id="f5909-138">脅威モデル分析のサンプル シナリオ</span><span class="sxs-lookup"><span data-stu-id="f5909-138">Sample Scenarios for Threat Model Analysis</span></span>](../core/sample-scenarios-for-threat-model-analysis.md)