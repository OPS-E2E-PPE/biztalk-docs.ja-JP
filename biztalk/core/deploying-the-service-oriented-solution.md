---
title: 指向ソリューションのサービスの展開 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, service solution tutorial
- deploying, tutorials
- service solution tutorial, deploying
- service solution tutorial, background information
- tutorials, deploying
ms.assetid: 88d4d28d-9031-4fb8-ab62-04ee27949673
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7246635c4e0d55fd424fd0052eee91e118c8cb17
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239194"
---
# <a name="deploying-the-service-oriented-solution"></a><span data-ttu-id="d6cd4-102">指向ソリューションのサービスの展開</span><span class="sxs-lookup"><span data-stu-id="d6cd4-102">Deploying the Service Oriented Solution</span></span>
<span data-ttu-id="d6cd4-103">サービス指向のアーキテクチャ (SOA) は、分散システムを構築するためのアプローチです。</span><span class="sxs-lookup"><span data-stu-id="d6cd4-103">Service Oriented Architecture (SOA) is an approach to building distributed systems.</span></span> <span data-ttu-id="d6cd4-104">サービス指向ソリューションでは、クライアントで使用できる 1 つのサービスにさまざまなプロトコルを使用して複数のバックエンド システムを集計することができますを示しています。</span><span class="sxs-lookup"><span data-stu-id="d6cd4-104">The service oriented solution demonstrates how several back-end systems using different protocols can be aggregated into a single service that clients can consume.</span></span> <span data-ttu-id="d6cd4-105">このソリューションでは、配信およびパフォーマンスの特性を保証するアプローチで各種のサービスを統合しています。</span><span class="sxs-lookup"><span data-stu-id="d6cd4-105">This solution integrates services with an approach that guarantees delivery and performance characteristics.</span></span>  
  
 <span data-ttu-id="d6cd4-106">サービス指向ソリューションは、サービス レベル契約のシナリオをモデル化しています。ソリューションに接続されている BizTalk Server および基幹業務 (LOB) アプリケーション サーバーは、3 秒以内にサービス要求に応答する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6cd4-106">The service oriented solution is modeled after a service-level agreement scenario in which BizTalk Server and the Line of Business (LOB) application servers connected to it are given three seconds to respond with a service request.</span></span> <span data-ttu-id="d6cd4-107">この 3 秒間のうちの 1 秒は、BizTalk Server によって消費される場合があります。</span><span class="sxs-lookup"><span data-stu-id="d6cd4-107">One of those three seconds may be taken up by the BizTalk Server.</span></span>  
  
 <span data-ttu-id="d6cd4-108">このセクションの各トピックでは、サービス指向ソリューションを 1 台のコンピュータおよび複数の実稼働サーバーにインストールし、テストする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d6cd4-108">The topics in this section describe how to install and test the service oriented solution on a single computer and multiple production servers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d6cd4-109">サービス指向ソリューションの 3 つのバージョンがあります。 アダプタ、インライン、およびスタブ。</span><span class="sxs-lookup"><span data-stu-id="d6cd4-109">There are three versions of the service oriented solution: adapter, inline, and stub.</span></span> <span data-ttu-id="d6cd4-110">サービス指向ソリューションの 3 つのバージョンの違いの詳細については、次を参照してください。[サービス指向ソリューションを理解する](../core/understanding-the-service-oriented-solution.md)です。</span><span class="sxs-lookup"><span data-stu-id="d6cd4-110">For more information about the differences between three versions of the service-oriented solution, see [Understanding the Service Oriented Solution](../core/understanding-the-service-oriented-solution.md).</span></span>  
  
 <span data-ttu-id="d6cd4-111">**対象読者**</span><span class="sxs-lookup"><span data-stu-id="d6cd4-111">**Reader Guidance**</span></span>  
  
 <span data-ttu-id="d6cd4-112">このドキュメントは、BizTalk Server、Windows Server、および Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] に関する知識があることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="d6cd4-112">This document assumes that you are familiar with BizTalk Server, Windows Server, and Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="d6cd4-113">また、エンタープライズ アプリケーション統合と Web サービスの基本的な概念についても理解していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="d6cd4-113">It also assumes that you understand basic concepts about enterprise application integration and Web services.</span></span> <span data-ttu-id="d6cd4-114">さらに、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] を使用してアプリケーションを作成する方法や、プロジェクトの作成、参照の設定、デバッグ モードを使用したソリューションのデバッグおよびテストに関しても理解しておいてください。</span><span class="sxs-lookup"><span data-stu-id="d6cd4-114">Additionally, we recommend that you are familiar with how to build applications by using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and that you are familiar with creating projects, setting references, and using the debug mode to debug and test your solution.</span></span> <span data-ttu-id="d6cd4-115">IT 担当者および開発者の必要なスキルと知識の詳細については、次を参照してください。[前提条件のスキルと知識](../core/prerequisite-skills-and-knowledge5.md)です。</span><span class="sxs-lookup"><span data-stu-id="d6cd4-115">For more information about the prerequisite skills and knowledge for IT professionals and developers, see [Prerequisite Skills and Knowledge](../core/prerequisite-skills-and-knowledge5.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d6cd4-116">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d6cd4-116">In This Section</span></span>  
  
-   [<span data-ttu-id="d6cd4-117">開発者のコンピュータ設定、サービス指向ソリューション</span><span class="sxs-lookup"><span data-stu-id="d6cd4-117">Developer Machine Setup for the Service Oriented Solution</span></span>](../core/developer-machine-setup-for-the-service-oriented-solution.md)