---
title: 送信および受信 ASPX ページ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d93c41a87465a75adc2047889ff6cb80cdf629fa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281962"
---
# <a name="send-and-receive-aspx-pages"></a><span data-ttu-id="88076-102">送信および受信 ASPX ページ</span><span class="sxs-lookup"><span data-stu-id="88076-102">Send and Receive ASPX Pages</span></span>
<span data-ttu-id="88076-103">Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] ASPX ページは、直接結ぶインターフェイス[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]とインターネットです。</span><span class="sxs-lookup"><span data-stu-id="88076-103">The Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] ASPX pages are the direct interfaces between [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] and the Internet.</span></span> <span data-ttu-id="88076-104">2 つの ASPX ページは、受信ページ (RNIFReceive.aspx) と、送信ページ (RNIFSend.aspx) です。</span><span class="sxs-lookup"><span data-stu-id="88076-104">The two ASPX pages are the receive page (RNIFReceive.aspx) and the send page (RNIFSend.aspx).</span></span> <span data-ttu-id="88076-105">各 ASPX ページは、対応する拡張子[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]パイプライン。</span><span class="sxs-lookup"><span data-stu-id="88076-105">Each ASPX page is an extension to the corresponding [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] pipeline.</span></span> <span data-ttu-id="88076-106">パイプラインでは、RosettaNet Implementation Framework (RNIF) ヘッダーを処理する ASPX ページが必要です。</span><span class="sxs-lookup"><span data-stu-id="88076-106">The pipeline requires the ASPX page to handle RosettaNet Implementation Framework (RNIF) headers.</span></span> <span data-ttu-id="88076-107">パイプライン処理です。 HTTP のほとんどを実行します。ただし、各 ASPX ページは、RNIF ヘッダーの HTTP 処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="88076-107">The pipeline performs most of the HTTP processing; however, each ASPX page performs the HTTP processing of the RNIF headers.</span></span> <span data-ttu-id="88076-108">ページの機能を補完する、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] HTTP アダプター。</span><span class="sxs-lookup"><span data-stu-id="88076-108">The pages augment the functionality in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] HTTP adapter.</span></span>  
  
 <span data-ttu-id="88076-109">各 ASPX ページは、ASP[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] Web ユーザー インターフェイスを持たないアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="88076-109">Each ASPX page is an ASP[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] Web application with no user interface.</span></span> <span data-ttu-id="88076-110">ASP を使用する[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]Web セキュリティを外部関係者とセキュリティで保護された接続を確認します。</span><span class="sxs-lookup"><span data-stu-id="88076-110">They use ASP[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] Web security to ensure a secure connection with external parties.</span></span> <span data-ttu-id="88076-111">フォールト トレランス、スケーラビリティ、および可用性の高いサービスを実装できるレイヤを備えています。</span><span class="sxs-lookup"><span data-stu-id="88076-111">They provide a layer in which you can implement fault tolerance, scalability, and highly available services.</span></span>  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] <span data-ttu-id="88076-112">セットアップの展開ごとに RNIFSend.aspx ページと RNIFReceive.aspx ページのインストール[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="88076-112">setup installs an RNIFSend.aspx page and an RNIFReceive.aspx page on each deployment of [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)].</span></span> <span data-ttu-id="88076-113">応答側か相手側が取引先パートナーとメッセージを交換するとき[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]ASPX ページを使用して、メッセージを送信または取引先の URL からメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="88076-113">When the initiator or responder exchanges messages with the trading partner, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] uses the ASPX pages to send messages to, or receive messages from, the partner URL.</span></span> <span data-ttu-id="88076-114">場合は、イニシエーターとレスポンダーの両方を使用して、 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]、発信側の 2 つの ASPX ページが応答側の 2 つの ASPX ページとメッセージを交換します。</span><span class="sxs-lookup"><span data-stu-id="88076-114">If both the initiator and the responder use [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)], the two ASPX pages on the initiator exchange messages with the two ASPX pages on the responder.</span></span> <span data-ttu-id="88076-115">詳細については、「イニシエーターとレスポンダー ASPX ページの対話方法」の下のサブセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="88076-115">For more information, see the "How Initiator and Responder ASPX Pages Interact" subsection below.</span></span>  
  
