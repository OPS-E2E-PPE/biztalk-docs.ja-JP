---
title: サンプル アーキテクチャ:FTP アダプター |Microsoft Docs
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
- independent software vendor (ISV)
- security, examples
- security, architecture
- examples, architecture
- architecture, security
- FTP adapters, security
- FTP adapters, architecture examples
ms.assetid: 13fc1086-6acc-483c-be83-4ff6a60cd2bc
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: baa9a9514d7e1524cd277e3e822f7b15a2904d7d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393941"
---
# <a name="sample-architecture-ftp-adapter"></a><span data-ttu-id="13397-102">サンプル アーキテクチャ:FTP アダプター</span><span class="sxs-lookup"><span data-stu-id="13397-102">Sample Architecture: FTP Adapter</span></span>
<span data-ttu-id="13397-103">このトピックでは、FTP アダプターを使用してメッセージを送信する場合、サンプル アーキテクチャについて説明します。</span><span class="sxs-lookup"><span data-stu-id="13397-103">This topic describes the sample architecture when you use the FTP adapter to send and receive messages.</span></span>  
  
 <span data-ttu-id="13397-104">次の図は、FTP アダプターを使用する場合に、BizTalk Server のコンポーネントのサンプル アーキテクチャを示します。</span><span class="sxs-lookup"><span data-stu-id="13397-104">The following figure shows the components of the BizTalk Server sample architecture when you use the FTP adapter.</span></span>  
  
 <span data-ttu-id="13397-105">**FTP アダプタを示す図 1 サンプル アーキテクチャ**</span><span class="sxs-lookup"><span data-stu-id="13397-105">**Figure 1 Sample architecture that shows FTP adapter**</span></span>  
  
 <span data-ttu-id="13397-106">![FTP アダプターのアーキテクチャのサンプル](../core/media/tdi-sec-refarch-ftp.gif "TDI_Sec_RefArch_FTP")</span><span class="sxs-lookup"><span data-stu-id="13397-106">![Sample architecture for FTP adapter](../core/media/tdi-sec-refarch-ftp.gif "TDI_Sec_RefArch_FTP")</span></span>  
  
 <span data-ttu-id="13397-107">このサンプル アーキテクチャには、次のセクションで説明したように、コンポーネントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="13397-107">This sample architecture contains the components as discussed in following sections.</span></span>  
  
## <a name="perimeter-networkinternet"></a><span data-ttu-id="13397-108">境界ネットワーク-インターネット</span><span class="sxs-lookup"><span data-stu-id="13397-108">Perimeter network―Internet</span></span>  
 <span data-ttu-id="13397-109">FTP サーバーが、FTP アダプターを使用すると、インターネット境界ネットワークであります。</span><span class="sxs-lookup"><span data-stu-id="13397-109">When you use the FTP adapter, there is an FTP server in the Internet perimeter network.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="13397-110">環境の外部、FTP サーバーを配置することも、パートナーのネットワークに、またはサード パーティの独立系ソフトウェア ベンダー (ISV) によってホストされています。</span><span class="sxs-lookup"><span data-stu-id="13397-110">The FTP server can also be located outside your environment—in the partner's network, or hosted by a third-party independent software vendor (ISV).</span></span>  
  
## <a name="perimeter-networkintranet"></a><span data-ttu-id="13397-111">境界ネットワーク-イントラネット</span><span class="sxs-lookup"><span data-stu-id="13397-111">Perimeter network―intranet</span></span>  
 <span data-ttu-id="13397-112">企業は、インターネット ベースの通信に FTP プロトコルを使用する一般的と、このシナリオをサポートするためにイントラネット境界ネットワーク内のサーバーでそのため必要がありません。</span><span class="sxs-lookup"><span data-stu-id="13397-112">Companies commonly use the FTP protocol for Internet-based communications, and therefore you do not need any servers in the intranet perimeter network to support this scenario.</span></span>  
  
## <a name="e-business-domain"></a><span data-ttu-id="13397-113">E ビジネス ドメイン</span><span class="sxs-lookup"><span data-stu-id="13397-113">E-Business domain</span></span>  
 <span data-ttu-id="13397-114">このドメイン内のサーバーは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="13397-114">The servers in this domain are:</span></span>  
  
