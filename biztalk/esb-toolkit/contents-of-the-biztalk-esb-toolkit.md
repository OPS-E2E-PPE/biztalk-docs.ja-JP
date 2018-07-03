---
title: BizTalk ESB Toolkit の内容 |Microsoft Docs
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
ms.openlocfilehash: af25a536152544f26d55eebab1d11ee76493187c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009435"
---
# <a name="contents-of-the-biztalk-esb-toolkit"></a><span data-ttu-id="69cc2-102">BizTalk ESB Toolkit の内容</span><span class="sxs-lookup"><span data-stu-id="69cc2-102">Contents of the BizTalk ESB Toolkit</span></span>
<span data-ttu-id="69cc2-103">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]アーキテクチャに関するガイダンス、パターンとプラクティス、および Microsoft プラットフォームでのエンタープライズ規模のソリューションの開発を簡略化の BizTalk Server と .NET Framework のコンポーネントのコレクションを提供します。</span><span class="sxs-lookup"><span data-stu-id="69cc2-103">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] provides architectural guidance, patterns and practices, and a collection of BizTalk Server and .NET Framework components to simplify the development of enterprise-scale solutions on the Microsoft platform.</span></span> <span data-ttu-id="69cc2-104">このツールキットには、開発者が既存のメッセージングの拡張機能と統合ソリューションも提供します。</span><span class="sxs-lookup"><span data-stu-id="69cc2-104">The toolkit also provides capabilities to help developers extend existing messaging and integration solutions.</span></span> <span data-ttu-id="69cc2-105">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]をサポートし、メッセージ ベースの動的なエンタープライズ アプリケーションを構築するプロセスを簡素化する疎結合メッセージング環境を実装するコンポーネントの相互運用のコレクションで構成されます。</span><span class="sxs-lookup"><span data-stu-id="69cc2-105">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] consists of a collection of interoperating components that support and implement a loosely coupled messaging environment that simplifies the process of building dynamic message-based enterprise applications.</span></span>  

 <span data-ttu-id="69cc2-106">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]次のコンポーネントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="69cc2-106">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] contains the following components:</span></span>  

- <span data-ttu-id="69cc2-107">[ESB Web サービス](../esb-toolkit/esb-web-services.md)します。</span><span class="sxs-lookup"><span data-stu-id="69cc2-107">[ESB Web Services](../esb-toolkit/esb-web-services.md).</span></span> <span data-ttu-id="69cc2-108">主な機能を例外管理、動的解決のエンドポイントやマップの BizTalk 操作、Universal Description, Discovery, and Integration (UDDI) 相互運用性、スケジュールに基づくルーティングなど、ESB のコンシューマーに公開し、メッセージの内容の変換です。</span><span class="sxs-lookup"><span data-stu-id="69cc2-108">These expose key capabilities to ESB consumers, such as itinerary-based routing, exception management, dynamic resolution of endpoints and maps, BizTalk operations, Universal Description, Discovery, and Integration (UDDI) interoperability, and transformation of message content.</span></span>  

- <span data-ttu-id="69cc2-109">[ESB 管理ポータル](../esb-toolkit/esb-management-portal.md)します。</span><span class="sxs-lookup"><span data-stu-id="69cc2-109">[ESB Management Portal](../esb-toolkit/esb-management-portal.md).</span></span> <span data-ttu-id="69cc2-110">これは、例外とエラー メッセージ再送信を追跡するには、アラートと通知、UDDI の統合、レポートし分析、および構成機能のサポートをします。</span><span class="sxs-lookup"><span data-stu-id="69cc2-110">This provides support for exception and fault tracking, message resubmission, alerts and notifications, UDDI integration, reporting and analytics, and configuration capabilities.</span></span>  

- <span data-ttu-id="69cc2-111">[ESB パイプライン相互運用機能コンポーネント](../esb-toolkit/esb-pipeline-interop-components.md)します。</span><span class="sxs-lookup"><span data-stu-id="69cc2-111">[ESB Pipeline Interop Components](../esb-toolkit/esb-pipeline-interop-components.md).</span></span> <span data-ttu-id="69cc2-112">これらは、BizTalk Server に、外部システムとの相互運用を容易にするためのパイプライン コンポーネントを提供します。</span><span class="sxs-lookup"><span data-stu-id="69cc2-112">These provide BizTalk Server pipeline components that facilitate interoperability with external systems.</span></span>  

- <span data-ttu-id="69cc2-113">[例外管理フレームワーク](../esb-toolkit/exception-management-framework.md)します。</span><span class="sxs-lookup"><span data-stu-id="69cc2-113">[Exception Management Framework](../esb-toolkit/exception-management-framework.md).</span></span> <span data-ttu-id="69cc2-114">BizTalk メッセージングおよびオーケストレーションのサブシステムからの例外を統合し、エラー メッセージを処理するための 1 つのメカニズムを提供します。 これはキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="69cc2-114">This captures and consolidates exceptions from both BizTalk Messaging and Orchestration subsystems and provides a single mechanism for handling fault messages.</span></span> <span data-ttu-id="69cc2-115">例外 Web サービスでは、例外管理 API、および強化、処理、および例外の詳細を渡す ESB 管理ポータルにコンポーネントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="69cc2-115">It includes the exception Web service, the exception management API, and components that enrich, process, and pass exception details to the ESB Management Portal.</span></span>  

- <span data-ttu-id="69cc2-116">[ESB リゾルバーとアダプターのプロバイダー フレームワーク](../esb-toolkit/esb-resolver-and-adapter-provider-framework.md)します。</span><span class="sxs-lookup"><span data-stu-id="69cc2-116">[ESB Resolver and Adapter Provider Framework](../esb-toolkit/esb-resolver-and-adapter-provider-framework.md).</span></span> <span data-ttu-id="69cc2-117">これは、プラグ可能な構成可能なアーキテクチャは、エンドポイントと変換の要件を動的に解決するため、メッセージのルーティングを実装します。</span><span class="sxs-lookup"><span data-stu-id="69cc2-117">This implements a pluggable and configurable architecture for dynamically resolving endpoints and transform requirements and for routing messages.</span></span>  

- <span data-ttu-id="69cc2-118">[ルーティングと処理のスケジュールに基づく](../esb-toolkit/itinerary-based-routing-and-processing.md)します。</span><span class="sxs-lookup"><span data-stu-id="69cc2-118">[Itinerary-Based Routing and Processing](../esb-toolkit/itinerary-based-routing-and-processing.md).</span></span> <span data-ttu-id="69cc2-119">スケジュール処理メカニズムは、動的に記述する、送信、および複数のサービスの呼び出しまたは要求をルーティング/変換を実行する軽量の機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="69cc2-119">The Itinerary Processing mechanism provides a lightweight capability for dynamically describing, submitting, and executing multiple service invocations or routing/transformation requests.</span></span>  

- <span data-ttu-id="69cc2-120">[BizTalk ESB Toolkit のサンプル アプリケーション](../esb-toolkit/biztalk-esb-toolkit-sample-applications.md)します。</span><span class="sxs-lookup"><span data-stu-id="69cc2-120">[BizTalk ESB Toolkit Sample Applications](../esb-toolkit/biztalk-esb-toolkit-sample-applications.md).</span></span> <span data-ttu-id="69cc2-121">含まれているサンプル アプリケーションでは、可能な実装を示しています。、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]を使用する方法と、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] SOA と ESB アプリケーションで機能します。</span><span class="sxs-lookup"><span data-stu-id="69cc2-121">The included sample applications demonstrate possible implementations of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] and how you can use the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] features in your own SOA and ESB applications.</span></span>
