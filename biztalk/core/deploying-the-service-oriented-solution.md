---
title: 指向ソリューションのサービスの展開 |Microsoft Docs
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
ms.openlocfilehash: d86b3b1cd1e5cadc8505e88db119cdffdaf653dd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389544"
---
# <a name="deploying-the-service-oriented-solution"></a><span data-ttu-id="1074f-102">指向ソリューションのサービスのデプロイ</span><span class="sxs-lookup"><span data-stu-id="1074f-102">Deploying the Service Oriented Solution</span></span>
<span data-ttu-id="1074f-103">サービス指向アーキテクチャ (SOA) は、分散システムを構築する方法です。</span><span class="sxs-lookup"><span data-stu-id="1074f-103">Service Oriented Architecture (SOA) is an approach to building distributed systems.</span></span> <span data-ttu-id="1074f-104">サービス指向ソリューションでは、クライアントが利用できる 1 つのサービスに集約できるさまざまなプロトコルを使用して複数のバックエンド システムを示します。</span><span class="sxs-lookup"><span data-stu-id="1074f-104">The service oriented solution demonstrates how several back-end systems using different protocols can be aggregated into a single service that clients can consume.</span></span> <span data-ttu-id="1074f-105">このソリューションでは、配信およびパフォーマンスの特性を保証するアプローチとサービスを統合します。</span><span class="sxs-lookup"><span data-stu-id="1074f-105">This solution integrates services with an approach that guarantees delivery and performance characteristics.</span></span>  
  
 <span data-ttu-id="1074f-106">サービス指向ソリューションがモデルに BizTalk Server および基幹業務 (LOB) アプリケーション サーバーが接続されたサービス レベル アグリーメントによってシナリオには、サービス要求に応答する 3 秒が与えられます。</span><span class="sxs-lookup"><span data-stu-id="1074f-106">The service oriented solution is modeled after a service-level agreement scenario in which BizTalk Server and the Line of Business (LOB) application servers connected to it are given three seconds to respond with a service request.</span></span> <span data-ttu-id="1074f-107">この 3 秒間のいずれかが占有されます、BizTalk Server でします。</span><span class="sxs-lookup"><span data-stu-id="1074f-107">One of those three seconds may be taken up by the BizTalk Server.</span></span>  
  
 <span data-ttu-id="1074f-108">このセクションのトピックでは、インストールして、1 台のコンピューターおよび複数の実稼働サーバー上のサービス指向ソリューションをテストする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1074f-108">The topics in this section describe how to install and test the service oriented solution on a single computer and multiple production servers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1074f-109">サービス指向ソリューションの 3 つのバージョンがあります。 アダプタ、インライン、およびスタブ。</span><span class="sxs-lookup"><span data-stu-id="1074f-109">There are three versions of the service oriented solution: adapter, inline, and stub.</span></span> <span data-ttu-id="1074f-110">サービス指向ソリューションの 3 つのバージョンの違いの詳細については、次を参照してください。[サービス指向ソリューションを理解する](../core/understanding-the-service-oriented-solution.md)します。</span><span class="sxs-lookup"><span data-stu-id="1074f-110">For more information about the differences between three versions of the service-oriented solution, see [Understanding the Service Oriented Solution](../core/understanding-the-service-oriented-solution.md).</span></span>  
  
 <span data-ttu-id="1074f-111">**対象読者**</span><span class="sxs-lookup"><span data-stu-id="1074f-111">**Reader Guidance**</span></span>  
  
 <span data-ttu-id="1074f-112">このドキュメントは、BizTalk Server、Windows Server、および Microsoft に精通していることを前提としています。[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="1074f-112">This document assumes that you are familiar with BizTalk Server, Windows Server, and Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="1074f-113">また、エンタープライズ アプリケーション統合と Web サービスの基本的な概念についても理解していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="1074f-113">It also assumes that you understand basic concepts about enterprise application integration and Web services.</span></span> <span data-ttu-id="1074f-114">またを使用してアプリケーションをビルドする方法について理解しているが推奨[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]した参照の設定、デバッグおよびテスト ソリューションをデバッグ モードを使用してプロジェクトの作成について理解しているとします。</span><span class="sxs-lookup"><span data-stu-id="1074f-114">Additionally, we recommend that you are familiar with how to build applications by using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and that you are familiar with creating projects, setting references, and using the debug mode to debug and test your solution.</span></span> <span data-ttu-id="1074f-115">IT プロフェッショナルと開発者のスキルと知識の詳細については、次を参照してください。[前提条件のスキルと知識](../core/prerequisite-skills-and-knowledge5.md)します。</span><span class="sxs-lookup"><span data-stu-id="1074f-115">For more information about the prerequisite skills and knowledge for IT professionals and developers, see [Prerequisite Skills and Knowledge](../core/prerequisite-skills-and-knowledge5.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1074f-116">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="1074f-116">In This Section</span></span>  
  
-   [<span data-ttu-id="1074f-117">サービス指向ソリューションに対する開発者のコンピューター設定</span><span class="sxs-lookup"><span data-stu-id="1074f-117">Developer Machine Setup for the Service Oriented Solution</span></span>](../core/developer-machine-setup-for-the-service-oriented-solution.md)