---
title: BizTalk Server で ESB Toolkit の概要 |Microsoft Docs
description: ESB Toolkit と BizTalk Server でその機能の説明
caps.latest.revision: 6
author: MandiOhlinger
manager: anneta
ms.custom: ''
ms.date: 08/10/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e190b34-40bc-4f27-9b4f-56e98591e1d4
ms.author: mandia
ms.openlocfilehash: c334e5c4404492fbda28c301d8806471b25623ca
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400047"
---
# <a name="what-is-the-biztalk-esb-toolkit"></a><span data-ttu-id="438ed-103">BizTalk ESB Toolkit とは</span><span class="sxs-lookup"><span data-stu-id="438ed-103">What is the BizTalk ESB Toolkit</span></span>

## <a name="overview"></a><span data-ttu-id="438ed-104">概要</span><span class="sxs-lookup"><span data-stu-id="438ed-104">Overview</span></span>
<span data-ttu-id="438ed-105">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]疎結合のメッセージング アーキテクチャをサポートするために BizTalk Server の機能を拡張します。</span><span class="sxs-lookup"><span data-stu-id="438ed-105">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] extends the capabilities of BizTalk Server to support a loosely coupled messaging architecture.</span></span> <span data-ttu-id="438ed-106">ほとんどの開発者は、コードを使用した、手順、またはオブジェクト指向開発パラダイムに慣れています。</span><span class="sxs-lookup"><span data-stu-id="438ed-106">Most developers are familiar with code-oriented, procedural, or object-oriented development paradigms.</span></span> <span data-ttu-id="438ed-107">ただし、BizTalk ソリューションの開発を始めるには、ときに開発者を BizTalk Server のメッセージ指向の機能が見落とされがちに傾向があります。</span><span class="sxs-lookup"><span data-stu-id="438ed-107">However, when starting to develop BizTalk solutions, developers tend to overlook the message-oriented capabilities of BizTalk Server.</span></span>  
  
 <span data-ttu-id="438ed-108">BizTalk Server には、サブスクリプションの入力を作成して動作する強力なパブリッシュ/サブスクライブのメカニズムが含まれています。</span><span class="sxs-lookup"><span data-stu-id="438ed-108">BizTalk Server includes a powerful publish/subscribe mechanism that works by creating and filling subscriptions.</span></span> <span data-ttu-id="438ed-109">BizTalk メッセージ ボックス データベースに新しいメッセージが到着すると、メッセージ エージェントはサブスクライバーを識別して、サブスクリプションを持つ任意のエンドポイントにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="438ed-109">When a new message arrives in the BizTalk Message Box database, a message agent identifies subscribers and sends the message to any endpoints that have subscriptions.</span></span> <span data-ttu-id="438ed-110">関連付けられた受信のメッセージは、待機しているまたは送信ポートの作成 (など、型は、受信メッセージのプロパティに一致するフィルター条件を持つ、受信ポートにオーケストレーションをバインドを含む、いくつかの方法でサブスクリプションを作成できます。ポイント、またはルーティング可能なプロパティの値)。</span><span class="sxs-lookup"><span data-stu-id="438ed-110">Subscriptions can be created in several ways, including binding an orchestration to a receive port, having a correlated receive waiting for a message, or creating a send port with a filter condition that matches a property of the message (such as the type, the receive point, or the value of a routable property).</span></span>  
  
 <span data-ttu-id="438ed-111">BizTalk Server では、この効率的でスケーラブルな方法を提供し、一連の不連続のサブ プロセスを作成して、シーケンスの詳細について心配せずに、その呼び出しをトリガーするメッセージの種類を定義ができます。</span><span class="sxs-lookup"><span data-stu-id="438ed-111">By providing this efficient and scalable approach, BizTalk Server enables developers to create a series of discrete sub-processes, define the types of messages that trigger their invocation, and not worry about the sequence.</span></span> <span data-ttu-id="438ed-112">メッセージの到着によって開始されたプロセスは、メッセージの処理を実行します。メッセージを処理した後、これは、1 つまたは複数のサブプロセスをアクティブ化できるメッセージ ボックス データベースを同じまたは別のメッセージを提供できます。</span><span class="sxs-lookup"><span data-stu-id="438ed-112">A process initiated by the arrival of a message performs its processing on the message; after it processes the message, it can deliver this or another message to the Message Box database, which, in turn, may activate one or more sub-processes.</span></span>  
  
 <span data-ttu-id="438ed-113">Microsoft では、Windows Server、.NET Framework では、BizTalk Server など、包括的なサービス指向のインフラストラクチャを構築するために必要な重要な構成要素を提供します。</span><span class="sxs-lookup"><span data-stu-id="438ed-113">Microsoft provides key building blocks that are required for building comprehensive Service-Oriented Infrastructures, including Windows Server, the .NET Framework, and BizTalk Server.</span></span> <span data-ttu-id="438ed-114">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]次を含む、ESB の最も一般的なサービスの基礎を提供するため、BizTalk Server に基づきます。</span><span class="sxs-lookup"><span data-stu-id="438ed-114">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] is based on BizTalk Server because it provides the basis for the most common ESB services, including the following:</span></span>  
  
