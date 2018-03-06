---
title: "HTTP 受信アダプター |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9008833c-5a02-4fb4-a43e-09ca28a21eff
caps.latest.revision: 
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f2f309a129c66d11d019b28b8ffc2b51d68e93d
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2018
---
# <a name="http-receive-adapter"></a><span data-ttu-id="80ff2-102">HTTP 受信アダプター</span><span class="sxs-lookup"><span data-stu-id="80ff2-102">HTTP Receive Adapter</span></span>
<span data-ttu-id="80ff2-103">HTTP 受信アダプターの受信場所は、BizTalk Server 管理コンソールで構成された個別の URL です。</span><span class="sxs-lookup"><span data-stu-id="80ff2-103">The receive location for the HTTP receive adapter is a distinct URL configured through the BizTalk Server Administration console.</span></span>  
  
 <span data-ttu-id="80ff2-104">HTTP 受信アダプターは、クライアントからの非同期送信用にも同期送信用にも構成できます。</span><span class="sxs-lookup"><span data-stu-id="80ff2-104">You can configure the HTTP receive adapter for either asynchronous submission or synchronous submission from the client.</span></span> <span data-ttu-id="80ff2-105">非同期送信は一方向の送信、同期通信は双方向または要求 - 応答の送信です。</span><span class="sxs-lookup"><span data-stu-id="80ff2-105">Asynchronous submissions are one-way submissions and synchronous submissions are two way or request-response submissions.</span></span>  
  
 <span data-ttu-id="80ff2-106">受信要求の認証および承認には、IIS セキュリティを使用します。</span><span class="sxs-lookup"><span data-stu-id="80ff2-106">You use IIS security for authentication and authorization of incoming requests.</span></span>  
  
## <a name="http-get-and-http-post-requests"></a><span data-ttu-id="80ff2-107">HTTP GET 要求および HTTP POST 要求</span><span class="sxs-lookup"><span data-stu-id="80ff2-107">HTTP GET and HTTP POST Requests</span></span>  
 <span data-ttu-id="80ff2-108">HTTP 受信アダプターは、2 つの方法でメッセージを受信することができます-HTTP POST 要求または HTTP GET 要求。</span><span class="sxs-lookup"><span data-stu-id="80ff2-108">The HTTP receive adapter can receive messages in two different ways—by an HTTP POST request or an HTTP GET request.</span></span>  
  
 <span data-ttu-id="80ff2-109">HTTP 受信アダプターが HTTP POST 要求でメッセージを取得すると、次のような一連のイベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="80ff2-109">When an HTTP receive adapter gets messages on an HTTP POST request, the following sequence of events occurs:</span></span>  
  
1.  <span data-ttu-id="80ff2-110">BizTalk Server で構成された URL は、受信場所で新しいメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="80ff2-110">The URL configured in BizTalk Server receives a new message on the receive location.</span></span>  
  
2.  <span data-ttu-id="80ff2-111">受信アダプターは、メッセージをサーバーに送信できるように、BizTalk メッセージ オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="80ff2-111">The receive adapter creates a BizTalk Message object so that the message can be submitted to the server.</span></span>  
  
3.  <span data-ttu-id="80ff2-112">受信アダプターが 1 つだけの部分を含む BizTalk メッセージ オブジェクトを作成、ボディ部です。</span><span class="sxs-lookup"><span data-stu-id="80ff2-112">The receive adapter creates the BizTalk Message object with only one part—the body part.</span></span>  
  