## <a name="send-aspx-page"></a><span data-ttu-id="88076-116">送信 ASPX ページ</span><span class="sxs-lookup"><span data-stu-id="88076-116">Send ASPX Page</span></span>  
 <span data-ttu-id="88076-117">RNIFSend.aspx ページは、BizTalk HTTP アダプターからメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="88076-117">The RNIFSend.aspx page receives a message from the BizTalk HTTP adapter.</span></span> <span data-ttu-id="88076-118">作成し、メッセージを RNIF ヘッダーを追加し、インターネット経由でパートナーにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="88076-118">It creates and adds RNIF headers to the message, and then sends the message to the partner over the Internet.</span></span> <span data-ttu-id="88076-119">HTTP アダプターは、次のコマンドを使用して RNIFSend.aspx を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="88076-119">The HTTP adapter calls RNIFSend.aspx with the following command:</span></span>  
  
```  
http://localhost:<port number>/RNIFSend.aspx?<query string>  
```  
  
 <span data-ttu-id="88076-120">クエリ文字列には、次のデータ送信ページが、パートナーにメッセージを送信する必要があると、パートナーがメッセージの処理に必要なデータが含まれています。</span><span class="sxs-lookup"><span data-stu-id="88076-120">The query string includes the following data that the send page needs to send the message to the partner, and the data that the partner must have to process the message:</span></span>  
  
- <span data-ttu-id="88076-121">取引先 URL: http://www.\<*アドレス*\>.com/RNIFReceive.aspx</span><span class="sxs-lookup"><span data-stu-id="88076-121">The trading-partner URL: http://www.\<*address*\>.com/RNIFReceive.aspx</span></span>  
  
- <span data-ttu-id="88076-122">応答タイプ: 同期または非同期</span><span class="sxs-lookup"><span data-stu-id="88076-122">The response type: sync or async</span></span>  
  
- <span data-ttu-id="88076-123">RNIF バージョン:1.1 または 2.0。</span><span class="sxs-lookup"><span data-stu-id="88076-123">The RNIF version: 1.1 or 2.0.</span></span>  
  
  <span data-ttu-id="88076-124">BizTalk HTTP アダプターによって生成された MIME メッセージの送信、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]開始側の RNIFSend.aspx ページに送信パイプラインです。</span><span class="sxs-lookup"><span data-stu-id="88076-124">The BizTalk HTTP adapter sends a MIME message produced by the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] send pipeline to the initiator RNIFSend.aspx page.</span></span> <span data-ttu-id="88076-125">RNIFSend.aspx では、としては、次のように、メッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="88076-125">RNIFSend.aspx processes the message as follows:</span></span>  
  
1.  <span data-ttu-id="88076-126">送信ページは、メッセージの検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="88076-126">The send page performs validation on the message.</span></span>  
  
2.  <span data-ttu-id="88076-127">送信ページは、コンテンツの種類、長さ、ID、および MIME バージョンに基づいて、Multipurpose Internet Mail Extensions (MIME) ヘッダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="88076-127">The send page creates a Multipurpose Internet Mail Extensions (MIME) header based upon the content type, the length, the ID, and the MIME version.</span></span> <span data-ttu-id="88076-128">MIME ヘッダー、および上限と下限の MIME 境界をメッセージに追加します。</span><span class="sxs-lookup"><span data-stu-id="88076-128">It adds the MIME header, and upper and lower MIME boundaries, to the message.</span></span>  
  
3.  <span data-ttu-id="88076-129">RNIF 2.01 は、送信ページは、HTTP ヘッダーのプロパティとしては、次のように設定されます。</span><span class="sxs-lookup"><span data-stu-id="88076-129">For RNIF 2.01, the send page sets properties of the HTTP header as follows:</span></span>  
  
    1.  <span data-ttu-id="88076-130">プロセス構成設定のバージョンのプロパティに入力されているバージョンに X-RN バージョン プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="88076-130">It sets the X-RN-Version property to the version entered in the Version property of the process configuration settings.</span></span>  
  
    2.  <span data-ttu-id="88076-131">同期または非同期にプロセス構成設定の IsSynchronous プロパティの設定に応じてのいずれかに X-RN-ResponseType プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="88076-131">It sets the X-RN-ResponseType property to either sync or async, depending upon the setting of the IsSynchronous property in the process configuration settings.</span></span>  
  
    3.  <span data-ttu-id="88076-132">完全なメッセージのサイズをコンテンツの長さのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="88076-132">It sets the Content-Length property to the size of the full message.</span></span>  
  