-   <span data-ttu-id="438ed-115">メッセージのルーティング</span><span class="sxs-lookup"><span data-stu-id="438ed-115">Message routing</span></span>  
  
-   <span data-ttu-id="438ed-116">メッセージの検証</span><span class="sxs-lookup"><span data-stu-id="438ed-116">Message validation</span></span>  
  
-   <span data-ttu-id="438ed-117">メッセージの変換</span><span class="sxs-lookup"><span data-stu-id="438ed-117">Message transformation</span></span>  
  
-   <span data-ttu-id="438ed-118">接続用の拡張可能なアダプター フレームワーク</span><span class="sxs-lookup"><span data-stu-id="438ed-118">Extensible adapter framework for connectivity</span></span>  
  
-   <span data-ttu-id="438ed-119">サービス オーケストレーション</span><span class="sxs-lookup"><span data-stu-id="438ed-119">Service orchestration</span></span>  
  
-   <span data-ttu-id="438ed-120">ビジネス ルール エンジン</span><span class="sxs-lookup"><span data-stu-id="438ed-120">Business rules engine</span></span>  
  
-   <span data-ttu-id="438ed-121">ビジネス アクティビティの監視</span><span class="sxs-lookup"><span data-stu-id="438ed-121">Business activity monitoring</span></span>  
  
-   <span data-ttu-id="438ed-122">Web サービスと ws-\* (WCF アダプター) の統合</span><span class="sxs-lookup"><span data-stu-id="438ed-122">Web service and WS-\* integration (WCF adapter)</span></span>  

## <a name="core-capabilities"></a><span data-ttu-id="438ed-123">コア機能</span><span class="sxs-lookup"><span data-stu-id="438ed-123">Core capabilities</span></span>  
 <span data-ttu-id="438ed-124">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]さまざまな堅牢な接続されている、サービス指向アプリケーションの構築に重点を置いた新しい機能を提供する BizTalk Server の機能を拡張します。</span><span class="sxs-lookup"><span data-stu-id="438ed-124">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] extends the functionality of BizTalk Server to provide a range of new capabilities focused on building robust, connected, service-oriented applications.</span></span> <span data-ttu-id="438ed-125">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] BizTalk Server コンポーネントを接続できる作業の個々 の単位として扱われます、必要に応じて形成疎結合されたソリューション。</span><span class="sxs-lookup"><span data-stu-id="438ed-125">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] treats BizTalk Server components as individual units of work that can be connected, as desired, to form loosely coupled solutions.</span></span> <span data-ttu-id="438ed-126">コア機能の一部を次にする、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] BizTalk Server の機能を強化するために提供します。</span><span class="sxs-lookup"><span data-stu-id="438ed-126">The following are some of the core capabilities that the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] provides to enhance the capabilities of BizTalk Server:</span></span>  
  