4.  <span data-ttu-id="80ff2-113">メッセージの読み取りおよびサーバーへの送信が正常に完了した後、HTTP 受信アダプターからクライアントに、要求が受理されたことを示す HTTP コード 202 が返されます。</span><span class="sxs-lookup"><span data-stu-id="80ff2-113">After the message has been read and successfully submitted to the server, the HTTP receive adapter sends an HTTP code 202 back to the client indicating that the request was accepted.</span></span>  
  
     <span data-ttu-id="80ff2-114">必要に応じて、HTTP 受信アダプターは、HTTP 応答でメッセージの関連付けトークンを送信できます。</span><span class="sxs-lookup"><span data-stu-id="80ff2-114">Optionally, the HTTP receive adapter can send a message correlation token on the HTTP response.</span></span> <span data-ttu-id="80ff2-115">この関連付けトークンは、BizTalk Server 内のメッセージを表します。</span><span class="sxs-lookup"><span data-stu-id="80ff2-115">This correlation token represents the message within BizTalk Server.</span></span> <span data-ttu-id="80ff2-116">HTTP 受信場所が要求 - 応答のポートの場合、アダプターから、応答メッセージと共に成功コード 200 が返されます。</span><span class="sxs-lookup"><span data-stu-id="80ff2-116">If the HTTP receive location is in a request-response port, the adapter returns success code 200 along with the response message.</span></span>  
  
 <span data-ttu-id="80ff2-117">HTTP 受信アダプターで HTTP GET 要求からのメッセージを処理する場合、受信アダプターによって、BizTalk メッセージ オブジェクトが作成され、HTTP GET 要求のデコードされたクエリ文字列が BizTalk メッセージのボディ部に配置されます。</span><span class="sxs-lookup"><span data-stu-id="80ff2-117">When an HTTP receive adapter processes messages from an HTTP GET request, the receive adapter creates a BizTalk Message object and puts the decoded query string of the HTTP GET request into the BizTalk message body part.</span></span> <span data-ttu-id="80ff2-118">HTTP アダプターは、次のアルゴリズムを使用して、BizTalk メッセージのボディ部に配置されるクエリ文字列を選択します。</span><span class="sxs-lookup"><span data-stu-id="80ff2-118">The HTTP adapter selects the query string that is placed into the BizTalk message body part using the following algorithm:</span></span>  
  
-   <span data-ttu-id="80ff2-119">HTTP 受信アダプターで HTTP GET 要求を受信する場合、受信 URI 文字列を 2 つに分割します。その際、区切り記号として疑問符 (?) を使用します。</span><span class="sxs-lookup"><span data-stu-id="80ff2-119">If the HTTP receive adapter receives an HTTP GET request, it splits the incoming URI string into two parts, using the question mark (?) symbol as a delimiter.</span></span>  
  
-   <span data-ttu-id="80ff2-120">疑問符 () 区切り記号の前に、の部分であり、URI 文字列の最初の部分にコピーされます、 **InboundTransportLocation** メッセージ コンテキストのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="80ff2-120">The first part of the URI string, the part before the question mark delimiter, is copied into the **InboundTransportLocation** property on the message context.</span></span> <span data-ttu-id="80ff2-121">**InboundTransportLocation** プロパティは、BizTalk Server がメッセージを受信する場所を一意に識別します。</span><span class="sxs-lookup"><span data-stu-id="80ff2-121">The **InboundTransportLocation** property uniquely identifies the location where BizTalk Server received the message.</span></span> <span data-ttu-id="80ff2-122">エンジンは、このプロパティを使用して、メッセージ対して稼働する受信場所を判別します。</span><span class="sxs-lookup"><span data-stu-id="80ff2-122">The engine uses this property to determine which receive location to run for the message.</span></span>  
  
-   <span data-ttu-id="80ff2-123">HTTP アダプターは、残りの URI 文字列、つまり、区切り記号である疑問符より後の部分を取得し、デコードして BizTalk メッセージのボディ部にコピーします。</span><span class="sxs-lookup"><span data-stu-id="80ff2-123">The HTTP adapter takes the rest of the URI string, the part after the question mark delimiter, and decodes and copies it into the BizTalk message body part.</span></span>  
  
-   <span data-ttu-id="80ff2-124">空の HTTP GET または HTTP POST 操作は、HTTP 受信アダプターで受信されると、拒否されます。</span><span class="sxs-lookup"><span data-stu-id="80ff2-124">If an empty HTTP GET or HTTP POST operation is received by the HTTP receive adapter, it is rejected.</span></span>  
  
## <a name="http-receive-adapter-processing-of-a-get-request"></a><span data-ttu-id="80ff2-125">HTTP 受信アダプターによる GET 要求の処理</span><span class="sxs-lookup"><span data-stu-id="80ff2-125">HTTP Receive Adapter Processing of a GET Request</span></span>  
 <span data-ttu-id="80ff2-126">HTTP GET 要求が受け取ったメッセージを HTTP 受信アダプターで処理する方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="80ff2-126">The following are examples of how the HTTP receive adapter processes messages received by HTTP GET requests.</span></span> <span data-ttu-id="80ff2-127">この例では、HTTP 受信アダプターが次の 2 つの受信場所で構成されていると想定しています。</span><span class="sxs-lookup"><span data-stu-id="80ff2-127">These examples assume that the HTTP receive adapter is configured with the following two receive locations:</span></span>  
  
```  
/vroot/BTSHTTPReceive.dll  
/vroot/BTSHTTPReceive.dll?LocationID=1  
```  
  
