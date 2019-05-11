---
title: アダプター |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d3e669f31f1050a0e2c37388cd8106a2386da45
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361079"
---
# <a name="adapters"></a><span data-ttu-id="0ecb8-102">アダプター</span><span class="sxs-lookup"><span data-stu-id="0ecb8-102">Adapters</span></span>
<span data-ttu-id="0ecb8-103">外部システム、アプリケーション、およびエンティティとメッセージを交換するのには、Microsoft BizTalk Server は、アダプターの概念を使用します。</span><span class="sxs-lookup"><span data-stu-id="0ecb8-103">To exchange messages with external systems, applications, and entities Microsoft BizTalk Server uses the concept of an adapter.</span></span> <span data-ttu-id="0ecb8-104">*アダプター* com またはします。NET ベースのコンポーネントとビジネス エンドポイント (ファイル システム、データベース、カスタム ビジネス アプリケーションなど) のメッセージを転送するさまざまな通信プロトコルを使用します。</span><span class="sxs-lookup"><span data-stu-id="0ecb8-104">*Adapters* are COM or .NET-based components that transfer messages to and from business endpoints (such as file systems, databases, and custom business applications) using various communication protocols.</span></span>  
  
 <span data-ttu-id="0ecb8-105">アダプターは送信で外部のエンティティとメッセージを交換し、操作を受信する BizTalk Server で使用します。</span><span class="sxs-lookup"><span data-stu-id="0ecb8-105">Adapters are used by BizTalk Server to exchange messages with external entities in send and receive operations</span></span>  
  
-   <span data-ttu-id="0ecb8-106">送信 (または送信側) 操作は、情報が BizTalk Server によってアダプターによってサポートされるプロトコルを使用して外部エンティティに送信されるときに発生します。</span><span class="sxs-lookup"><span data-stu-id="0ecb8-106">Send (or send-side) operations occur when information is being sent by BizTalk Server to an external entity using the protocols supported by the adapter.</span></span>  
  
-   <span data-ttu-id="0ecb8-107">受信 (または受信側) 操作とは、アダプターは、外部エンティティから情報を受信し、BizTalk Server メッセージング エンジンに渡します。</span><span class="sxs-lookup"><span data-stu-id="0ecb8-107">Receive (or receive-side) operations occur when the adapter receives information from an external entity and passes it into the BizTalk Server Messaging Engine.</span></span>  
  
## <a name="the-adapter-framework"></a><span data-ttu-id="0ecb8-108">アダプター フレームワーク</span><span class="sxs-lookup"><span data-stu-id="0ecb8-108">The Adapter Framework</span></span>  
 <span data-ttu-id="0ecb8-109">次の図は、アダプターとアダプター フレームワークが連携して、アプリケーションを BizTalk Server に接続する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0ecb8-109">The following figure shows how an adapter and the Adapter Framework work together to connect your application to BizTalk Server.</span></span>  
  
1. <span data-ttu-id="0ecb8-110">データは、指定されたアドレスで特定のプロトコルのメッセージをリッスンする受信場所を介して受信されます。</span><span class="sxs-lookup"><span data-stu-id="0ecb8-110">Data is received through a receive location that is listening for messages of a certain protocol at a specified address.</span></span> <span data-ttu-id="0ecb8-111">受信場所は、アダプターと受信パイプラインに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="0ecb8-111">The receive location is associated with an adapter and a receive pipeline.</span></span> <span data-ttu-id="0ecb8-112">アダプターとパイプライン コンポーネントがあらかじめ決められたプロトコルのメッセージで特定のロジックを実行するを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="0ecb8-112">You can configure both the adapter and the pipeline components to perform certain logic on messages having a predetermined protocol.</span></span>  
  
2. <span data-ttu-id="0ecb8-113">受信場所でメッセージを受信すると、メッセージは、アダプターは、新しい BizTalk Server メッセージを作成、データ ストリームをアタッチします (通常のメッセージのボディ部) のメッセージに、エンドポイント経由でに関するメタデータを追加する送信されデータが受信したが、メッセージング エンジンにそのメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="0ecb8-113">After the message is received by the receive location, the message is sent to the adapter, which creates a new BizTalk Server message, attaches the data stream to the message (typically in the body part of the message), adds any metadata pertaining to the endpoint over which the data was received, and then submits that message into the Messaging Engine.</span></span>  
  
3. <span data-ttu-id="0ecb8-114">メッセージング エンジンは、場所データが XML に変換、メッセージの送信者の認証、メッセージを復号化、および XML の検証、受信パイプラインにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="0ecb8-114">The Messaging Engine sends the message to the receive pipeline where the data is transformed into XML, the message sender is authenticated, the message is decrypted, and the XML is validated.</span></span>  
  