- <span data-ttu-id="438ed-127">**ポリシーに基づく仲介します。**</span><span class="sxs-lookup"><span data-stu-id="438ed-127">**Policy driven mediation.**</span></span> <span data-ttu-id="438ed-128">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]は次の処理します。</span><span class="sxs-lookup"><span data-stu-id="438ed-128">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] does the following:</span></span>  
  
  - <span data-ttu-id="438ed-129">メッセージの発行時に軽量のサービスの構成をサポートするスケジュールに基づくルーティングを提供します。</span><span class="sxs-lookup"><span data-stu-id="438ed-129">It provides itinerary-based routing that supports lightweight service composition at the time of message publication.</span></span> <span data-ttu-id="438ed-130">このアプローチには、サービス エンドポイントとサービスのレジストリまたはビジネス ルール ポリシーを使用してメッセージのルーティングで仲介要件の動的な検出ができます。</span><span class="sxs-lookup"><span data-stu-id="438ed-130">This approach allows dynamic discovery of service endpoints and mediation requirements for message routing using a service registry or the business rules policy.</span></span>  
  
  - <span data-ttu-id="438ed-131">スケジュールに基づくが動的に解決され、メッセージの後に、メッセージ コンテキストに追加するサーバー側のスケジュールを使用してルーティングが受信されるは、ポリシーの集中化のサポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="438ed-131">It adds support for policy centralization for itinerary-based routing using server-side itineraries that are dynamically resolved and added to the message context after a message is received.</span></span> <span data-ttu-id="438ed-132">ユーザーに対する要求のルーティング方法の完全に対応していないクライアントからのメッセージの処理を中央の場所での旅程を管理できます。</span><span class="sxs-lookup"><span data-stu-id="438ed-132">Managing itineraries in a central location enables the processing of messages from clients that are completely unaware of how their requests are being routed.</span></span>  
  
  - <span data-ttu-id="438ed-133">拡張のバージョンを使用して、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]リゾルバーとアダプターのプロバイダー フレームワーク、エンドポイントと変換の要件の動的な解決を有効にする; 効果的に分離され、サービスのコンシューマーです。</span><span class="sxs-lookup"><span data-stu-id="438ed-133">It uses an enhanced version of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Resolver and Adapter Provider Framework, which enables dynamic resolution of endpoints and transformation requirements; this effectively decouples the consumer from the services.</span></span>  
  
- <span data-ttu-id="438ed-134">**システムを接続します。**</span><span class="sxs-lookup"><span data-stu-id="438ed-134">**Connecting systems.**</span></span> <span data-ttu-id="438ed-135">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]は次の処理します。</span><span class="sxs-lookup"><span data-stu-id="438ed-135">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] does the following:</span></span>  
  
  -   <span data-ttu-id="438ed-136">XML メッセージの名前空間の正規化のパイプライン コンポーネントを提供します。</span><span class="sxs-lookup"><span data-stu-id="438ed-136">It provides pipeline components that normalize XML message namespaces.</span></span>  
  
  -   <span data-ttu-id="438ed-137">統合 JMS WebSphere MQ アダプターを通じて BizTalk Server にします。</span><span class="sxs-lookup"><span data-stu-id="438ed-137">It integrates with JMS through the WebSphere MQ adapter for BizTalk Server.</span></span>  
  
  -   <span data-ttu-id="438ed-138">サービスの動的な集計、メッセージのルーティング、メッセージの検証、およびメッセージの変換を有効にするメッセージ交換パターンが容易になります。</span><span class="sxs-lookup"><span data-stu-id="438ed-138">It facilitates message exchange patterns that enable dynamic service aggregation, message routing, message validation, and message transformation.</span></span>  
  
  -   <span data-ttu-id="438ed-139">レジストリと UDDI 3.0 を使用して統合をリポジトリからサービス エンドポイントの検出をサポートします。</span><span class="sxs-lookup"><span data-stu-id="438ed-139">It supports service endpoint discovery from registry and repository integration using UDDI 3.0.</span></span>  
  
  -   <span data-ttu-id="438ed-140">BizTalk Server の WCF カスタム BizTalk アダプターを使用して基幹業務 (LOB) アダプターを通じてメッセージのルーティングをサポートします。</span><span class="sxs-lookup"><span data-stu-id="438ed-140">It supports message routing through line-of-business (LOB) adapters by using the WCF-Custom BizTalk Adapter for BizTalk Server.</span></span>  
  
