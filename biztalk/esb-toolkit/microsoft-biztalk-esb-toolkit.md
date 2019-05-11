---
title: Microsoft BizTalk ESB Toolkit |Microsoft Docs
description: 概要説明、一般的なシナリオ、および BizTalk Server で ESB Toolkit のコンポーネント
caps.latest.revision: 14
author: MandiOhlinger
manager: anneta
ms.custom: ''
ms.date: 08/10/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 17ffaebc-7e33-4de8-8e94-109cd5d16ca0
ms.author: mandia
ms.openlocfilehash: 67c81f787d71cddee3962021f574342058edfa4a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400097"
---
# <a name="microsoft-biztalk-esb-toolkit"></a><span data-ttu-id="a3540-103">Microsoft BizTalk ESB Toolkit</span><span class="sxs-lookup"><span data-stu-id="a3540-103">Microsoft BizTalk ESB Toolkit</span></span>
<span data-ttu-id="a3540-104">![BizTalk ESB Toolkit ロゴ](../esb-toolkit/media/biztalkesbtoolkitlogo.gif "BizTalkESBToolkitLogo")</span><span class="sxs-lookup"><span data-stu-id="a3540-104">![BizTalk ESB Toolkit Logo](../esb-toolkit/media/biztalkesbtoolkitlogo.gif "BizTalkESBToolkitLogo")</span></span>  
  
## <a name="summary"></a><span data-ttu-id="a3540-105">まとめ</span><span class="sxs-lookup"><span data-stu-id="a3540-105">Summary</span></span>  
 <span data-ttu-id="a3540-106">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]使用[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]疎結合のメッセージング アーキテクチャをサポートします。</span><span class="sxs-lookup"><span data-stu-id="a3540-106">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] uses [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] to support a loosely coupled messaging architecture.</span></span> <span data-ttu-id="a3540-107">BizTalk Server には、サービス指向アーキテクチャ (SOA) アプリケーションの効率性と拡張性の高いプラットフォームを提供するメッセージング アプリケーションを作成して動作して、いっぱいになるサブスクリプションの強力なパブリッシュ/サブスクライブ メカニズムが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a3540-107">BizTalk Server includes a powerful publish/subscribe mechanism for messaging applications that works by creating and filling subscriptions, which provides a highly efficient and scalable platform for service-oriented architecture (SOA) applications.</span></span>  
  
 <span data-ttu-id="a3540-108">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]さまざまな軽量のサービスのスケジュールに基づくサービス呼び出しが組み込まれた堅牢な接続されている、サービス指向のアプリケーションの構築に重点を置いた新しい機能を提供する BizTalk Server の機能を拡張合成、動的解決のエンドポイントやマップ Web サービスと ws-\* の統合、障害管理とレポート、およびサードパーティの SOA 管理ソリューションとの統合。</span><span class="sxs-lookup"><span data-stu-id="a3540-108">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] extends the functionality of BizTalk Server to provide a range of new capabilities focused on building robust, connected, service-oriented applications that incorporate itinerary-based service invocation for lightweight service composition, dynamic resolution of endpoints and maps, Web service and WS-\* integration, fault management and reporting, and integration with third-party SOA governance solutions.</span></span>  
  
## <a name="overview"></a><span data-ttu-id="a3540-109">概要</span><span class="sxs-lookup"><span data-stu-id="a3540-109">Overview</span></span>  
 <span data-ttu-id="a3540-110">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]アーキテクチャに関するガイダンス、パターン、および Microsoft プラットフォームでエンタープライズ サービス バス (ESB) の開発を簡略化し、Microsoft のお客様に拡張を許可する、BizTalk Server と .NET Framework のコンポーネントのコレクションを提供します。独自のメッセージングとの統合ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="a3540-110">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] provides architectural guidance, patterns, and a collection of BizTalk Server and .NET Framework components to simplify the development of an Enterprise Service Bus (ESB) on the Microsoft platform and to allow Microsoft customers to extend their own messaging and integration solutions.</span></span>  
  