4. <span data-ttu-id="0ecb8-115">メッセージング エンジンは、メッセージ ボックスに、メッセージを発行します。</span><span class="sxs-lookup"><span data-stu-id="0ecb8-115">The Messaging Engine publishes the message to the MessageBox.</span></span> <span data-ttu-id="0ecb8-116">メッセージ ボックスは、処理するメッセージを格納している Microsoft SQL Server テーブルです。</span><span class="sxs-lookup"><span data-stu-id="0ecb8-116">The MessageBox is a Microsoft SQL Server table containing messages to be processed.</span></span> <span data-ttu-id="0ecb8-117">両方のオーケストレーションおよび送信ポートは、メッセージ ボックス データベースにサブスクライブできます。</span><span class="sxs-lookup"><span data-stu-id="0ecb8-117">Both orchestrations and send ports can subscribe to the MessageBox.</span></span>  
  
5. <span data-ttu-id="0ecb8-118">メッセージング エンジンは、オーケストレーションまたは送信ポートのサブスクライバー、サブスクライバーのフィルターで一連の仕様に一致するメッセージ コンテキスト プロパティに基づいて、メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="0ecb8-118">The Messaging Engine sends the message to either an orchestration or a send port subscriber based upon the message context properties matching the specifications set in the filter on the subscriber.</span></span>  
  
6. <span data-ttu-id="0ecb8-119">オーケストレーションがサブスクライバーの場合は、メッセージを処理して、送信ポートを使用して送信されます。</span><span class="sxs-lookup"><span data-stu-id="0ecb8-119">If an orchestration is the subscriber, it processes the message and sends it out using a send port.</span></span> <span data-ttu-id="0ecb8-120">送信ポートが、または唯一のサブスクライバーと、メッセージが、送信アダプターの送信パイプラインを通じて、ネットワーク経由で送信される前に渡します。</span><span class="sxs-lookup"><span data-stu-id="0ecb8-120">After the send port has it, or is the only subscriber, the message passes through the send pipeline into a send adapter before being transmitted over the wire.</span></span>  
  
   <span data-ttu-id="0ecb8-121">アダプター フレームワーク</span><span class="sxs-lookup"><span data-stu-id="0ecb8-121">The Adapter Framework</span></span>  
  
   <span data-ttu-id="0ecb8-122">![アダプター フレームワーク](../core/media/ebiz-sdk-adpttoday.gif "ebiz_sdk_adpttoday")</span><span class="sxs-lookup"><span data-stu-id="0ecb8-122">![The adapter framework](../core/media/ebiz-sdk-adpttoday.gif "ebiz_sdk_adpttoday")</span></span>  
  
## <a name="receive-adapters"></a><span data-ttu-id="0ecb8-123">受信アダプター</span><span class="sxs-lookup"><span data-stu-id="0ecb8-123">Receive Adapters</span></span>  
 <span data-ttu-id="0ecb8-124">受信アダプターはメッセージの本文に、ネットワーク/データ ソースのストリームを添付して新しい BizTalk Server メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="0ecb8-124">Receive adapters are responsible for creating a new BizTalk Server message by attaching the network/data source stream to the message body.</span></span> <span data-ttu-id="0ecb8-125">また、どのデータを受信しましたが、そのメッセージをメッセージング エンジンに送信エンドポイントに関連するメタデータも追加します。</span><span class="sxs-lookup"><span data-stu-id="0ecb8-125">It also adds any metadata pertinent to the endpoint over which the data was received, then submits that message to the Messaging Engine.</span></span>  
  
 <span data-ttu-id="0ecb8-126">アダプターは、受信エンドポイントからデータを削除または BizTalk Server にデータが受け入れられたことを示すクライアントに適切な受信確認メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="0ecb8-126">The adapter deletes the data from the receive endpoint or sends the appropriate acknowledgement message to the client indicating that the data has been accepted into BizTalk Server.</span></span>  
  
## <a name="send-adapters"></a><span data-ttu-id="0ecb8-127">送信アダプター</span><span class="sxs-lookup"><span data-stu-id="0ecb8-127">Send Adapters</span></span>  
 <span data-ttu-id="0ecb8-128">送信アダプターは BizTalk メッセージをその特定のトランスポート プロトコルを使用して、指定されたエンドポイントに送信します。</span><span class="sxs-lookup"><span data-stu-id="0ecb8-128">Send adapters are responsible for sending a BizTalk message to the specified endpoint using its specific transport protocol.</span></span>  
  
 <span data-ttu-id="0ecb8-129">アダプターの詳細については、アダプター、およびカスタム アダプターの作成の構造を参照してください[カスタム アダプターの開発](../core/developing-custom-adapters.md)します。</span><span class="sxs-lookup"><span data-stu-id="0ecb8-129">For more information about adapters, the structure of an adapter, and writing custom adapters, see [Developing Custom Adapters](../core/developing-custom-adapters.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ecb8-130">参照</span><span class="sxs-lookup"><span data-stu-id="0ecb8-130">See Also</span></span>  
 [<span data-ttu-id="0ecb8-131">アイテム</span><span class="sxs-lookup"><span data-stu-id="0ecb8-131">Artifacts</span></span>](../core/artifacts.md)