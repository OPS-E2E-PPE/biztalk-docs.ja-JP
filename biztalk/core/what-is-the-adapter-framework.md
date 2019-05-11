---
title: アダプター フレームワークとは何ですか。 | Microsoft Docs
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
ms.openlocfilehash: dd96ab8287a3c8d02bb612d4595c9f418e566eb9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243217"
---
# <a name="what-is-the-adapter-framework"></a><span data-ttu-id="5bc3b-103">アダプター フレームワークとは何ですか。</span><span class="sxs-lookup"><span data-stu-id="5bc3b-103">What Is the Adapter Framework?</span></span>
<span data-ttu-id="5bc3b-104">BizTalk アダプター フレームワークは、実装またはからの作業にアクセスするすべてのアダプターを開き、安定したメカニズムを提供しています、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージング エンジン。</span><span class="sxs-lookup"><span data-stu-id="5bc3b-104">The BizTalk Adapter Framework offers a stable, open mechanism for all adapters to implement or access work from the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Messaging Engine.</span></span> <span data-ttu-id="5bc3b-105">説明されている、インターフェイス、 **Microsoft.BizTalk.Adapter.Framework**名前空間の構成プロパティ ページを変更する手段を提供するアダプターを有効にします。</span><span class="sxs-lookup"><span data-stu-id="5bc3b-105">The interfaces described in the **Microsoft.BizTalk.Adapter.Framework** namespace enable adapters to provide a means to modify configuration property pages.</span></span> <span data-ttu-id="5bc3b-106">サービスとスキーマを BizTalk プロジェクトにインポートするための手段にもなります。</span><span class="sxs-lookup"><span data-stu-id="5bc3b-106">It also is a means to import services and schemas into the BizTalk project.</span></span>  
  
 <span data-ttu-id="5bc3b-107">次の図は、アダプターとアダプター フレームワークがどのように連携して、アプリケーションを接続する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="5bc3b-107">The following figure shows how an adapter and the Adapter Framework work together to connect your application to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="5bc3b-108">![アダプター フレームワーク](../core/media/ebiz-sdk-adpttoday.gif "ebiz_sdk_adpttoday")</span><span class="sxs-lookup"><span data-stu-id="5bc3b-108">![The adapter framework](../core/media/ebiz-sdk-adpttoday.gif "ebiz_sdk_adpttoday")</span></span>  
  
 <span data-ttu-id="5bc3b-109">次の手順では、この図に示す手順の順序について説明します。</span><span class="sxs-lookup"><span data-stu-id="5bc3b-109">The following steps describe the sequence of steps shown in this figure:</span></span>  
  
1. <span data-ttu-id="5bc3b-110">データは、指定されたアドレスで特定のプロトコルでメッセージをリッスンする受信場所から受信されます。</span><span class="sxs-lookup"><span data-stu-id="5bc3b-110">Data is received from a receive location that is listening for messages with a certain protocol at a specified address.</span></span> <span data-ttu-id="5bc3b-111">受信場所は、アダプターと受信パイプラインに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="5bc3b-111">The receive location is associated with an adapter and a receive pipeline.</span></span> <span data-ttu-id="5bc3b-112">アダプターとパイプライン コンポーネントがあらかじめ決められたプロトコルのメッセージに対して特定のロジックを実行するを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="5bc3b-112">You can configure both the adapter and the pipeline components to perform certain logic on messages of a predetermined protocol.</span></span>  
  
2. <span data-ttu-id="5bc3b-113">受信場所でメッセージを受信すると、メッセージは、新しい BizTalk メッセージを作成、データ ストリームをアタッチします (通常のメッセージのボディ部) のメッセージに、どのエンドポイントに関するメタデータを追加すると、アダプターに送信されデータは、受信したし、メッセージング エンジンにそのメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="5bc3b-113">After the message is received by the receive location, the message is sent to the adapter, which creates a new BizTalk message, attaches the data stream to the message (typically in the body part of the message), adds any metadata pertaining to the endpoint over which the data was received, and then submits that message into the Messaging Engine.</span></span>  
  