## <a name="common-scenarios"></a><span data-ttu-id="a3540-111">一般的なシナリオ</span><span class="sxs-lookup"><span data-stu-id="a3540-111">Common Scenarios</span></span>  
 <span data-ttu-id="a3540-112">サービス指向アーキテクチャ (SOA) を有効にするためのインフラストラクチャの実装のコンテキストで Enterprise Service Bus (ESB) が広く使用されているターム。</span><span class="sxs-lookup"><span data-stu-id="a3540-112">The term Enterprise Service Bus (ESB) is widely used in the context of implementing an infrastructure for enabling a service-oriented architecture (SOA).</span></span> <span data-ttu-id="a3540-113">ただし、Soa のデプロイによって現実エクスペリエンスでは、ESB は包括的なサービス指向インフラストラクチャ (SOI) を構成する多くの構成要素の 1 つだけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a3540-113">However, real-world experience with the deployment of SOAs has shown that an ESB is only one of many building blocks that make up a comprehensive Service-Oriented Infrastructure (SOI).</span></span> <span data-ttu-id="a3540-114">ESB がさまざまな異なる方向で変化したという用語とその定義は、個々 の ESB との統合プラットフォーム ベンダーの解釈および特定の SOA イニシアティブの要件によって異なります。</span><span class="sxs-lookup"><span data-stu-id="a3540-114">The term ESB has morphed in a number of different directions, and its definition depends on the interpretation of individual ESB and integration platform vendors and on the requirements of particular SOA initiatives.</span></span>  
  
 <span data-ttu-id="a3540-115">Microsoft が成功した多くの現実 SOI 実装から収集された経験に基づき、考えることができます、ESB の従来のエンタープライズ アプリケーション統合 (EAI)、メッセージ指向ミドルウェア、に基づいてアーキテクチャのパターンのコレクションWeb サービス、.NET と Java の相互運用性、ホスト システム統合、およびサービス レジストリおよび資産リポジトリとの相互運用。</span><span class="sxs-lookup"><span data-stu-id="a3540-115">Based on the experience Microsoft has gathered from many successful real-world SOI implementations, you can think of an ESB as a collection of architectural patterns based on traditional enterprise application integration (EAI), message-oriented middleware, Web services, .NET and Java interoperability, host system integration, and interoperability with service registries and asset repositories.</span></span>  
  
 <span data-ttu-id="a3540-116">図 1 は、ESB アーキテクチャを提供する相互接続の種類の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="a3540-116">Figure 1 shows a high-level view of the type of interconnectivity that an ESB architecture can provide.</span></span>  
  
 <span data-ttu-id="a3540-117">![ESB の概要](../esb-toolkit/media/esboverview.gif "ESBOverview")</span><span class="sxs-lookup"><span data-stu-id="a3540-117">![ESB Overview](../esb-toolkit/media/esboverview.gif "ESBOverview")</span></span>  
  
 <span data-ttu-id="a3540-118">**図 1**</span><span class="sxs-lookup"><span data-stu-id="a3540-118">**Figure 1**</span></span>  
  
 <span data-ttu-id="a3540-119">**接続の高度な例は、Enterprise Service Bus のアーキテクチャを提供**</span><span class="sxs-lookup"><span data-stu-id="a3540-119">**A high-level example of the connectivity provided the Enterprise Service Bus architecture**</span></span>  
  
## <a name="audience-requirements"></a><span data-ttu-id="a3540-120">対象ユーザーの要件</span><span class="sxs-lookup"><span data-stu-id="a3540-120">Audience Requirements</span></span>  
 <span data-ttu-id="a3540-121">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Microsoft BizTalk Server ソリューションまたはを使用するその他のソリューションを作成する開発者のためのものでは、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="a3540-121">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] is intended for developers who create Microsoft BizTalk Server solutions or other solutions that use the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] components.</span></span> <span data-ttu-id="a3540-122">フル活用するために、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]開発者の知識を持っているし、次の操作が発生する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3540-122">To take full advantage of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)], developers should possess knowledge and experience working with the following:</span></span>  

- [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]

- [!INCLUDE[btsVStudioNoVersion_md](../includes/btsvstudionoversion-md.md)]
  
- <span data-ttu-id="a3540-123">Microsoft .NET 開発手法、ASP.NET Web サービスと .NET Framework コンポーネントの開発など</span><span class="sxs-lookup"><span data-stu-id="a3540-123">Microsoft .NET development techniques, including the development of ASP.NET Web services and .NET Framework components</span></span>  
  
