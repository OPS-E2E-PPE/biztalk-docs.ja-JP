---
title: "送信および受信 ASPX ページ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BTARN, ASPX pages
- ASPX pages, initiator
- HTTP adapters
- connections, HTTP adapters
- connections, single-action
- ASPX pages, responder
- single-action connections
- RNIFSend.aspx
- connections, asynchronous
- ASPX pages, about ASPX pages
- double-action connections
- connections, synchronous
- connections, double-action
- ASPX pages
- HTTP adapters, connections
- asynchronous connections
- RNIFReceive.aspx
- synchronous connections
ms.assetid: 21e52390-35d8-44b1-a5cd-1cd60cfe6e61
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0782c421dfe771cd024b5ce4df893e2aaa45721d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="send-and-receive-aspx-pages"></a><span data-ttu-id="4a3de-102">送信および受信 ASPX ページ</span><span class="sxs-lookup"><span data-stu-id="4a3de-102">Send and Receive ASPX Pages</span></span>
<span data-ttu-id="4a3de-103">[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] ASPX ページは、直接結ぶインターフェイス[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]とインターネットです。</span><span class="sxs-lookup"><span data-stu-id="4a3de-103">The [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] ASPX pages are the direct interfaces between [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] and the Internet.</span></span> <span data-ttu-id="4a3de-104">受信ページ (RNIFReceive.aspx) と送信ページ (RNIFSend.aspx) の 2 つの ASPX ページで構成されています。</span><span class="sxs-lookup"><span data-stu-id="4a3de-104">The two ASPX pages are the receive page (RNIFReceive.aspx) and the send page (RNIFSend.aspx).</span></span> <span data-ttu-id="4a3de-105">各 ASPX ページは、対応する [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] パイプラインを拡張したものです。</span><span class="sxs-lookup"><span data-stu-id="4a3de-105">Each ASPX page is an extension to the corresponding [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] pipeline.</span></span> <span data-ttu-id="4a3de-106">パイプラインは ASPX ページに対して、RNIF (RosettaNet Implementation Framework) ヘッダーの処理を要求します。</span><span class="sxs-lookup"><span data-stu-id="4a3de-106">The pipeline requires the ASPX page to handle RosettaNet Implementation Framework (RNIF) headers.</span></span> <span data-ttu-id="4a3de-107">ほとんどの HTTP 処理はパイプラインが実行しますが、RNIF ヘッダーの HTTP 処理は各 ASPX ページが実行します。</span><span class="sxs-lookup"><span data-stu-id="4a3de-107">The pipeline performs most of the HTTP processing; however, each ASPX page performs the HTTP processing of the RNIF headers.</span></span> <span data-ttu-id="4a3de-108">ASPX ページは、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] HTTP アダプタの機能を強化します。</span><span class="sxs-lookup"><span data-stu-id="4a3de-108">The pages augment the functionality in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] HTTP adapter.</span></span>  
  
 <span data-ttu-id="4a3de-109">各 ASPX ページは、ユーザー インターフェイスを持たない ASP[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] Web アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="4a3de-109">Each ASPX page is an ASP[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] Web application with no user interface.</span></span> <span data-ttu-id="4a3de-110">ASP[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] Web セキュリティを使用して、外部パーティとの安全な接続を確立します。</span><span class="sxs-lookup"><span data-stu-id="4a3de-110">They use ASP[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] Web security to ensure a secure connection with external parties.</span></span> <span data-ttu-id="4a3de-111">フォールト トレランス、スケーラビリティ、可用性の高いサービスを実装できるレイヤを備えています。</span><span class="sxs-lookup"><span data-stu-id="4a3de-111">They provide a layer in which you can implement fault tolerance, scalability, and highly available services.</span></span>  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="4a3de-112"> のセットアップ プログラムによって、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] の展開ごとに RNIFSend.aspx ページと RNIFReceive.aspx ページがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="4a3de-112"> setup installs an RNIFSend.aspx page and an RNIFReceive.aspx page on each deployment of [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)].</span></span> <span data-ttu-id="4a3de-113">開始側または応答側が取引先とメッセージを交換する場合、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] は ASPX ページを使用して、取引先の URL との間でメッセージの送受信を行います。</span><span class="sxs-lookup"><span data-stu-id="4a3de-113">When the initiator or responder exchanges messages with the trading partner, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] uses the ASPX pages to send messages to, or receive messages from, the partner URL.</span></span> <span data-ttu-id="4a3de-114">開始側と応答側の両方で [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] を使用する場合は、開始側の 2 つの ASPX ページが応答側の 2 つの ASPX ページとメッセージを交換します。</span><span class="sxs-lookup"><span data-stu-id="4a3de-114">If both the initiator and the responder use [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)], the two ASPX pages on the initiator exchange messages with the two ASPX pages on the responder.</span></span> <span data-ttu-id="4a3de-115">詳細については、下の「開始側と応答側の ASPX ページの相互作用」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a3de-115">For more information, see the "How Initiator and Responder ASPX Pages Interact" subsection below.</span></span>  
  
