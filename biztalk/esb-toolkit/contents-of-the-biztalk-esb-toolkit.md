---
title: BizTalk ESB Toolkit の内容 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6e7114df-dadf-49ab-b024-44d84e47faa5
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3dcfc5bbe761f70269c31294484ee37e7e79f83
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22290618"
---
# <a name="contents-of-the-biztalk-esb-toolkit"></a><span data-ttu-id="bb11c-102">BizTalk ESB Toolkit の内容</span><span class="sxs-lookup"><span data-stu-id="bb11c-102">Contents of the BizTalk ESB Toolkit</span></span>
<span data-ttu-id="bb11c-103">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]アーキテクチャに関するガイダンス、パターンとプラクティス、および BizTalk Server と .NET Framework のコンポーネント、Microsoft プラットフォームでのエンタープライズ規模のソリューションの開発を簡略化のコレクションを提供します。</span><span class="sxs-lookup"><span data-stu-id="bb11c-103">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] provides architectural guidance, patterns and practices, and a collection of BizTalk Server and .NET Framework components to simplify the development of enterprise-scale solutions on the Microsoft platform.</span></span> <span data-ttu-id="bb11c-104">このツールキットは、開発者が既存のメッセージングを拡張に役立つ機能や統合ソリューションも提供します。</span><span class="sxs-lookup"><span data-stu-id="bb11c-104">The toolkit also provides capabilities to help developers extend existing messaging and integration solutions.</span></span> <span data-ttu-id="bb11c-105">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]動的メッセージ ベースのエンタープライズ アプリケーションを構築するプロセスを簡略化する疎結合メッセージング環境を実装およびサポートするコンポーネントの相互運用のコレクションを構成します。</span><span class="sxs-lookup"><span data-stu-id="bb11c-105">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] consists of a collection of interoperating components that support and implement a loosely coupled messaging environment that simplifies the process of building dynamic message-based enterprise applications.</span></span>  
  
 <span data-ttu-id="bb11c-106">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]次のコンポーネントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="bb11c-106">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] contains the following components:</span></span>  
  
-   <span data-ttu-id="bb11c-107">[Web サービスの ESB](../esb-toolkit/esb-web-services.md)です。</span><span class="sxs-lookup"><span data-stu-id="bb11c-107">[ESB Web Services](../esb-toolkit/esb-web-services.md).</span></span> <span data-ttu-id="bb11c-108">公開されるため、例外管理、動的解決のエンドポイントやマップの BizTalk 操作、Universal Description, Discovery, and Integration (UDDI) 相互運用性、行程ベースのルーティングなど、ESB コンシューマーに主要な機能とメッセージの内容の変換です。</span><span class="sxs-lookup"><span data-stu-id="bb11c-108">These expose key capabilities to ESB consumers, such as itinerary-based routing, exception management, dynamic resolution of endpoints and maps, BizTalk operations, Universal Description, Discovery, and Integration (UDDI) interoperability, and transformation of message content.</span></span>  
  
-   <span data-ttu-id="bb11c-109">[管理ポータルの ESB](../esb-toolkit/esb-management-portal.md)です。</span><span class="sxs-lookup"><span data-stu-id="bb11c-109">[ESB Management Portal](../esb-toolkit/esb-management-portal.md).</span></span> <span data-ttu-id="bb11c-110">これは、例外、およびフォールト メッセージ再送信を追跡するには、アラートと通知、UDDI の統合、レポートし分析、および構成機能のサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="bb11c-110">This provides support for exception and fault tracking, message resubmission, alerts and notifications, UDDI integration, reporting and analytics, and configuration capabilities.</span></span>  
  
-   <span data-ttu-id="bb11c-111">[ESB のパイプライン コンポーネントを相互運用機能](../esb-toolkit/esb-pipeline-interop-components.md)します。</span><span class="sxs-lookup"><span data-stu-id="bb11c-111">[ESB Pipeline Interop Components](../esb-toolkit/esb-pipeline-interop-components.md).</span></span> <span data-ttu-id="bb11c-112">これらは、BizTalk Server に、外部システムとの相互運用を容易にするためのパイプライン コンポーネントを提供します。</span><span class="sxs-lookup"><span data-stu-id="bb11c-112">These provide BizTalk Server pipeline components that facilitate interoperability with external systems.</span></span>  
  
-   <span data-ttu-id="bb11c-113">[例外管理フレームワーク](../esb-toolkit/exception-management-framework.md)です。</span><span class="sxs-lookup"><span data-stu-id="bb11c-113">[Exception Management Framework](../esb-toolkit/exception-management-framework.md).</span></span> <span data-ttu-id="bb11c-114">これをキャプチャし、BizTalk メッセージングおよびオーケストレーションのサブシステムから例外をまとめてフォールト メッセージを処理するための 1 つのメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="bb11c-114">This captures and consolidates exceptions from both BizTalk Messaging and Orchestration subsystems and provides a single mechanism for handling fault messages.</span></span> <span data-ttu-id="bb11c-115">例外 Web サービス、例外管理 API、および強化し、処理および例外の詳細を ESB の管理ポータルに渡すコンポーネントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="bb11c-115">It includes the exception Web service, the exception management API, and components that enrich, process, and pass exception details to the ESB Management Portal.</span></span>  
  
-   <span data-ttu-id="bb11c-116">[ESB リゾルバーとアダプターのプロバイダー フレームワーク](../esb-toolkit/esb-resolver-and-adapter-provider-framework.md)です。</span><span class="sxs-lookup"><span data-stu-id="bb11c-116">[ESB Resolver and Adapter Provider Framework](../esb-toolkit/esb-resolver-and-adapter-provider-framework.md).</span></span> <span data-ttu-id="bb11c-117">これは、プラグ可能な構成可能なアーキテクチャは、動的にエンドポイントとトランス フォーム要件を解決するため、メッセージのルーティングを実装します。</span><span class="sxs-lookup"><span data-stu-id="bb11c-117">This implements a pluggable and configurable architecture for dynamically resolving endpoints and transform requirements and for routing messages.</span></span>  
  
-   <span data-ttu-id="bb11c-118">[行程ベースのルーティングと処理](../esb-toolkit/itinerary-based-routing-and-processing.md)です。</span><span class="sxs-lookup"><span data-stu-id="bb11c-118">[Itinerary-Based Routing and Processing](../esb-toolkit/itinerary-based-routing-and-processing.md).</span></span> <span data-ttu-id="bb11c-119">行程処理メカニズムを動的に記述、送信、および複数のサービスの呼び出しまたはルーティング/変換要求を実行するための軽量な機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="bb11c-119">The Itinerary Processing mechanism provides a lightweight capability for dynamically describing, submitting, and executing multiple service invocations or routing/transformation requests.</span></span>  
  
-   <span data-ttu-id="bb11c-120">[BizTalk ESB Toolkit のサンプル アプリケーション](../esb-toolkit/biztalk-esb-toolkit-sample-applications.md)です。</span><span class="sxs-lookup"><span data-stu-id="bb11c-120">[BizTalk ESB Toolkit Sample Applications](../esb-toolkit/biztalk-esb-toolkit-sample-applications.md).</span></span> <span data-ttu-id="bb11c-121">可能な実装をデモンストレーションするサンプル アプリケーション、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]を使用する方法と、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] SOA および ESB アプリケーションで機能します。</span><span class="sxs-lookup"><span data-stu-id="bb11c-121">The included sample applications demonstrate possible implementations of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] and how you can use the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] features in your own SOA and ESB applications.</span></span>