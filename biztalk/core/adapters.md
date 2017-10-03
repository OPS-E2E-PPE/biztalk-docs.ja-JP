---
title: "アダプター |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adapters, receive adapters
- adapters
- send adapters
- adapters, about adapters
- send adapters, about send adapters
- receive adapters, about receive adapters
- adapters, adapter framework
- receive adapters
- adapters, send adapters
ms.assetid: 7803a806-3396-4662-877f-eae11cb5e3e4
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a7f58a9d67b9702cfbb7b21788f751717ac61e4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="adapters"></a><span data-ttu-id="53f5e-102">アダプタ</span><span class="sxs-lookup"><span data-stu-id="53f5e-102">Adapters</span></span>
<span data-ttu-id="53f5e-103">Microsoft BizTalk Server では、外部のシステム、アプリケーション、およびエンティティとメッセージを交換するために、アダプターの概念を使用します。</span><span class="sxs-lookup"><span data-stu-id="53f5e-103">To exchange messages with external systems, applications, and entities Microsoft BizTalk Server uses the concept of an adapter.</span></span> <span data-ttu-id="53f5e-104">*アダプター* com またはします。NET ベースのコンポーネントとビジネス エンドポイント (ファイル システム、データベース、カスタム ビジネス アプリケーションなど) からメッセージを転送するさまざまな通信プロトコルを使用します。</span><span class="sxs-lookup"><span data-stu-id="53f5e-104">*Adapters* are COM or .NET-based components that transfer messages to and from business endpoints (such as file systems, databases, and custom business applications) using various communication protocols.</span></span>  
  
 <span data-ttu-id="53f5e-105">BizTalk Server では、送受信操作において外部のエンティティとメッセージを交換するためにアダプターを使用します。</span><span class="sxs-lookup"><span data-stu-id="53f5e-105">Adapters are used by BizTalk Server to exchange messages with external entities in send and receive operations</span></span>  
  
-   <span data-ttu-id="53f5e-106">送信 (送信側) 操作とは、アダプターでサポートされているプロトコルを使用して、BizTalk Server が外部エンティティに情報を送信することをいいます。</span><span class="sxs-lookup"><span data-stu-id="53f5e-106">Send (or send-side) operations occur when information is being sent by BizTalk Server to an external entity using the protocols supported by the adapter.</span></span>  
  
-   <span data-ttu-id="53f5e-107">受信 (受信側) 操作とは、アダプターが外部エンティティから情報を受信し、BizTalk Server メッセージング エンジンにその情報を渡すことをいいます。</span><span class="sxs-lookup"><span data-stu-id="53f5e-107">Receive (or receive-side) operations occur when the adapter receives information from an external entity and passes it into the BizTalk Server Messaging Engine.</span></span>  
  
## <a name="the-adapter-framework"></a><span data-ttu-id="53f5e-108">アダプター フレームワーク</span><span class="sxs-lookup"><span data-stu-id="53f5e-108">The Adapter Framework</span></span>  
 <span data-ttu-id="53f5e-109">次の図は、アダプターとアダプター フレームワークがどのように連動してアプリケーションを BizTalk Server に接続するかを示しています。</span><span class="sxs-lookup"><span data-stu-id="53f5e-109">The following figure shows how an adapter and the Adapter Framework work together to connect your application to BizTalk Server.</span></span>  
  
1.  <span data-ttu-id="53f5e-110">データは、指定したアドレスで特定のプロトコルのメッセージをリッスンしている受信場所を介して受信されます。</span><span class="sxs-lookup"><span data-stu-id="53f5e-110">Data is received through a receive location that is listening for messages of a certain protocol at a specified address.</span></span> <span data-ttu-id="53f5e-111">受信場所は、アダプターと受信パイプラインに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="53f5e-111">The receive location is associated with an adapter and a receive pipeline.</span></span> <span data-ttu-id="53f5e-112">あらかじめ決められたプロトコルを持つメッセージに対して特定のロジックを実行するように、アダプター コンポーネントとパイプライン コンポーネントの両方を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="53f5e-112">You can configure both the adapter and the pipeline components to perform certain logic on messages having a predetermined protocol.</span></span>  
  
2.  <span data-ttu-id="53f5e-113">受信場所でメッセージが受信されると、メッセージがアダプターに送信され、そこで新しい BizTalk Server メッセージが作成されます。アダプターは、データ ストリームをメッセージ (通常はメッセージのボディ部内) に添付し、データの受信元エンドポイントに関するメタデータを追加して、そのメッセージをメッセージング エンジンに送信します。</span><span class="sxs-lookup"><span data-stu-id="53f5e-113">After the message is received by the receive location, the message is sent to the adapter, which creates a new BizTalk Server message, attaches the data stream to the message (typically in the body part of the message), adds any metadata pertaining to the endpoint over which the data was received, and then submits that message into the Messaging Engine.</span></span>  
  
3.  <span data-ttu-id="53f5e-114">メッセージング エンジンが受信パイプラインにメッセージを送信すると、そこでデータが XML に変換され、メッセージの送信者が認証されます。さらに、メッセージの解読および XML の検証が行われます。</span><span class="sxs-lookup"><span data-stu-id="53f5e-114">The Messaging Engine sends the message to the receive pipeline where the data is transformed into XML, the message sender is authenticated, the message is decrypted, and the XML is validated.</span></span>  
  
