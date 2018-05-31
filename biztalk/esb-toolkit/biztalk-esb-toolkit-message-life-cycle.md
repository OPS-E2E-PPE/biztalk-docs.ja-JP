---
title: BizTalk ESB Toolkit のメッセージのライフ サイクル |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c72fdbda-b9ef-431a-8322-56dba98e9eab
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2cb15a4c87a497a5595327b65019ca95b3201664
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22290354"
---
# <a name="biztalk-esb-toolkit-message-life-cycle"></a><span data-ttu-id="3d507-102">BizTalk ESB Toolkit のメッセージのライフ サイクル</span><span class="sxs-lookup"><span data-stu-id="3d507-102">BizTalk ESB Toolkit Message Life Cycle</span></span>
<span data-ttu-id="3d507-103">外部システムから開始され、最終的な送信先に到達する ESB 内を移動するメッセージのライフ サイクルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="3d507-103">The following is the life cycle of a message that originates from an external system and traverses through the ESB to reach its final destination:</span></span>  
  
1.  <span data-ttu-id="3d507-104">ランプでは、メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="3d507-104">An on-ramp receives the message.</span></span> <span data-ttu-id="3d507-105">送信のパーティまたはクライアントによって、メッセージは可能性があります。 またはメッセージの処理命令を定義する旅程を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="3d507-105">Depending on the submitting party or client, the message may or may not contain an itinerary that defines the processing instructions for the message.</span></span>  
  
2.  <span data-ttu-id="3d507-106">ESB パイプライン コンポーネントを itinerary (存在する場合、SOAP ヘッダー内) にコピー、メッセージのコンテキストとして昇格させたプロパティ。</span><span class="sxs-lookup"><span data-stu-id="3d507-106">ESB pipeline components copy the itinerary (if present in the SOAP header) into the context of the message as promoted properties.</span></span> <span data-ttu-id="3d507-107">日程せず、メッセージを受信する場合は、メッセージのコンテンツやコンテキストによっては、データベースから適切な旅程を選択し、メッセージのコンテキストに旅行計画をコピーする、特定のパイプライン コンポーネントを構成できます。</span><span class="sxs-lookup"><span data-stu-id="3d507-107">If the message is received without an itinerary, a specific pipeline component can be configured to select the appropriate itinerary from a database, depending on message content or context, and then copy the itinerary into the context of the message.</span></span> <span data-ttu-id="3d507-108">メッセージの有効期間中は、旅行計画はメッセージ コンテキスト内で維持されます。</span><span class="sxs-lookup"><span data-stu-id="3d507-108">For the duration of the lifetime of the message, the itinerary is maintained within the message context.</span></span>  
  
3.  <span data-ttu-id="3d507-109">パイプラインで旅行計画が評価され、メッセージ ベースの itinerary サービスがメッセージを処理できます。</span><span class="sxs-lookup"><span data-stu-id="3d507-109">While still in the pipeline, the itinerary is evaluated and message-based itinerary services can process the message.</span></span> <span data-ttu-id="3d507-110">これらの itinerary サービスには、メッセージ変換可能性がありますも、ルーティングのエンドポイントを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="3d507-110">These itinerary services may transform the message or configure routing endpoints.</span></span>  
  
4.  <span data-ttu-id="3d507-111">メッセージは、Microsoft BizTalk Server メッセージ ボックス データベースに発行されます。</span><span class="sxs-lookup"><span data-stu-id="3d507-111">The message is published to the Microsoft BizTalk Server Message Box database.</span></span>  
  
5.  <span data-ttu-id="3d507-112">BizTalk Server は、1 つまたは複数のサブスクライバーに対して、メッセージのメッセージとキューの昇格させたプロパティを評価します。</span><span class="sxs-lookup"><span data-stu-id="3d507-112">BizTalk Server evaluates the promoted properties of the message and queues the message for one or more subscribers.</span></span>  
  
6.  <span data-ttu-id="3d507-113">サブスクライバーでは、BizTalk Server の一般的なメカニズムを使用してメッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="3d507-113">The subscriber(s) process the message using typical BizTalk Server mechanisms.</span></span> <span data-ttu-id="3d507-114">サブスクライバーには、次のいずれかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="3d507-114">A subscriber can be either of the following:</span></span>  
  
    -   <span data-ttu-id="3d507-115">直接バインドで構成されているフィルターを使用して BizTalk Server オーケストレーションの受信ポート</span><span class="sxs-lookup"><span data-stu-id="3d507-115">A BizTalk Server orchestration with a filter configured on a direct-bound receive port</span></span>  
  
    -   <span data-ttu-id="3d507-116">動的な BizTalk Server は送信ポートで、ESB 出口とも呼びますです。</span><span class="sxs-lookup"><span data-stu-id="3d507-116">A dynamic BizTalk Server send port, which is also referred to as an ESB off-ramp.</span></span> <span data-ttu-id="3d507-117">旅行計画では、メッセージの処理を続行するポートを構成する方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="3d507-117">The itinerary determines how the port will be configured to continue processing the message.</span></span>  
  
 <span data-ttu-id="3d507-118">Itinerary 入り口経由で到着するメッセージを代わりに、BizTalk Server オーケストレーションが ESB 処理のため、メッセージ ボックスのメッセージを発行することもできます。</span><span class="sxs-lookup"><span data-stu-id="3d507-118">As an alternative to a message arriving through an itinerary on-ramp, BizTalk Server orchestrations can also publish messages to the Message Box for ESB processing:</span></span>  
  
1.  <span data-ttu-id="3d507-119">メッセージが BizTalk Server オーケストレーション内で作成します。</span><span class="sxs-lookup"><span data-stu-id="3d507-119">A message is created within a BizTalk Server orchestration.</span></span>  
  
2.  <span data-ttu-id="3d507-120">メッセージのコンテキストには、ESB 行程が格納されます。</span><span class="sxs-lookup"><span data-stu-id="3d507-120">The message's context is populated with the ESB itinerary.</span></span>  
  
3.  <span data-ttu-id="3d507-121">メッセージはメッセージ ボックス データベースに直接バインド ポート経由で公開します。</span><span class="sxs-lookup"><span data-stu-id="3d507-121">The message is published through a direct-bound port to the Message Box database.</span></span>