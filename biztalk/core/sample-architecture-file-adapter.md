---
title: 'サンプル アーキテクチャ: ファイル アダプターの |Microsoft ドキュメント'
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
ms.openlocfilehash: 11884786f743ece21a8009ea339a251b107420c9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269610"
---
# <a name="sample-architecture-file-adapter"></a><span data-ttu-id="c79f8-102">ファイル アダプターのサンプル アーキテクチャ:</span><span class="sxs-lookup"><span data-stu-id="c79f8-102">Sample Architecture: File Adapter</span></span>
<span data-ttu-id="c79f8-103">このトピックでは、ファイル アダプターを使用してメッセージを送受信する場合のサンプル アーキテクチャについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c79f8-103">This topic describes the sample architecture when you use the File adapter to send and receive messages.</span></span>  
  
## <a name="file-adapter-components"></a><span data-ttu-id="c79f8-104">ファイル アダプタ コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c79f8-104">File Adapter Components</span></span>  
 <span data-ttu-id="c79f8-105">次の図は、ファイル アダプタを使用する場合の BizTalk サンプル アーキテクチャのコンポーネントを示しています。</span><span class="sxs-lookup"><span data-stu-id="c79f8-105">The following figure shows the components of the BizTalk Server sample architecture when you use the File adapter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c79f8-106">このサンプル アーキテクチャは、EDI アダプタを使用する場合にも適用できます。</span><span class="sxs-lookup"><span data-stu-id="c79f8-106">This sample architecture is also applicable when you use the EDI adapter.</span></span>  
  
 <span data-ttu-id="c79f8-107">**ファイル アダプタを示すサンプル アーキテクチャを図 1**</span><span class="sxs-lookup"><span data-stu-id="c79f8-107">**Figure 1 Sample architecture that shows File adapter**</span></span>  
  
 <span data-ttu-id="c79f8-108">![サンプル ファイル アダプターのアーキテクチャ](../core/media/tdi-sec-refarch-file.gif "TDI_Sec_RefArch_File")</span><span class="sxs-lookup"><span data-stu-id="c79f8-108">![Sample architecture for File adapter](../core/media/tdi-sec-refarch-file.gif "TDI_Sec_RefArch_File")</span></span>  
  
 <span data-ttu-id="c79f8-109">このサンプル アーキテクチャには、次のセクションで説明されているコンポーネントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c79f8-109">This sample architecture contains the components discussed in the following sections.</span></span>  
  
## <a name="perimeter-network-internet"></a><span data-ttu-id="c79f8-110">境界ネットワーク-インターネット</span><span class="sxs-lookup"><span data-stu-id="c79f8-110">Perimeter network-Internet</span></span>  
 <span data-ttu-id="c79f8-111">企業ではイントラネット ベースの通信にファイル プロトコルを使用することが多いので、このシナリオをサポートするためにインターネットの境界ネットワーク内にサーバーを配置する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c79f8-111">Companies commonly use the File protocol for intranet-based communications, and therefore you do not need any servers in the Internet perimeter network to support this scenario.</span></span>  
  
## <a name="perimeter-network-intranet"></a><span data-ttu-id="c79f8-112">境界ネットワーク-イントラネット</span><span class="sxs-lookup"><span data-stu-id="c79f8-112">Perimeter network-intranet</span></span>  
 <span data-ttu-id="c79f8-113">ファイル アダプタを使用する場合、イントラネットの境界ネットワーク内にファイル サーバーがあります。</span><span class="sxs-lookup"><span data-stu-id="c79f8-113">When you use the File adapter, there is a File server in the intranet perimeter network.</span></span> <span data-ttu-id="c79f8-114">これはパートナーがメッセージをドロップするサーバーです。BizTalk ファイル受信アダプタはこのサーバーからメッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="c79f8-114">This is the server where your partners drop their messages, and the BizTalk File receive adapter picks up messages from this server.</span></span>  
  
## <a name="e-business-domain"></a><span data-ttu-id="c79f8-115">E ビジネス ドメイン</span><span class="sxs-lookup"><span data-stu-id="c79f8-115">E-Business domain</span></span>  
 <span data-ttu-id="c79f8-116">このドメイン内のサーバーは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c79f8-116">The servers in this domain are:</span></span>  
  
