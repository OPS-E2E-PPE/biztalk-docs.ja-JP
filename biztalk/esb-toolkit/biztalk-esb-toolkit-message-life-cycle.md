---
title: BizTalk ESB Toolkit メッセージ ライフ サイクル |Microsoft Docs
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
ms.openlocfilehash: 26db3a32cc31f417d518b2eb8663f2da3ba5e8ee
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392080"
---
# <a name="biztalk-esb-toolkit-message-life-cycle"></a><span data-ttu-id="2fc66-102">BizTalk ESB Toolkit メッセージ ライフ サイクル</span><span class="sxs-lookup"><span data-stu-id="2fc66-102">BizTalk ESB Toolkit Message Life Cycle</span></span>
<span data-ttu-id="2fc66-103">外部システムから開始され、最終的な宛先に到達する ESB を走査するメッセージのライフ サイクルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="2fc66-103">The following is the life cycle of a message that originates from an external system and traverses through the ESB to reach its final destination:</span></span>  

1. <span data-ttu-id="2fc66-104">傾斜では、メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="2fc66-104">An on-ramp receives the message.</span></span> <span data-ttu-id="2fc66-105">送信のパーティまたはクライアントによって、メッセージは可能性があります。 またはメッセージの処理命令を定義する旅行プランを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="2fc66-105">Depending on the submitting party or client, the message may or may not contain an itinerary that defines the processing instructions for the message.</span></span>  

2. <span data-ttu-id="2fc66-106">ESB パイプライン コンポーネントをコピー、旅行プラン (SOAP ヘッダーに存在する) 場合、メッセージのコンテキストに昇格させたプロパティとして。</span><span class="sxs-lookup"><span data-stu-id="2fc66-106">ESB pipeline components copy the itinerary (if present in the SOAP header) into the context of the message as promoted properties.</span></span> <span data-ttu-id="2fc66-107">スケジュールなし、メッセージを受信する場合は、メッセージの内容またはコンテキストに応じて、データベースから適切な旅行プランを選択し、メッセージのコンテキストに旅行プランをコピーする特定のパイプライン コンポーネントを構成できます。</span><span class="sxs-lookup"><span data-stu-id="2fc66-107">If the message is received without an itinerary, a specific pipeline component can be configured to select the appropriate itinerary from a database, depending on message content or context, and then copy the itinerary into the context of the message.</span></span> <span data-ttu-id="2fc66-108">メッセージの有効期間中は、メッセージ コンテキスト内で、スケジュールが維持されます。</span><span class="sxs-lookup"><span data-stu-id="2fc66-108">For the duration of the lifetime of the message, the itinerary is maintained within the message context.</span></span>  

3. <span data-ttu-id="2fc66-109">パイプラインでは、旅行プランが評価され、メッセージ ベースのスケジュール サービスがメッセージを処理できます。</span><span class="sxs-lookup"><span data-stu-id="2fc66-109">While still in the pipeline, the itinerary is evaluated and message-based itinerary services can process the message.</span></span> <span data-ttu-id="2fc66-110">これらのスケジュール サービスは、メッセージを変換またはルーティング エンドポイントの構成可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2fc66-110">These itinerary services may transform the message or configure routing endpoints.</span></span>  

4. <span data-ttu-id="2fc66-111">メッセージは、Microsoft BizTalk Server メッセージ ボックス データベースに発行されます。</span><span class="sxs-lookup"><span data-stu-id="2fc66-111">The message is published to the Microsoft BizTalk Server Message Box database.</span></span>  

5. <span data-ttu-id="2fc66-112">BizTalk Server では、1 つまたは複数のサブスクライバーのメッセージとキューの昇格させたプロパティ、メッセージを評価します。</span><span class="sxs-lookup"><span data-stu-id="2fc66-112">BizTalk Server evaluates the promoted properties of the message and queues the message for one or more subscribers.</span></span>  

6. <span data-ttu-id="2fc66-113">サブスクライバーでは、BizTalk Server の一般的なメカニズムを使用してメッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="2fc66-113">The subscriber(s) process the message using typical BizTalk Server mechanisms.</span></span> <span data-ttu-id="2fc66-114">サブスクライバーには、次のいずれかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="2fc66-114">A subscriber can be either of the following:</span></span>  

   -   <span data-ttu-id="2fc66-115">直接バインドで構成されているフィルターを使用して BizTalk Server オーケストレーションの受信ポート</span><span class="sxs-lookup"><span data-stu-id="2fc66-115">A BizTalk Server orchestration with a filter configured on a direct-bound receive port</span></span>  

   -   <span data-ttu-id="2fc66-116">動的な BizTalk Server は、ESB を導入とも呼ばれますポートを送信します。</span><span class="sxs-lookup"><span data-stu-id="2fc66-116">A dynamic BizTalk Server send port, which is also referred to as an ESB off-ramp.</span></span> <span data-ttu-id="2fc66-117">旅行プランは、メッセージの処理を続行するポートを構成する方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="2fc66-117">The itinerary determines how the port will be configured to continue processing the message.</span></span>  

   <span data-ttu-id="2fc66-118">スケジュール オンランプ入り口で到着したメッセージを代わりに、BizTalk Server オーケストレーションが ESB 処理のため、メッセージ ボックスのメッセージを発行することもできます。</span><span class="sxs-lookup"><span data-stu-id="2fc66-118">As an alternative to a message arriving through an itinerary on-ramp, BizTalk Server orchestrations can also publish messages to the Message Box for ESB processing:</span></span>  

7. <span data-ttu-id="2fc66-119">メッセージが BizTalk Server オーケストレーション内で作成されます。</span><span class="sxs-lookup"><span data-stu-id="2fc66-119">A message is created within a BizTalk Server orchestration.</span></span>  

8. <span data-ttu-id="2fc66-120">メッセージのコンテキストには、ESB 行程が設定されます。</span><span class="sxs-lookup"><span data-stu-id="2fc66-120">The message's context is populated with the ESB itinerary.</span></span>  

9. <span data-ttu-id="2fc66-121">メッセージ ボックス データベースに直接バインドされたポートを通じてメッセージが発行されます。</span><span class="sxs-lookup"><span data-stu-id="2fc66-121">The message is published through a direct-bound port to the Message Box database.</span></span>
