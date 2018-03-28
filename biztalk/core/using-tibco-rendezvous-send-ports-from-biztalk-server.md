---
title: BizTalk Server から TIBCO Rendezvous 送信ポートの使用 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 34e3edf7-cfc5-4c89-8069-63e8784bc9f9
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 950c4c367fe053195ba14029405f5015381fc6be
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="using-tibco-rendezvous-send-ports"></a><span data-ttu-id="f974c-102">TIBCO Rendezvous の送信ポートの使用</span><span class="sxs-lookup"><span data-stu-id="f974c-102">Using TIBCO Rendezvous Send Ports</span></span>
<span data-ttu-id="f974c-103">送信ポートはあらゆる種類のメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="f974c-103">A transmit port can send any kind of message.</span></span> <span data-ttu-id="f974c-104">BizTalk Server で Microsoft BizTalk Adapter for TIBCO Rendezvous を介してメッセージを送信する場合、アダプターはメッセージ コンテキストのプロパティ値に基づいてメッセージを生成するか、既定値を使用して、メッセージを指定されたサブジェクトに送信します。</span><span class="sxs-lookup"><span data-stu-id="f974c-104">When BizTalk Server sends a message through Microsoft BizTalk Adapter for TIBCO Rendezvous, the adapter generates the message based on message context properties values, or it uses the default and sends it to the specified subject.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f974c-105">TIBCO Rendezvous のドキュメントに従って、送信サブジェクト名ではワイルドカード文字はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f974c-105">According to the TIBCO Rendezvous documentation, wildcard characters are not supported in transmit subject names.</span></span>  
  
## <a name="message-handling"></a><span data-ttu-id="f974c-106">メッセージの処理</span><span class="sxs-lookup"><span data-stu-id="f974c-106">Message Handling</span></span>  
 <span data-ttu-id="f974c-107">アダプターは状態を維持し、それに従って BizTalk Server の受信メッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="f974c-107">The adapter maintains a state and handles incoming BizTalk Server messages accordingly.</span></span>  
  
-   <span data-ttu-id="f974c-108">トランスポートのエラーでメッセージを送信できない場合、BizTalk Server に対して後で再送信するように指示されます。</span><span class="sxs-lookup"><span data-stu-id="f974c-108">If a message cannot be sent because of transport failure, BizTalk Server is instructed to resubmit later.</span></span>  
  
-   <span data-ttu-id="f974c-109">アダプターがまだ初期化中であるためにメッセージを送信できない場合、BizTalk Server メッセージはキューに配置されます。</span><span class="sxs-lookup"><span data-stu-id="f974c-109">If a message cannot be sent because the adapter is still initializing, the BizTalk Server message is queued.</span></span> <span data-ttu-id="f974c-110">初期化に失敗した場合、BizTalk Server は後で再送信するように指示されます。</span><span class="sxs-lookup"><span data-stu-id="f974c-110">If initialization fails, BizTalk Server is instructed to resubmit later.</span></span>  
  
## <a name="message-generation"></a><span data-ttu-id="f974c-111">メッセージの生成</span><span class="sxs-lookup"><span data-stu-id="f974c-111">Message Generation</span></span>  
 <span data-ttu-id="f974c-112">送信アダプターを使用する場合、BizTalk Adapter for TIBCO Rendezvous はメッセージのターゲットの名前空間およびルート要素を無視します。</span><span class="sxs-lookup"><span data-stu-id="f974c-112">With the transmit adapter, BizTalk Adapter for TIBCO Rendezvous ignores the message target namespace and root element.</span></span> <span data-ttu-id="f974c-113">アダプターがメッセージを送信する場合、アダプターはペイロードをそのまま送信します。</span><span class="sxs-lookup"><span data-stu-id="f974c-113">If the adapter sends messages, it sends the payload as is.</span></span> <span data-ttu-id="f974c-114">アダプターが構造化 TIBCO Rendezvous メッセージを生成する場合、ルート要素の名前は無視されます (メッセージに名前はありません)。</span><span class="sxs-lookup"><span data-stu-id="f974c-114">If the adapter generates a structured TIBCO Rendezvous message, the name of the root element is ignored (a message does not have a name).</span></span> <span data-ttu-id="f974c-115">いずれの場合も、アダプターはコンテキスト プロパティを使用して、メッセージを公開するときに使用するサブジェクトを検索します。</span><span class="sxs-lookup"><span data-stu-id="f974c-115">In every case, the adapter uses a context property to find which subject to use when publishing the message.</span></span>  
  
 <span data-ttu-id="f974c-116">詳細については、次を参照してください。 [BizTalk Server のメッセージ コンテキスト プロパティ (送信ハンドラー)](../core/biztalk-server-message-context-properties-send-handlers.md)と[TIBCO Rendezvous の受信ハンドラーのデータ型マッピング](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md)です。</span><span class="sxs-lookup"><span data-stu-id="f974c-116">For more information, see [BizTalk Server Message Context Properties (Send Handlers)](../core/biztalk-server-message-context-properties-send-handlers.md) and [Data Type Mapping for Receive Handlers in TIBCO Rendezvous](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md).</span></span>  