4.  <span data-ttu-id="88076-133">HTTP Post を使用して、送信ページにメッセージを送信パートナーの送信先の URL、取引先アグリーメントでアクションの URL またはシグナル URL の設定で設定されています。</span><span class="sxs-lookup"><span data-stu-id="88076-133">Using an HTTP Post, the send page sends the message to the partner's destination URL, as set in the Action URL or Signal URL settings in the trading partner agreement.</span></span>  
  
5.  <span data-ttu-id="88076-134">送信ページは、HTTP 応答を待機します。</span><span class="sxs-lookup"><span data-stu-id="88076-134">The send page waits for the HTTP response.</span></span> <span data-ttu-id="88076-135">応答を受信した場合、HTTP アダプターにルーティングします。</span><span class="sxs-lookup"><span data-stu-id="88076-135">When it receives the response, it routes it to the HTTP adapter.</span></span>  
  
6.  <span data-ttu-id="88076-136">接続が非同期の場合は、送信ページは、接続を閉じます、その処理が完了します。</span><span class="sxs-lookup"><span data-stu-id="88076-136">If the connection is asynchronous, the send page closes the connection, and its processing is complete.</span></span>  
  
7.  <span data-ttu-id="88076-137">接続が同期の場合、送信ページ接続を開いたまま返信メッセージ用。</span><span class="sxs-lookup"><span data-stu-id="88076-137">If the connection is synchronous, the send page keeps the connection open for a returned message.</span></span> <span data-ttu-id="88076-138">メッセージを受信した後は、RNIFReceive.aspx ページに受信したメッセージに対して実行しますし、HTTP アダプターに受信したメッセージを送信し、接続を閉じますことと同じ処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="88076-138">After it receives the message, it performs the same processing that an RNIFReceive.aspx page performs on a received message, sends the received message to the HTTP adapter, and then closes the connection.</span></span>  
  
## <a name="receive-aspx-page"></a><span data-ttu-id="88076-139">受信 ASPX ページ</span><span class="sxs-lookup"><span data-stu-id="88076-139">Receive ASPX Page</span></span>  
 <span data-ttu-id="88076-140">RNIFReceive.aspx ページは、インターネット経由でパートナーからの HTTP メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="88076-140">The RNIFReceive.aspx page receives an HTTP message from the partner over the Internet.</span></span> <span data-ttu-id="88076-141">処理、検証、および、RNIF ヘッダーを削除し、HTTP アダプターにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="88076-141">It processes, validates, and then removes the RNIF headers, and submits the message to the HTTP adapter.</span></span> <span data-ttu-id="88076-142">受信ページが受信したメッセージは、RNIF HTTP トランスポートに準拠していませんである必要があります。</span><span class="sxs-lookup"><span data-stu-id="88076-142">The message received by the receive page must be RNIF HTTP transport-compliant.</span></span> <span data-ttu-id="88076-143">受信ページは、としては、次のようにメッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="88076-143">The receive page processes messages as follows:</span></span>  
  
1.  <span data-ttu-id="88076-144">応答側の RNIFReceive.aspx ページは、発信側からメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="88076-144">The responder RNIFReceive.aspx page receives the message from the initiator.</span></span> <span data-ttu-id="88076-145">メッセージには、MIME ヘッダーと上限と下限の境界が含まれています。</span><span class="sxs-lookup"><span data-stu-id="88076-145">The message contains the MIME header and upper and lower boundaries.</span></span>  
  
2.  <span data-ttu-id="88076-146">受信ページが MIME ヘッダーを検証します。</span><span class="sxs-lookup"><span data-stu-id="88076-146">The receive page validates the MIME header.</span></span>  
  
3.  <span data-ttu-id="88076-147">受信ページは、メッセージから MIME ヘッダーと境界を削除します。</span><span class="sxs-lookup"><span data-stu-id="88076-147">The receive page removes the MIME header and boundaries from the message.</span></span>  
  