4.  <span data-ttu-id="53f5e-115">メッセージング エンジンは、メッセージをメッセージ ボックスに公開します。</span><span class="sxs-lookup"><span data-stu-id="53f5e-115">The Messaging Engine publishes the message to the MessageBox.</span></span> <span data-ttu-id="53f5e-116">メッセージ ボックスとは、処理するメッセージが含まれている Microsoft SQL Server テーブルです。</span><span class="sxs-lookup"><span data-stu-id="53f5e-116">The MessageBox is a Microsoft SQL Server table containing messages to be processed.</span></span> <span data-ttu-id="53f5e-117">オーケストレーションと送信ポートの両方が、メッセージ ボックスをサブスクライブできます。</span><span class="sxs-lookup"><span data-stu-id="53f5e-117">Both orchestrations and send ports can subscribe to the MessageBox.</span></span>  
  
5.  <span data-ttu-id="53f5e-118">メッセージング エンジンは、サブスクライバーのフィルターの仕様セットに一致するメッセージ コンテキストのプロパティに基づいて、メッセージをオーケストレーションまたは送信ポートのサブスクライバーにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="53f5e-118">The Messaging Engine sends the message to either an orchestration or a send port subscriber based upon the message context properties matching the specifications set in the filter on the subscriber.</span></span>  
  
6.  <span data-ttu-id="53f5e-119">オーケストレーションがサブスクライバーの場合、処理されたメッセージは送信ポートを使用して送信されます。</span><span class="sxs-lookup"><span data-stu-id="53f5e-119">If an orchestration is the subscriber, it processes the message and sends it out using a send port.</span></span> <span data-ttu-id="53f5e-120">送信ポートにメッセージが到達した場合、または送信ポートが唯一のサブスクライバーの場合、メッセージは回線で送信される前に送信パイプラインを通じて送信アダプターに渡されます。</span><span class="sxs-lookup"><span data-stu-id="53f5e-120">After the send port has it, or is the only subscriber, the message passes through the send pipeline into a send adapter before being transmitted over the wire.</span></span>  
  
 <span data-ttu-id="53f5e-121">アダプター フレームワーク</span><span class="sxs-lookup"><span data-stu-id="53f5e-121">The Adapter Framework</span></span>  
  
 <span data-ttu-id="53f5e-122">![アダプター フレームワーク](../core/media/ebiz-sdk-adpttoday.gif "ebiz_sdk_adpttoday")</span><span class="sxs-lookup"><span data-stu-id="53f5e-122">![The adapter framework](../core/media/ebiz-sdk-adpttoday.gif "ebiz_sdk_adpttoday")</span></span>  
  
## <a name="receive-adapters"></a><span data-ttu-id="53f5e-123">受信アダプター</span><span class="sxs-lookup"><span data-stu-id="53f5e-123">Receive Adapters</span></span>  
 <span data-ttu-id="53f5e-124">受信アダプターは、ネットワーク/データ ソース ストリームをメッセージのボディ部に添付して新しい BizTalk Server メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="53f5e-124">Receive adapters are responsible for creating a new BizTalk Server message by attaching the network/data source stream to the message body.</span></span> <span data-ttu-id="53f5e-125">また、どのデータを受信しましたが、メッセージング エンジンにそのメッセージを送信するエンドポイントに関連するすべてのメタデータを追加します。</span><span class="sxs-lookup"><span data-stu-id="53f5e-125">It also adds any metadata pertinent to the endpoint over which the data was received, then submits that message to the Messaging Engine.</span></span>  
  
 <span data-ttu-id="53f5e-126">アダプターは、受信エンドポイントからデータを削除したり、適切な確認メッセージをクライアントに送信して、データが BizTalk Server で受理されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="53f5e-126">The adapter deletes the data from the receive endpoint or sends the appropriate acknowledgement message to the client indicating that the data has been accepted into BizTalk Server.</span></span>  
  
## <a name="send-adapters"></a><span data-ttu-id="53f5e-127">送信アダプター</span><span class="sxs-lookup"><span data-stu-id="53f5e-127">Send Adapters</span></span>  
 <span data-ttu-id="53f5e-128">アダプターは、特定のトランスポート プロトコルを使用して、指定されたエンドポイントに BizTalk メッセージを送信するために送信します。</span><span class="sxs-lookup"><span data-stu-id="53f5e-128">Send adapters are responsible for sending a BizTalk message to the specified endpoint using its specific transport protocol.</span></span>  
  
 <span data-ttu-id="53f5e-129">アダプターの詳細については、アダプター、およびカスタム アダプターの作成の構造を参照してください[カスタム アダプターの開発](../core/developing-custom-adapters.md)です。</span><span class="sxs-lookup"><span data-stu-id="53f5e-129">For more information about adapters, the structure of an adapter, and writing custom adapters, see [Developing Custom Adapters](../core/developing-custom-adapters.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53f5e-130">参照</span><span class="sxs-lookup"><span data-stu-id="53f5e-130">See Also</span></span>  
 [<span data-ttu-id="53f5e-131">成果物</span><span class="sxs-lookup"><span data-stu-id="53f5e-131">Artifacts</span></span>](../core/artifacts.md)