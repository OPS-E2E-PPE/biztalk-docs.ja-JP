---
title: "BizTalk Server のメッセージ コンテキスト プロパティ (送信ハンドラー) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- message context properties, BizTalk Server
- reply subjects
- send handlers, BizTalk Server message context properties
- replies
ms.assetid: a065ba89-9fdb-47dc-9021-fb95cf347cdc
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c8e5ddb1feb02a015fdebd62d183d1b8442fe5e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="biztalk-server-message-context-properties-send-handlers"></a><span data-ttu-id="c76c8-102">BizTalk Server のメッセージ コンテキスト プロパティ (送信ハンドラー)</span><span class="sxs-lookup"><span data-stu-id="c76c8-102">BizTalk Server Message Context Properties (Send Handlers)</span></span>
<span data-ttu-id="c76c8-103">BizTalk Server オーケストレーションの実行時には、メッセージ ペイロードに加えて、メッセージに含まれる補足情報にもアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="c76c8-103">In addition to the message payload, the supplementary information that a message contains must be accessible from the BizTalk Server orchestration at run time.</span></span>  
  
## <a name="tibco-rv-message-information-promoted-as-message-context-properties"></a><span data-ttu-id="c76c8-104">メッセージ コンテキストのプロパティとして昇格される TIBCO RV メッセージ情報</span><span class="sxs-lookup"><span data-stu-id="c76c8-104">TIBCO RV Message Information Promoted as Message Context Properties</span></span>  
  
|<span data-ttu-id="c76c8-105">データ ID</span><span class="sxs-lookup"><span data-stu-id="c76c8-105">Data Identification</span></span>|<span data-ttu-id="c76c8-106">型</span><span class="sxs-lookup"><span data-stu-id="c76c8-106">Type</span></span>|<span data-ttu-id="c76c8-107">ルーティング可能</span><span class="sxs-lookup"><span data-stu-id="c76c8-107">Routable</span></span>|<span data-ttu-id="c76c8-108">送信場所</span><span class="sxs-lookup"><span data-stu-id="c76c8-108">Send Location</span></span>|  
|-------------------------|----------|--------------|-------------------|  
|<span data-ttu-id="c76c8-109">送信サブジェクト</span><span class="sxs-lookup"><span data-stu-id="c76c8-109">Send Subject</span></span>|<span data-ttu-id="c76c8-110">string</span><span class="sxs-lookup"><span data-stu-id="c76c8-110">string</span></span>|<span data-ttu-id="c76c8-111">はい</span><span class="sxs-lookup"><span data-stu-id="c76c8-111">Yes</span></span>|<span data-ttu-id="c76c8-112">オーケストレーションにより TIBCO Rendezvous 送信サブジェクトが指定されます。</span><span class="sxs-lookup"><span data-stu-id="c76c8-112">Orchestration specifies the TIBCO Rendezvous send subject.</span></span> <span data-ttu-id="c76c8-113">既定値は Null です。</span><span class="sxs-lookup"><span data-stu-id="c76c8-113">Default value is Null.</span></span> <span data-ttu-id="c76c8-114">既定のサブジェクトがポート構成で指定されていない場合は必須です。</span><span class="sxs-lookup"><span data-stu-id="c76c8-114">Mandatory unless a default subject is specified in the port configuration.</span></span>|  
|<span data-ttu-id="c76c8-115">返信サブジェクト</span><span class="sxs-lookup"><span data-stu-id="c76c8-115">Reply Subject</span></span>|<span data-ttu-id="c76c8-116">string</span><span class="sxs-lookup"><span data-stu-id="c76c8-116">string</span></span>|<span data-ttu-id="c76c8-117">はい</span><span class="sxs-lookup"><span data-stu-id="c76c8-117">Yes</span></span>|<span data-ttu-id="c76c8-118">必要に応じて、オーケストレーションにより返信メッセージのサブジェクトが指定されます。</span><span class="sxs-lookup"><span data-stu-id="c76c8-118">Orchestration provides a subject for reply messages, when pertinent.</span></span> <span data-ttu-id="c76c8-119">既定値は Null です。</span><span class="sxs-lookup"><span data-stu-id="c76c8-119">Default value is Null.</span></span>|  
  
