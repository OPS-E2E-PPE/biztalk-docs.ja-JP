---
title: 構成を受信 Mdn の受信ポート |Microsoft Docs
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
ms.openlocfilehash: b630555d5ec32ca9c1a3d48a8320f138a977284f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391388"
---
# <a name="configuring-a-receive-port-for-incoming-mdns"></a><span data-ttu-id="72fac-102">構成を受信 Mdn の受信ポート</span><span class="sxs-lookup"><span data-stu-id="72fac-102">Configuring a Receive Port for Incoming MDNs</span></span>
<span data-ttu-id="72fac-103">AS2 MDN を受信するには、作成、一方向 HTTP 受信ポート、メッセージを受信し、パーティへの応答を返します。</span><span class="sxs-lookup"><span data-stu-id="72fac-103">To receive an AS2 MDN, create a one-way HTTP receive port to receive the message and return a response back to the party.</span></span>  
  
 <span data-ttu-id="72fac-104">双方向の要求-応答の受信 MDN メッセージを受信するメッセージを使用しない必要があります AS2 の受信に使用されるポート。</span><span class="sxs-lookup"><span data-stu-id="72fac-104">A two-way request-response receive port that is used to receive AS2 messages should not be used to receive MDN messages.</span></span> <span data-ttu-id="72fac-105">受信ポート 200OK メッセージなるため、MDN 送信の不要な再試行を原因となり、受信 MDN への応答で返される MDN を要求-応答を使用します。</span><span class="sxs-lookup"><span data-stu-id="72fac-105">Using a request-response receive port for an MDN would prevent a 200OK message from being returned in response to the incoming MDN, thereby causing unnecessary retries of the MDN transmission.</span></span>  
  
 <span data-ttu-id="72fac-106">AS2Receive または AS2EdiReceive パイプラインのいずれかを使用して、受信した MDN を処理することができます。</span><span class="sxs-lookup"><span data-stu-id="72fac-106">You can use either the AS2Receive or the AS2EdiReceive pipeline to process a received MDN.</span></span> <span data-ttu-id="72fac-107">ただし、AS2EdiReceive を使用する場合ことはできません MDN をルーティングするメッセージ ボックスに設定して、 **MessageBox にルーティング/配信の受信 MDN を処理する**プロパティを**受信確認**ページ一方向アグリーメント タブ。操作を実行しようと、MSN が MDN を処理できない EDI デコーダーに渡されるために、EDI エラーが発生するがします。</span><span class="sxs-lookup"><span data-stu-id="72fac-107">However, if you use AS2EdiReceive, you cannot route the MDN into the MessageBox by setting the **Process inbound MDN into MessageBox for routing/delivery options** property on the **Acknowledgements** page of the one-way agreement tab. Trying to do so will result in an EDI error because the MSN will be passed to the EDI Decoder, which cannot process an MDN.</span></span> <span data-ttu-id="72fac-108">メッセージ ボックスに MDN が送信されない場合、AS2Decoder は EDI デコーダーに渡されませんので、MDN を消費します。</span><span class="sxs-lookup"><span data-stu-id="72fac-108">If the MDN is not sent to the MessageBox, the AS2Decoder will consume the MDN, so it will not be passed to the EDI Decoder.</span></span>  
  
 <span data-ttu-id="72fac-109">次の構成を使用して受信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="72fac-109">Create the receive port with the following configuration:</span></span>  
  
|<span data-ttu-id="72fac-110">場所</span><span class="sxs-lookup"><span data-stu-id="72fac-110">Location</span></span>|<span data-ttu-id="72fac-111">プロパティ</span><span class="sxs-lookup"><span data-stu-id="72fac-111">Property</span></span>|<span data-ttu-id="72fac-112">設定</span><span class="sxs-lookup"><span data-stu-id="72fac-112">Setting</span></span>|  
|--------------|--------------|-------------|  
|<span data-ttu-id="72fac-113">**受信ポートのプロパティ。[全般]**</span><span class="sxs-lookup"><span data-stu-id="72fac-113">**Receive Port Properties: General**</span></span>|<span data-ttu-id="72fac-114">[ポートの種類]</span><span class="sxs-lookup"><span data-stu-id="72fac-114">Port type</span></span>|<span data-ttu-id="72fac-115">一方向</span><span class="sxs-lookup"><span data-stu-id="72fac-115">One-Way</span></span>|  
|<span data-ttu-id="72fac-116">**受信場所のプロパティ。[全般]**</span><span class="sxs-lookup"><span data-stu-id="72fac-116">**Receive Location Properties: General**</span></span>|<span data-ttu-id="72fac-117">トランスポートの種類</span><span class="sxs-lookup"><span data-stu-id="72fac-117">Transport Type</span></span>|<span data-ttu-id="72fac-118">HTTP</span><span class="sxs-lookup"><span data-stu-id="72fac-118">HTTP</span></span><br /><br /> <span data-ttu-id="72fac-119">**注**EDIINT/AS2 でエンコードされたメッセージは、Mdn を転送するため、HTTP アダプタのみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="72fac-119">**Note** Only the HTTP adapter can be used for transporting MDNs, which are EDIINT/AS2-encoded messages.</span></span> <span data-ttu-id="72fac-120">このトランスポートは、HTTP アダプタ以外のアダプタでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="72fac-120">This transport will not work with an adapter other than the HTTP adapter.</span></span>|  
|<span data-ttu-id="72fac-121">**受信場所のプロパティ。[全般]**</span><span class="sxs-lookup"><span data-stu-id="72fac-121">**Receive Location Properties: General**</span></span>|<span data-ttu-id="72fac-122">[受信ハンドラー]</span><span class="sxs-lookup"><span data-stu-id="72fac-122">Receive handler</span></span>|<span data-ttu-id="72fac-123">BizTalkServerIsolatedHost</span><span class="sxs-lookup"><span data-stu-id="72fac-123">BizTalkServerIsolatedHost</span></span>|  
|<span data-ttu-id="72fac-124">**受信場所のプロパティ。[全般]**</span><span class="sxs-lookup"><span data-stu-id="72fac-124">**Receive Location Properties: General**</span></span>|<span data-ttu-id="72fac-125">受信パイプライン。</span><span class="sxs-lookup"><span data-stu-id="72fac-125">Receive pipeline</span></span>|<span data-ttu-id="72fac-126">AS2Receive または AS2EdiReceive</span><span class="sxs-lookup"><span data-stu-id="72fac-126">AS2Receive or AS2EdiReceive</span></span>|  
|<span data-ttu-id="72fac-127">**HTTP トランスポートのプロパティ**</span><span class="sxs-lookup"><span data-stu-id="72fac-127">**HTTP Transport Properties**</span></span>|<span data-ttu-id="72fac-128">仮想ディレクトリと ISAPI 拡張</span><span class="sxs-lookup"><span data-stu-id="72fac-128">Virtual directory plus ISAPI extension</span></span>|<span data-ttu-id="72fac-129">/\<仮想ディレクトリの名前\>>/btshttpreceive.dll</span><span class="sxs-lookup"><span data-stu-id="72fac-129">/\<name of virtual directory\>/BTSHTTPReceive.dll</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="72fac-130">参照</span><span class="sxs-lookup"><span data-stu-id="72fac-130">See Also</span></span>  
 [<span data-ttu-id="72fac-131">AS2 ソリューションのポートの構成</span><span class="sxs-lookup"><span data-stu-id="72fac-131">Configuring Ports for an AS2 Solution</span></span>](../core/configuring-ports-for-an-as2-solution.md)