---
title: BizTalk Server のメッセージ コンテキスト プロパティ (送信ハンドラー) |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a065ba89-9fdb-47dc-9021-fb95cf347cdc
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0504e13115229f1325938e8ca48acc17fa5bc1d
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24013841"
---
# <a name="biztalk-server-message-context-properties-send-handlers"></a><span data-ttu-id="f43ad-102">BizTalk Server のメッセージ コンテキスト プロパティ (送信ハンドラー)</span><span class="sxs-lookup"><span data-stu-id="f43ad-102">BizTalk Server Message Context Properties (Send Handlers)</span></span>
<span data-ttu-id="f43ad-103">BizTalk Server オーケストレーションの実行時には、メッセージ ペイロードに加えて、メッセージに含まれる補足情報にもアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f43ad-103">In addition to the message payload, the supplementary information that a message contains must be accessible from the BizTalk Server orchestration at run time.</span></span>  
  
## <a name="tibco-rv-message-information-promoted-as-message-context-properties"></a><span data-ttu-id="f43ad-104">メッセージ コンテキストのプロパティとして昇格される TIBCO RV メッセージ情報</span><span class="sxs-lookup"><span data-stu-id="f43ad-104">TIBCO RV Message Information Promoted as Message Context Properties</span></span>  
  
|<span data-ttu-id="f43ad-105">データ ID</span><span class="sxs-lookup"><span data-stu-id="f43ad-105">Data Identification</span></span>|<span data-ttu-id="f43ad-106">型</span><span class="sxs-lookup"><span data-stu-id="f43ad-106">Type</span></span>|<span data-ttu-id="f43ad-107">ルーティング可能</span><span class="sxs-lookup"><span data-stu-id="f43ad-107">Routable</span></span>|<span data-ttu-id="f43ad-108">送信場所</span><span class="sxs-lookup"><span data-stu-id="f43ad-108">Send Location</span></span>|  
|-------------------------|----------|--------------|-------------------|  
|<span data-ttu-id="f43ad-109">送信サブジェクト</span><span class="sxs-lookup"><span data-stu-id="f43ad-109">Send Subject</span></span>|<span data-ttu-id="f43ad-110">string</span><span class="sxs-lookup"><span data-stu-id="f43ad-110">string</span></span>|<span data-ttu-id="f43ad-111">はい</span><span class="sxs-lookup"><span data-stu-id="f43ad-111">Yes</span></span>|<span data-ttu-id="f43ad-112">オーケストレーションにより TIBCO Rendezvous 送信サブジェクトが指定されます。</span><span class="sxs-lookup"><span data-stu-id="f43ad-112">Orchestration specifies the TIBCO Rendezvous send subject.</span></span> <span data-ttu-id="f43ad-113">既定値は Null です。</span><span class="sxs-lookup"><span data-stu-id="f43ad-113">Default value is Null.</span></span> <span data-ttu-id="f43ad-114">既定のサブジェクトがポート構成で指定されていない場合は必須です。</span><span class="sxs-lookup"><span data-stu-id="f43ad-114">Mandatory unless a default subject is specified in the port configuration.</span></span>|  
|<span data-ttu-id="f43ad-115">返信サブジェクト</span><span class="sxs-lookup"><span data-stu-id="f43ad-115">Reply Subject</span></span>|<span data-ttu-id="f43ad-116">string</span><span class="sxs-lookup"><span data-stu-id="f43ad-116">string</span></span>|<span data-ttu-id="f43ad-117">はい</span><span class="sxs-lookup"><span data-stu-id="f43ad-117">Yes</span></span>|<span data-ttu-id="f43ad-118">必要に応じて、オーケストレーションにより返信メッセージのサブジェクトが指定されます。</span><span class="sxs-lookup"><span data-stu-id="f43ad-118">Orchestration provides a subject for reply messages, when pertinent.</span></span> <span data-ttu-id="f43ad-119">既定値は Null です。</span><span class="sxs-lookup"><span data-stu-id="f43ad-119">Default value is Null.</span></span>|  
  
