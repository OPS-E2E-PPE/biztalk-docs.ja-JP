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
ms.openlocfilehash: f425c02e8f869952658f93185c78474e58df304b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023400"
---
# <a name="microsoft-biztalk-esb-toolkit"></a><span data-ttu-id="a5448-103">Microsoft BizTalk ESB Toolkit</span><span class="sxs-lookup"><span data-stu-id="a5448-103">Microsoft BizTalk ESB Toolkit</span></span>
<span data-ttu-id="a5448-104">![BizTalk ESB Toolkit ロゴ](../esb-toolkit/media/biztalkesbtoolkitlogo.gif "BizTalkESBToolkitLogo")</span><span class="sxs-lookup"><span data-stu-id="a5448-104">![BizTalk ESB Toolkit Logo](../esb-toolkit/media/biztalkesbtoolkitlogo.gif "BizTalkESBToolkitLogo")</span></span>  
  
## <a name="summary"></a><span data-ttu-id="a5448-105">まとめ</span><span class="sxs-lookup"><span data-stu-id="a5448-105">Summary</span></span>  
 <span data-ttu-id="a5448-106">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]使用[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]疎結合のメッセージング アーキテクチャをサポートします。</span><span class="sxs-lookup"><span data-stu-id="a5448-106">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] uses [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] to support a loosely coupled messaging architecture.</span></span> <span data-ttu-id="a5448-107">BizTalk Server には、メッセージング アプリケーション用の強力なパブリッシュ/サブスクライブ メカニズムが組み込まれています。このメカニズムは、サブスクリプションを作成および入力することによって機能し、サービス指向アーキテクチャ (SOA) アプリケーション向けの、高い効率と拡張性を備えたプラットフォームを提供します。</span><span class="sxs-lookup"><span data-stu-id="a5448-107">BizTalk Server includes a powerful publish/subscribe mechanism for messaging applications that works by creating and filling subscriptions, which provides a highly efficient and scalable platform for service-oriented architecture (SOA) applications.</span></span>  
  
 <span data-ttu-id="a5448-108">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]さまざまな軽量のサービスのスケジュールに基づくサービス呼び出しが組み込まれた堅牢な接続されている、サービス指向のアプリケーションの構築に重点を置いた新しい機能を提供する BizTalk Server の機能を拡張合成、動的解決のエンドポイントやマップ Web サービスと ws-\* の統合、障害管理とレポート、およびサードパーティの SOA 管理ソリューションとの統合。</span><span class="sxs-lookup"><span data-stu-id="a5448-108">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] extends the functionality of BizTalk Server to provide a range of new capabilities focused on building robust, connected, service-oriented applications that incorporate itinerary-based service invocation for lightweight service composition, dynamic resolution of endpoints and maps, Web service and WS-\* integration, fault management and reporting, and integration with third-party SOA governance solutions.</span></span>  
  
## <a name="overview"></a><span data-ttu-id="a5448-109">概要</span><span class="sxs-lookup"><span data-stu-id="a5448-109">Overview</span></span>  
 <span data-ttu-id="a5448-110">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]アーキテクチャに関するガイダンス、パターン、および Microsoft プラットフォームでエンタープライズ サービス バス (ESB) の開発を簡略化し、Microsoft のお客様に拡張を許可する、BizTalk Server と .NET Framework のコンポーネントのコレクションを提供します。独自のメッセージングとの統合ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="a5448-110">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] provides architectural guidance, patterns, and a collection of BizTalk Server and .NET Framework components to simplify the development of an Enterprise Service Bus (ESB) on the Microsoft platform and to allow Microsoft customers to extend their own messaging and integration solutions.</span></span>  
  