3. <span data-ttu-id="5bc3b-114">メッセージング エンジンは、場所データが XML に変換、メッセージの送信者の認証、メッセージを復号化、および XML の検証、受信パイプラインにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="5bc3b-114">The Messaging Engine sends the message to the receive pipeline where the data is transformed into XML, the message sender is authenticated, the message is decrypted, and the XML is validated.</span></span>  
  
4. <span data-ttu-id="5bc3b-115">メッセージング エンジンは、メッセージ ボックス データベースにメッセージを発行します。</span><span class="sxs-lookup"><span data-stu-id="5bc3b-115">The Messaging Engine publishes the message to the MessageBox database.</span></span> <span data-ttu-id="5bc3b-116">メッセージ ボックスは、Microsoft[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]処理されるメッセージを含むテーブル。</span><span class="sxs-lookup"><span data-stu-id="5bc3b-116">The MessageBox is a Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] table containing messages to be processed.</span></span> <span data-ttu-id="5bc3b-117">両方のオーケストレーションおよび送信ポートは、メッセージ ボックス データベースにサブスクライブできます。</span><span class="sxs-lookup"><span data-stu-id="5bc3b-117">Both orchestrations and send ports can subscribe to the MessageBox.</span></span>  
  
5. <span data-ttu-id="5bc3b-118">メッセージング エンジンは、オーケストレーションまたは送信ポートのサブスクライバー、サブスクライバーのフィルターで一連の仕様に一致するメッセージ コンテキスト プロパティに基づいて、メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="5bc3b-118">The Messaging Engine sends the message to either an orchestration or a send port subscriber based upon the message context properties matching the specifications set in the filter on the subscriber.</span></span>  
  
6. <span data-ttu-id="5bc3b-119">オーケストレーションがサブスクライバーの場合は、メッセージを処理して、送信ポートを通じて送信されます。</span><span class="sxs-lookup"><span data-stu-id="5bc3b-119">If an orchestration is the subscriber, it processes the message and sends it out through a send port.</span></span> <span data-ttu-id="5bc3b-120">場合は、サブスクライバーに、メッセージは、送信パイプラインを通じて送信アダプターに送信される前に送信されます。</span><span class="sxs-lookup"><span data-stu-id="5bc3b-120">If the subscriber is a send the message passes through the send pipeline into a send adapter before being transmitted.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5bc3b-121">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="5bc3b-121">In This Section</span></span>  
  
-   [<span data-ttu-id="5bc3b-122">アダプター フレームワーク ツールの使用</span><span class="sxs-lookup"><span data-stu-id="5bc3b-122">Using the Adapter Framework Tools</span></span>](../core/using-the-adapter-framework-tools.md)  
  
-   [<span data-ttu-id="5bc3b-123">アダプターのメッセージ交換パターン</span><span class="sxs-lookup"><span data-stu-id="5bc3b-123">Adapter Message Exchange Patterns</span></span>](../core/adapter-message-exchange-patterns.md)  
  
-   [<span data-ttu-id="5bc3b-124">アダプター フレームワーク コンポーネント</span><span class="sxs-lookup"><span data-stu-id="5bc3b-124">Adapter Framework Components</span></span>](../core/adapter-framework-components.md)  
  
-   [<span data-ttu-id="5bc3b-125">アダプターのホスト モデル</span><span class="sxs-lookup"><span data-stu-id="5bc3b-125">Adapter Hosting Model</span></span>](../core/adapter-hosting-model.md)  
  
-   [<span data-ttu-id="5bc3b-126">アダプター コンポーネント</span><span class="sxs-lookup"><span data-stu-id="5bc3b-126">Adapter Components</span></span>](../core/adapter-components.md)