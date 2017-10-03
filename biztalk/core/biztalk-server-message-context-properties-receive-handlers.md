---
title: "BizTalk Server のメッセージ コンテキスト プロパティが (受信ハンドラー) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- message context properties
- receive handlers, message context properties
ms.assetid: 7f47e2a0-6ac8-404a-bc0a-c7739911af74
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a60896a8e1cace909a160c1dc942e63e9258d85
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="biztalk-server-message-context-properties-receive-handlers"></a><span data-ttu-id="589bf-102">BizTalk Server のメッセージ コンテキスト プロパティが (受信ハンドラー)</span><span class="sxs-lookup"><span data-stu-id="589bf-102">BizTalk Server Message Context Properties (Receive Handlers)</span></span>
<span data-ttu-id="589bf-103">メッセージ ペイロードに加えて、メッセージを構成する補足情報に BizTalk Server オーケストレーションから実行時にアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="589bf-103">In addition to the message payload, the supplementary information that composes a message must be accessible from a BizTalk Server orchestration at run time.</span></span>  
  
## <a name="tibco-rv-message-information-promoted-as-message-context-properties"></a><span data-ttu-id="589bf-104">メッセージ コンテキストのプロパティとして昇格される TIBCO RV メッセージ情報</span><span class="sxs-lookup"><span data-stu-id="589bf-104">TIBCO RV Message Information Promoted as Message Context Properties</span></span>  
 <span data-ttu-id="589bf-105">次の表に、この補足情報を示します。</span><span class="sxs-lookup"><span data-stu-id="589bf-105">The following table lists this supplementary information:</span></span>  
  
|<span data-ttu-id="589bf-106">データ ID</span><span class="sxs-lookup"><span data-stu-id="589bf-106">Data Identification</span></span>|<span data-ttu-id="589bf-107">型</span><span class="sxs-lookup"><span data-stu-id="589bf-107">Type</span></span>|<span data-ttu-id="589bf-108">ルーティング可能</span><span class="sxs-lookup"><span data-stu-id="589bf-108">Routable</span></span>|<span data-ttu-id="589bf-109">受信場所</span><span class="sxs-lookup"><span data-stu-id="589bf-109">Receive Location</span></span>|  
|-------------------------|----------|--------------|----------------------|  
|<span data-ttu-id="589bf-110">送信サブジェクト [null]</span><span class="sxs-lookup"><span data-stu-id="589bf-110">Send Subject [null]</span></span>|<span data-ttu-id="589bf-111">string</span><span class="sxs-lookup"><span data-stu-id="589bf-111">string</span></span>|<span data-ttu-id="589bf-112">はい</span><span class="sxs-lookup"><span data-stu-id="589bf-112">Yes</span></span>|<span data-ttu-id="589bf-113">このメッセージの送信先サブジェクトをオーケストレーションに伝えます。</span><span class="sxs-lookup"><span data-stu-id="589bf-113">Tells orchestration which subject this message was sent to.</span></span>|  
|<span data-ttu-id="589bf-114">応答サブジェクト [null]</span><span class="sxs-lookup"><span data-stu-id="589bf-114">Reply Subject [null]</span></span>|<span data-ttu-id="589bf-115">string</span><span class="sxs-lookup"><span data-stu-id="589bf-115">string</span></span>|<span data-ttu-id="589bf-116">はい</span><span class="sxs-lookup"><span data-stu-id="589bf-116">Yes</span></span>|<span data-ttu-id="589bf-117">送信者が応答の送信先として期待する場所 (そのような場所が期待される場合) をオーケストレーションに伝えます。</span><span class="sxs-lookup"><span data-stu-id="589bf-117">Tells orchestration where the sender expects the reply to be sent, if one is expected.</span></span>|  
|<span data-ttu-id="589bf-118">フィールド数 [読み取り専用]</span><span class="sxs-lookup"><span data-stu-id="589bf-118">Field Count [read only]</span></span>|<span data-ttu-id="589bf-119">unsigned int</span><span class="sxs-lookup"><span data-stu-id="589bf-119">unsigned int</span></span>|<span data-ttu-id="589bf-120">不可</span><span class="sxs-lookup"><span data-stu-id="589bf-120">No</span></span>|<span data-ttu-id="589bf-121">上位レベル メッセージ内のフィールドの数。</span><span class="sxs-lookup"><span data-stu-id="589bf-121">Number of fields in upper level message.</span></span> <span data-ttu-id="589bf-122">TIBCO RV によって指定されるプロパティです。</span><span class="sxs-lookup"><span data-stu-id="589bf-122">A property provided by TIBCO RV.</span></span>|  
|<span data-ttu-id="589bf-123">CM 送信者名 [読み取り専用]</span><span class="sxs-lookup"><span data-stu-id="589bf-123">CM Sender Name [read-only]</span></span>|<span data-ttu-id="589bf-124">string</span><span class="sxs-lookup"><span data-stu-id="589bf-124">string</span></span>|<span data-ttu-id="589bf-125">はい</span><span class="sxs-lookup"><span data-stu-id="589bf-125">Yes</span></span>|<span data-ttu-id="589bf-126">送信者の CM 通信者名。</span><span class="sxs-lookup"><span data-stu-id="589bf-126">CM Correspondent name of the sender.</span></span>|  
|<span data-ttu-id="589bf-127">CM シーケンス番号 [読み取り専用]</span><span class="sxs-lookup"><span data-stu-id="589bf-127">CM Sequence Number [read only]</span></span>|<span data-ttu-id="589bf-128">long</span><span class="sxs-lookup"><span data-stu-id="589bf-128">long</span></span>|<span data-ttu-id="589bf-129">不可</span><span class="sxs-lookup"><span data-stu-id="589bf-129">No</span></span>|<span data-ttu-id="589bf-130">送信元の TIBCO トランスポート オブジェクトによって割り当てられたシーケンス番号。</span><span class="sxs-lookup"><span data-stu-id="589bf-130">Sequence number assigned by the sending TIBCO transport object.</span></span>|  
|<span data-ttu-id="589bf-131">CM タイム リミット [読み取り専用]</span><span class="sxs-lookup"><span data-stu-id="589bf-131">CM Time Limit [read-only]</span></span>|<span data-ttu-id="589bf-132">double</span><span class="sxs-lookup"><span data-stu-id="589bf-132">double</span></span>|<span data-ttu-id="589bf-133">不可</span><span class="sxs-lookup"><span data-stu-id="589bf-133">No</span></span>|<span data-ttu-id="589bf-134">送信元プログラムがその CM トランスポートによるメッセージ配信の認証を期待しなくなるまでのタイム リミット。</span><span class="sxs-lookup"><span data-stu-id="589bf-134">A time limit, after which the sending program no longer expects its CM transport to certify delivery of the message.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="589bf-135">参照</span><span class="sxs-lookup"><span data-stu-id="589bf-135">See Also</span></span>  
 <span data-ttu-id="589bf-136">[TIBCO Rendezvous のメッセージ マッピング](../core/message-mapping-in-tibco-rendezvous.md) </span><span class="sxs-lookup"><span data-stu-id="589bf-136">[Message Mapping in TIBCO Rendezvous](../core/message-mapping-in-tibco-rendezvous.md) </span></span>  
 [<span data-ttu-id="589bf-137">作成元の TIBCO Rendezvous 受信ハンドラー</span><span class="sxs-lookup"><span data-stu-id="589bf-137">Creating TIBCO Rendezvous Receive Handlers</span></span>](../core/creating-tibco-rendezvous-receive-handlers.md)