- <span data-ttu-id="438ed-141">**管理および監視します。**</span><span class="sxs-lookup"><span data-stu-id="438ed-141">**Management and monitoring.**</span></span> <span data-ttu-id="438ed-142">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]は次の処理します。</span><span class="sxs-lookup"><span data-stu-id="438ed-142">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] does the following:</span></span>  
  
  -   <span data-ttu-id="438ed-143">例外管理フレームワークとツールを提供します。</span><span class="sxs-lookup"><span data-stu-id="438ed-143">It provides exception management framework and tools.</span></span>  
  
  -   <span data-ttu-id="438ed-144">メッセージの修復と再送信、管理ポータルを使用できるサンプル アプリケーションに付属しています。</span><span class="sxs-lookup"><span data-stu-id="438ed-144">It facilitates message repair and resubmission using a management portal, shipped as a sample application.</span></span> <span data-ttu-id="438ed-145">この Web アプリケーションは、特定のエラーが発生した場合にもカスタマイズ可能な電子メール通知をサポートします。</span><span class="sxs-lookup"><span data-stu-id="438ed-145">This Web application also supports customizable e-mail notifications when a specific error occurs.</span></span>  
  
  -   <span data-ttu-id="438ed-146">BizTalk Server のエンドポイントとレジストリの統合、管理、および発行できます。</span><span class="sxs-lookup"><span data-stu-id="438ed-146">It allows BizTalk Server endpoint and registry integration, management, and publication.</span></span>  
  
  -   <span data-ttu-id="438ed-147">サーバー側のバージョン管理されたスケジュールのリポジトリを集中管理を提供します。</span><span class="sxs-lookup"><span data-stu-id="438ed-147">It provides a centralized repository of versioned server-side itineraries.</span></span>  
  
  -   <span data-ttu-id="438ed-148">BizTalk Server アプリケーションのレポートと分析をサポートします。</span><span class="sxs-lookup"><span data-stu-id="438ed-148">It supports reporting and analytics for BizTalk Server applications.</span></span>  
  
  -   <span data-ttu-id="438ed-149">これには、開始時刻、終了時刻、およびサービス仲介シーケンスなど、スケジュール サービスの実行を追跡するために、ビジネス アクティビティ監視コンポーネントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="438ed-149">It includes Business Activity Monitoring components to track itinerary service execution, including start time, end time, and service mediation sequence.</span></span>  
  
- <span data-ttu-id="438ed-150">**SOA ガバナンス。**</span><span class="sxs-lookup"><span data-stu-id="438ed-150">**SOA governance.**</span></span> <span data-ttu-id="438ed-151">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]は次の処理します。</span><span class="sxs-lookup"><span data-stu-id="438ed-151">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] does the following:</span></span>  
  
  -   <span data-ttu-id="438ed-152">AmberPoint と SOA ソフトウェアから BizTalk Server 用の組み込み管理エージェントなど、サードパーティの SOA ガバナンス ソリューションと統合します。</span><span class="sxs-lookup"><span data-stu-id="438ed-152">It integrates with third-party SOA governance solutions, including embedded management agents for BizTalk Server from AmberPoint and SOA Software.</span></span>  

> [!TIP]
> <span data-ttu-id="438ed-153">[Understanding BizTalk Server](../core/understanding-biztalk-server.md)メッセージング エンジンでは、その他の詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="438ed-153">[Understanding BizTalk Server](../core/understanding-biztalk-server.md) provides more details on the messaging engine, and more.</span></span>

## <a name="get-some-help"></a><span data-ttu-id="438ed-154">いくつかのヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="438ed-154">Get some help</span></span>
<span data-ttu-id="438ed-155">いくつかのヘルプを取得し、ヘルプにある他のユーザー、 [BizTalk ESB Toolkit フォーラム](http://go.microsoft.com/fwlink/?LinkID=185951&clcid=0x409)します。</span><span class="sxs-lookup"><span data-stu-id="438ed-155">Get some help, and help others at the [BizTalk ESB Toolkit forums](http://go.microsoft.com/fwlink/?LinkID=185951&clcid=0x409).</span></span>

## <a name="next-steps"></a><span data-ttu-id="438ed-156">次のステップ</span><span class="sxs-lookup"><span data-stu-id="438ed-156">Next steps</span></span>
[<span data-ttu-id="438ed-157">BizTalk ESB Toolkit の内容</span><span class="sxs-lookup"><span data-stu-id="438ed-157">Contents of the BizTalk ESB Toolkit</span></span>](contents-of-the-biztalk-esb-toolkit.md)  