## <a name="design-goals"></a><span data-ttu-id="a3540-124">設計目標</span><span class="sxs-lookup"><span data-stu-id="a3540-124">Design Goals</span></span>  
 <span data-ttu-id="a3540-125">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]一連をサポートし、メッセージ ベースのエンタープライズ アプリケーションを構築しやすく疎結合メッセージング環境を実装するコンポーネントの相互運用で構成されています。</span><span class="sxs-lookup"><span data-stu-id="a3540-125">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] consists of a series of interoperating components that support and implement a loosely coupled messaging environment that makes it easier to build message-based enterprise applications.</span></span> <span data-ttu-id="a3540-126">サービスとコンポーネントは、次の 7 つのカテゴリに自然な分類されます。</span><span class="sxs-lookup"><span data-stu-id="a3540-126">The services and components fall naturally into the following seven categories:</span></span>  
  
- <span data-ttu-id="a3540-127">**Web サービス**:これらは、スケジュールの処理、例外管理、エンドポイント、マップ、BizTalk Server の操作、およびメッセージの変換の解像度などの内部サービスを公開します。</span><span class="sxs-lookup"><span data-stu-id="a3540-127">**Web services** : These expose internal services such as itinerary processing, exception management, resolution of endpoints and maps, BizTalk Server operations, and message transformation.</span></span>  
  
- <span data-ttu-id="a3540-128">**スケジュール サービス**:スケジュールに基づくルーティングを実行するためのオーケストレーションおよびメッセージング ベースのサービスが含まれます[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="a3540-128">**Itinerary services** : These include orchestration-based and messaging-based services for performing itinerary-based routing for [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="a3540-129">スケジュールに基づくルーティングのカスタム サービスを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="a3540-129">You can create custom services for itinerary-based routing.</span></span>  
  
- <span data-ttu-id="a3540-130">**スケジュール オンランプします。**</span><span class="sxs-lookup"><span data-stu-id="a3540-130">**Itinerary on-ramps.**</span></span> <span data-ttu-id="a3540-131">これら外部メッセージを受信、メッセージごとに適切なスケジュールをアタッチおよびスケジュールの処理を実行使用する、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]リゾルバーとアダプターのプロバイダー フレームワークのエンドポイントとメタデータの動的な解決します。</span><span class="sxs-lookup"><span data-stu-id="a3540-131">These receive external messages, attach the appropriate itinerary for each message, and perform itinerary processing; they use the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Resolver and Adapter Provider Framework for dynamic resolution of endpoints and metadata.</span></span>  
  
- <span data-ttu-id="a3540-132">**オンランプ**:これらは、さまざまな形式と HTTP、JMS、WMQ、FTP、フラット ファイル、XML などのトランスポートで外部メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="a3540-132">**On-ramps** : These receive external messages in a range of formats and transports, such as HTTP, JMS, WMQ, FTP, Flat File, and XML.</span></span> <span data-ttu-id="a3540-133">一般的な BizTalk Server は必要に応じて使用する受信場所、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]相互運用のパイプライン コンポーネント、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]リゾルバーとアダプターのプロバイダー フレームワークのエンドポイントとメタデータの動的な解決します。</span><span class="sxs-lookup"><span data-stu-id="a3540-133">They are typical BizTalk Server receive locations that optionally use the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] interop pipeline components and the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Resolver and Adapter Provider Framework for dynamic resolution of endpoints and metadata.</span></span>  
  
- <span data-ttu-id="a3540-134">**オフランプ**:これらの実装では、形式と SOAP、WCF、JMS、WMQ、FTP、HTTP、フラット ファイル、XML、またはその他のすべてのカスタム形式などのトランスポートを使用してメッセージの配信用のポートを送信します。</span><span class="sxs-lookup"><span data-stu-id="a3540-134">**Off-ramps** : These implement send ports for the delivery of messages using formats and transports such as SOAP, WCF, JMS, WMQ, FTP, HTTP, Flat File, XML, or any other custom formats.</span></span> <span data-ttu-id="a3540-135">通常の BizTalk Server の動的送信ポートを直接バインドされたメッセージ ボックスに、必要に応じて使用するには、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]相互運用のパイプライン コンポーネント、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]リゾルバーとアダプターのエンドポイントの動的解決のためのプロバイダー フレームワークメタデータ。</span><span class="sxs-lookup"><span data-stu-id="a3540-135">They are typical BizTalk Server dynamic send ports that are direct-bound to the Message Box and that optionally use the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] interop pipeline components and the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Resolver and Adapter Provider Framework for dynamic resolution of endpoints and metadata.</span></span>  
  