## <a name="common-scenarios"></a><span data-ttu-id="a5448-111">一般的なシナリオ</span><span class="sxs-lookup"><span data-stu-id="a5448-111">Common Scenarios</span></span>  
 <span data-ttu-id="a5448-112">Enterprise Service Bus (ESB) という用語は、サービス指向アーキテクチャ (SOA) を実現するためのインフラストラクチャの実装というコンテキストにおいて広く利用されています。</span><span class="sxs-lookup"><span data-stu-id="a5448-112">The term Enterprise Service Bus (ESB) is widely used in the context of implementing an infrastructure for enabling a service-oriented architecture (SOA).</span></span> <span data-ttu-id="a5448-113">しかし、SOA の開発にかかわった実際の経験から、ESB は包括的なサービス指向インフラストラクチャ (SOI) を構成する多数の構成要素の 1 つにすぎないことが判明しています。</span><span class="sxs-lookup"><span data-stu-id="a5448-113">However, real-world experience with the deployment of SOAs has shown that an ESB is only one of many building blocks that make up a comprehensive Service-Oriented Infrastructure (SOI).</span></span> <span data-ttu-id="a5448-114">ESB という用語は数多くの多様な方向に変貌し、その定義は、個々の ESB ベンダーおよび統合プラットフォーム ベンダーによって、また、特定の SOA イニシアティブの要件によって異なります。</span><span class="sxs-lookup"><span data-stu-id="a5448-114">The term ESB has morphed in a number of different directions, and its definition depends on the interpretation of individual ESB and integration platform vendors and on the requirements of particular SOA initiatives.</span></span>  
  
 <span data-ttu-id="a5448-115">Microsoft が SOA 実装の多数の実例から得た経験に基づいて、ESB を次のように考えることができます。つまり、ESB は、従来のエンタープライズ アプリケーション統合 (EAI)、メッセージ指向ミドルウェア、Web サービス、.NET と Java の相互運用性、ホスト システム統合、サービス レジストリおよび資産リポジトリとの相互運用性をベースとするアーキテクチャ パターンのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="a5448-115">Based on the experience Microsoft has gathered from many successful real-world SOI implementations, you can think of an ESB as a collection of architectural patterns based on traditional enterprise application integration (EAI), message-oriented middleware, Web services, .NET and Java interoperability, host system integration, and interoperability with service registries and asset repositories.</span></span>  
  
 <span data-ttu-id="a5448-116">図 1 は、ESB アーキテクチャを提供する相互接続の種類の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="a5448-116">Figure 1 shows a high-level view of the type of interconnectivity that an ESB architecture can provide.</span></span>  
  
 <span data-ttu-id="a5448-117">![ESB の概要](../esb-toolkit/media/esboverview.gif "ESBOverview")</span><span class="sxs-lookup"><span data-stu-id="a5448-117">![ESB Overview](../esb-toolkit/media/esboverview.gif "ESBOverview")</span></span>  
  
 <span data-ttu-id="a5448-118">**図 1**</span><span class="sxs-lookup"><span data-stu-id="a5448-118">**Figure 1**</span></span>  
  
 <span data-ttu-id="a5448-119">**接続の高度な例は、Enterprise Service Bus のアーキテクチャを提供**</span><span class="sxs-lookup"><span data-stu-id="a5448-119">**A high-level example of the connectivity provided the Enterprise Service Bus architecture**</span></span>  
  
## <a name="audience-requirements"></a><span data-ttu-id="a5448-120">利用者の要件</span><span class="sxs-lookup"><span data-stu-id="a5448-120">Audience Requirements</span></span>  
 <span data-ttu-id="a5448-121">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Microsoft BizTalk Server ソリューションまたはを使用するその他のソリューションを作成する開発者のためのものでは、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="a5448-121">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] is intended for developers who create Microsoft BizTalk Server solutions or other solutions that use the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] components.</span></span> <span data-ttu-id="a5448-122">フル活用するために、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]開発者の知識を持っているし、次の操作が発生する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5448-122">To take full advantage of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)], developers should possess knowledge and experience working with the following:</span></span>  

- [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]

- [!INCLUDE[btsVStudioNoVersion_md](../includes/btsvstudionoversion-md.md)]
  
- <span data-ttu-id="a5448-123">Microsoft .NET 開発手法 (ASP.NET Web サービスおよび .NET Framework コンポーネントの開発など)</span><span class="sxs-lookup"><span data-stu-id="a5448-123">Microsoft .NET development techniques, including the development of ASP.NET Web services and .NET Framework components</span></span>  
  