## <a name="getting-a-tibco-reply"></a><span data-ttu-id="c76c8-120">TIBCO の返信の取得</span><span class="sxs-lookup"><span data-stu-id="c76c8-120">Getting a TIBCO Reply</span></span>  
 <span data-ttu-id="c76c8-121">**質問:** TIBCO Rendezvous の読み取りおよび応答の送信サブジェクトとして使用できるように、オーケストレーション内の返信サブジェクトを操作については、BizTalk アダプターにはどのしますか?</span><span class="sxs-lookup"><span data-stu-id="c76c8-121">**Question:** How does BizTalk Adapter for TIBCO Rendezvous read and manipulate the reply subject inside an orchestration so that you can use it as the send subject for the response?</span></span> <span data-ttu-id="c76c8-122">BizTalk Adapter for TIBCO Rendezvous では Rendezvous からの受信メッセージのメッセージ コンテキストにどのようにアクセスしますか。</span><span class="sxs-lookup"><span data-stu-id="c76c8-122">How does the adapter get to the message context of an incoming message from Rendezvous?</span></span>  
  
 <span data-ttu-id="c76c8-123">**回答:**返信サブジェクトが、受信メッセージのコンテキストで値が入力され、オーケストレーションで読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="c76c8-123">**Answer:** The reply subject is populated in the context of the incoming message, and the orchestration can read it.</span></span> <span data-ttu-id="c76c8-124">最終的にオーケストレーションで返信を作成する場合は、その値を使用して返信メッセージの送信サブジェクトを設定できます。</span><span class="sxs-lookup"><span data-stu-id="c76c8-124">If the orchestration ultimately produces a reply, it can use that value to set the send subject of the reply message.</span></span>  
  
1.  <span data-ttu-id="c76c8-125">BizTalk Server プロジェクトで、<install_directory>\TibcoRV\bin\Microsoft.BizTalk.Adapters.TibRV.Properties.dll への参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="c76c8-125">In a BizTalk Server project, add a reference to <install_directory>\TibcoRV\bin\Microsoft.BizTalk.Adapters.TibRV.Properties.dll.</span></span>  
  
2.  <span data-ttu-id="c76c8-126">オーケストレーション (受信 Rendezvous メッセージを渡す受信図形と、返信を送信する送信図形の間の場所) 内で、作成した返信に次の例のような処理を実行するメッセージの構築/割り当て図形 (または式図形) を追加します。</span><span class="sxs-lookup"><span data-stu-id="c76c8-126">In the orchestration (somewhere between the Receive shape that is handed the incoming Rendezvous message and the Send shape that is sending the reply), add a message construction/assignment shape (or an expression shape) to do something like the following example to the reply you constructed:</span></span>  
  
    ```  
    OutgoingMsg(Rendezvous.SendSubject) = IncomingMsg  
    (Rendezvous.ReplySubject);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="c76c8-127">参照</span><span class="sxs-lookup"><span data-stu-id="c76c8-127">See Also</span></span>  
 <span data-ttu-id="c76c8-128">[TIBCO Rendezvous での送信ハンドラーのデータ型マッピング](../core/data-type-mapping-for-send-handlers-in-tibco-rendezvous.md) </span><span class="sxs-lookup"><span data-stu-id="c76c8-128">[Data Type Mapping for Send Handlers in TIBCO Rendezvous](../core/data-type-mapping-for-send-handlers-in-tibco-rendezvous.md) </span></span>  
 [<span data-ttu-id="c76c8-129">TIBCO Rendezvous 送信ハンドラーを作成します。</span><span class="sxs-lookup"><span data-stu-id="c76c8-129">Creating TIBCO Rendezvous Send Handlers</span></span>](../core/creating-tibco-rendezvous-send-handlers.md)