## <a name="send-aspx-page"></a><span data-ttu-id="4a3de-116">送信 ASPX ページ</span><span class="sxs-lookup"><span data-stu-id="4a3de-116">Send ASPX Page</span></span>  
 <span data-ttu-id="4a3de-117">RNIFSend.aspx ページは、BizTalk HTTP アダプターからメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="4a3de-117">The RNIFSend.aspx page receives a message from the BizTalk HTTP adapter.</span></span> <span data-ttu-id="4a3de-118">作成し、メッセージを RNIF ヘッダーを追加し、インターネット経由でパートナーにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="4a3de-118">It creates and adds RNIF headers to the message, and then sends the message to the partner over the Internet.</span></span> <span data-ttu-id="4a3de-119">HTTP アダプターは、次のコマンドを使用して RNIFSend.aspx を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4a3de-119">The HTTP adapter calls RNIFSend.aspx with the following command:</span></span>  
  
```  
http://localhost:<port number>/RNIFSend.aspx?<query string>  
```  
  
 <span data-ttu-id="4a3de-120">クエリ文字列には、以下に示すように、送信ページがメッセージをパートナーに送信するために必要なデータ、およびパートナーがメッセージを処理するために必要なデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4a3de-120">The query string includes the following data that the send page needs to send the message to the partner, and the data that the partner must have to process the message:</span></span>  
  
-   <span data-ttu-id="4a3de-121">取引先の URL: http://www。\<*アドレス*\>.com/RNIFReceive.aspx</span><span class="sxs-lookup"><span data-stu-id="4a3de-121">The trading-partner URL: http://www.\<*address*\>.com/RNIFReceive.aspx</span></span>  
  
-   <span data-ttu-id="4a3de-122">応答タイプ : 同期または非同期</span><span class="sxs-lookup"><span data-stu-id="4a3de-122">The response type: sync or async</span></span>  
  
-   <span data-ttu-id="4a3de-123">RNIF バージョン : 1.1 または 2.0</span><span class="sxs-lookup"><span data-stu-id="4a3de-123">The RNIF version: 1.1 or 2.0.</span></span>  
  
 <span data-ttu-id="4a3de-124">BizTalk HTTP アダプタは、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 送信パイプラインによって生成された MIME メッセージを開始側の RNIFSend.aspx ページに送信します。</span><span class="sxs-lookup"><span data-stu-id="4a3de-124">The BizTalk HTTP adapter sends a MIME message produced by the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] send pipeline to the initiator RNIFSend.aspx page.</span></span> <span data-ttu-id="4a3de-125">RNIFSend.aspx では、次のようにメッセージが処理されます。</span><span class="sxs-lookup"><span data-stu-id="4a3de-125">RNIFSend.aspx processes the message as follows:</span></span>  
  
1.  <span data-ttu-id="4a3de-126">送信ページがメッセージを検証します。</span><span class="sxs-lookup"><span data-stu-id="4a3de-126">The send page performs validation on the message.</span></span>  
  
2.  <span data-ttu-id="4a3de-127">コンテンツ タイプ、長さ、ID、MIME バージョンに基づいて、送信ページが MIME (Multipurpose Internet Mail Extensions) ヘッダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="4a3de-127">The send page creates a Multipurpose Internet Mail Extensions (MIME) header based upon the content type, the length, the ID, and the MIME version.</span></span> <span data-ttu-id="4a3de-128">さらに、MIME ヘッダー、および MIME の上位と下位の境界をメッセージに追加します。</span><span class="sxs-lookup"><span data-stu-id="4a3de-128">It adds the MIME header, and upper and lower MIME boundaries, to the message.</span></span>  
  