-   <span data-ttu-id="c79f8-117">**BizTalk Server (処理、ファイル アダプター、および追跡ホスト)。**</span><span class="sxs-lookup"><span data-stu-id="c79f8-117">**BizTalk Server (processing, File adapter, and tracking hosts).**</span></span> <span data-ttu-id="c79f8-118">このサーバーには、BizTalk Server ランタイムがインストールされており、BizTalk オーケストレーション、パイプライン、ビジネス ルール エンジン、およびその他のビジネス プロセスを含むホストのインスタンスが格納されています。</span><span class="sxs-lookup"><span data-stu-id="c79f8-118">This server has an installation of the BizTalk Server runtime, and has instances of the hosts that contain the BizTalk orchestrations, pipelines, Business Rule Engine, and other business processes.</span></span> <span data-ttu-id="c79f8-119">ここには、BizTalk Server のポート、受信場所、パイプライン、マップ、スキーマ、およびアセンブリがメッセージを受信、ルーティング、処理、および送信するために配置されています。</span><span class="sxs-lookup"><span data-stu-id="c79f8-119">This is where the BizTalk Server ports, receive locations, pipelines, maps, schemas, and assemblies are located to receive, route, process, and send messages.</span></span> <span data-ttu-id="c79f8-120">このサーバーでは、正常性監視とビジネスの監視データの追跡をサポートするホストのホスト インスタンスもあります。</span><span class="sxs-lookup"><span data-stu-id="c79f8-120">This server also has a host instance of a host that supports tracking of health monitoring and business monitoring data.</span></span> <span data-ttu-id="c79f8-121">さらに、このホストには、ファイル送信アダプタとファイル受信アダプタを実行するホストのインスタンスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c79f8-121">Additionally, this host contains instances of the host that runs the File send and receive adapters.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c79f8-122">パフォーマンスを向上させる必要がある場合、処理ホストのホスト インスタンス用の環境に BizTalk Server をさらに追加できます。</span><span class="sxs-lookup"><span data-stu-id="c79f8-122">As your performance needs increase, you can add more BizTalk Servers to your environment for host instances of your processing hosts.</span></span> <span data-ttu-id="c79f8-123">BizTalk Server の高可用性を構成する方法の詳細については、次を参照してください。[高可用性の計画](../core/planning-for-high-availability3.md)です。</span><span class="sxs-lookup"><span data-stu-id="c79f8-123">For more information about how to configure BizTalk Server for high availability, see [Planning for High Availability](../core/planning-for-high-availability3.md).</span></span>  
  
-   <span data-ttu-id="c79f8-124">**マスター シークレット サーバーです。**</span><span class="sxs-lookup"><span data-stu-id="c79f8-124">**Master secret server.**</span></span> <span data-ttu-id="c79f8-125">同じように、[サンプル アーキテクチャ: 基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="c79f8-125">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="c79f8-126">**SQL Server。**</span><span class="sxs-lookup"><span data-stu-id="c79f8-126">**SQL Server.**</span></span> <span data-ttu-id="c79f8-127">同じように、[サンプル アーキテクチャ: 基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="c79f8-127">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="c79f8-128">**ドメイン コント ローラー。**</span><span class="sxs-lookup"><span data-stu-id="c79f8-128">**Domain controller.**</span></span> <span data-ttu-id="c79f8-129">同じように、[サンプル アーキテクチャ: 基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="c79f8-129">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="c79f8-130">**管理ツールです。**</span><span class="sxs-lookup"><span data-stu-id="c79f8-130">**Administration tools.**</span></span> <span data-ttu-id="c79f8-131">同じように、[サンプル アーキテクチャ: 基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="c79f8-131">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c79f8-132">参照</span><span class="sxs-lookup"><span data-stu-id="c79f8-132">See Also</span></span>  
 <span data-ttu-id="c79f8-133">[小規模および中規模企業向けのサンプル アーキテクチャ](../core/sample-architectures-for-small-medium-sized-companies.md) </span><span class="sxs-lookup"><span data-stu-id="c79f8-133">[Sample Architectures for Small & Medium-Sized Companies](../core/sample-architectures-for-small-medium-sized-companies.md) </span></span>  
 [<span data-ttu-id="c79f8-134">脅威モデル分析のサンプル シナリオ</span><span class="sxs-lookup"><span data-stu-id="c79f8-134">Sample Scenarios for Threat Model Analysis</span></span>](../core/sample-scenarios-for-threat-model-analysis.md)