---
title: サンプル アーキテクチャ:ファイル アダプター |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, security
- architecture, examples
- File adapters, security
- security, examples
- security, architecture
- examples, architecture
- architecture, security
- File adapters, architecture examples
ms.assetid: fdcbba0c-e301-46ce-8940-d617232cafbd
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 961c4e3f7820f88c4935e070c739aacaab5d1a63
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65271154"
---
# <a name="sample-architecture-file-adapter"></a><span data-ttu-id="6bb7a-102">サンプル アーキテクチャ:ファイル アダプター</span><span class="sxs-lookup"><span data-stu-id="6bb7a-102">Sample Architecture: File Adapter</span></span>
<span data-ttu-id="6bb7a-103">このトピックでは、ファイル アダプターを使用してメッセージを送受信するときに、サンプル アーキテクチャについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6bb7a-103">This topic describes the sample architecture when you use the File adapter to send and receive messages.</span></span>  
  
## <a name="file-adapter-components"></a><span data-ttu-id="6bb7a-104">ファイル アダプタ コンポーネント</span><span class="sxs-lookup"><span data-stu-id="6bb7a-104">File Adapter Components</span></span>  
 <span data-ttu-id="6bb7a-105">次の図は、ファイル アダプターを使用する場合に、BizTalk Server のコンポーネントのサンプル アーキテクチャを示します。</span><span class="sxs-lookup"><span data-stu-id="6bb7a-105">The following figure shows the components of the BizTalk Server sample architecture when you use the File adapter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6bb7a-106">このサンプルのアーキテクチャは、EDI アダプタを使用する場合にも適用できます。</span><span class="sxs-lookup"><span data-stu-id="6bb7a-106">This sample architecture is also applicable when you use the EDI adapter.</span></span>  
  
 <span data-ttu-id="6bb7a-107">**ファイル アダプタを示す図 1 サンプル アーキテクチャ**</span><span class="sxs-lookup"><span data-stu-id="6bb7a-107">**Figure 1 Sample architecture that shows File adapter**</span></span>  
  
 <span data-ttu-id="6bb7a-108">![サンプル ファイル アダプターのアーキテクチャ](../core/media/tdi-sec-refarch-file.gif "TDI_Sec_RefArch_File")</span><span class="sxs-lookup"><span data-stu-id="6bb7a-108">![Sample architecture for File adapter](../core/media/tdi-sec-refarch-file.gif "TDI_Sec_RefArch_File")</span></span>  
  
 <span data-ttu-id="6bb7a-109">このサンプル アーキテクチャには、次のセクションで説明されているコンポーネントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6bb7a-109">This sample architecture contains the components discussed in the following sections.</span></span>  
  
## <a name="perimeter-network-internet"></a><span data-ttu-id="6bb7a-110">境界ネットワーク-インターネット</span><span class="sxs-lookup"><span data-stu-id="6bb7a-110">Perimeter network-Internet</span></span>  
 <span data-ttu-id="6bb7a-111">企業は、イントラネット ベースの通信では、ファイル プロトコルを使用する一般的と、このシナリオをサポートするためにインターネット境界ネットワーク内のサーバーでそのため必要がありません。</span><span class="sxs-lookup"><span data-stu-id="6bb7a-111">Companies commonly use the File protocol for intranet-based communications, and therefore you do not need any servers in the Internet perimeter network to support this scenario.</span></span>  
  
## <a name="perimeter-network-intranet"></a><span data-ttu-id="6bb7a-112">境界ネットワーク-イントラネット</span><span class="sxs-lookup"><span data-stu-id="6bb7a-112">Perimeter network-intranet</span></span>  
 <span data-ttu-id="6bb7a-113">ファイル サーバーがファイル アダプターを使用すると、イントラネット境界ネットワークであります。</span><span class="sxs-lookup"><span data-stu-id="6bb7a-113">When you use the File adapter, there is a File server in the intranet perimeter network.</span></span> <span data-ttu-id="6bb7a-114">これは、場所、パートナーは、メッセージをドロップされ、BizTalk ファイル受信アダプターがメッセージ取得このサーバーからサーバーです。</span><span class="sxs-lookup"><span data-stu-id="6bb7a-114">This is the server where your partners drop their messages, and the BizTalk File receive adapter picks up messages from this server.</span></span>  
  
## <a name="e-business-domain"></a><span data-ttu-id="6bb7a-115">E ビジネス ドメイン</span><span class="sxs-lookup"><span data-stu-id="6bb7a-115">E-Business domain</span></span>  
 <span data-ttu-id="6bb7a-116">このドメイン内のサーバーは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6bb7a-116">The servers in this domain are:</span></span>  
  