3.  <span data-ttu-id="4a3de-129">RNIF 2.01 では、送信ページは次のように HTTP ヘッダーのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="4a3de-129">For RNIF 2.01, the send page sets properties of the HTTP header as follows:</span></span>  
  
    1.  <span data-ttu-id="4a3de-130">X-RN-Version プロパティを、プロセス構成設定のバージョン プロパティに入力されているバージョンに設定します。</span><span class="sxs-lookup"><span data-stu-id="4a3de-130">It sets the X-RN-Version property to the version entered in the Version property of the process configuration settings.</span></span>  
  
    2.  <span data-ttu-id="4a3de-131">X-RN-ResponseType プロパティを、プロセス構成設定の IsSynchronous プロパティの設定に基づいて sync または async のいずれかに設定します。</span><span class="sxs-lookup"><span data-stu-id="4a3de-131">It sets the X-RN-ResponseType property to either sync or async, depending upon the setting of the IsSynchronous property in the process configuration settings.</span></span>  
  
    3.  <span data-ttu-id="4a3de-132">Content-Length プロパティを、メッセージ全体のサイズに設定します。</span><span class="sxs-lookup"><span data-stu-id="4a3de-132">It sets the Content-Length property to the size of the full message.</span></span>  
  
4.  <span data-ttu-id="4a3de-133">送信ページは HTTP Post を使用して、取引先アグリーメント内のアクション URL またはシグナル URL の設定に基づいて、パートナーの送信先 URL にメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="4a3de-133">Using an HTTP Post, the send page sends the message to the partner's destination URL, as set in the Action URL or Signal URL settings in the trading partner agreement.</span></span>  
  
5.  <span data-ttu-id="4a3de-134">送信ページは、HTTP 応答を待ちます。</span><span class="sxs-lookup"><span data-stu-id="4a3de-134">The send page waits for the HTTP response.</span></span> <span data-ttu-id="4a3de-135">送信ページは応答を受信すると、HTTP アダプターにルーティングします。</span><span class="sxs-lookup"><span data-stu-id="4a3de-135">When it receives the response, it routes it to the HTTP adapter.</span></span>  
  
6.  <span data-ttu-id="4a3de-136">接続が非同期の場合、送信ページは接続を閉じて処理を終わらせます。</span><span class="sxs-lookup"><span data-stu-id="4a3de-136">If the connection is asynchronous, the send page closes the connection, and its processing is complete.</span></span>  
  
7.  <span data-ttu-id="4a3de-137">接続が同期の場合、送信ページは返信メッセージ用に接続を開いたままにしておきます。</span><span class="sxs-lookup"><span data-stu-id="4a3de-137">If the connection is synchronous, the send page keeps the connection open for a returned message.</span></span> <span data-ttu-id="4a3de-138">送信ページはメッセージを受け取ると、RNIFReceive.aspx ページが受信メッセージに対して実行する処理と同じ処理を実行して、受信メッセージを HTTP アダプターに送信してから接続を閉じます。</span><span class="sxs-lookup"><span data-stu-id="4a3de-138">After it receives the message, it performs the same processing that an RNIFReceive.aspx page performs on a received message, sends the received message to the HTTP adapter, and then closes the connection.</span></span>  
  
## <a name="receive-aspx-page"></a><span data-ttu-id="4a3de-139">受信 ASPX ページ</span><span class="sxs-lookup"><span data-stu-id="4a3de-139">Receive ASPX Page</span></span>  
 <span data-ttu-id="4a3de-140">RNIFReceive.aspx ページは、インターネット経由でパートナーから HTTP メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="4a3de-140">The RNIFReceive.aspx page receives an HTTP message from the partner over the Internet.</span></span> <span data-ttu-id="4a3de-141">RNIF ヘッダーの処理、検証、削除を行った後で、メッセージを HTTP アダプターに送信します。</span><span class="sxs-lookup"><span data-stu-id="4a3de-141">It processes, validates, and then removes the RNIF headers, and submits the message to the HTTP adapter.</span></span> <span data-ttu-id="4a3de-142">受信ページが受け取るメッセージは、RNIF HTTP トランスポートに準拠している必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a3de-142">The message received by the receive page must be RNIF HTTP transport-compliant.</span></span> <span data-ttu-id="4a3de-143">受信ページでは、次のようにメッセージが処理されます。</span><span class="sxs-lookup"><span data-stu-id="4a3de-143">The receive page processes messages as follows:</span></span>  
  
1.  <span data-ttu-id="4a3de-144">応答側の RNIFReceive.aspx ページが開始側からメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="4a3de-144">The responder RNIFReceive.aspx page receives the message from the initiator.</span></span> <span data-ttu-id="4a3de-145">メッセージには、MIME ヘッダーと上位および下位の境界が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4a3de-145">The message contains the MIME header and upper and lower boundaries.</span></span>  
  
2.  <span data-ttu-id="4a3de-146">受信ページが MIME ヘッダーを検証します。</span><span class="sxs-lookup"><span data-stu-id="4a3de-146">The receive page validates the MIME header.</span></span>  
  
