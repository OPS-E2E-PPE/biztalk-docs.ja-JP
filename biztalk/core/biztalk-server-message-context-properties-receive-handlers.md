---
title: TIBCO Rendezvous のメッセージ コンテキスト プロパティが表示される |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7f47e2a0-6ac8-404a-bc0a-c7739911af74
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e330926c6f362ea5a84ad7b4b9291a5f2f310eee
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528324"
---
# <a name="biztalk-server-message-context-properties-receive-handlers"></a><span data-ttu-id="ee486-102">BizTalk Server メッセージ コンテキストのプロパティ (受信ハンドラー)</span><span class="sxs-lookup"><span data-stu-id="ee486-102">BizTalk Server Message Context Properties (Receive Handlers)</span></span>
<span data-ttu-id="ee486-103">メッセージ ペイロードに加えて、メッセージを構成する補足情報には、実行時に BizTalk Server オーケストレーションからアクセスできなければなりません。</span><span class="sxs-lookup"><span data-stu-id="ee486-103">In addition to the message payload, the supplementary information that composes a message must be accessible from a BizTalk Server orchestration at run time.</span></span>  
  
## <a name="tibco-rv-message-information-promoted-as-message-context-properties"></a><span data-ttu-id="ee486-104">メッセージ コンテキストのプロパティとして昇格される TIBCO RV メッセージ情報</span><span class="sxs-lookup"><span data-stu-id="ee486-104">TIBCO RV Message Information Promoted as Message Context Properties</span></span>  
 <span data-ttu-id="ee486-105">次の表は、この補足情報。</span><span class="sxs-lookup"><span data-stu-id="ee486-105">The following table lists this supplementary information:</span></span>  
  
|<span data-ttu-id="ee486-106">データ ID</span><span class="sxs-lookup"><span data-stu-id="ee486-106">Data Identification</span></span>|<span data-ttu-id="ee486-107">型</span><span class="sxs-lookup"><span data-stu-id="ee486-107">Type</span></span>|<span data-ttu-id="ee486-108">ルーティング可能</span><span class="sxs-lookup"><span data-stu-id="ee486-108">Routable</span></span>|<span data-ttu-id="ee486-109">受信場所</span><span class="sxs-lookup"><span data-stu-id="ee486-109">Receive Location</span></span>|  
|-------------------------|----------|--------------|----------------------|  
|<span data-ttu-id="ee486-110">送信サブジェクト [null]</span><span class="sxs-lookup"><span data-stu-id="ee486-110">Send Subject [null]</span></span>|<span data-ttu-id="ee486-111">string</span><span class="sxs-lookup"><span data-stu-id="ee486-111">string</span></span>|<span data-ttu-id="ee486-112">はい</span><span class="sxs-lookup"><span data-stu-id="ee486-112">Yes</span></span>|<span data-ttu-id="ee486-113">オーケストレーションにこのメッセージが送信されて、件名に指示します。</span><span class="sxs-lookup"><span data-stu-id="ee486-113">Tells orchestration which subject this message was sent to.</span></span>|  
|<span data-ttu-id="ee486-114">返信サブジェクト [null]</span><span class="sxs-lookup"><span data-stu-id="ee486-114">Reply Subject [null]</span></span>|<span data-ttu-id="ee486-115">string</span><span class="sxs-lookup"><span data-stu-id="ee486-115">string</span></span>|<span data-ttu-id="ee486-116">はい</span><span class="sxs-lookup"><span data-stu-id="ee486-116">Yes</span></span>|<span data-ttu-id="ee486-117">求められた場合に、送信者が送信される応答を期待する場所をオーケストレーションに指示します。</span><span class="sxs-lookup"><span data-stu-id="ee486-117">Tells orchestration where the sender expects the reply to be sent, if one is expected.</span></span>|  
|<span data-ttu-id="ee486-118">[読み取り専用] フィールドの数</span><span class="sxs-lookup"><span data-stu-id="ee486-118">Field Count [read only]</span></span>|<span data-ttu-id="ee486-119">unsigned int</span><span class="sxs-lookup"><span data-stu-id="ee486-119">unsigned int</span></span>|<span data-ttu-id="ee486-120">いいえ</span><span class="sxs-lookup"><span data-stu-id="ee486-120">No</span></span>|<span data-ttu-id="ee486-121">上位レベル メッセージ内のフィールドの数。</span><span class="sxs-lookup"><span data-stu-id="ee486-121">Number of fields in upper level message.</span></span> <span data-ttu-id="ee486-122">TIBCO rv さん。 によって指定されるプロパティ</span><span class="sxs-lookup"><span data-stu-id="ee486-122">A property provided by TIBCO RV.</span></span>|  
|<span data-ttu-id="ee486-123">CM 送信者名 [読み取り専用]</span><span class="sxs-lookup"><span data-stu-id="ee486-123">CM Sender Name [read-only]</span></span>|<span data-ttu-id="ee486-124">string</span><span class="sxs-lookup"><span data-stu-id="ee486-124">string</span></span>|<span data-ttu-id="ee486-125">はい</span><span class="sxs-lookup"><span data-stu-id="ee486-125">Yes</span></span>|<span data-ttu-id="ee486-126">送信者の CM 送信者名です。</span><span class="sxs-lookup"><span data-stu-id="ee486-126">CM Correspondent name of the sender.</span></span>|  
|<span data-ttu-id="ee486-127">CM シーケンス番号 [読み取り専用]</span><span class="sxs-lookup"><span data-stu-id="ee486-127">CM Sequence Number [read only]</span></span>|<span data-ttu-id="ee486-128">long</span><span class="sxs-lookup"><span data-stu-id="ee486-128">long</span></span>|<span data-ttu-id="ee486-129">いいえ</span><span class="sxs-lookup"><span data-stu-id="ee486-129">No</span></span>|<span data-ttu-id="ee486-130">送信元の TIBCO トランスポート オブジェクトによって割り当てられたシーケンス番号。</span><span class="sxs-lookup"><span data-stu-id="ee486-130">Sequence number assigned by the sending TIBCO transport object.</span></span>|  
|<span data-ttu-id="ee486-131">CM タイム リミット [読み取り専用]</span><span class="sxs-lookup"><span data-stu-id="ee486-131">CM Time Limit [read-only]</span></span>|<span data-ttu-id="ee486-132">double</span><span class="sxs-lookup"><span data-stu-id="ee486-132">double</span></span>|<span data-ttu-id="ee486-133">いいえ</span><span class="sxs-lookup"><span data-stu-id="ee486-133">No</span></span>|<span data-ttu-id="ee486-134">送信元のプログラムがメッセージの配信の認定を受けるには、その CM トランスポートを不要になった期待される時間制限。</span><span class="sxs-lookup"><span data-stu-id="ee486-134">A time limit, after which the sending program no longer expects its CM transport to certify delivery of the message.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ee486-135">参照</span><span class="sxs-lookup"><span data-stu-id="ee486-135">See Also</span></span>  
 <span data-ttu-id="ee486-136">[TIBCO Rendezvous でのメッセージ マッピング](../core/message-mapping-in-tibco-rendezvous.md) </span><span class="sxs-lookup"><span data-stu-id="ee486-136">[Message Mapping in TIBCO Rendezvous](../core/message-mapping-in-tibco-rendezvous.md) </span></span>  
 [<span data-ttu-id="ee486-137">TIBCO Rendezvous 受信ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="ee486-137">Creating TIBCO Rendezvous Receive Handlers</span></span>](../core/creating-tibco-rendezvous-receive-handlers.md)