- <span data-ttu-id="a3540-136">**例外管理フレームワーク**:これには、例外 Web サービスでは、例外管理 API、および強化、処理、および例外の詳細を渡す ESB 管理ポータルにコンポーネントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a3540-136">**Exception Management Framework** : This includes the exception Web service, the exception management API, and components that enrich, process, and pass exception details to the ESB Management Portal.</span></span>  
  
- <span data-ttu-id="a3540-137">**ESB 管理ポータル**:これは、レジストリのプロビジョニング、例外の仲介、アラート通知、および分析を提供します。</span><span class="sxs-lookup"><span data-stu-id="a3540-137">**ESB Management Portal** : This provides registry provisioning, exception mediation, alert notification, and analytics.</span></span>  
  
  <span data-ttu-id="a3540-138">大部分のこれらのコンポーネントとサービスによって実装される機能に依存して[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]オーケストレーション、変換、およびビジネス ルール エンジンと、メッセージ ボックス データベースなどです。</span><span class="sxs-lookup"><span data-stu-id="a3540-138">Many of these components and services rely on features implemented by [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)], such as the Orchestration, Transformation, and Business Rules engines and the Message Box database.</span></span> <span data-ttu-id="a3540-139">図 2 は、カテゴリ; の概略を示しています。コンポーネントと各カテゴリ内で発生する通常のサービスで使用されるコアの BizTalk Server システム コンポーネント、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="a3540-139">Figure 2 shows a schematic view of the categories; the components and services typically occurring within each category; and the core BizTalk Server system components used by the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span>  
  
  <span data-ttu-id="a3540-140">![ESB アーキテクチャ](../esb-toolkit/media/esbarchitecture.gif "ESBArchitecture")</span><span class="sxs-lookup"><span data-stu-id="a3540-140">![ESB Architecture](../esb-toolkit/media/esbarchitecture.gif "ESBArchitecture")</span></span>  
  
  <span data-ttu-id="a3540-141">**図 2**</span><span class="sxs-lookup"><span data-stu-id="a3540-141">**Figure 2**</span></span>  
  
  <span data-ttu-id="a3540-142">**アーキテクチャとのコンポーネント、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="a3540-142">**The architecture and components of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]**</span></span>  
  
## <a name="how-the-biztalk-esb-toolkit-works"></a><span data-ttu-id="a3540-143">BizTalk ESB Toolkit の動作</span><span class="sxs-lookup"><span data-stu-id="a3540-143">How the BizTalk ESB Toolkit Works</span></span>  
 <span data-ttu-id="a3540-144">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]受信メッセージを受け取り、演算を実行して、おそらく (が常にではありません) など、変換、配信、またはその他のカスタム定義プロセスのプロセスを実行することによって。</span><span class="sxs-lookup"><span data-stu-id="a3540-144">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] accepts inbound messages and operates on them, perhaps (but not always) by performing processes such as transformation, delivery, or any other custom defined process.</span></span> <span data-ttu-id="a3540-145">演算を指定するために必要な中心となる処理コンポーネントには、メッセージの内容を実行するには、関連付けられている手順またはを適用するプロセスを定義するメタデータとタスクを格納するメッセージが必要です。</span><span class="sxs-lookup"><span data-stu-id="a3540-145">To specify the operations required, the core processing components require a message to contain associated instructions or metadata that define the processes to apply and the tasks to execute with the message content.</span></span>  
  
 <span data-ttu-id="a3540-146">このアプローチは、サービス間の疎結合を提供します。これは、ESB メッセージごとに、特定の処理に関する予備知識が必要ないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="a3540-146">This approach provides loose coupling between services; this means that the ESB does not require prior knowledge of the specific processing for each message.</span></span> <span data-ttu-id="a3540-147">考えられる範囲のプロセスと各プロセスを適用する方法を知るだけがあります。</span><span class="sxs-lookup"><span data-stu-id="a3540-147">It just has to know the possible range of processes and how to apply each process.</span></span> <span data-ttu-id="a3540-148">広範囲の可能なプロセスのプロセスとメッセージ内の指示のマッピングを指定するためのオプションは、構成およびコードを再デプロイを変更しなくても、動作を調整するための柔軟なメカニズムを提供します。コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="a3540-148">The wide range of options for specifying the available processes and the mapping between the processes and the instructions within messages provides a flexible mechanism for configuring and adjusting behavior, without requiring changes to code and redeployment of components.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a3540-149">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="a3540-149">In this section</span></span>