1.  <span data-ttu-id="80ff2-128">クライアントは次の HTTP GET 要求を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="80ff2-128">Given the following HTTP GET request for the client:</span></span>  
  
    ```  
    http://servername/vroot/BTSHTTPReceive.dll?LocationID=1  
    ```  
  
     <span data-ttu-id="80ff2-129">HTTP 受信アダプターによって行われる操作は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="80ff2-129">The action taken by the HTTP receive adapter is as follows:</span></span>  
  
     <span data-ttu-id="80ff2-130">設定、 **InboundTransportLocation** プロパティを/vroot/BTSHTTPReceive.dll に設定し、BizTalk メッセージ オブジェクト ボディ部を LocationID メッセージ コンテキスト = 1 です。</span><span class="sxs-lookup"><span data-stu-id="80ff2-130">Set the **InboundTransportLocation** property on the message context equal to /vroot/BTSHTTPReceive.dll, and the BizTalk Message object body part equal to LocationID=1.</span></span>  
  
2.  <span data-ttu-id="80ff2-131">クライアントは次の HTTP GET 要求を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="80ff2-131">Given the following HTTP GET request for the client:</span></span>  
  
    ```  
    http://servername/vroot/BTSHTTPReceive.dll?LocationID=1&MyParam=My%20Value  
    ```  
  
     <span data-ttu-id="80ff2-132">HTTP 受信アダプターによって行われる操作は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="80ff2-132">The action taken by the HTTP receive adapter is as follows:</span></span>  
  
     <span data-ttu-id="80ff2-133">設定、 **InboundTransportLocation** プロパティを/vroot/BTSHTTPReceive.dll に設定し、BizTalk メッセージ オブジェクトのボディ部を LocationID = 1 & MyParam = My Value です。</span><span class="sxs-lookup"><span data-stu-id="80ff2-133">Set the **InboundTransportLocation** property equal to /vroot/BTSHTTPReceive.dll, and the BizTalk Message object body part equal to LocationID=1&MyParam=My Value.</span></span>  
  
3.  <span data-ttu-id="80ff2-134">クライアントは次の HTTP GET 要求を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="80ff2-134">Given the following HTTP GET request for the client:</span></span>  
  
    ```  
    http://servername/vroot/BTSHTTPReceive.dll  
    ```  
  
     <span data-ttu-id="80ff2-135">実行するアクションを HTTP 受信アダプターは、次のように +。</span><span class="sxs-lookup"><span data-stu-id="80ff2-135">The action taken by the HTTP receive adapter is+ as follows:</span></span>  
  
     <span data-ttu-id="80ff2-136">HTTP GET 要求の形式が誤っているため、要求を拒否します。</span><span class="sxs-lookup"><span data-stu-id="80ff2-136">Reject the request due to incorrect formatting of the HTTP GET request.</span></span>  
  
## <a name="batching-support-for-the-http-receive-adapter"></a><span data-ttu-id="80ff2-137">HTTP 受信アダプターのバッチ処理のサポート</span><span class="sxs-lookup"><span data-stu-id="80ff2-137">Batching Support for the HTTP Receive Adapter</span></span>  
 <span data-ttu-id="80ff2-138">HTTP 受信アダプターは、メッセージをバッチ単位でサーバーに送信します。</span><span class="sxs-lookup"><span data-stu-id="80ff2-138">The HTTP receive adapter submits messages to the server in batches.</span></span> <span data-ttu-id="80ff2-139">サーバーへのメッセージ送信に使用されるバッチのサイズは、HTTP アダプターの受信ハンドラーで構成できます。</span><span class="sxs-lookup"><span data-stu-id="80ff2-139">The size of the batch used to submit messages to the server can be configured on the HTTP adapter receive handler.</span></span>  
  
## <a name="http-receive-adapter-support-for-suspending-failed-requests"></a><span data-ttu-id="80ff2-140">HTTP 受信アダプターによる、失敗した要求の中断のサポート</span><span class="sxs-lookup"><span data-stu-id="80ff2-140">HTTP Receive Adapter Support for Suspending Failed Requests</span></span>  
 <span data-ttu-id="80ff2-141">BizTalk Server の HTTP 受信アダプターが構成の設定、**失敗した要求の中断**マッピングの失敗が、受信パイプライン障害によって着信処理が失敗した場合は、HTTP 要求の動作を制御する、またはルーティングに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="80ff2-141">The BizTalk Server HTTP receive adapter has a configuration setting, **Suspend Failed Requests**, to control what happens with an HTTP request if it fails inbound processing due to a receive pipeline failure, a mapping failure, or a routing failure.</span></span> <span data-ttu-id="80ff2-142">この設定には、次の 2 つの有効値があります。</span><span class="sxs-lookup"><span data-stu-id="80ff2-142">The setting has two possible values:</span></span>  
  
