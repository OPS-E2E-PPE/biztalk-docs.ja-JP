---
title: 'サンプル アーキテクチャ: FTP アダプター |Microsoft ドキュメント'
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
ms.openlocfilehash: bed15e06027bec5e73c19cf73548674bc51ce68a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269850"
---
# <a name="sample-architecture-ftp-adapter"></a><span data-ttu-id="9fc49-102">FTP アダプターのサンプル アーキテクチャ:</span><span class="sxs-lookup"><span data-stu-id="9fc49-102">Sample Architecture: FTP Adapter</span></span>
<span data-ttu-id="9fc49-103">このトピックでは、FTP アダプターを使用してメッセージを送受信する場合のサンプル アーキテクチャについて説明します。</span><span class="sxs-lookup"><span data-stu-id="9fc49-103">This topic describes the sample architecture when you use the FTP adapter to send and receive messages.</span></span>  
  
 <span data-ttu-id="9fc49-104">次の図は、FTP アダプタを使用する場合の BizTalk サンプル アーキテクチャのコンポーネントを示しています。</span><span class="sxs-lookup"><span data-stu-id="9fc49-104">The following figure shows the components of the BizTalk Server sample architecture when you use the FTP adapter.</span></span>  
  
 <span data-ttu-id="9fc49-105">**FTP アダプタを示すサンプル アーキテクチャを図 1**</span><span class="sxs-lookup"><span data-stu-id="9fc49-105">**Figure 1 Sample architecture that shows FTP adapter**</span></span>  
  
 <span data-ttu-id="9fc49-106">![FTP アダプターのアーキテクチャをサンプル](../core/media/tdi-sec-refarch-ftp.gif "TDI_Sec_RefArch_FTP")</span><span class="sxs-lookup"><span data-stu-id="9fc49-106">![Sample architecture for FTP adapter](../core/media/tdi-sec-refarch-ftp.gif "TDI_Sec_RefArch_FTP")</span></span>  
  
 <span data-ttu-id="9fc49-107">このサンプル アーキテクチャには、次のセクションで説明したように、コンポーネントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9fc49-107">This sample architecture contains the components as discussed in following sections.</span></span>  
  
## <a name="perimeter-networkinternet"></a><span data-ttu-id="9fc49-108">境界ネットワーク - インターネット</span><span class="sxs-lookup"><span data-stu-id="9fc49-108">Perimeter network―Internet</span></span>  
 <span data-ttu-id="9fc49-109">FTP アダプタを使用する場合、インターネットの境界ネットワーク内に FTP サーバーがあります。</span><span class="sxs-lookup"><span data-stu-id="9fc49-109">When you use the FTP adapter, there is an FTP server in the Internet perimeter network.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9fc49-110">環境の外部、FTP サーバーを配置することも — ネットワークでは、パートナーのまたはサード パーティの独立系ソフトウェア ベンダー (ISV) によってホストされています。</span><span class="sxs-lookup"><span data-stu-id="9fc49-110">The FTP server can also be located outside your environment—in the partner's network, or hosted by a third-party independent software vendor (ISV).</span></span>  
  
## <a name="perimeter-networkintranet"></a><span data-ttu-id="9fc49-111">境界ネットワーク - イントラネット</span><span class="sxs-lookup"><span data-stu-id="9fc49-111">Perimeter network―intranet</span></span>  
 <span data-ttu-id="9fc49-112">企業ではインターネット ベースの通信に FTP プロトコルを使用することが多いので、このシナリオをサポートするためにイントラネットの境界ネットワーク内にサーバーを配置する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9fc49-112">Companies commonly use the FTP protocol for Internet-based communications, and therefore you do not need any servers in the intranet perimeter network to support this scenario.</span></span>  
  
## <a name="e-business-domain"></a><span data-ttu-id="9fc49-113">E ビジネス ドメイン</span><span class="sxs-lookup"><span data-stu-id="9fc49-113">E-Business domain</span></span>  
 <span data-ttu-id="9fc49-114">このドメイン内のサーバーは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9fc49-114">The servers in this domain are:</span></span>  
  