- [<span data-ttu-id="a3540-150">インストールして、Microsoft BizTalk ESB Toolkit の構成</span><span class="sxs-lookup"><span data-stu-id="a3540-150">Install and configure the Microsoft BizTalk ESB Toolkit</span></span>](install-and-configure-the-microsoft-biztalk-esb-toolkit.md)

- [<span data-ttu-id="a3540-151">BizTalk ESB Toolkit について</span><span class="sxs-lookup"><span data-stu-id="a3540-151">Introduction to the BizTalk ESB Toolkit</span></span>](introduction-to-the-biztalk-esb-toolkit.md)

- [<span data-ttu-id="a3540-152">作業の開始し、BizTalk ESB Toolkit を理解します。</span><span class="sxs-lookup"><span data-stu-id="a3540-152">Getting started and understanding the BizTalk ESB Toolkit</span></span>](getting-started-with-the-biztalk-esb-toolkit.md)

- [<span data-ttu-id="a3540-153">主要なシナリオおよび開発タスク</span><span class="sxs-lookup"><span data-stu-id="a3540-153">Key scenarios and development tasks</span></span>](key-scenarios-and-development-tasks.md)

- [<span data-ttu-id="a3540-154">Itinerary designer を使用してスケジュールを作成します。</span><span class="sxs-lookup"><span data-stu-id="a3540-154">Creating itineraries using itinerary designer</span></span>](creating-itineraries-using-itinerary-designer.md)

- [<span data-ttu-id="a3540-155">BizTalk ESB Toolkit サンプル アプリケーション</span><span class="sxs-lookup"><span data-stu-id="a3540-155">BizTalk ESB Toolkit sample applications</span></span>](biztalk-esb-toolkit-sample-applications.md)

- [<span data-ttu-id="a3540-156">変更して、BizTalk ESB Toolkit の拡張</span><span class="sxs-lookup"><span data-stu-id="a3540-156">Modifying and extending the BizTalk ESB Toolkit</span></span>](modifying-and-extending-the-biztalk-esb-toolkit.md)

- [<span data-ttu-id="a3540-157">BizTalk ESB Toolkit による管理</span><span class="sxs-lookup"><span data-stu-id="a3540-157">Administration with the BizTalk ESB Toolkit</span></span>](administration-with-the-biztalk-esb-toolkit.md)

- [<span data-ttu-id="a3540-158">SOA ガバナンス統合</span><span class="sxs-lookup"><span data-stu-id="a3540-158">SOA governance integration</span></span>](soa-governance-integration.md)

- [<span data-ttu-id="a3540-159">BizTalk ESB Toolkit のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="a3540-159">Troubleshooting the BizTalk ESB Toolkit</span></span>](troubleshooting-the-biztalk-esb-toolkit.md)
  
## <a name="related-topics"></a><span data-ttu-id="a3540-160">関連トピック</span><span class="sxs-lookup"><span data-stu-id="a3540-160">Related topics</span></span>  
  
-   [<span data-ttu-id="a3540-161">BizTalk サービス指向ソリューション</span><span class="sxs-lookup"><span data-stu-id="a3540-161">BizTalk Service Oriented Solutions</span></span>](../core/service-oriented-solution.md)

- [<span data-ttu-id="a3540-162">BizTalk Server と Web サービスの使用</span><span class="sxs-lookup"><span data-stu-id="a3540-162">Using Web Services with BizTalk Server</span></span>](../core/using-web-services.md)  