-   <span data-ttu-id="80ff2-143">**False を指定します。**</span><span class="sxs-lookup"><span data-stu-id="80ff2-143">**False.**</span></span> <span data-ttu-id="80ff2-144">これが既定の設定です。</span><span class="sxs-lookup"><span data-stu-id="80ff2-144">This is the default setting.</span></span> <span data-ttu-id="80ff2-145">HTTP 受信アダプターは、受信パイプライン、マッピング、またはルーティングの障害によって受信処理に失敗したメッセージを破棄します。</span><span class="sxs-lookup"><span data-stu-id="80ff2-145">The HTTP receive adapter discards messages that fail inbound processing due to a receive pipeline failure, a mapping failure, or a routing failure.</span></span> <span data-ttu-id="80ff2-146">さらに、エラー状態コード 401 または 500 をクライアントに送信します。</span><span class="sxs-lookup"><span data-stu-id="80ff2-146">Additionally, an error status code 401 or 500 is sent to the client.</span></span> 
  
-   <span data-ttu-id="80ff2-147">**True を指定します。**</span><span class="sxs-lookup"><span data-stu-id="80ff2-147">**True.**</span></span> <span data-ttu-id="80ff2-148">HTTP 受信アダプターは、受信パイプライン、マッピング、またはルーティングの障害によって着信処理に失敗したメッセージを中断します。</span><span class="sxs-lookup"><span data-stu-id="80ff2-148">The HTTP receive adapter suspends messages that fail inbound processing due to a receive pipeline failure, a mapping failure, or a routing failure.</span></span> <span data-ttu-id="80ff2-149">一方向受信ポート、 **Accepted** ステータス コード 202 がクライアントに送信します。</span><span class="sxs-lookup"><span data-stu-id="80ff2-149">For one-way receive ports an **Accepted** status code 202 is sent to the client.</span></span> <span data-ttu-id="80ff2-150">双方向受信ポート、 **エラー** ステータス コード 500 をクライアントに送信します。</span><span class="sxs-lookup"><span data-stu-id="80ff2-150">For two-way receive ports an **Error** status code 500 is sent to the client.</span></span>  
  
## <a name="chunked-encoding-support-for-the-http-receive-adapter"></a><span data-ttu-id="80ff2-151">HTTP 受信アダプターのチャンク エンコードのサポート</span><span class="sxs-lookup"><span data-stu-id="80ff2-151">Chunked Encoding Support for the HTTP Receive Adapter</span></span>  
 <span data-ttu-id="80ff2-152">HTTP 受信アダプターは、チャンク エンコードされたメッセージ本文を含む HTTP 要求を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="80ff2-152">The HTTP receive adapter accepts HTTP requests with chunked encoded body messages.</span></span> <span data-ttu-id="80ff2-153">受信アダプターでは、本文のサイズが 4 KB を超えると、チャンク エンコードを使用して応答メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="80ff2-153">The receive adapter uses chunked encoding to send response messages when the body size is larger than 4 KB.</span></span> <span data-ttu-id="80ff2-154">説明した DWORD レジストリ エントリを設定して、オフにすることができますチャンク エンコード[HTTP アダプタの構成およびチューニング パラメータ](../core/http-adapter-configuration-and-tuning-parameters.md)</span><span class="sxs-lookup"><span data-stu-id="80ff2-154">Chunked encoding can be turned off by setting the DWORD registry entry described in [HTTP Adapter Configuration and Tuning Parameters](../core/http-adapter-configuration-and-tuning-parameters.md)</span></span>  
  
## <a name="client-certificates-for-the-http-receive-adapter"></a><span data-ttu-id="80ff2-155">HTTP 受信アダプターのクライアント証明書</span><span class="sxs-lookup"><span data-stu-id="80ff2-155">Client Certificates for the HTTP Receive Adapter</span></span>  
 <span data-ttu-id="80ff2-156">クライアント証明書とのセキュリティで保護された接続が HTTP 受信場所に使用されるたびに、HTTP 受信アダプターは、Microsoft インターネット インフォメーション サービス (IIS) からクライアント証明書の拇印を取得して、その場所で HTTPS 経由で受信したすべてのメッセージのメッセージ コンテキストに追加します。</span><span class="sxs-lookup"><span data-stu-id="80ff2-156">Whenever a secure connection with a client certificate is used for the HTTP receive location, the HTTP receive adapter obtains the client certificate thumbprint from Microsoft Internet Information Services (IIS) and adds it to the message context of all messages that were received over HTTPS on that location.</span></span> <span data-ttu-id="80ff2-157">HTTP 受信アダプターでは、次のシステム プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="80ff2-157">The HTTP receive adapter sets the following system properties:</span></span>  
  
