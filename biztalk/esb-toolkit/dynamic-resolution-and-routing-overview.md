---
title: 動的な解決とルーティングの概要 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a9a32491-132b-4b25-ac8c-4a927052f0be
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ab158fe2bf16e4e03b2d4817a644d3e37e9567b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65306264"
---
# <a name="dynamic-resolution-and-routing-overview"></a><span data-ttu-id="974b4-102">動的な解決とルーティングの概要</span><span class="sxs-lookup"><span data-stu-id="974b4-102">Dynamic Resolution and Routing Overview</span></span>
<span data-ttu-id="974b4-103">ESB リゾルバー クラスは、次の実行時の解像度をサポートします。</span><span class="sxs-lookup"><span data-stu-id="974b4-103">The ESB Resolver classes support run-time resolution of the following:</span></span>  

- <span data-ttu-id="974b4-104">メッセージ配信のエンドポイント</span><span class="sxs-lookup"><span data-stu-id="974b4-104">Message delivery endpoints</span></span>  

- <span data-ttu-id="974b4-105">変換のマップ</span><span class="sxs-lookup"><span data-stu-id="974b4-105">Maps for transformation</span></span>  

- <span data-ttu-id="974b4-106">エンドポイントの構成</span><span class="sxs-lookup"><span data-stu-id="974b4-106">Endpoint configuration</span></span>  

- <span data-ttu-id="974b4-107">カスタムのサービス メタデータ</span><span class="sxs-lookup"><span data-stu-id="974b4-107">Custom service metadata</span></span>  

- <span data-ttu-id="974b4-108">サーバー側のスケジュール</span><span class="sxs-lookup"><span data-stu-id="974b4-108">Server-side itineraries</span></span>  

  <span data-ttu-id="974b4-109">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]メッセージが届いたときに、マップとエンドポイントの解決を試行する競合回避モジュールの接続文字列を使用します。</span><span class="sxs-lookup"><span data-stu-id="974b4-109">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] uses resolver connection strings to attempt resolution of maps and endpoints when messages arrive.</span></span> <span data-ttu-id="974b4-110">これらの接続文字列は可能性がありますが到着した、または、次のパイプライン コンポーネントのいずれかを使用してカスタム パイプラインで設定できますにスケジュールするメッセージの SOAP ヘッダーに存在します。ESB スケジュール セレクター、ESB ディスパッチャー、または ESB ディスパッチャー逆アセンブルします。</span><span class="sxs-lookup"><span data-stu-id="974b4-110">These connections strings may exist in the itinerary SOAP header of messages when they arrive, or they may be set in a custom pipeline using one of the following pipeline components: ESB Itinerary Selector, ESB Dispatcher, or ESB Dispatcher Disassemble.</span></span> <span data-ttu-id="974b4-111">解像度は、ESB リゾルバーとアダプターのプロバイダー フレームワーク コンポーネントの"- just-in-time"(JIT) の解決機能を使用して処理ライフ サイクルの後半に発生します。</span><span class="sxs-lookup"><span data-stu-id="974b4-111">Resolution occurs later in the processing life cycle using the "just-in-time" (JIT) resolution capabilities of the ESB Resolver and Adapter Provider Framework components.</span></span>  

  <span data-ttu-id="974b4-112">たとえばをマップする必要がありますが、マップ名が決定されていないメッセージを受信すると、動的変換エージェントに関連付けられている競合回避モジュールを使用して、解決を実行することがされます。</span><span class="sxs-lookup"><span data-stu-id="974b4-112">For example, if the dynamic transformation agent receives a message that it must map, but the map name has not yet been determined, it will attempt to use the associated resolver to perform the resolution.</span></span> <span data-ttu-id="974b4-113">JIT の解決に失敗した場合、システムは例外メッセージを生成、エラーとして分類するがします。</span><span class="sxs-lookup"><span data-stu-id="974b4-113">If JIT resolution fails, which is classed as an error, the system generates an exception message.</span></span>  

  <span data-ttu-id="974b4-114">リゾルバーとアダプターのプロバイダー フレームワークは、次のデータ ストアまたは解決メカニズムを照会できます。</span><span class="sxs-lookup"><span data-stu-id="974b4-114">The Resolver and Adapter Provider Framework can query the following data stores or resolution mechanisms:</span></span>  

- <span data-ttu-id="974b4-115">ハード コーディングされたマップやエンドポイントの大文字と小文字の動的な解決は発生しません</span><span class="sxs-lookup"><span data-stu-id="974b4-115">Hard-coded maps or endpoints, in which case dynamic resolution does not occur</span></span>  

- <span data-ttu-id="974b4-116">ビジネス ルール エンジン (BRE) ポリシー</span><span class="sxs-lookup"><span data-stu-id="974b4-116">A Business Rules Engine (BRE) policy</span></span>  

- <span data-ttu-id="974b4-117">実装するカスタム アセンブリ、 **IResolveProvider**インターフェイス</span><span class="sxs-lookup"><span data-stu-id="974b4-117">A custom assembly implementing the **IResolveProvider** interface</span></span>  

- <span data-ttu-id="974b4-118">メッセージの上、XPath クエリ</span><span class="sxs-lookup"><span data-stu-id="974b4-118">An XPath query over the message</span></span>  

- <span data-ttu-id="974b4-119">Universal Description, Discovery, and Integration (UDDI) の参照</span><span class="sxs-lookup"><span data-stu-id="974b4-119">A Universal Description, Discovery, and Integration (UDDI) lookup</span></span>