-   <span data-ttu-id="13397-115">**BizTalk Server (処理、FTP アダプター、および追跡ホスト)。**</span><span class="sxs-lookup"><span data-stu-id="13397-115">**BizTalk Server (processing, FTP adapter, and tracking hosts).**</span></span> <span data-ttu-id="13397-116">このサーバーは、BizTalk Server ランタイムのインストールされてし、BizTalk オーケストレーション、パイプライン、ビジネス ルール エンジン、および他のビジネス プロセスが含まれているホストのインスタンスが存在します。</span><span class="sxs-lookup"><span data-stu-id="13397-116">This server has an installation of the BizTalk Server runtime, and has instances of the hosts that contain the BizTalk orchestrations, pipelines, Business Rule Engine, and other business processes.</span></span> <span data-ttu-id="13397-117">これは、BizTalk Server のポート、受信場所、パイプライン、マップ、スキーマ、およびアセンブリが存在する受信、ルーティング、処理、およびメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="13397-117">This is where the BizTalk Server ports, receive locations, pipelines, maps, schemas, and assemblies are located to receive, route, process, and send messages.</span></span> <span data-ttu-id="13397-118">このサーバーでは、正常性の監視とビジネスの監視データの追跡をサポートするホストのホスト インスタンスもあります。</span><span class="sxs-lookup"><span data-stu-id="13397-118">This server also has a host instance of a host that supports tracking of health monitoring and business monitoring data.</span></span> <span data-ttu-id="13397-119">さらに、このホストは、FTP 送信を実行するホストのインスタンスが含まれ、受信アダプター。</span><span class="sxs-lookup"><span data-stu-id="13397-119">Additionally, this host contains instances of the host that runs the FTP send and receive adapters.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="13397-120">パフォーマンス ニーズの増加に応じて、処理ホストのホスト インスタンスの環境に BizTalk Server を追加できます。</span><span class="sxs-lookup"><span data-stu-id="13397-120">As your performance needs increase, you can add more BizTalk Servers to your environment for host instances of your processing hosts.</span></span> <span data-ttu-id="13397-121">高可用性のための BizTalk Server を構成する方法の詳細については、次を参照してください。[高可用性の計画](../core/planning-for-high-availability3.md)します。</span><span class="sxs-lookup"><span data-stu-id="13397-121">For more information about how to configure BizTalk Server for high availability, see [Planning for High Availability](../core/planning-for-high-availability3.md).</span></span>  
  
-   <span data-ttu-id="13397-122">**マスター シークレット サーバーです。**</span><span class="sxs-lookup"><span data-stu-id="13397-122">**Master secret server.**</span></span> <span data-ttu-id="13397-123">同じように、[サンプル アーキテクチャ。基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="13397-123">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="13397-124">**SQL Server。**</span><span class="sxs-lookup"><span data-stu-id="13397-124">**SQL Server.**</span></span> <span data-ttu-id="13397-125">同じ、[サンプル アーキテクチャ。基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="13397-125">Same as the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="13397-126">**ドメイン コント ローラー。**</span><span class="sxs-lookup"><span data-stu-id="13397-126">**Domain controller.**</span></span> <span data-ttu-id="13397-127">同じものと同じように、[サンプル アーキテクチャ。基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="13397-127">Same as in the Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="13397-128">**管理ツールです。**</span><span class="sxs-lookup"><span data-stu-id="13397-128">**Administration tools.**</span></span> <span data-ttu-id="13397-129">同じように、[サンプル アーキテクチャ。基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="13397-129">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13397-130">参照</span><span class="sxs-lookup"><span data-stu-id="13397-130">See Also</span></span>  
 <span data-ttu-id="13397-131">[中小規模の企業向けのサンプル アーキテクチャ](../core/sample-architectures-for-small-medium-sized-companies.md) </span><span class="sxs-lookup"><span data-stu-id="13397-131">[Sample Architectures for Small & Medium-Sized Companies](../core/sample-architectures-for-small-medium-sized-companies.md) </span></span>  
 [<span data-ttu-id="13397-132">脅威モデル分析のサンプル シナリオ</span><span class="sxs-lookup"><span data-stu-id="13397-132">Sample Scenarios for Threat Model Analysis</span></span>](../core/sample-scenarios-for-threat-model-analysis.md)