4.  <span data-ttu-id="88076-148">受信ページは、HTTP の受信場所を使用して、HTTP アダプターにメッセージを投稿します。</span><span class="sxs-lookup"><span data-stu-id="88076-148">The receive page posts the message to the HTTP adapter using the HTTP receive location.</span></span> <span data-ttu-id="88076-149">受信ページは、HTTP 応答を受信し、発信側の送信ページに HTTP 応答を返します。</span><span class="sxs-lookup"><span data-stu-id="88076-149">The receive page receives an HTTP response, and returns the HTTP response to the send page of the initiator.</span></span>  
  
5.  <span data-ttu-id="88076-150">接続が非同期の場合、受信ページは、接続を閉じます。</span><span class="sxs-lookup"><span data-stu-id="88076-150">If the connection is asynchronous, the receive page closes the connection.</span></span>  
  
6.  <span data-ttu-id="88076-151">接続が同期の場合、受信ページ接続を開いたまま、返されたメッセージを待機しています。</span><span class="sxs-lookup"><span data-stu-id="88076-151">If the connection is synchronous, the receive page keeps the connection open, waiting for a returned message.</span></span>  
  
7.  <span data-ttu-id="88076-152">HTTP アダプターから返されたメッセージを受信した後、受信ページ実行と同じ処理を RNIFSend.aspx ページは、開始側の送信ページに、返されたメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="88076-152">After it receives the returned message from the HTTP adapter, the receive page performs the same processing that an RNIFSend.aspx page does, and sends the returned message to the initiator send page.</span></span> <span data-ttu-id="88076-153">HTTP 応答を受信した後は、接続を閉じます。</span><span class="sxs-lookup"><span data-stu-id="88076-153">After it receives the HTTP response, it closes the connection.</span></span>  
  
## <a name="how-initiator-and-responder-aspx-pages-interact"></a><span data-ttu-id="88076-154">イニシエーターとレスポンダーの ASPX ページの相互作用</span><span class="sxs-lookup"><span data-stu-id="88076-154">How Initiator and Responder ASPX Pages Interact</span></span>  
 <span data-ttu-id="88076-155">場合は、イニシエーターとレスポンダーの両方を使用して、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]イニシエーターとレスポンダーの 4 つの ASPX ページは、接続が非同期または同期がかどうかと、メッセージがシングル アクションかダブル アクションのかどうかに応じて異なる方法で対話.</span><span class="sxs-lookup"><span data-stu-id="88076-155">If both the initiator and the responder use [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)], the four ASPX pages on the initiator and responder interact differently depending on whether the connections are asynchronous or synchronous, and whether the messages are single-action or double-action.</span></span> <span data-ttu-id="88076-156">次のサブセクションでは、相互作用の完全なセットについて説明します。</span><span class="sxs-lookup"><span data-stu-id="88076-156">The following subsections describe the complete set of interactions.</span></span>  
  
 <span data-ttu-id="88076-157">**非同期のダブル アクション**</span><span class="sxs-lookup"><span data-stu-id="88076-157">**Double-Action Asynchronous**</span></span>  
  
 <span data-ttu-id="88076-158">このシナリオには、ステップごとに 1 つの 4 つの異なる HTTP 接続が含まれます。</span><span class="sxs-lookup"><span data-stu-id="88076-158">This scenario involves four separate HTTP connections, one for each step:</span></span>  
  
1. <span data-ttu-id="88076-159">アクション要求メッセージ、応答側を発信側の送信ページはページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="88076-159">The initiator send page sends the action request message to the responder receive page.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="88076-160">手順 2. および 3. 下のシステムの負荷に応じて、逆の順序で発生します。</span><span class="sxs-lookup"><span data-stu-id="88076-160">Steps 2 and 3 below may occur in the reverse order, depending upon system load.</span></span>  
  
2. <span data-ttu-id="88076-161">要求シグナル メッセージの発信側に応答側の送信ページはページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="88076-161">The responder send page sends a request signal message to the initiator receive page.</span></span>  
  
3. <span data-ttu-id="88076-162">アクションの応答メッセージの発信側に応答側の送信ページはページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="88076-162">The responder send page sends an action response message to the initiator receive page.</span></span>  
  