3.  <span data-ttu-id="4a3de-147">受信ページが MIME ヘッダーと境界をメッセージから削除します。</span><span class="sxs-lookup"><span data-stu-id="4a3de-147">The receive page removes the MIME header and boundaries from the message.</span></span>  
  
4.  <span data-ttu-id="4a3de-148">受信ページが HTTP の受信場所を使用して、HTTP アダプターにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="4a3de-148">The receive page posts the message to the HTTP adapter using the HTTP receive location.</span></span> <span data-ttu-id="4a3de-149">受信ページが HTTP 応答を受信し、開始側の送信ページに HTTP 応答を返します。</span><span class="sxs-lookup"><span data-stu-id="4a3de-149">The receive page receives an HTTP response, and returns the HTTP response to the send page of the initiator.</span></span>  
  
5.  <span data-ttu-id="4a3de-150">接続が非同期の場合、受信ページは接続を閉じます。</span><span class="sxs-lookup"><span data-stu-id="4a3de-150">If the connection is asynchronous, the receive page closes the connection.</span></span>  
  
6.  <span data-ttu-id="4a3de-151">接続が同期の場合、受信ページは接続を開いたまま返信メッセージを待ちます。</span><span class="sxs-lookup"><span data-stu-id="4a3de-151">If the connection is synchronous, the receive page keeps the connection open, waiting for a returned message.</span></span>  
  
7.  <span data-ttu-id="4a3de-152">HTTP アダプターから返信メッセージを受け取ると、受信ページが RNIFSend.aspx ページと同じ処理を実行して、返信メッセージを開始側の送信ページに送信します。</span><span class="sxs-lookup"><span data-stu-id="4a3de-152">After it receives the returned message from the HTTP adapter, the receive page performs the same processing that an RNIFSend.aspx page does, and sends the returned message to the initiator send page.</span></span> <span data-ttu-id="4a3de-153">HTTP 応答を受信した後で接続を閉じます。</span><span class="sxs-lookup"><span data-stu-id="4a3de-153">After it receives the HTTP response, it closes the connection.</span></span>  
  
## <a name="how-initiator-and-responder-aspx-pages-interact"></a><span data-ttu-id="4a3de-154">開始側と応答側の ASPX ページの相互作用</span><span class="sxs-lookup"><span data-stu-id="4a3de-154">How Initiator and Responder ASPX Pages Interact</span></span>  
 <span data-ttu-id="4a3de-155">開始側と応答側の両方で [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] を使用する場合、双方合わせて 4 つの ASPX ページの動作は、接続が同期か非同期かに応じて、およびメッセージがシングル アクションかダブル アクションかに応じて変わります。</span><span class="sxs-lookup"><span data-stu-id="4a3de-155">If both the initiator and the responder use [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)], the four ASPX pages on the initiator and responder interact differently depending on whether the connections are asynchronous or synchronous, and whether the messages are single-action or double-action.</span></span> <span data-ttu-id="4a3de-156">以下に、それぞれの場合の動作について説明します。</span><span class="sxs-lookup"><span data-stu-id="4a3de-156">The following subsections describe the complete set of interactions.</span></span>  
  
 <span data-ttu-id="4a3de-157">**非同期のダブル アクション**</span><span class="sxs-lookup"><span data-stu-id="4a3de-157">**Double-Action Asynchronous**</span></span>  
  
 <span data-ttu-id="4a3de-158">このシナリオでは、手順ごとに異なる HTTP 接続 (つまり合計で 4 つの HTTP 接続) を使用します。</span><span class="sxs-lookup"><span data-stu-id="4a3de-158">This scenario involves four separate HTTP connections, one for each step:</span></span>  
  
1.  <span data-ttu-id="4a3de-159">開始側の送信ページがアクション要求メッセージを応答側の受信ページに送信します。</span><span class="sxs-lookup"><span data-stu-id="4a3de-159">The initiator send page sends the action request message to the responder receive page.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4a3de-160">システムの負荷によっては、手順 2. と 3. の順序が入れ替わる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4a3de-160">Steps 2 and 3 below may occur in the reverse order, depending upon system load.</span></span>  
  
2.  <span data-ttu-id="4a3de-161">応答側の送信ページが要求シグナル メッセージを開始側の受信ページに送信します。</span><span class="sxs-lookup"><span data-stu-id="4a3de-161">The responder send page sends a request signal message to the initiator receive page.</span></span>  
  
3.  <span data-ttu-id="4a3de-162">応答側の送信ページがアクション応答メッセージを開始側の受信ページに送信します。</span><span class="sxs-lookup"><span data-stu-id="4a3de-162">The responder send page sends an action response message to the initiator receive page.</span></span>  
  
