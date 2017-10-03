---
title: "BizTalk Server で ESB Toolkit の概要 |Microsoft ドキュメント"
description: "BizTalk Server でどのように、ESB Toolkit の説明"
caps.latest.revision: "6"
author: MandiOhlinger
manager: anneta
ms.custom: 
ms.date: 08/10/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3e190b34-40bc-4f27-9b4f-56e98591e1d4
ms.author: mandia
ms.openlocfilehash: 9ce0bbe3710530a63127701447db87b0a3135b4a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-the-biztalk-esb-toolkit"></a><span data-ttu-id="5e501-103">BizTalk ESB Toolkit は、新機能</span><span class="sxs-lookup"><span data-stu-id="5e501-103">What is the BizTalk ESB Toolkit</span></span>

## <a name="overview"></a><span data-ttu-id="5e501-104">概要</span><span class="sxs-lookup"><span data-stu-id="5e501-104">Overview</span></span>
<span data-ttu-id="5e501-105">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]疎結合のメッセージング アーキテクチャをサポートするために BizTalk Server の機能を拡張します。</span><span class="sxs-lookup"><span data-stu-id="5e501-105">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] extends the capabilities of BizTalk Server to support a loosely coupled messaging architecture.</span></span> <span data-ttu-id="5e501-106">ほとんどの開発者は、コード指向、手順、または他のオブジェクト指向開発パラダイムに慣れています。</span><span class="sxs-lookup"><span data-stu-id="5e501-106">Most developers are familiar with code-oriented, procedural, or object-oriented development paradigms.</span></span> <span data-ttu-id="5e501-107">ただし、開始時に BizTalk ソリューションを開発し、開発者を BizTalk Server のメッセージ指向の機能を見落とされる傾向があります。</span><span class="sxs-lookup"><span data-stu-id="5e501-107">However, when starting to develop BizTalk solutions, developers tend to overlook the message-oriented capabilities of BizTalk Server.</span></span>  
  
 <span data-ttu-id="5e501-108">BizTalk Server には、作成し、サブスクリプションで動作する強力なパブリッシュ/サブスクライブ メカニズムが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5e501-108">BizTalk Server includes a powerful publish/subscribe mechanism that works by creating and filling subscriptions.</span></span> <span data-ttu-id="5e501-109">BizTalk メッセージ ボックス データベースに新しいメッセージが到着すると、メッセージ エージェントはサブスクライバーを識別し、サブスクリプションを持つエンドポイントにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="5e501-109">When a new message arrives in the BizTalk Message Box database, a message agent identifies subscribers and sends the message to any endpoints that have subscriptions.</span></span> <span data-ttu-id="5e501-110">関連付けられた受信のメッセージは、待機しているか (など、型では、受信メッセージのプロパティに一致するフィルター条件の送信ポートの作成を持つ、受信ポートにオーケストレーションをバインドなど、いくつかの方法でサブスクリプションを作成できます。ポイント、またはルーティング可能なプロパティの値)。</span><span class="sxs-lookup"><span data-stu-id="5e501-110">Subscriptions can be created in several ways, including binding an orchestration to a receive port, having a correlated receive waiting for a message, or creating a send port with a filter condition that matches a property of the message (such as the type, the receive point, or the value of a routable property).</span></span>  
  
 <span data-ttu-id="5e501-111">この効率的でスケーラブルな方法を提供する BizTalk Server 開発者は一連の個別のサブ プロセスを作成するには、その呼び出しをトリガーして、シーケンスは気にメッセージの種類を定義できます。</span><span class="sxs-lookup"><span data-stu-id="5e501-111">By providing this efficient and scalable approach, BizTalk Server enables developers to create a series of discrete sub-processes, define the types of messages that trigger their invocation, and not worry about the sequence.</span></span> <span data-ttu-id="5e501-112">メッセージの到着によって開始されたプロセスは、メッセージの処理を実行します。メッセージを処理した後、メッセージ ボックス データベースに、さらに、1 つまたは複数のサブプロセスをアクティブ化できる同じまたは別のメッセージの配信、ことができます。</span><span class="sxs-lookup"><span data-stu-id="5e501-112">A process initiated by the arrival of a message performs its processing on the message; after it processes the message, it can deliver this or another message to the Message Box database, which, in turn, may activate one or more sub-processes.</span></span>  
  
 <span data-ttu-id="5e501-113">Microsoft では、Windows Server、.NET Framework は、BizTalk Server を含め、サービス指向の包括的なインフラストラクチャを構築するために必要なキーの構成要素を提供します。</span><span class="sxs-lookup"><span data-stu-id="5e501-113">Microsoft provides key building blocks that are required for building comprehensive Service-Oriented Infrastructures, including Windows Server, the .NET Framework, and BizTalk Server.</span></span> <span data-ttu-id="5e501-114">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]次を含む、最も一般的な ESB サービスの基盤が提供されているために、BizTalk Server に基づきます。</span><span class="sxs-lookup"><span data-stu-id="5e501-114">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] is based on BizTalk Server because it provides the basis for the most common ESB services, including the following:</span></span>  
  