4. <span data-ttu-id="88076-163">開始側の送信ページは応答シグナルが応答側にメッセージの受信ページ。</span><span class="sxs-lookup"><span data-stu-id="88076-163">The initiator send page sends a response signal message to the responder receive page.</span></span>  
  
   <span data-ttu-id="88076-164">**非同期のシングル アクション**</span><span class="sxs-lookup"><span data-stu-id="88076-164">**Single-Action Asynchronous**</span></span>  
  
   <span data-ttu-id="88076-165">このシナリオには、各手順のいずれか 2 つの異なる HTTP 接続が含まれます。</span><span class="sxs-lookup"><span data-stu-id="88076-165">This scenario involves two separate HTTP connections, one for each step.</span></span> <span data-ttu-id="88076-166">このシナリオでは手順 1. および 2. 非同期ダブル アクション シナリオのことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="88076-166">Note that this scenario consists of step 1 and 2 of the double-action asynchronous scenario.</span></span>  
  
5. <span data-ttu-id="88076-167">アクション要求メッセージ、応答側を発信側の送信ページはページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="88076-167">The initiator send page sends the action request message to the responder receive page.</span></span>  
  
6. <span data-ttu-id="88076-168">要求シグナル メッセージの発信側に応答側の送信ページはページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="88076-168">The responder send page sends a request signal message to the initiator receive page.</span></span>  
  
   <span data-ttu-id="88076-169">**同期のダブル アクション**</span><span class="sxs-lookup"><span data-stu-id="88076-169">**Double-Action Synchronous**</span></span>  
  
   <span data-ttu-id="88076-170">このシナリオには、1 つの HTTP 接続が含まれます。</span><span class="sxs-lookup"><span data-stu-id="88076-170">This scenario involves one HTTP connection:</span></span>  
  
7. <span data-ttu-id="88076-171">アクション要求メッセージ、応答側を発信側の送信ページはページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="88076-171">The initiator send page sends the action request message to the responder receive page.</span></span>  
  
8. <span data-ttu-id="88076-172">応答側の受信ページは、アクション応答メッセージ (または問題がある場合は例外) を手順 1. で使用する同じ接続上でイニシエーターの送信ページ。</span><span class="sxs-lookup"><span data-stu-id="88076-172">The responder receive page sends an action response message (or an exception, if there is a problem) to the initiator send page on the same connection used in step 1.</span></span>  
  
   <span data-ttu-id="88076-173">**シングル アクションの同期**</span><span class="sxs-lookup"><span data-stu-id="88076-173">**Single-Action Synchronous**</span></span>  
  
   <span data-ttu-id="88076-174">このシナリオには、1 つの HTTP 接続が含まれます。</span><span class="sxs-lookup"><span data-stu-id="88076-174">This scenario involves one HTTP connection:</span></span>  
  
9. <span data-ttu-id="88076-175">アクション要求メッセージ、応答側を発信側の送信ページはページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="88076-175">The initiator send page sends the action request message to the responder receive page.</span></span>  
  
10. <span data-ttu-id="88076-176">応答側の受信ページは、要求シグナル メッセージ (または問題がある場合は例外) を同じ接続上でイニシエーターの送信ページ。</span><span class="sxs-lookup"><span data-stu-id="88076-176">The responder receive page sends a request signal message (or an exception, if there is a problem) to the initiator send page on the same connection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88076-177">参照</span><span class="sxs-lookup"><span data-stu-id="88076-177">See Also</span></span>  
 <span data-ttu-id="88076-178">[BTARN でのメッセージ処理](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md) </span><span class="sxs-lookup"><span data-stu-id="88076-178">[Message Processing in BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md) </span></span>  
 <span data-ttu-id="88076-179">[BTARN 受信パイプライン](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md) </span><span class="sxs-lookup"><span data-stu-id="88076-179">[BTARN Receive Pipeline](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md) </span></span>  
 [<span data-ttu-id="88076-180">BTARN 送信パイプライン</span><span class="sxs-lookup"><span data-stu-id="88076-180">BTARN Send Pipeline</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/btarn-send-pipeline.md)