## <a name="getting-a-tibco-reply"></a><span data-ttu-id="f43ad-120">TIBCO の返信の取得</span><span class="sxs-lookup"><span data-stu-id="f43ad-120">Getting a TIBCO Reply</span></span>  
 <span data-ttu-id="f43ad-121">**質問:** TIBCO Rendezvous の読み取りおよび応答の送信サブジェクトとして使用できるように、オーケストレーション内の返信サブジェクトを操作については、BizTalk アダプターにはどのしますか?</span><span class="sxs-lookup"><span data-stu-id="f43ad-121">**Question:** How does BizTalk Adapter for TIBCO Rendezvous read and manipulate the reply subject inside an orchestration so that you can use it as the send subject for the response?</span></span> <span data-ttu-id="f43ad-122">BizTalk Adapter for TIBCO Rendezvous では Rendezvous からの受信メッセージのメッセージ コンテキストにどのようにアクセスしますか。</span><span class="sxs-lookup"><span data-stu-id="f43ad-122">How does the adapter get to the message context of an incoming message from Rendezvous?</span></span>  
  
 <span data-ttu-id="f43ad-123">**回答:** 返信サブジェクトが、受信メッセージのコンテキストで値が入力され、オーケストレーションで読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="f43ad-123">**Answer:** The reply subject is populated in the context of the incoming message, and the orchestration can read it.</span></span> <span data-ttu-id="f43ad-124">最終的にオーケストレーションで返信を作成する場合は、その値を使用して返信メッセージの送信サブジェクトを設定できます。</span><span class="sxs-lookup"><span data-stu-id="f43ad-124">If the orchestration ultimately produces a reply, it can use that value to set the send subject of the reply message.</span></span>  
  
1.  <span data-ttu-id="f43ad-125">BizTalk Server プロジェクトで、<install_directory>\TibcoRV\bin\Microsoft.BizTalk.Adapters.TibRV.Properties.dll への参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="f43ad-125">In a BizTalk Server project, add a reference to <install_directory>\TibcoRV\bin\Microsoft.BizTalk.Adapters.TibRV.Properties.dll.</span></span>  
  
2.  <span data-ttu-id="f43ad-126">オーケストレーション (受信 Rendezvous メッセージを渡す受信図形と、返信を送信する送信図形の間の場所) 内で、作成した返信に次の例のような処理を実行するメッセージの構築/割り当て図形 (または式図形) を追加します。</span><span class="sxs-lookup"><span data-stu-id="f43ad-126">In the orchestration (somewhere between the Receive shape that is handed the incoming Rendezvous message and the Send shape that is sending the reply), add a message construction/assignment shape (or an expression shape) to do something like the following example to the reply you constructed:</span></span>  
  
    ```  
    OutgoingMsg(Rendezvous.SendSubject) = IncomingMsg  
    (Rendezvous.ReplySubject);  
    ```  
## <a name="management-assembly"></a><span data-ttu-id="f43ad-127">アセンブリの管理</span><span class="sxs-lookup"><span data-stu-id="f43ad-127">Management assembly</span></span>
<span data-ttu-id="f43ad-128">TIBCO Rendezvous はメタデータ リポジトリを備えておらず、Microsoft BizTalk Adapter for TIBCO Rendezvous 管理アセンブリは参照機能またはスキーマ生成機能を備えていません。</span><span class="sxs-lookup"><span data-stu-id="f43ad-128">TIBCO Rendezvous does not provide metadata repositories, and Microsoft BizTalk Adapter for TIBCO Rendezvous management assembly does not provide browsing capabilities or schema generation.</span></span> <span data-ttu-id="f43ad-129">したがって、ユーザーがスキーマを BizTalk Server に提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f43ad-129">Therefore, you must provide a schema to BizTalk Server.</span></span> <span data-ttu-id="f43ad-130">詳細については、次を参照してください。[インストール、スキーマ、および制限事項](../core/installing-biztalk-adapter-for-tibco-rendezvous.md)です。</span><span class="sxs-lookup"><span data-stu-id="f43ad-130">For more information, see [Install, schemas, & limitations](../core/installing-biztalk-adapter-for-tibco-rendezvous.md).</span></span>
  
 <span data-ttu-id="f43ad-131">BizTalk Adapter for TIBCO Rendezvous には定義済みの型のスキーマが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f43ad-131">BizTalk Adapter for TIBCO Rendezvous includes a schema with predefined types.</span></span> <span data-ttu-id="f43ad-132">アダプターは、一部の特定のデータ型 (配列) のメッセージを生成するときに、これらの型を使用します。</span><span class="sxs-lookup"><span data-stu-id="f43ad-132">The adapter uses these types when generating messages for some specific data types (arrays).</span></span>

  
## <a name="see-also"></a><span data-ttu-id="f43ad-133">参照</span><span class="sxs-lookup"><span data-stu-id="f43ad-133">See Also</span></span>  
 <span data-ttu-id="f43ad-134">[TIBCO Rendezvous での送信ハンドラーのデータ型マッピング](../core/data-type-mapping-for-send-handlers-in-tibco-rendezvous.md) </span><span class="sxs-lookup"><span data-stu-id="f43ad-134">[Data Type Mapping for Send Handlers in TIBCO Rendezvous](../core/data-type-mapping-for-send-handlers-in-tibco-rendezvous.md) </span></span>  
 [<span data-ttu-id="f43ad-135">TIBCO Rendezvous 送信ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="f43ad-135">Creating TIBCO Rendezvous Send Handlers</span></span>](../core/creating-tibco-rendezvous-send-handlers.md)