-   <span data-ttu-id="5e501-115">メッセージのルーティング</span><span class="sxs-lookup"><span data-stu-id="5e501-115">Message routing</span></span>  
  
-   <span data-ttu-id="5e501-116">メッセージの検証</span><span class="sxs-lookup"><span data-stu-id="5e501-116">Message validation</span></span>  
  
-   <span data-ttu-id="5e501-117">メッセージの変換</span><span class="sxs-lookup"><span data-stu-id="5e501-117">Message transformation</span></span>  
  
-   <span data-ttu-id="5e501-118">接続の拡張可能なアダプター フレームワーク</span><span class="sxs-lookup"><span data-stu-id="5e501-118">Extensible adapter framework for connectivity</span></span>  
  
-   <span data-ttu-id="5e501-119">サービスの調整</span><span class="sxs-lookup"><span data-stu-id="5e501-119">Service orchestration</span></span>  
  
-   <span data-ttu-id="5e501-120">ビジネス ルール エンジン</span><span class="sxs-lookup"><span data-stu-id="5e501-120">Business rules engine</span></span>  
  
-   <span data-ttu-id="5e501-121">ビジネス アクティビティの監視</span><span class="sxs-lookup"><span data-stu-id="5e501-121">Business activity monitoring</span></span>  
  
-   <span data-ttu-id="5e501-122">Web サービスと ws-* (WCF アダプター) の統合</span><span class="sxs-lookup"><span data-stu-id="5e501-122">Web service and WS-* integration (WCF adapter)</span></span>  

## <a name="core-capabilities"></a><span data-ttu-id="5e501-123">コア機能</span><span class="sxs-lookup"><span data-stu-id="5e501-123">Core capabilities</span></span>  
 <span data-ttu-id="5e501-124">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]堅牢性、接続されている、サービス指向アプリケーションの構築に重点を置いての新機能の範囲を指定する BizTalk Server の機能を拡張します。</span><span class="sxs-lookup"><span data-stu-id="5e501-124">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] extends the functionality of BizTalk Server to provide a range of new capabilities focused on building robust, connected, service-oriented applications.</span></span> <span data-ttu-id="5e501-125">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]は BizTalk Server コンポーネントを接続可能な作業の個々 の単位として処理、必要に応じてを形成疎結合されたソリューションです。</span><span class="sxs-lookup"><span data-stu-id="5e501-125">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] treats BizTalk Server components as individual units of work that can be connected, as desired, to form loosely coupled solutions.</span></span> <span data-ttu-id="5e501-126">コア機能の一部を次に示しますを[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]BizTalk Server の機能を強化するために提供します。</span><span class="sxs-lookup"><span data-stu-id="5e501-126">The following are some of the core capabilities that the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] provides to enhance the capabilities of BizTalk Server:</span></span>  
  