## <a name="design-goals"></a><span data-ttu-id="a5448-124">設計目標</span><span class="sxs-lookup"><span data-stu-id="a5448-124">Design Goals</span></span>  
 <span data-ttu-id="a5448-125">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]一連をサポートし、メッセージ ベースのエンタープライズ アプリケーションを構築しやすく疎結合メッセージング環境を実装するコンポーネントの相互運用で構成されています。</span><span class="sxs-lookup"><span data-stu-id="a5448-125">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] consists of a series of interoperating components that support and implement a loosely coupled messaging environment that makes it easier to build message-based enterprise applications.</span></span> <span data-ttu-id="a5448-126">サービスとコンポーネントは、次の 7 つのカテゴリに自然な分類されます。</span><span class="sxs-lookup"><span data-stu-id="a5448-126">The services and components fall naturally into the following seven categories:</span></span>  
  
- <span data-ttu-id="a5448-127">**Web サービス**: これら itinerary 処理、例外管理、エンドポイント、マップ、BizTalk Server の操作、およびメッセージの変換の解像度などの内部サービスを公開します。</span><span class="sxs-lookup"><span data-stu-id="a5448-127">**Web services** : These expose internal services such as itinerary processing, exception management, resolution of endpoints and maps, BizTalk Server operations, and message transformation.</span></span>  
  
- <span data-ttu-id="a5448-128">**スケジュール サービス**: スケジュールに基づくルーティングを実行するためのオーケストレーションおよびメッセージング ベースのサービスが含まれます[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="a5448-128">**Itinerary services** : These include orchestration-based and messaging-based services for performing itinerary-based routing for [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="a5448-129">スケジュールに基づくルーティングのカスタム サービスを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="a5448-129">You can create custom services for itinerary-based routing.</span></span>  
  
- <span data-ttu-id="a5448-130">**スケジュール オンランプします。**</span><span class="sxs-lookup"><span data-stu-id="a5448-130">**Itinerary on-ramps.**</span></span> <span data-ttu-id="a5448-131">これら外部メッセージを受信、メッセージごとに適切なスケジュールをアタッチおよびスケジュールの処理を実行使用する、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]リゾルバーとアダプターのプロバイダー フレームワークのエンドポイントとメタデータの動的な解決します。</span><span class="sxs-lookup"><span data-stu-id="a5448-131">These receive external messages, attach the appropriate itinerary for each message, and perform itinerary processing; they use the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Resolver and Adapter Provider Framework for dynamic resolution of endpoints and metadata.</span></span>  
  
- <span data-ttu-id="a5448-132">**オンランプ**: 範囲の形式とトランスポートで HTTP、JMS、WMQ、FTP、フラット ファイル、XML などの外部のメッセージが表示されるこれらします。</span><span class="sxs-lookup"><span data-stu-id="a5448-132">**On-ramps** : These receive external messages in a range of formats and transports, such as HTTP, JMS, WMQ, FTP, Flat File, and XML.</span></span> <span data-ttu-id="a5448-133">一般的な BizTalk Server は必要に応じて使用する受信場所、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]相互運用のパイプライン コンポーネント、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]リゾルバーとアダプターのプロバイダー フレームワークのエンドポイントとメタデータの動的な解決します。</span><span class="sxs-lookup"><span data-stu-id="a5448-133">They are typical BizTalk Server receive locations that optionally use the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] interop pipeline components and the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Resolver and Adapter Provider Framework for dynamic resolution of endpoints and metadata.</span></span>  
  
- <span data-ttu-id="a5448-134">**オフランプ**: これらの形式と SOAP、WCF、JMS、WMQ、FTP、HTTP、フラット ファイル、XML、またはその他のすべてのカスタム形式などのトランスポートを使用してメッセージの配信の送信ポートを実装します。</span><span class="sxs-lookup"><span data-stu-id="a5448-134">**Off-ramps** : These implement send ports for the delivery of messages using formats and transports such as SOAP, WCF, JMS, WMQ, FTP, HTTP, Flat File, XML, or any other custom formats.</span></span> <span data-ttu-id="a5448-135">通常の BizTalk Server の動的送信ポートを直接バインドされたメッセージ ボックスに、必要に応じて使用するには、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]相互運用のパイプライン コンポーネント、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]リゾルバーとアダプターのエンドポイントの動的解決のためのプロバイダー フレームワークメタデータ。</span><span class="sxs-lookup"><span data-stu-id="a5448-135">They are typical BizTalk Server dynamic send ports that are direct-bound to the Message Box and that optionally use the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] interop pipeline components and the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Resolver and Adapter Provider Framework for dynamic resolution of endpoints and metadata.</span></span>  
  