-   <span data-ttu-id="6bb7a-117">**BizTalk Server (処理、ファイル アダプター、および追跡ホスト)。**</span><span class="sxs-lookup"><span data-stu-id="6bb7a-117">**BizTalk Server (processing, File adapter, and tracking hosts).**</span></span> <span data-ttu-id="6bb7a-118">このサーバーは、BizTalk Server ランタイムのインストールされてし、BizTalk オーケストレーション、パイプライン、ビジネス ルール エンジン、および他のビジネス プロセスが含まれているホストのインスタンスが存在します。</span><span class="sxs-lookup"><span data-stu-id="6bb7a-118">This server has an installation of the BizTalk Server runtime, and has instances of the hosts that contain the BizTalk orchestrations, pipelines, Business Rule Engine, and other business processes.</span></span> <span data-ttu-id="6bb7a-119">これは、BizTalk Server のポート、受信場所、パイプライン、マップ、スキーマ、およびアセンブリが存在する受信、ルーティング、処理、およびメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="6bb7a-119">This is where the BizTalk Server ports, receive locations, pipelines, maps, schemas, and assemblies are located to receive, route, process, and send messages.</span></span> <span data-ttu-id="6bb7a-120">このサーバーでは、正常性の監視とビジネスの監視データの追跡をサポートするホストのホスト インスタンスもあります。</span><span class="sxs-lookup"><span data-stu-id="6bb7a-120">This server also has a host instance of a host that supports tracking of health monitoring and business monitoring data.</span></span> <span data-ttu-id="6bb7a-121">さらに、このホストは、ファイルの送信を実行するホストのインスタンスが含まれ、受信アダプター。</span><span class="sxs-lookup"><span data-stu-id="6bb7a-121">Additionally, this host contains instances of the host that runs the File send and receive adapters.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6bb7a-122">パフォーマンス ニーズの増加に応じて、処理ホストのホスト インスタンスの環境に BizTalk Server を追加できます。</span><span class="sxs-lookup"><span data-stu-id="6bb7a-122">As your performance needs increase, you can add more BizTalk Servers to your environment for host instances of your processing hosts.</span></span> <span data-ttu-id="6bb7a-123">高可用性のための BizTalk Server を構成する方法の詳細については、次を参照してください。[高可用性の計画](../core/planning-for-high-availability3.md)します。</span><span class="sxs-lookup"><span data-stu-id="6bb7a-123">For more information about how to configure BizTalk Server for high availability, see [Planning for High Availability](../core/planning-for-high-availability3.md).</span></span>  
  
-   <span data-ttu-id="6bb7a-124">**マスター シークレット サーバーです。**</span><span class="sxs-lookup"><span data-stu-id="6bb7a-124">**Master secret server.**</span></span> <span data-ttu-id="6bb7a-125">同じように、[サンプル アーキテクチャ。基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="6bb7a-125">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="6bb7a-126">**SQL Server。**</span><span class="sxs-lookup"><span data-stu-id="6bb7a-126">**SQL Server.**</span></span> <span data-ttu-id="6bb7a-127">同じように、[サンプル アーキテクチャ。基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="6bb7a-127">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="6bb7a-128">**ドメイン コント ローラー。**</span><span class="sxs-lookup"><span data-stu-id="6bb7a-128">**Domain controller.**</span></span> <span data-ttu-id="6bb7a-129">同じように、[サンプル アーキテクチャ。基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="6bb7a-129">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="6bb7a-130">**管理ツールです。**</span><span class="sxs-lookup"><span data-stu-id="6bb7a-130">**Administration tools.**</span></span> <span data-ttu-id="6bb7a-131">同じように、[サンプル アーキテクチャ。基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="6bb7a-131">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bb7a-132">参照</span><span class="sxs-lookup"><span data-stu-id="6bb7a-132">See Also</span></span>  
 <span data-ttu-id="6bb7a-133">[中小規模の企業向けのサンプル アーキテクチャ](../core/sample-architectures-for-small-medium-sized-companies.md) </span><span class="sxs-lookup"><span data-stu-id="6bb7a-133">[Sample Architectures for Small & Medium-Sized Companies](../core/sample-architectures-for-small-medium-sized-companies.md) </span></span>  
 [<span data-ttu-id="6bb7a-134">脅威モデル分析のサンプル シナリオ</span><span class="sxs-lookup"><span data-stu-id="6bb7a-134">Sample Scenarios for Threat Model Analysis</span></span>](../core/sample-scenarios-for-threat-model-analysis.md)