-   <span data-ttu-id="5e501-127">**ポリシーが仲介を駆動します。**</span><span class="sxs-lookup"><span data-stu-id="5e501-127">**Policy driven mediation.**</span></span> <span data-ttu-id="5e501-128">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]は次の実行します。</span><span class="sxs-lookup"><span data-stu-id="5e501-128">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] does the following:</span></span>  
  
    -   <span data-ttu-id="5e501-129">メッセージの発行時に軽量なサービス構成をサポートする行程ベースのルーティングを提供します。</span><span class="sxs-lookup"><span data-stu-id="5e501-129">It provides itinerary-based routing that supports lightweight service composition at the time of message publication.</span></span> <span data-ttu-id="5e501-130">このアプローチでは、サービス エンドポイントとサービス レジストリまたはビジネス ルール ポリシーを使用してメッセージのルーティング仲介要件の動的な検出できます。</span><span class="sxs-lookup"><span data-stu-id="5e501-130">This approach allows dynamic discovery of service endpoints and mediation requirements for message routing using a service registry or the business rules policy.</span></span>  
  
    -   <span data-ttu-id="5e501-131">受信した日程ベースのルーティングを動的解決し、メッセージの後、メッセージ コンテキストに追加するサーバー側の日程を使用するは、ポリシーの集中化のサポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="5e501-131">It adds support for policy centralization for itinerary-based routing using server-side itineraries that are dynamically resolved and added to the message context after a message is received.</span></span> <span data-ttu-id="5e501-132">自身の要求のルーティング方法の完全に対応していないクライアントからのメッセージの処理を有効、一元化された場所の日程を管理します。</span><span class="sxs-lookup"><span data-stu-id="5e501-132">Managing itineraries in a central location enables the processing of messages from clients that are completely unaware of how their requests are being routed.</span></span>  
  
    -   <span data-ttu-id="5e501-133">拡張のバージョンを使用して、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]型リゾルバーとアダプター プロバイダー フレームワークでは、エンドポイントと変換の要件の動的な解決を有効にする以外の場合は、サービスからコンシューマーを効果的に分離これです。</span><span class="sxs-lookup"><span data-stu-id="5e501-133">It uses an enhanced version of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Resolver and Adapter Provider Framework, which enables dynamic resolution of endpoints and transformation requirements; this effectively decouples the consumer from the services.</span></span>  
  
-   <span data-ttu-id="5e501-134">**システムを接続します。**</span><span class="sxs-lookup"><span data-stu-id="5e501-134">**Connecting systems.**</span></span> <span data-ttu-id="5e501-135">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]は次の実行します。</span><span class="sxs-lookup"><span data-stu-id="5e501-135">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] does the following:</span></span>  
  
    -   <span data-ttu-id="5e501-136">メッセージの XML 名前空間を正規化するパイプライン コンポーネントを提供します。</span><span class="sxs-lookup"><span data-stu-id="5e501-136">It provides pipeline components that normalize XML message namespaces.</span></span>  
  
    -   <span data-ttu-id="5e501-137">その統合 JMS WebSphere MQ アダプターを通じて BizTalk Server 用です。</span><span class="sxs-lookup"><span data-stu-id="5e501-137">It integrates with JMS through the WebSphere MQ adapter for BizTalk Server.</span></span>  
  
    -   <span data-ttu-id="5e501-138">動的なサービスの集計、メッセージのルーティング、メッセージ検証、およびメッセージの変換を有効にできるメッセージ交換パターンが容易になります。</span><span class="sxs-lookup"><span data-stu-id="5e501-138">It facilitates message exchange patterns that enable dynamic service aggregation, message routing, message validation, and message transformation.</span></span>  
  
    -   <span data-ttu-id="5e501-139">これは、レジストリと UDDI 3.0 を使用してリポジトリ統合からサービス エンドポイントの検出をサポートします。</span><span class="sxs-lookup"><span data-stu-id="5e501-139">It supports service endpoint discovery from registry and repository integration using UDDI 3.0.</span></span>  
  
    -   <span data-ttu-id="5e501-140">基幹業務 (LOB) アダプターを通じて BizTalk Server の WCF カスタム BizTalk アダプターを使用して、メッセージのルーティングをサポートします。</span><span class="sxs-lookup"><span data-stu-id="5e501-140">It supports message routing through line-of-business (LOB) adapters by using the WCF-Custom BizTalk Adapter for BizTalk Server.</span></span>  
  