4.  <span data-ttu-id="4a3de-163">開始側の送信ページが応答シグナル メッセージを応答側の受信ページに送信します。</span><span class="sxs-lookup"><span data-stu-id="4a3de-163">The initiator send page sends a response signal message to the responder receive page.</span></span>  
  
 <span data-ttu-id="4a3de-164">**非同期のシングル アクション**</span><span class="sxs-lookup"><span data-stu-id="4a3de-164">**Single-Action Asynchronous**</span></span>  
  
 <span data-ttu-id="4a3de-165">このシナリオでは、手順ごとに異なる HTTP 接続 (つまり合計で 2 つの HTTP 接続) を使用します。</span><span class="sxs-lookup"><span data-stu-id="4a3de-165">This scenario involves two separate HTTP connections, one for each step.</span></span> <span data-ttu-id="4a3de-166">このシナリオは、非同期のダブル アクションのシナリオの手順 1. と 2. から構成されています。</span><span class="sxs-lookup"><span data-stu-id="4a3de-166">Note that this scenario consists of step 1 and 2 of the double-action asynchronous scenario.</span></span>  
  
1.  <span data-ttu-id="4a3de-167">開始側の送信ページがアクション要求メッセージを応答側の受信ページに送信します。</span><span class="sxs-lookup"><span data-stu-id="4a3de-167">The initiator send page sends the action request message to the responder receive page.</span></span>  
  
2.  <span data-ttu-id="4a3de-168">応答側の送信ページが要求シグナル メッセージを開始側の受信ページに送信します。</span><span class="sxs-lookup"><span data-stu-id="4a3de-168">The responder send page sends a request signal message to the initiator receive page.</span></span>  
  
 <span data-ttu-id="4a3de-169">**同期のダブル アクション**</span><span class="sxs-lookup"><span data-stu-id="4a3de-169">**Double-Action Synchronous**</span></span>  
  
 <span data-ttu-id="4a3de-170">このシナリオでは、1 つの HTTP 接続を使用します。</span><span class="sxs-lookup"><span data-stu-id="4a3de-170">This scenario involves one HTTP connection:</span></span>  
  
1.  <span data-ttu-id="4a3de-171">開始側の送信ページがアクション要求メッセージを応答側の受信ページに送信します。</span><span class="sxs-lookup"><span data-stu-id="4a3de-171">The initiator send page sends the action request message to the responder receive page.</span></span>  
  
2.  <span data-ttu-id="4a3de-172">応答側の受信ページは手順 1. と同じ接続を使用して、アクション応答メッセージ (問題がある場合は例外) を開始側の送信ページに送信します。</span><span class="sxs-lookup"><span data-stu-id="4a3de-172">The responder receive page sends an action response message (or an exception, if there is a problem) to the initiator send page on the same connection used in step 1.</span></span>  
  
 <span data-ttu-id="4a3de-173">**同期のシングル アクション**</span><span class="sxs-lookup"><span data-stu-id="4a3de-173">**Single-Action Synchronous**</span></span>  
  
 <span data-ttu-id="4a3de-174">このシナリオでは、1 つの HTTP 接続を使用します。</span><span class="sxs-lookup"><span data-stu-id="4a3de-174">This scenario involves one HTTP connection:</span></span>  
  
1.  <span data-ttu-id="4a3de-175">開始側の送信ページがアクション要求メッセージを応答側の受信ページに送信します。</span><span class="sxs-lookup"><span data-stu-id="4a3de-175">The initiator send page sends the action request message to the responder receive page.</span></span>  
  
2.  <span data-ttu-id="4a3de-176">応答側の受信ページは同じ接続を使用して、要求シグナル メッセージ (問題がある場合は例外) を開始側の送信ページに送信します。</span><span class="sxs-lookup"><span data-stu-id="4a3de-176">The responder receive page sends a request signal message (or an exception, if there is a problem) to the initiator send page on the same connection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a3de-177">参照</span><span class="sxs-lookup"><span data-stu-id="4a3de-177">See Also</span></span>  
 <span data-ttu-id="4a3de-178">[BTARN でのメッセージ処理](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md) </span><span class="sxs-lookup"><span data-stu-id="4a3de-178">[Message Processing in BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md) </span></span>  
 <span data-ttu-id="4a3de-179">[BTARN 受信パイプライン](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md) </span><span class="sxs-lookup"><span data-stu-id="4a3de-179">[BTARN Receive Pipeline](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md) </span></span>  
 [<span data-ttu-id="4a3de-180">BTARN 送信パイプライン</span><span class="sxs-lookup"><span data-stu-id="4a3de-180">BTARN Send Pipeline</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/btarn-send-pipeline.md)