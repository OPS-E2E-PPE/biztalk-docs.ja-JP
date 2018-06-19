---
title: 開発、サービス指向ソリューション |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tutorials, developing
- service solution tutorial, background information
- service solution tutorial, developing
- developing, tutorials
- developing, service solution tutorial
ms.assetid: 7979a05c-7fd3-4476-a623-55de8abdc493
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d8e33baa51a551d0f1f851410fda696abc96983
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239330"
---
# <a name="developing-a-service-oriented-solution"></a><span data-ttu-id="634a5-102">指向ソリューションのサービスの開発</span><span class="sxs-lookup"><span data-stu-id="634a5-102">Developing a Service Oriented Solution</span></span>
<span data-ttu-id="634a5-103">サービス指向ソリューションでは、Woodgrove Bank のクレジット口座残高システムを示します。</span><span class="sxs-lookup"><span data-stu-id="634a5-103">The service oriented solution demonstrates a credit account balance system for Woodgrove Bank.</span></span> <span data-ttu-id="634a5-104">アカウントに関する情報は次の 3 つのレガシ システムから取得します。 与信限度額を提供する SAP システム、メインフレームで実行されている pending transactions システムおよび MQSeries を使用して、payment tracking システム。</span><span class="sxs-lookup"><span data-stu-id="634a5-104">Information about an account comes from three legacy systems: an SAP system that provides the credit limit, a pending transactions system running on a mainframe, and a payment tracking system using MQSeries.</span></span> <span data-ttu-id="634a5-105">残高照会の要求は、Web サービスまたは音声自動応答装置 (IVR) から取得します。</span><span class="sxs-lookup"><span data-stu-id="634a5-105">Balance check requests come through a Web service or an Interactive Voice Response (IVR) system.</span></span> <span data-ttu-id="634a5-106">シナリオの詳細については、次を参照してください。[サービス指向ソリューションを理解する](../core/understanding-the-service-oriented-solution.md)です。</span><span class="sxs-lookup"><span data-stu-id="634a5-106">For more information about the scenario, see [Understanding the Service Oriented Solution](../core/understanding-the-service-oriented-solution.md).</span></span>  
  
 <span data-ttu-id="634a5-107">この開発者ガイドでは、Woodgrove Bank シナリオにサービス指向のアーキテクチャ ソリューションを構築するための 1 つのアプローチを提示します。</span><span class="sxs-lookup"><span data-stu-id="634a5-107">This Developer's Guide presents one approach to building a service oriented architecture solution for the Woodgrove Bank scenario.</span></span> <span data-ttu-id="634a5-108">このガイドでは、業界標準のパターンで考えられるソリューションの検討から開始します。</span><span class="sxs-lookup"><span data-stu-id="634a5-108">The Guide begins by considering a possible solution in terms of industry-standard patterns.</span></span> <span data-ttu-id="634a5-109">サービス指向ソリューションのパターンについてのセクションでは、まず、パターンを BizTalk アプリケーションの適切なアイテムに変換します。</span><span class="sxs-lookup"><span data-stu-id="634a5-109">"Patterns in the Service Oriented Solution" begins the translation of that pattern into the appropriate artifacts of a BizTalk application.</span></span> <span data-ttu-id="634a5-110">次のサービス指向ソリューションのコンポーネントについてのセクションでは、アプリケーションのさまざまな部分とその関係についてまとめます。</span><span class="sxs-lookup"><span data-stu-id="634a5-110">The next section, "Components of the Service Oriented Solution," summarizes the various parts of the application and their relationships.</span></span> <span data-ttu-id="634a5-111">実装を強調表示セクションには、領域がについて説明します: など、エンタープライズ シングル サインオンを使用して — をシナリオの条件を満たすために特別な作業が必要です。</span><span class="sxs-lookup"><span data-stu-id="634a5-111">The Implementation Highlights section discusses areas—such as using Enterprise Single Sign-On—that required special work to meet the criteria of the scenario.</span></span> <span data-ttu-id="634a5-112">BAM の使用によるサービス指向ソリューションの監視についてのセクションでは、BAM API を使用したソリューションによる要求と結果の進行状況の追跡方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="634a5-112">"Monitoring the Service Oriented Solution with BAM" describes how the solution uses the BAM API to track progress of requests and results.</span></span> <span data-ttu-id="634a5-113">サービス指向ソリューションのバージョン管理についてのセクションと、サービス指向ソリューションの拡張についてのセクションでは、ソリューションの拡張および修正方法を提案します。</span><span class="sxs-lookup"><span data-stu-id="634a5-113">The "Versioning the Service Oriented Solution" and "Scaling the Service Oriented Solution" sections suggest ways of extending or modifying the solution.</span></span> <span data-ttu-id="634a5-114">参照セクションでは、ソリューションのファイルとメッセージへの参照の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="634a5-114">The reference section lists the files in the solution and provides a reference to the messages.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="634a5-115">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="634a5-115">In This Section</span></span>  
  
-   [<span data-ttu-id="634a5-116">パターンで、サービス指向ソリューション</span><span class="sxs-lookup"><span data-stu-id="634a5-116">Patterns in the Service Oriented Solution</span></span>](../core/patterns-in-the-service-oriented-solution.md)  
  
-   [<span data-ttu-id="634a5-117">コンポーネントのサービス指向ソリューション</span><span class="sxs-lookup"><span data-stu-id="634a5-117">Components of the Service Oriented Solution</span></span>](../core/components-of-the-service-oriented-solution.md)  
  
-   [<span data-ttu-id="634a5-118">指向ソリューションのサービスの実装の要点</span><span class="sxs-lookup"><span data-stu-id="634a5-118">Implementation Highlights of the Service Oriented Solution</span></span>](../core/implementation-highlights-of-the-service-oriented-solution.md)  
  
-   [<span data-ttu-id="634a5-119">BAM によるソリューションを指向サービスを監視します。</span><span class="sxs-lookup"><span data-stu-id="634a5-119">Monitoring the Service Oriented Solution with BAM</span></span>](../core/monitoring-the-service-oriented-solution-with-bam.md)  
  
-   [<span data-ttu-id="634a5-120">バージョン管理、サービス指向ソリューション</span><span class="sxs-lookup"><span data-stu-id="634a5-120">Versioning the Service Oriented Solution</span></span>](../core/versioning-the-service-oriented-solution.md)  
  
-   [<span data-ttu-id="634a5-121">スケーリング、サービス指向ソリューション</span><span class="sxs-lookup"><span data-stu-id="634a5-121">Scaling the Service Oriented Solution</span></span>](../core/scaling-the-service-oriented-solution.md)  
  
-   [<span data-ttu-id="634a5-122">サービス指向ソリューション リファレンス</span><span class="sxs-lookup"><span data-stu-id="634a5-122">Service Oriented Solution Reference</span></span>](../core/service-oriented-solution-reference.md)