## <a name="using-biztalk-to-send-messages"></a><span data-ttu-id="f974c-117">BizTalk を使用してメッセージを送信するには</span><span class="sxs-lookup"><span data-stu-id="f974c-117">Using BizTalk to Send Messages</span></span>
<span data-ttu-id="f974c-118">Microsoft BizTalk Adapter for TIBCO Rendezvous は、非同期 API (Transport.Send) を使用します。</span><span class="sxs-lookup"><span data-stu-id="f974c-118">Microsoft BizTalk Adapter for TIBCO Rendezvous uses the asynchronous API (Transport.Send).</span></span> <span data-ttu-id="f974c-119">メッセージ コンテキスト プロパティを使用して、このアダプターが送信するメッセージの種類を指定できます。</span><span class="sxs-lookup"><span data-stu-id="f974c-119">You can specify what kind of message the adapter sends using a message context property:</span></span>  
  
-   <span data-ttu-id="f974c-120">**構造化された**: アダプターには、BizTalk Server から受信した XML データに基づいて、TIBRVMSG_MSG 構造化されたメッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="f974c-120">**Structured**: The adapter generates a TIBRVMSG_MSG structured message, based on the XML data received from BizTalk Server.</span></span> <span data-ttu-id="f974c-121">(\*)</span><span class="sxs-lookup"><span data-stu-id="f974c-121">(\*)</span></span>  
  
 <span data-ttu-id="f974c-122">BizTalk Server が 127 文字を超える名前を持つフィールドのあるメッセージを送信した場合、BizTalk Adapter for TIBCO Rendezvous は、TIBCO Rendezvous の最大フィールド名サイズ (127 文字) に名前を切り捨てます。</span><span class="sxs-lookup"><span data-stu-id="f974c-122">If BizTalk Server sends a message with fields that have names longer than 127 characters, BizTalk Adapter for TIBCO Rendezvous truncates the names to the maximum field name size for TIBCO Rendezvous, which is 127.</span></span>  
  
 <span data-ttu-id="f974c-123">`reply subject name` プロパティが指定されている場合、このプロパティを使用して TIBCO Rendezvous メッセージの返信の件名が設定されます。</span><span class="sxs-lookup"><span data-stu-id="f974c-123">If a `reply subject name` property is provided, it is used to set the reply subject on the TIBCO Rendezvous message.</span></span> <span data-ttu-id="f974c-124">受信ポートが応答を待機して BizTalk Server に転送するように設定されているか、その他の TIBCO Rendezvous プログラムが応答を処理すると想定されています。</span><span class="sxs-lookup"><span data-stu-id="f974c-124">It is assumed that either a receive port is set to listen for the reply and forward it to BizTalk Server, or some other TIBCO Rendezvous program is taking care of the reply.</span></span>  
  
 <span data-ttu-id="f974c-125">トリプレット (サービス、デーモン、およびネットワーク) がトランスポートの構成を形成します。</span><span class="sxs-lookup"><span data-stu-id="f974c-125">The triplet (service, daemon, network) makes up the transport configuration.</span></span> <span data-ttu-id="f974c-126">トランスポートの構成が空白の場合 (既定)、メッセージは既定のトランスポート オブジェクトを介して送信されます。</span><span class="sxs-lookup"><span data-stu-id="f974c-126">An empty (default) transport configuration results in a message being sent through the default transport object.</span></span>  
  
 <span data-ttu-id="f974c-127">コード ページを指定しない場合、このアダプターは UTF-8 エンコーディング (コード ページ 65001) を使用します。</span><span class="sxs-lookup"><span data-stu-id="f974c-127">If the code page is left unspecified, the adapter uses UTF-8 encoding (code page 65001).</span></span> <span data-ttu-id="f974c-128">伝送側では、認定済みメッセージはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="f974c-128">Certified Messages are not supported on the transmitter side.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f974c-129">参照</span><span class="sxs-lookup"><span data-stu-id="f974c-129">See Also</span></span>  
 <span data-ttu-id="f974c-130">[送信ポートの作成](../core/creating-send-ports2.md) </span><span class="sxs-lookup"><span data-stu-id="f974c-130">[Creating Send Ports](../core/creating-send-ports2.md) </span></span>  
 [<span data-ttu-id="f974c-131">TIBCO Rendezvous 送信ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="f974c-131">Creating TIBCO Rendezvous Send Handlers</span></span>](../core/creating-tibco-rendezvous-send-handlers.md)