-   <span data-ttu-id="5e501-141">**管理および監視します。**</span><span class="sxs-lookup"><span data-stu-id="5e501-141">**Management and monitoring.**</span></span> <span data-ttu-id="5e501-142">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]は次の実行します。</span><span class="sxs-lookup"><span data-stu-id="5e501-142">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] does the following:</span></span>  
  
    -   <span data-ttu-id="5e501-143">例外管理フレームワークとツールを提供します。</span><span class="sxs-lookup"><span data-stu-id="5e501-143">It provides exception management framework and tools.</span></span>  
  
    -   <span data-ttu-id="5e501-144">メッセージの修復して、管理ポータルを使用して再送信を容易にサンプル アプリケーションとして付属します。</span><span class="sxs-lookup"><span data-stu-id="5e501-144">It facilitates message repair and resubmission using a management portal, shipped as a sample application.</span></span> <span data-ttu-id="5e501-145">この Web アプリケーションは、特定のエラーが発生したときにもカスタマイズ可能な電子メール通知をサポートします。</span><span class="sxs-lookup"><span data-stu-id="5e501-145">This Web application also supports customizable e-mail notifications when a specific error occurs.</span></span>  
  
    -   <span data-ttu-id="5e501-146">これにより、BizTalk Server のエンドポイントとレジストリの統合、管理、および公開できます。</span><span class="sxs-lookup"><span data-stu-id="5e501-146">It allows BizTalk Server endpoint and registry integration, management, and publication.</span></span>  
  
    -   <span data-ttu-id="5e501-147">バージョン管理されたサーバー側の日程の一元的なリポジトリを提供します。</span><span class="sxs-lookup"><span data-stu-id="5e501-147">It provides a centralized repository of versioned server-side itineraries.</span></span>  
  
    -   <span data-ttu-id="5e501-148">BizTalk Server アプリケーションのレポートと分析をサポートします。</span><span class="sxs-lookup"><span data-stu-id="5e501-148">It supports reporting and analytics for BizTalk Server applications.</span></span>  
  
    -   <span data-ttu-id="5e501-149">開始時刻、終了時刻、およびサービスの仲介のシーケンスをなど、itinerary サービスの実行を追跡するためにビジネス アクティビティ監視のコンポーネントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5e501-149">It includes Business Activity Monitoring components to track itinerary service execution, including start time, end time, and service mediation sequence.</span></span>  
  
-   <span data-ttu-id="5e501-150">**SOA 統制します。**</span><span class="sxs-lookup"><span data-stu-id="5e501-150">**SOA governance.**</span></span> <span data-ttu-id="5e501-151">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]は次の実行します。</span><span class="sxs-lookup"><span data-stu-id="5e501-151">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] does the following:</span></span>  
  
    -   <span data-ttu-id="5e501-152">AmberPoint と SOA ソフトウェアから BizTalk Server の組み込み管理エージェントを含む、サード パーティの SOA 管理ソリューションと統合できます。</span><span class="sxs-lookup"><span data-stu-id="5e501-152">It integrates with third-party SOA governance solutions, including embedded management agents for BizTalk Server from AmberPoint and SOA Software.</span></span>  

> [!TIP]
> <span data-ttu-id="5e501-153">[Understanding BizTalk Server](../core/understanding-biztalk-server.md)メッセージング エンジンでは、その他の詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="5e501-153">[Understanding BizTalk Server](../core/understanding-biztalk-server.md) provides more details on the messaging engine, and more.</span></span>

## <a name="get-some-help"></a><span data-ttu-id="5e501-154">いくつかのヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="5e501-154">Get some help</span></span>
<span data-ttu-id="5e501-155">いくつかのヘルプを取得し、会社の他のヘルプ、 [BizTalk ESB Toolkit フォーラム](http://go.microsoft.com/fwlink/?LinkID=185951&clcid=0x409)です。</span><span class="sxs-lookup"><span data-stu-id="5e501-155">Get some help, and help others at the [BizTalk ESB Toolkit forums](http://go.microsoft.com/fwlink/?LinkID=185951&clcid=0x409).</span></span>

## <a name="next-steps"></a><span data-ttu-id="5e501-156">次の手順</span><span class="sxs-lookup"><span data-stu-id="5e501-156">Next steps</span></span>
[<span data-ttu-id="5e501-157">BizTalk ESB Toolkit の内容</span><span class="sxs-lookup"><span data-stu-id="5e501-157">Contents of the BizTalk ESB Toolkit</span></span>](contents-of-the-biztalk-esb-toolkit.md)  