- <span data-ttu-id="a5448-136">**例外管理フレームワーク**: 例外 Web サービスを例外管理 API が含まれます、強化、コンポーネントの処理、および例外の詳細を ESB 管理ポータルに渡します。</span><span class="sxs-lookup"><span data-stu-id="a5448-136">**Exception Management Framework** : This includes the exception Web service, the exception management API, and components that enrich, process, and pass exception details to the ESB Management Portal.</span></span>  
  
- <span data-ttu-id="a5448-137">**ESB 管理ポータル**: これにより、レジストリのプロビジョニング、例外の仲介、アラート通知、および分析します。</span><span class="sxs-lookup"><span data-stu-id="a5448-137">**ESB Management Portal** : This provides registry provisioning, exception mediation, alert notification, and analytics.</span></span>  
  
  <span data-ttu-id="a5448-138">大部分のこれらのコンポーネントとサービスによって実装される機能に依存して[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]オーケストレーション、変換、およびビジネス ルール エンジンと、メッセージ ボックス データベースなどです。</span><span class="sxs-lookup"><span data-stu-id="a5448-138">Many of these components and services rely on features implemented by [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)], such as the Orchestration, Transformation, and Business Rules engines and the Message Box database.</span></span> <span data-ttu-id="a5448-139">図 2 は、カテゴリ; の概略を示しています。コンポーネントと各カテゴリ内で発生する通常のサービスで使用されるコアの BizTalk Server システム コンポーネント、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="a5448-139">Figure 2 shows a schematic view of the categories; the components and services typically occurring within each category; and the core BizTalk Server system components used by the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span>  
  
  <span data-ttu-id="a5448-140">![ESB アーキテクチャ](../esb-toolkit/media/esbarchitecture.gif "ESBArchitecture")</span><span class="sxs-lookup"><span data-stu-id="a5448-140">![ESB Architecture](../esb-toolkit/media/esbarchitecture.gif "ESBArchitecture")</span></span>  
  
  <span data-ttu-id="a5448-141">**図 2**</span><span class="sxs-lookup"><span data-stu-id="a5448-141">**Figure 2**</span></span>  
  
  <span data-ttu-id="a5448-142">**アーキテクチャとのコンポーネント、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="a5448-142">**The architecture and components of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]**</span></span>  
  
## <a name="how-the-biztalk-esb-toolkit-works"></a><span data-ttu-id="a5448-143">BizTalk ESB Toolkit の動作</span><span class="sxs-lookup"><span data-stu-id="a5448-143">How the BizTalk ESB Toolkit Works</span></span>  
 <span data-ttu-id="a5448-144">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]受信メッセージを受け取り、演算を実行して、おそらく (が常にではありません) など、変換、配信、またはその他のカスタム定義プロセスのプロセスを実行することによって。</span><span class="sxs-lookup"><span data-stu-id="a5448-144">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] accepts inbound messages and operates on them, perhaps (but not always) by performing processes such as transformation, delivery, or any other custom defined process.</span></span> <span data-ttu-id="a5448-145">必要な操作を指定するには、中心となる処理コンポーネントに、関連付けられた指示またはメタデータを格納するメッセージが必要です。その指示またはメタデータにより、メッセージの内容に対して適用するプロセスおよび実行するタスクが定義されます。</span><span class="sxs-lookup"><span data-stu-id="a5448-145">To specify the operations required, the core processing components require a message to contain associated instructions or metadata that define the processes to apply and the tasks to execute with the message content.</span></span>  
  
 <span data-ttu-id="a5448-146">このアプローチは、サービス間の疎結合を提供します。これは、ESB メッセージごとに、特定の処理に関する予備知識が必要ないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="a5448-146">This approach provides loose coupling between services; this means that the ESB does not require prior knowledge of the specific processing for each message.</span></span> <span data-ttu-id="a5448-147">ESB に必要な情報は、発生する可能性のあるプロセスの範囲と、各プロセスを適用する方法だけです。</span><span class="sxs-lookup"><span data-stu-id="a5448-147">It just has to know the possible range of processes and how to apply each process.</span></span> <span data-ttu-id="a5448-148">使用可能なプロセスおよびプロセスと指示のマッピングをメッセージ内に指定するための広範囲なオプションが用意されているので、コードの変更やコンポーネントの再展開を必要とせずに動作を構成および調整するための柔軟なメカニズムが実現されています。</span><span class="sxs-lookup"><span data-stu-id="a5448-148">The wide range of options for specifying the available processes and the mapping between the processes and the instructions within messages provides a flexible mechanism for configuring and adjusting behavior, without requiring changes to code and redeployment of components.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a5448-149">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="a5448-149">In this section</span></span>