```  
SourcePartyEvidenceQualifier = "Certificate"  
SourcePartyEvidence = <certificate thumbprint>  
```  
  
## <a name="status-codes-returned-by-the-http-receive-adapter"></a><span data-ttu-id="80ff2-158">HTTP 受信アダプターによって返される状態コード</span><span class="sxs-lookup"><span data-stu-id="80ff2-158">Status Codes Returned by the HTTP Receive Adapter</span></span>  
 <span data-ttu-id="80ff2-159">次の一覧に、HTTP 受信アダプターによって返される状態コードを示します。</span><span class="sxs-lookup"><span data-stu-id="80ff2-159">The following list contains status codes returned by the HTTP receive adapter.</span></span>  
  
-   <span data-ttu-id="80ff2-160">**200 OK です。**</span><span class="sxs-lookup"><span data-stu-id="80ff2-160">**200 OK.**</span></span> <span data-ttu-id="80ff2-161">アダプターは、正常に要求メッセージを処理して応答を生成しました。</span><span class="sxs-lookup"><span data-stu-id="80ff2-161">The adapter successfully processed the request message and generated a response.</span></span> <span data-ttu-id="80ff2-162">アダプターは、HTTP 要求 - 応答ポートからの HTTP 応答でこの状態コードを返します。</span><span class="sxs-lookup"><span data-stu-id="80ff2-162">The adapter returns this status code on the HTTP response from the HTTP request-response port.</span></span>  
  
-   <span data-ttu-id="80ff2-163">**202 メッセージが受け入れられます。**</span><span class="sxs-lookup"><span data-stu-id="80ff2-163">**202 Message Accepted.**</span></span> <span data-ttu-id="80ff2-164">アダプターがメッセージをサーバーに正常に送信したか、一方向の要求が保留されました。</span><span class="sxs-lookup"><span data-stu-id="80ff2-164">The adapter successfully submitted the message into the server or a one-way request is suspended.</span></span> <span data-ttu-id="80ff2-165">アダプターは、一方向の HTTP 受信ポートからの HTTP 応答でこの状態コードを返します。</span><span class="sxs-lookup"><span data-stu-id="80ff2-165">The adapter returns this status code on the HTTP response from a one way HTTP receive port.</span></span>  
  
-   <span data-ttu-id="80ff2-166">**401 アクセス拒否されました。**</span><span class="sxs-lookup"><span data-stu-id="80ff2-166">**401 Access Denied.**</span></span> <span data-ttu-id="80ff2-167">HTTP 要求は認証が必要な受信ポートで受信され、そのメッセージのセキュリティ チェックに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="80ff2-167">The HTTP request is received on an authentication-required receive port and the security check for that message failed.</span></span> <span data-ttu-id="80ff2-168">たとえば、パーティが解決されなかったり、メッセージの暗号化が解除されていません。</span><span class="sxs-lookup"><span data-stu-id="80ff2-168">For example, the party was not resolved or the message was not decrypted.</span></span>  
  
-   <span data-ttu-id="80ff2-169">**500 内部サーバー エラーがあります。**</span><span class="sxs-lookup"><span data-stu-id="80ff2-169">**500 Internal Server Error.**</span></span> <span data-ttu-id="80ff2-170">HTTP 要求を処理する際に一般エラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="80ff2-170">A general failure to process the HTTP request.</span></span> <span data-ttu-id="80ff2-171">しない限り、BizTalk Server でメッセージが中断されていない構成設定 **失敗した要求を中断** に設定されている **True** 双方向の受信ポートです。</span><span class="sxs-lookup"><span data-stu-id="80ff2-171">The message is not suspended by BizTalk Server unless the configuration setting **Suspend Failed Requests** is set to **True** for a two-way receive port.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80ff2-172">参照</span><span class="sxs-lookup"><span data-stu-id="80ff2-172">See Also</span></span>  
 [<span data-ttu-id="80ff2-173">HTTP アダプター</span><span class="sxs-lookup"><span data-stu-id="80ff2-173">HTTP Adapter</span></span>](../core/http-adapter.md)