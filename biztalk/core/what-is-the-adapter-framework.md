---
title: アダプター フレームワークについて | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bd1e2fd7-4e77-49c4-839d-c2bf16b10ba2
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 648c22a52e543b24458daa73146836e1e3a5463e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289602"
---
# <a name="what-is-the-adapter-framework"></a><span data-ttu-id="c4548-103">アダプター フレームワークについて</span><span class="sxs-lookup"><span data-stu-id="c4548-103">What Is the Adapter Framework?</span></span>
<span data-ttu-id="c4548-104">BizTalk Server アダプター フレームワークは、すべてのアダプターで実装するための、または [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] メッセージング エンジンによる作業にアクセスするための、安定したオープンなメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="c4548-104">The BizTalk Adapter Framework offers a stable, open mechanism for all adapters to implement or access work from the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Messaging Engine.</span></span> <span data-ttu-id="c4548-105">説明されているインターフェイス、 **Microsoft.BizTalk.Adapter.Framework**名前空間には、構成のプロパティ ページを変更する手段を提供するアダプターが有効にします。</span><span class="sxs-lookup"><span data-stu-id="c4548-105">The interfaces described in the **Microsoft.BizTalk.Adapter.Framework** namespace enable adapters to provide a means to modify configuration property pages.</span></span> <span data-ttu-id="c4548-106">これは、サービスやスキーマを BizTalk プロジェクトにインポートする手段でもあります。</span><span class="sxs-lookup"><span data-stu-id="c4548-106">It also is a means to import services and schemas into the BizTalk project.</span></span>  
  
 <span data-ttu-id="c4548-107">次の図は、アダプターとアダプター フレームワークがどのように連動してアプリケーションを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に接続するかを示しています。</span><span class="sxs-lookup"><span data-stu-id="c4548-107">The following figure shows how an adapter and the Adapter Framework work together to connect your application to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="c4548-108">![アダプター フレームワーク](../core/media/ebiz-sdk-adpttoday.gif "ebiz_sdk_adpttoday")</span><span class="sxs-lookup"><span data-stu-id="c4548-108">![The adapter framework](../core/media/ebiz-sdk-adpttoday.gif "ebiz_sdk_adpttoday")</span></span>  
  
 <span data-ttu-id="c4548-109">次の手順では、この図に示されている一連の手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="c4548-109">The following steps describe the sequence of steps shown in this figure:</span></span>  
  
1.  <span data-ttu-id="c4548-110">データの受信は、指定のアドレスで特定のプロトコルのメッセージを待ち受けている受信場所で行われます。</span><span class="sxs-lookup"><span data-stu-id="c4548-110">Data is received from a receive location that is listening for messages with a certain protocol at a specified address.</span></span> <span data-ttu-id="c4548-111">受信場所は、アダプターと受信パイプラインに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="c4548-111">The receive location is associated with an adapter and a receive pipeline.</span></span> <span data-ttu-id="c4548-112">あらかじめ決められたプロトコルのメッセージに対して特定のロジックを実行するように、アダプター コンポーネントとパイプライン コンポーネントの両方を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="c4548-112">You can configure both the adapter and the pipeline components to perform certain logic on messages of a predetermined protocol.</span></span>  
  
2.  <span data-ttu-id="c4548-113">受信場所でメッセージが受信されると、メッセージがアダプターに送信され、そこで新しい BizTalk メッセージが作成されます。アダプターは、データ ストリームをメッセージ (通常はメッセージのボディ部内) に添付し、データの受信元エンドポイントに関するメタデータを追加して、そのメッセージをメッセージング エンジンに送信します。</span><span class="sxs-lookup"><span data-stu-id="c4548-113">After the message is received by the receive location, the message is sent to the adapter, which creates a new BizTalk message, attaches the data stream to the message (typically in the body part of the message), adds any metadata pertaining to the endpoint over which the data was received, and then submits that message into the Messaging Engine.</span></span>  
  
3.  <span data-ttu-id="c4548-114">メッセージング エンジンが受信パイプラインにメッセージを送信すると、そこでデータが XML に変換され、メッセージの送信者が認証されます。さらに、メッセージの解読および XML の検証が行われます。</span><span class="sxs-lookup"><span data-stu-id="c4548-114">The Messaging Engine sends the message to the receive pipeline where the data is transformed into XML, the message sender is authenticated, the message is decrypted, and the XML is validated.</span></span>  
  
4.  <span data-ttu-id="c4548-115">メッセージング エンジンは、メッセージをメッセージ ボックス データベースに公開します。</span><span class="sxs-lookup"><span data-stu-id="c4548-115">The Messaging Engine publishes the message to the MessageBox database.</span></span> <span data-ttu-id="c4548-116">メッセージ ボックスとは、処理するメッセージが含まれている Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] テーブルです。</span><span class="sxs-lookup"><span data-stu-id="c4548-116">The MessageBox is a Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] table containing messages to be processed.</span></span> <span data-ttu-id="c4548-117">オーケストレーションと送信ポートの両方が、メッセージ ボックスをサブスクライブできます。</span><span class="sxs-lookup"><span data-stu-id="c4548-117">Both orchestrations and send ports can subscribe to the MessageBox.</span></span>  
  
5.  <span data-ttu-id="c4548-118">メッセージング エンジンは、サブスクライバーのフィルターの仕様セットに一致するメッセージ コンテキストのプロパティに基づいて、メッセージをオーケストレーションまたは送信ポートのサブスクライバーにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="c4548-118">The Messaging Engine sends the message to either an orchestration or a send port subscriber based upon the message context properties matching the specifications set in the filter on the subscriber.</span></span>  
  
6.  <span data-ttu-id="c4548-119">オーケストレーションがサブスクライバーの場合、処理されたメッセージは送信ポートを通じて送信されます。</span><span class="sxs-lookup"><span data-stu-id="c4548-119">If an orchestration is the subscriber, it processes the message and sends it out through a send port.</span></span> <span data-ttu-id="c4548-120">サブスクライバーが送信ポートの場合、メッセージは回線で送信される前に送信パイプラインを通じて送信アダプターに渡されます。</span><span class="sxs-lookup"><span data-stu-id="c4548-120">If the subscriber is a send the message passes through the send pipeline into a send adapter before being transmitted.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c4548-121">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c4548-121">In This Section</span></span>  
  
-   [<span data-ttu-id="c4548-122">アダプター フレームワーク ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="c4548-122">Using the Adapter Framework Tools</span></span>](../core/using-the-adapter-framework-tools.md)  
  
-   [<span data-ttu-id="c4548-123">アダプターのメッセージ交換パターン</span><span class="sxs-lookup"><span data-stu-id="c4548-123">Adapter Message Exchange Patterns</span></span>](../core/adapter-message-exchange-patterns.md)  
  
-   [<span data-ttu-id="c4548-124">アダプター フレームワーク コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c4548-124">Adapter Framework Components</span></span>](../core/adapter-framework-components.md)  
  
-   [<span data-ttu-id="c4548-125">アダプターのホスト モデル</span><span class="sxs-lookup"><span data-stu-id="c4548-125">Adapter Hosting Model</span></span>](../core/adapter-hosting-model.md)  
  
-   [<span data-ttu-id="c4548-126">アダプター コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c4548-126">Adapter Components</span></span>](../core/adapter-components.md)