- [<span data-ttu-id="a5448-150">インストールして、Microsoft BizTalk ESB Toolkit の構成</span><span class="sxs-lookup"><span data-stu-id="a5448-150">Install and configure the Microsoft BizTalk ESB Toolkit</span></span>](install-and-configure-the-microsoft-biztalk-esb-toolkit.md)

- [<span data-ttu-id="a5448-151">BizTalk ESB Toolkit について</span><span class="sxs-lookup"><span data-stu-id="a5448-151">Introduction to the BizTalk ESB Toolkit</span></span>](introduction-to-the-biztalk-esb-toolkit.md)

- [<span data-ttu-id="a5448-152">作業の開始し、BizTalk ESB Toolkit を理解します。</span><span class="sxs-lookup"><span data-stu-id="a5448-152">Getting started and understanding the BizTalk ESB Toolkit</span></span>](getting-started-with-the-biztalk-esb-toolkit.md)

- [<span data-ttu-id="a5448-153">主要なシナリオおよび開発タスク</span><span class="sxs-lookup"><span data-stu-id="a5448-153">Key scenarios and development tasks</span></span>](key-scenarios-and-development-tasks.md)

- [<span data-ttu-id="a5448-154">Itinerary designer を使用してスケジュールを作成します。</span><span class="sxs-lookup"><span data-stu-id="a5448-154">Creating itineraries using itinerary designer</span></span>](creating-itineraries-using-itinerary-designer.md)

- [<span data-ttu-id="a5448-155">BizTalk ESB Toolkit サンプル アプリケーション</span><span class="sxs-lookup"><span data-stu-id="a5448-155">BizTalk ESB Toolkit sample applications</span></span>](biztalk-esb-toolkit-sample-applications.md)

- [<span data-ttu-id="a5448-156">変更して、BizTalk ESB Toolkit の拡張</span><span class="sxs-lookup"><span data-stu-id="a5448-156">Modifying and extending the BizTalk ESB Toolkit</span></span>](modifying-and-extending-the-biztalk-esb-toolkit.md)

- [<span data-ttu-id="a5448-157">BizTalk ESB Toolkit による管理</span><span class="sxs-lookup"><span data-stu-id="a5448-157">Administration with the BizTalk ESB Toolkit</span></span>](administration-with-the-biztalk-esb-toolkit.md)

- [<span data-ttu-id="a5448-158">SOA ガバナンス統合</span><span class="sxs-lookup"><span data-stu-id="a5448-158">SOA governance integration</span></span>](soa-governance-integration.md)

- [<span data-ttu-id="a5448-159">BizTalk ESB Toolkit のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="a5448-159">Troubleshooting the BizTalk ESB Toolkit</span></span>](troubleshooting-the-biztalk-esb-toolkit.md)
  
## <a name="related-topics"></a><span data-ttu-id="a5448-160">関連トピック</span><span class="sxs-lookup"><span data-stu-id="a5448-160">Related topics</span></span>  
  
-   [<span data-ttu-id="a5448-161">BizTalk サービス指向ソリューション</span><span class="sxs-lookup"><span data-stu-id="a5448-161">BizTalk Service Oriented Solutions</span></span>](../core/service-oriented-solution.md)

- [<span data-ttu-id="a5448-162">BizTalk Server と Web サービスの使用</span><span class="sxs-lookup"><span data-stu-id="a5448-162">Using Web Services with BizTalk Server</span></span>](../core/using-web-services.md)  