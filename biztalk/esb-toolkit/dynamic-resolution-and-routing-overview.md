---
title: "動的な解像度とルーティングの概要 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a9a32491-132b-4b25-ac8c-4a927052f0be
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 341b8389530ac85fdc459816f5691f3b814fbd56
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="dynamic-resolution-and-routing-overview"></a><span data-ttu-id="07b57-102">動的な解像度とルーティングの概要</span><span class="sxs-lookup"><span data-stu-id="07b57-102">Dynamic Resolution and Routing Overview</span></span>
<span data-ttu-id="07b57-103">ESB 競合回避モジュールのクラスは、次の実行時の解像度をサポートします。</span><span class="sxs-lookup"><span data-stu-id="07b57-103">The ESB Resolver classes support run-time resolution of the following:</span></span>  
  
-   <span data-ttu-id="07b57-104">メッセージ配信のエンドポイント</span><span class="sxs-lookup"><span data-stu-id="07b57-104">Message delivery endpoints</span></span>  
  
-   <span data-ttu-id="07b57-105">変換のマップ</span><span class="sxs-lookup"><span data-stu-id="07b57-105">Maps for transformation</span></span>  
  
-   <span data-ttu-id="07b57-106">エンドポイントの構成</span><span class="sxs-lookup"><span data-stu-id="07b57-106">Endpoint configuration</span></span>  
  
-   <span data-ttu-id="07b57-107">カスタムのサービス メタデータ</span><span class="sxs-lookup"><span data-stu-id="07b57-107">Custom service metadata</span></span>  
  
-   <span data-ttu-id="07b57-108">サーバー側の日程</span><span class="sxs-lookup"><span data-stu-id="07b57-108">Server-side itineraries</span></span>  
  
 <span data-ttu-id="07b57-109">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]メッセージが到着したときに、マップとエンドポイントの解決を試行する競合回避モジュールの接続文字列を使用します。</span><span class="sxs-lookup"><span data-stu-id="07b57-109">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] uses resolver connection strings to attempt resolution of maps and endpoints when messages arrive.</span></span> <span data-ttu-id="07b57-110">これらの接続文字列があります itinerary の SOAP ヘッダー メッセージの到着するは、次のパイプライン コンポーネントのいずれかを使用してカスタム パイプラインで設定することがあります: ESB 行程セレクター、ESB ディスパッチャーまたは ESB ディスパッチャーの逆アセンブルします。</span><span class="sxs-lookup"><span data-stu-id="07b57-110">These connections strings may exist in the itinerary SOAP header of messages when they arrive, or they may be set in a custom pipeline using one of the following pipeline components: ESB Itinerary Selector, ESB Dispatcher, or ESB Dispatcher Disassemble.</span></span> <span data-ttu-id="07b57-111">解像度は、機能を使用して、「ジャストでタイム」(JIT) の解像度 ESB 競合回避モジュールとアダプターのプロバイダー フレームワーク コンポーネントの処理のライフ サイクルの後で発生します。</span><span class="sxs-lookup"><span data-stu-id="07b57-111">Resolution occurs later in the processing life cycle using the "just-in-time" (JIT) resolution capabilities of the ESB Resolver and Adapter Provider Framework components.</span></span>  
  
 <span data-ttu-id="07b57-112">たとえば、動的変換エージェントをマップする必要がありますが、マップ名がまだ決定されているメッセージを受信した場合、しようと、解決を実行する、関連付けられている競合回避モジュールを使用します。</span><span class="sxs-lookup"><span data-stu-id="07b57-112">For example, if the dynamic transformation agent receives a message that it must map, but the map name has not yet been determined, it will attempt to use the associated resolver to perform the resolution.</span></span> <span data-ttu-id="07b57-113">JIT 解決が失敗した場合、システムは例外メッセージを生成をエラーとして分類されるはします。</span><span class="sxs-lookup"><span data-stu-id="07b57-113">If JIT resolution fails, which is classed as an error, the system generates an exception message.</span></span>  
  
 <span data-ttu-id="07b57-114">アダプター プロバイダーのフレームワークとの競合回避モジュールは、次のデータ ストア、または解決メカニズムを照会できます。</span><span class="sxs-lookup"><span data-stu-id="07b57-114">The Resolver and Adapter Provider Framework can query the following data stores or resolution mechanisms:</span></span>  
  
-   <span data-ttu-id="07b57-115">マップのハードコーディングまたはで動的解決のケースが存在しない、エンドポイント</span><span class="sxs-lookup"><span data-stu-id="07b57-115">Hard-coded maps or endpoints, in which case dynamic resolution does not occur</span></span>  
  
-   <span data-ttu-id="07b57-116">ビジネス ルール エンジン (BRE) ポリシー</span><span class="sxs-lookup"><span data-stu-id="07b57-116">A Business Rules Engine (BRE) policy</span></span>  
  
-   <span data-ttu-id="07b57-117">実装するカスタム アセンブリ、 **IResolveProvider**インターフェイス</span><span class="sxs-lookup"><span data-stu-id="07b57-117">A custom assembly implementing the **IResolveProvider** interface</span></span>  
  
-   <span data-ttu-id="07b57-118">メッセージに XPath クエリ</span><span class="sxs-lookup"><span data-stu-id="07b57-118">An XPath query over the message</span></span>  
  
-   <span data-ttu-id="07b57-119">Universal Description, Discovery, and Integration (UDDI) の参照</span><span class="sxs-lookup"><span data-stu-id="07b57-119">A Universal Description, Discovery, and Integration (UDDI) lookup</span></span>