-   <span data-ttu-id="9fc49-115">**BizTalk Server (処理、FTP アダプター、および追跡ホスト)。**</span><span class="sxs-lookup"><span data-stu-id="9fc49-115">**BizTalk Server (processing, FTP adapter, and tracking hosts).**</span></span> <span data-ttu-id="9fc49-116">このサーバーには、BizTalk Server ランタイムがインストールされており、BizTalk オーケストレーション、パイプライン、ビジネス ルール エンジン、およびその他のビジネス プロセスを含むホストのインスタンスが格納されています。</span><span class="sxs-lookup"><span data-stu-id="9fc49-116">This server has an installation of the BizTalk Server runtime, and has instances of the hosts that contain the BizTalk orchestrations, pipelines, Business Rule Engine, and other business processes.</span></span> <span data-ttu-id="9fc49-117">ここには、BizTalk Server のポート、受信場所、パイプライン、マップ、スキーマ、およびアセンブリがメッセージを受信、ルーティング、処理、および送信するために配置されています。</span><span class="sxs-lookup"><span data-stu-id="9fc49-117">This is where the BizTalk Server ports, receive locations, pipelines, maps, schemas, and assemblies are located to receive, route, process, and send messages.</span></span> <span data-ttu-id="9fc49-118">このサーバーでは、正常性監視とビジネスの監視データの追跡をサポートするホストのホスト インスタンスもあります。</span><span class="sxs-lookup"><span data-stu-id="9fc49-118">This server also has a host instance of a host that supports tracking of health monitoring and business monitoring data.</span></span> <span data-ttu-id="9fc49-119">さらに、FTP 送信アダプタと FTP 受信アダプタを実行するホストのインスタンスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9fc49-119">Additionally, this host contains instances of the host that runs the FTP send and receive adapters.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9fc49-120">パフォーマンスを向上させる必要がある場合、処理ホストのホスト インスタンス用の環境に BizTalk Server をさらに追加できます。</span><span class="sxs-lookup"><span data-stu-id="9fc49-120">As your performance needs increase, you can add more BizTalk Servers to your environment for host instances of your processing hosts.</span></span> <span data-ttu-id="9fc49-121">BizTalk Server の高可用性を構成する方法の詳細については、次を参照してください。[高可用性の計画](../core/planning-for-high-availability3.md)です。</span><span class="sxs-lookup"><span data-stu-id="9fc49-121">For more information about how to configure BizTalk Server for high availability, see [Planning for High Availability](../core/planning-for-high-availability3.md).</span></span>  
  
-   <span data-ttu-id="9fc49-122">**マスター シークレット サーバーです。**</span><span class="sxs-lookup"><span data-stu-id="9fc49-122">**Master secret server.**</span></span> <span data-ttu-id="9fc49-123">同じように、[サンプル アーキテクチャ: 基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="9fc49-123">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="9fc49-124">**SQL Server。**</span><span class="sxs-lookup"><span data-stu-id="9fc49-124">**SQL Server.**</span></span> <span data-ttu-id="9fc49-125">同じ、[サンプル アーキテクチャ: 基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="9fc49-125">Same as the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="9fc49-126">**ドメイン コント ローラー。**</span><span class="sxs-lookup"><span data-stu-id="9fc49-126">**Domain controller.**</span></span> <span data-ttu-id="9fc49-127">場合と同じように同じ、[サンプル アーキテクチャ: 基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="9fc49-127">Same as in the Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="9fc49-128">**管理ツールです。**</span><span class="sxs-lookup"><span data-stu-id="9fc49-128">**Administration tools.**</span></span> <span data-ttu-id="9fc49-129">同じように、[サンプル アーキテクチャ: 基盤となる BizTalk Server](../core/sample-architecture-base-biztalk-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="9fc49-129">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fc49-130">参照</span><span class="sxs-lookup"><span data-stu-id="9fc49-130">See Also</span></span>  
 <span data-ttu-id="9fc49-131">[小規模および中規模企業向けのサンプル アーキテクチャ](../core/sample-architectures-for-small-medium-sized-companies.md) </span><span class="sxs-lookup"><span data-stu-id="9fc49-131">[Sample Architectures for Small & Medium-Sized Companies](../core/sample-architectures-for-small-medium-sized-companies.md) </span></span>  
 [<span data-ttu-id="9fc49-132">脅威モデル分析のサンプル シナリオ</span><span class="sxs-lookup"><span data-stu-id="9fc49-132">Sample Scenarios for Threat Model Analysis</span></span>](../core/sample-scenarios-for-threat-model-analysis.md)