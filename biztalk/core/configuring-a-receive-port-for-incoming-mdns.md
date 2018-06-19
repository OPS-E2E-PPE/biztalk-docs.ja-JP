---
title: 構成、着信 Mdn の受信ポート |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d156beae-e145-48de-9f02-37457073ef97
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8585ae946e15d2677e225d42f6c123d5dd5e8e49
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968312"
---
# <a name="configuring-a-receive-port-for-incoming-mdns"></a><span data-ttu-id="f5908-102">受信 MDN の受信ポートの構成</span><span class="sxs-lookup"><span data-stu-id="f5908-102">Configuring a Receive Port for Incoming MDNs</span></span>
<span data-ttu-id="f5908-103">AS2 MDN を受信するには、メッセージを受信してパーティに応答を返すための一方向の HTTP 受信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="f5908-103">To receive an AS2 MDN, create a one-way HTTP receive port to receive the message and return a response back to the party.</span></span>  
  
 <span data-ttu-id="f5908-104">AS2 メッセージの受信に使用する双方向の要求 - 応答の受信ポートは、MDN メッセージの受信には使用できません。</span><span class="sxs-lookup"><span data-stu-id="f5908-104">A two-way request-response receive port that is used to receive AS2 messages should not be used to receive MDN messages.</span></span> <span data-ttu-id="f5908-105">MDN に要求 - 応答受信ポートを使用すると、受信 MDN に応答して 200OK メッセージが返されなくなるため、MDN 送信の不要な再試行が行われます。</span><span class="sxs-lookup"><span data-stu-id="f5908-105">Using a request-response receive port for an MDN would prevent a 200OK message from being returned in response to the incoming MDN, thereby causing unnecessary retries of the MDN transmission.</span></span>  
  
 <span data-ttu-id="f5908-106">受信 MDN の処理には、AS2Receive と AS2EdiReceive のいずれかのパイプラインを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f5908-106">You can use either the AS2Receive or the AS2EdiReceive pipeline to process a received MDN.</span></span> <span data-ttu-id="f5908-107">ただし、AS2EdiReceive を使用する場合することはできませんに MDN をルーティング、メッセージ ボックス データベースを設定して、**メッセージ ボックスに受信 MDN をルーティング/配信用処理**プロパティを**受信確認**ページ一方向アグリーメント タブです。この操作を実行しようとすると、MDN を処理できない EDI デコーダーに対して MDN が渡されるため、EDI エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="f5908-107">However, if you use AS2EdiReceive, you cannot route the MDN into the MessageBox by setting the **Process inbound MDN into MessageBox for routing/delivery options** property on the **Acknowledgements** page of the one-way agreement tab. Trying to do so will result in an EDI error because the MSN will be passed to the EDI Decoder, which cannot process an MDN.</span></span> <span data-ttu-id="f5908-108">MDN がメッセージ ボックスに送信されないと、AS2 デコーダーは MDN を利用 (消費) するため、MDN は EDI デコーダーに渡されません。</span><span class="sxs-lookup"><span data-stu-id="f5908-108">If the MDN is not sent to the MessageBox, the AS2Decoder will consume the MDN, so it will not be passed to the EDI Decoder.</span></span>  
  
 <span data-ttu-id="f5908-109">次の構成を使用して受信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="f5908-109">Create the receive port with the following configuration:</span></span>  
  
|<span data-ttu-id="f5908-110">場所</span><span class="sxs-lookup"><span data-stu-id="f5908-110">Location</span></span>|<span data-ttu-id="f5908-111">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f5908-111">Property</span></span>|<span data-ttu-id="f5908-112">設定</span><span class="sxs-lookup"><span data-stu-id="f5908-112">Setting</span></span>|  
|--------------|--------------|-------------|  
|<span data-ttu-id="f5908-113">**受信ポートのプロパティ: 全般**</span><span class="sxs-lookup"><span data-stu-id="f5908-113">**Receive Port Properties: General**</span></span>|<span data-ttu-id="f5908-114">[ポートの種類]</span><span class="sxs-lookup"><span data-stu-id="f5908-114">Port type</span></span>|<span data-ttu-id="f5908-115">一方向</span><span class="sxs-lookup"><span data-stu-id="f5908-115">One-Way</span></span>|  
|<span data-ttu-id="f5908-116">**受信場所のプロパティ: 全般**</span><span class="sxs-lookup"><span data-stu-id="f5908-116">**Receive Location Properties: General**</span></span>|<span data-ttu-id="f5908-117">トランスポートの種類</span><span class="sxs-lookup"><span data-stu-id="f5908-117">Transport Type</span></span>|<span data-ttu-id="f5908-118">HTTP</span><span class="sxs-lookup"><span data-stu-id="f5908-118">HTTP</span></span><br /><br /> <span data-ttu-id="f5908-119">**注**mdn の場合、される EDIINT/AS2 でエンコードされたメッセージを転送するため、HTTP アダプタのみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f5908-119">**Note** Only the HTTP adapter can be used for transporting MDNs, which are EDIINT/AS2-encoded messages.</span></span> <span data-ttu-id="f5908-120">このトランスポートは、HTTP アダプタ以外のアダプタでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="f5908-120">This transport will not work with an adapter other than the HTTP adapter.</span></span>|  
|<span data-ttu-id="f5908-121">**受信場所のプロパティ: 全般**</span><span class="sxs-lookup"><span data-stu-id="f5908-121">**Receive Location Properties: General**</span></span>|<span data-ttu-id="f5908-122">[受信ハンドラー]</span><span class="sxs-lookup"><span data-stu-id="f5908-122">Receive handler</span></span>|<span data-ttu-id="f5908-123">BizTalkServerIsolatedHost</span><span class="sxs-lookup"><span data-stu-id="f5908-123">BizTalkServerIsolatedHost</span></span>|  
|<span data-ttu-id="f5908-124">**受信場所のプロパティ: 全般**</span><span class="sxs-lookup"><span data-stu-id="f5908-124">**Receive Location Properties: General**</span></span>|<span data-ttu-id="f5908-125">受信パイプライン。</span><span class="sxs-lookup"><span data-stu-id="f5908-125">Receive pipeline</span></span>|<span data-ttu-id="f5908-126">AS2Receive または AS2EdiReceive</span><span class="sxs-lookup"><span data-stu-id="f5908-126">AS2Receive or AS2EdiReceive</span></span>|  
|<span data-ttu-id="f5908-127">**HTTP トランスポートのプロパティ**</span><span class="sxs-lookup"><span data-stu-id="f5908-127">**HTTP Transport Properties**</span></span>|<span data-ttu-id="f5908-128">仮想ディレクトリと ISAPI 拡張</span><span class="sxs-lookup"><span data-stu-id="f5908-128">Virtual directory plus ISAPI extension</span></span>|<span data-ttu-id="f5908-129">/\<仮想ディレクトリの名前\>>/btshttpreceive.dll</span><span class="sxs-lookup"><span data-stu-id="f5908-129">/\<name of virtual directory\>/BTSHTTPReceive.dll</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f5908-130">参照</span><span class="sxs-lookup"><span data-stu-id="f5908-130">See Also</span></span>  
 [<span data-ttu-id="f5908-131">AS2 ソリューションのポートの構成</span><span class="sxs-lookup"><span data-stu-id="f5908-131">Configuring Ports for an AS2 Solution</span></span>](../core/configuring-ports-for-an-as2-solution.md)