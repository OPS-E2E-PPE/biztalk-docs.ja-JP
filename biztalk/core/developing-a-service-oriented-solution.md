---
title: 開発、サービス指向ソリューション |Microsoft Docs
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
ms.openlocfilehash: 62bac2f534b5f542f65b316faef7ecbad976dfee
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65351462"
---
# <a name="developing-a-service-oriented-solution"></a><span data-ttu-id="0e6b6-102">開発、サービス指向ソリューション</span><span class="sxs-lookup"><span data-stu-id="0e6b6-102">Developing a Service Oriented Solution</span></span>
<span data-ttu-id="0e6b6-103">サービス指向ソリューションでは、Woodgrove Bank のクレジット口座の残高システムを示します。</span><span class="sxs-lookup"><span data-stu-id="0e6b6-103">The service oriented solution demonstrates a credit account balance system for Woodgrove Bank.</span></span> <span data-ttu-id="0e6b6-104">アカウントに関する情報は、次の 3 つのレガシ システムからは取得されます。 与信限度額を提供する SAP システム、メインフレームでは、で実行されている pending transactions システムおよび MQSeries を使用して、payment tracking システム。</span><span class="sxs-lookup"><span data-stu-id="0e6b6-104">Information about an account comes from three legacy systems: an SAP system that provides the credit limit, a pending transactions system running on a mainframe, and a payment tracking system using MQSeries.</span></span> <span data-ttu-id="0e6b6-105">残高照会の要求は、Web サービスまたは対話型音声応答 (IVR) システムによっていきます。</span><span class="sxs-lookup"><span data-stu-id="0e6b6-105">Balance check requests come through a Web service or an Interactive Voice Response (IVR) system.</span></span> <span data-ttu-id="0e6b6-106">シナリオの詳細については、次を参照してください。[サービス指向ソリューションを理解する](../core/understanding-the-service-oriented-solution.md)します。</span><span class="sxs-lookup"><span data-stu-id="0e6b6-106">For more information about the scenario, see [Understanding the Service Oriented Solution](../core/understanding-the-service-oriented-solution.md).</span></span>  
  
 <span data-ttu-id="0e6b6-107">この開発者ガイドでは、Woodgrove bank のサービス指向アーキテクチャ ソリューションを構築するための 1 つの方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0e6b6-107">This Developer's Guide presents one approach to building a service oriented architecture solution for the Woodgrove Bank scenario.</span></span> <span data-ttu-id="0e6b6-108">このガイドは、業界標準のパターンで考えられるソリューションの検討から開始します。</span><span class="sxs-lookup"><span data-stu-id="0e6b6-108">The Guide begins by considering a possible solution in terms of industry-standard patterns.</span></span> <span data-ttu-id="0e6b6-109">「サービス指向ソリューションのパターン」は、そのパターンの適切な BizTalk アプリケーションのアイテムへの翻訳を開始します。</span><span class="sxs-lookup"><span data-stu-id="0e6b6-109">"Patterns in the Service Oriented Solution" begins the translation of that pattern into the appropriate artifacts of a BizTalk application.</span></span> <span data-ttu-id="0e6b6-110">次のセクションでは、「コンポーネントのサービス指向ソリューションの」は、さまざまな部分のアプリケーションとの関係をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="0e6b6-110">The next section, "Components of the Service Oriented Solution," summarizes the various parts of the application and their relationships.</span></span> <span data-ttu-id="0e6b6-111">実装が強調表示セクションには、領域がについて説明します-など、エンタープライズ シングル サインオンを使用して: シナリオの条件を満たすために特別な作業が必要です。</span><span class="sxs-lookup"><span data-stu-id="0e6b6-111">The Implementation Highlights section discusses areas—such as using Enterprise Single Sign-On—that required special work to meet the criteria of the scenario.</span></span> <span data-ttu-id="0e6b6-112">「BAM を使用したサービス指向ソリューションの監視」には、ソリューションで、BAM API を使用して、要求と結果の進行状況を追跡する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0e6b6-112">"Monitoring the Service Oriented Solution with BAM" describes how the solution uses the BAM API to track progress of requests and results.</span></span> <span data-ttu-id="0e6b6-113">「バージョン管理、サービス指向ソリューション」と「スケーリング サービス指向ソリューションの」セクションでは、拡張、またはソリューションを変更する方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0e6b6-113">The "Versioning the Service Oriented Solution" and "Scaling the Service Oriented Solution" sections suggest ways of extending or modifying the solution.</span></span> <span data-ttu-id="0e6b6-114">参照セクションでは、ソリューション内のファイルを一覧表示し、メッセージへの参照を提供します。</span><span class="sxs-lookup"><span data-stu-id="0e6b6-114">The reference section lists the files in the solution and provides a reference to the messages.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0e6b6-115">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="0e6b6-115">In This Section</span></span>  
  
-   [<span data-ttu-id="0e6b6-116">サービス指向ソリューションのパターン</span><span class="sxs-lookup"><span data-stu-id="0e6b6-116">Patterns in the Service Oriented Solution</span></span>](../core/patterns-in-the-service-oriented-solution.md)  
  
-   [<span data-ttu-id="0e6b6-117">サービス指向ソリューションのコンポーネント</span><span class="sxs-lookup"><span data-stu-id="0e6b6-117">Components of the Service Oriented Solution</span></span>](../core/components-of-the-service-oriented-solution.md)  
  
-   [<span data-ttu-id="0e6b6-118">サービス指向ソリューションの実装の重要なポイント</span><span class="sxs-lookup"><span data-stu-id="0e6b6-118">Implementation Highlights of the Service Oriented Solution</span></span>](../core/implementation-highlights-of-the-service-oriented-solution.md)  
  
-   [<span data-ttu-id="0e6b6-119">BAM によるソリューションを指向サービスを監視します。</span><span class="sxs-lookup"><span data-stu-id="0e6b6-119">Monitoring the Service Oriented Solution with BAM</span></span>](../core/monitoring-the-service-oriented-solution-with-bam.md)  
  
-   [<span data-ttu-id="0e6b6-120">バージョン管理、サービス指向ソリューション</span><span class="sxs-lookup"><span data-stu-id="0e6b6-120">Versioning the Service Oriented Solution</span></span>](../core/versioning-the-service-oriented-solution.md)  
  
-   [<span data-ttu-id="0e6b6-121">スケーリング、サービス指向ソリューション</span><span class="sxs-lookup"><span data-stu-id="0e6b6-121">Scaling the Service Oriented Solution</span></span>](../core/scaling-the-service-oriented-solution.md)  
  
-   [<span data-ttu-id="0e6b6-122">サービス指向ソリューション リファレンス</span><span class="sxs-lookup"><span data-stu-id="0e6b6-122">Service Oriented Solution Reference</span></span>](../core/service-oriented-solution-reference.md)