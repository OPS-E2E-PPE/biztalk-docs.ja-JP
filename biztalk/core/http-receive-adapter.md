---
title: HTTP 受信アダプター |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9008833c-5a02-4fb4-a43e-09ca28a21eff
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea6731d6611d3cc2efbd374cd622b5fb239a3c9f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65332598"
---
# <a name="http-receive-adapter"></a><span data-ttu-id="4bf97-102">HTTP 受信アダプター</span><span class="sxs-lookup"><span data-stu-id="4bf97-102">HTTP Receive Adapter</span></span>
<span data-ttu-id="4bf97-103">HTTP 受信アダプターの受信場所では、BizTalk Server 管理コンソールで構成された個別の URL です。</span><span class="sxs-lookup"><span data-stu-id="4bf97-103">The receive location for the HTTP receive adapter is a distinct URL configured through the BizTalk Server Administration console.</span></span>  
  
 <span data-ttu-id="4bf97-104">HTTP を構成するクライアントから非同期の送信または同期送信アダプターを受信します。</span><span class="sxs-lookup"><span data-stu-id="4bf97-104">You can configure the HTTP receive adapter for either asynchronous submission or synchronous submission from the client.</span></span> <span data-ttu-id="4bf97-105">非同期送信は一方向の送信と同期通信は 2 つの方法または要求-応答送信します。</span><span class="sxs-lookup"><span data-stu-id="4bf97-105">Asynchronous submissions are one-way submissions and synchronous submissions are two way or request-response submissions.</span></span>  
  
 <span data-ttu-id="4bf97-106">受信要求の認証と承認の IIS のセキュリティを使用するとします。</span><span class="sxs-lookup"><span data-stu-id="4bf97-106">You use IIS security for authentication and authorization of incoming requests.</span></span>  
  
## <a name="http-get-and-http-post-requests"></a><span data-ttu-id="4bf97-107">HTTP GET と HTTP POST 要求</span><span class="sxs-lookup"><span data-stu-id="4bf97-107">HTTP GET and HTTP POST Requests</span></span>  
 <span data-ttu-id="4bf97-108">HTTP 受信アダプターは 2 つの方法でメッセージを受信することができます: HTTP POST 要求または HTTP GET 要求でします。</span><span class="sxs-lookup"><span data-stu-id="4bf97-108">The HTTP receive adapter can receive messages in two different ways—by an HTTP POST request or an HTTP GET request.</span></span>  
  
 <span data-ttu-id="4bf97-109">HTTP は受信アダプター、HTTP POST 要求でメッセージを取得、次の一連のイベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="4bf97-109">When an HTTP receive adapter gets messages on an HTTP POST request, the following sequence of events occurs:</span></span>  
  
1. <span data-ttu-id="4bf97-110">BizTalk Server で構成されている URL では、受信場所で新しいメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="4bf97-110">The URL configured in BizTalk Server receives a new message on the receive location.</span></span>  
  
2. <span data-ttu-id="4bf97-111">受信アダプターは、サーバーにメッセージを送信できるように、BizTalk メッセージ オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="4bf97-111">The receive adapter creates a BizTalk Message object so that the message can be submitted to the server.</span></span>  
  
3. <span data-ttu-id="4bf97-112">受信アダプターが 1 つだけの一部で、BizTalk メッセージ オブジェクトを作成します-ボディ部。</span><span class="sxs-lookup"><span data-stu-id="4bf97-112">The receive adapter creates the BizTalk Message object with only one part—the body part.</span></span>  
  
4. <span data-ttu-id="4bf97-113">メッセージが読み取りおよびサーバーに正常に送信された後、HTTP の受信要求が受理されたことを示すクライアントに HTTP コード 202 がバックアップ アダプターは。</span><span class="sxs-lookup"><span data-stu-id="4bf97-113">After the message has been read and successfully submitted to the server, the HTTP receive adapter sends an HTTP code 202 back to the client indicating that the request was accepted.</span></span>  
  
    <span data-ttu-id="4bf97-114">必要に応じて、HTTP の受信アダプターは、HTTP 応答でメッセージの関連付けトークンを送信することができます。</span><span class="sxs-lookup"><span data-stu-id="4bf97-114">Optionally, the HTTP receive adapter can send a message correlation token on the HTTP response.</span></span> <span data-ttu-id="4bf97-115">この関連付けトークンでは、BizTalk Server 内でメッセージを表します。</span><span class="sxs-lookup"><span data-stu-id="4bf97-115">This correlation token represents the message within BizTalk Server.</span></span> <span data-ttu-id="4bf97-116">場合は、HTTP 受信場所が要求-応答ポートでは、アダプターは、応答メッセージと共に成功コード 200 を返します。</span><span class="sxs-lookup"><span data-stu-id="4bf97-116">If the HTTP receive location is in a request-response port, the adapter returns success code 200 along with the response message.</span></span>  
  
   <span data-ttu-id="4bf97-117">ときに、HTTP アダプター プロセスから受信したメッセージを HTTP GET 要求、受信アダプターは BizTalk メッセージ オブジェクトを作成し、BizTalk メッセージのボディ部に HTTP GET 要求のデコードされたクエリ文字列を格納します。</span><span class="sxs-lookup"><span data-stu-id="4bf97-117">When an HTTP receive adapter processes messages from an HTTP GET request, the receive adapter creates a BizTalk Message object and puts the decoded query string of the HTTP GET request into the BizTalk message body part.</span></span> <span data-ttu-id="4bf97-118">HTTP アダプターは、次のアルゴリズムを使用して BizTalk メッセージのボディ部に配置されているクエリ文字列を選択します。</span><span class="sxs-lookup"><span data-stu-id="4bf97-118">The HTTP adapter selects the query string that is placed into the BizTalk message body part using the following algorithm:</span></span>  
  
-   <span data-ttu-id="4bf97-119">HTTP 受信アダプターが HTTP GET 要求を受け取る、区切り記号として疑問符 (?) 記号を使用して 2 つの部分に、受信 URI 文字列を分割。</span><span class="sxs-lookup"><span data-stu-id="4bf97-119">If the HTTP receive adapter receives an HTTP GET request, it splits the incoming URI string into two parts, using the question mark (?) symbol as a delimiter.</span></span>  
  
-   <span data-ttu-id="4bf97-120">疑問符 () 区切り記号の前に、の部分である URI 文字列の最初の部分がコピーされる、 **InboundTransportLocation**メッセージ コンテキストのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="4bf97-120">The first part of the URI string, the part before the question mark delimiter, is copied into the **InboundTransportLocation** property on the message context.</span></span> <span data-ttu-id="4bf97-121">**InboundTransportLocation**プロパティは、BizTalk Server がメッセージを受信する場所を一意に識別します。</span><span class="sxs-lookup"><span data-stu-id="4bf97-121">The **InboundTransportLocation** property uniquely identifies the location where BizTalk Server received the message.</span></span> <span data-ttu-id="4bf97-122">エンジンでは、このプロパティを使用して、メッセージ対して稼働する受信場所を決定します。</span><span class="sxs-lookup"><span data-stu-id="4bf97-122">The engine uses this property to determine which receive location to run for the message.</span></span>  
  
-   <span data-ttu-id="4bf97-123">HTTP アダプターは、URI 文字列、疑問符 () 区切り記号の後の部品の残りの部分しデコードし、BizTalk メッセージのボディ部にコピーします。</span><span class="sxs-lookup"><span data-stu-id="4bf97-123">The HTTP adapter takes the rest of the URI string, the part after the question mark delimiter, and decodes and copies it into the BizTalk message body part.</span></span>  
  
-   <span data-ttu-id="4bf97-124">空の HTTP GET または HTTP POST 操作が HTTP で受信した場合は、受信アダプター、拒否されます。</span><span class="sxs-lookup"><span data-stu-id="4bf97-124">If an empty HTTP GET or HTTP POST operation is received by the HTTP receive adapter, it is rejected.</span></span>  
  
## <a name="http-receive-adapter-processing-of-a-get-request"></a><span data-ttu-id="4bf97-125">HTTP 受信アダプターの GET 要求の処理</span><span class="sxs-lookup"><span data-stu-id="4bf97-125">HTTP Receive Adapter Processing of a GET Request</span></span>  
 <span data-ttu-id="4bf97-126">HTTP が HTTP GET 要求で受信したアダプター プロセス メッセージを受信する方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4bf97-126">The following are examples of how the HTTP receive adapter processes messages received by HTTP GET requests.</span></span> <span data-ttu-id="4bf97-127">この例では、HTTP 受信アダプターが構成されている次の 2 つの受信場所。</span><span class="sxs-lookup"><span data-stu-id="4bf97-127">These examples assume that the HTTP receive adapter is configured with the following two receive locations:</span></span>  
  
```  
/vroot/BTSHTTPReceive.dll  
/vroot/BTSHTTPReceive.dll?LocationID=1  
```  
  
1.  <span data-ttu-id="4bf97-128">クライアントの次の HTTP GET 要求を指定します。</span><span class="sxs-lookup"><span data-stu-id="4bf97-128">Given the following HTTP GET request for the client:</span></span>  
  
    ```  
    http://servername/vroot/BTSHTTPReceive.dll?LocationID=1  
    ```  
  
     <span data-ttu-id="4bf97-129">実行する操作によって、HTTP 受信アダプターは、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="4bf97-129">The action taken by the HTTP receive adapter is as follows:</span></span>  
  
     <span data-ttu-id="4bf97-130">設定、 **InboundTransportLocation**プロパティを/vroot/BTSHTTPReceive.dll、および BizTalk メッセージ オブジェクト ボディ部を LocationID と等しく、メッセージ コンテキストに 1 を = です。</span><span class="sxs-lookup"><span data-stu-id="4bf97-130">Set the **InboundTransportLocation** property on the message context equal to /vroot/BTSHTTPReceive.dll, and the BizTalk Message object body part equal to LocationID=1.</span></span>  
  
2.  <span data-ttu-id="4bf97-131">クライアントの次の HTTP GET 要求を指定します。</span><span class="sxs-lookup"><span data-stu-id="4bf97-131">Given the following HTTP GET request for the client:</span></span>  
  
    ```  
    http://servername/vroot/BTSHTTPReceive.dll?LocationID=1&MyParam=My%20Value  
    ```  
  
     <span data-ttu-id="4bf97-132">実行する操作によって、HTTP 受信アダプターは、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="4bf97-132">The action taken by the HTTP receive adapter is as follows:</span></span>  
  
     <span data-ttu-id="4bf97-133">設定、 **InboundTransportLocation**プロパティを/vroot/BTSHTTPReceive.dll に、BizTalk メッセージ オブジェクトのボディ部を LocationID = 1 & MyParam = My Value です。</span><span class="sxs-lookup"><span data-stu-id="4bf97-133">Set the **InboundTransportLocation** property equal to /vroot/BTSHTTPReceive.dll, and the BizTalk Message object body part equal to LocationID=1&MyParam=My Value.</span></span>  
  
3.  <span data-ttu-id="4bf97-134">クライアントの次の HTTP GET 要求を指定します。</span><span class="sxs-lookup"><span data-stu-id="4bf97-134">Given the following HTTP GET request for the client:</span></span>  
  
    ```  
    http://servername/vroot/BTSHTTPReceive.dll  
    ```  
  
     <span data-ttu-id="4bf97-135">実行する操作によって、HTTP 受信アダプターは、次のように +。</span><span class="sxs-lookup"><span data-stu-id="4bf97-135">The action taken by the HTTP receive adapter is+ as follows:</span></span>  
  
     <span data-ttu-id="4bf97-136">HTTP GET 要求の形式が誤っているために要求を拒否します。</span><span class="sxs-lookup"><span data-stu-id="4bf97-136">Reject the request due to incorrect formatting of the HTTP GET request.</span></span>  
  
## <a name="batching-support-for-the-http-receive-adapter"></a><span data-ttu-id="4bf97-137">バッチ処理の HTTP 受信アダプタのサポート</span><span class="sxs-lookup"><span data-stu-id="4bf97-137">Batching Support for the HTTP Receive Adapter</span></span>  
 <span data-ttu-id="4bf97-138">HTTP 受信アダプターがバッチ内のサーバーにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="4bf97-138">The HTTP receive adapter submits messages to the server in batches.</span></span> <span data-ttu-id="4bf97-139">HTTP アダプターで構成できるサーバーへのメッセージを送信するために使用するバッチのサイズは受信ハンドラーです。</span><span class="sxs-lookup"><span data-stu-id="4bf97-139">The size of the batch used to submit messages to the server can be configured on the HTTP adapter receive handler.</span></span>  
  
## <a name="http-receive-adapter-support-for-suspending-failed-requests"></a><span data-ttu-id="4bf97-140">失敗した要求を中断する前に HTTP の受信アダプターのサポート</span><span class="sxs-lookup"><span data-stu-id="4bf97-140">HTTP Receive Adapter Support for Suspending Failed Requests</span></span>  
 <span data-ttu-id="4bf97-141">BizTalk Server の HTTP 受信アダプターが構成の設定、**失敗した要求を中断**、受信パイプラインが失敗、マッピング、障害によって着信処理に失敗した場合、HTTP 要求で動作を制御する、またはルーティングに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="4bf97-141">The BizTalk Server HTTP receive adapter has a configuration setting, **Suspend Failed Requests**, to control what happens with an HTTP request if it fails inbound processing due to a receive pipeline failure, a mapping failure, or a routing failure.</span></span> <span data-ttu-id="4bf97-142">設定では、2 つの値があります。</span><span class="sxs-lookup"><span data-stu-id="4bf97-142">The setting has two possible values:</span></span>  
  
-   <span data-ttu-id="4bf97-143">**False です。**</span><span class="sxs-lookup"><span data-stu-id="4bf97-143">**False.**</span></span> <span data-ttu-id="4bf97-144">これが既定の設定です。</span><span class="sxs-lookup"><span data-stu-id="4bf97-144">This is the default setting.</span></span> <span data-ttu-id="4bf97-145">HTTP 受信アダプターでは、受信パイプライン、マッピング エラーの場合、またはルーティングの障害によって着信処理に失敗したメッセージが破棄されます。</span><span class="sxs-lookup"><span data-stu-id="4bf97-145">The HTTP receive adapter discards messages that fail inbound processing due to a receive pipeline failure, a mapping failure, or a routing failure.</span></span> <span data-ttu-id="4bf97-146">さらに、エラー状態コード 401 または 500 は、クライアントに送信されます。</span><span class="sxs-lookup"><span data-stu-id="4bf97-146">Additionally, an error status code 401 or 500 is sent to the client.</span></span> 
  
-   <span data-ttu-id="4bf97-147">**True です。**</span><span class="sxs-lookup"><span data-stu-id="4bf97-147">**True.**</span></span> <span data-ttu-id="4bf97-148">HTTP 受信アダプターは、受信パイプライン、マッピング エラーの場合、またはルーティングの障害によって着信処理に失敗したメッセージを中断します。</span><span class="sxs-lookup"><span data-stu-id="4bf97-148">The HTTP receive adapter suspends messages that fail inbound processing due to a receive pipeline failure, a mapping failure, or a routing failure.</span></span> <span data-ttu-id="4bf97-149">一方向受信ポート、 **Accepted**ステータス コード 202 がクライアントに送信します。</span><span class="sxs-lookup"><span data-stu-id="4bf97-149">For one-way receive ports an **Accepted** status code 202 is sent to the client.</span></span> <span data-ttu-id="4bf97-150">双方向受信ポート、**エラー**状態コード 500 をクライアントに送信します。</span><span class="sxs-lookup"><span data-stu-id="4bf97-150">For two-way receive ports an **Error** status code 500 is sent to the client.</span></span>  
  
## <a name="chunked-encoding-support-for-the-http-receive-adapter"></a><span data-ttu-id="4bf97-151">チャンク エンコードのサポート、http 受信アダプター</span><span class="sxs-lookup"><span data-stu-id="4bf97-151">Chunked Encoding Support for the HTTP Receive Adapter</span></span>  
 <span data-ttu-id="4bf97-152">HTTP 受信アダプターは、チャンク エンコードされたメッセージ本文と HTTP 要求を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="4bf97-152">The HTTP receive adapter accepts HTTP requests with chunked encoded body messages.</span></span> <span data-ttu-id="4bf97-153">チャンク エンコードを使用して本文のサイズが 4 KB を超える場合は、応答メッセージを送信する受信アダプター。</span><span class="sxs-lookup"><span data-stu-id="4bf97-153">The receive adapter uses chunked encoding to send response messages when the body size is larger than 4 KB.</span></span> <span data-ttu-id="4bf97-154">説明した DWORD レジストリ エントリを設定して、オフにすることができますチャンク エンコード[HTTP アダプターの構成およびチューニング パラメーター](../core/http-adapter-configuration-and-tuning-parameters.md)</span><span class="sxs-lookup"><span data-stu-id="4bf97-154">Chunked encoding can be turned off by setting the DWORD registry entry described in [HTTP Adapter Configuration and Tuning Parameters](../core/http-adapter-configuration-and-tuning-parameters.md)</span></span>  
  
## <a name="client-certificates-for-the-http-receive-adapter"></a><span data-ttu-id="4bf97-155">クライアント証明書を HTTP 受信アダプター</span><span class="sxs-lookup"><span data-stu-id="4bf97-155">Client Certificates for the HTTP Receive Adapter</span></span>  
 <span data-ttu-id="4bf97-156">クライアント証明書でセキュリティで保護された接続が使用されるたびに、HTTP 受信場所、HTTP 受信アダプターは、取得、クライアント証明書の拇印から Microsoft インターネット インフォメーション サービス (IIS) と、すべてのメッセージのメッセージ コンテキストに追加しますその場所で HTTPS 経由で受信します。</span><span class="sxs-lookup"><span data-stu-id="4bf97-156">Whenever a secure connection with a client certificate is used for the HTTP receive location, the HTTP receive adapter obtains the client certificate thumbprint from Microsoft Internet Information Services (IIS) and adds it to the message context of all messages that were received over HTTPS on that location.</span></span> <span data-ttu-id="4bf97-157">HTTP は、アダプター セットの次のシステム プロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4bf97-157">The HTTP receive adapter sets the following system properties:</span></span>  
  
```  
SourcePartyEvidenceQualifier = "Certificate"  
SourcePartyEvidence = <certificate thumbprint>  
```  
  
## <a name="status-codes-returned-by-the-http-receive-adapter"></a><span data-ttu-id="4bf97-158">HTTP によって返されるステータス コードの受信アダプター</span><span class="sxs-lookup"><span data-stu-id="4bf97-158">Status Codes Returned by the HTTP Receive Adapter</span></span>  
 <span data-ttu-id="4bf97-159">次の一覧には、状態が含まれています。 受信アダプターを、HTTP によって返されるコード。</span><span class="sxs-lookup"><span data-stu-id="4bf97-159">The following list contains status codes returned by the HTTP receive adapter.</span></span>  
  
-   <span data-ttu-id="4bf97-160">**200 OK をクリックします。**</span><span class="sxs-lookup"><span data-stu-id="4bf97-160">**200 OK.**</span></span> <span data-ttu-id="4bf97-161">正常に、アダプターは、要求メッセージを処理し、応答を生成します。</span><span class="sxs-lookup"><span data-stu-id="4bf97-161">The adapter successfully processed the request message and generated a response.</span></span> <span data-ttu-id="4bf97-162">アダプターは、HTTP 応答で HTTP 要求-応答ポートからこの状態コードを返します。</span><span class="sxs-lookup"><span data-stu-id="4bf97-162">The adapter returns this status code on the HTTP response from the HTTP request-response port.</span></span>  
  
-   <span data-ttu-id="4bf97-163">**202 メッセージが受け入れられます。**</span><span class="sxs-lookup"><span data-stu-id="4bf97-163">**202 Message Accepted.**</span></span> <span data-ttu-id="4bf97-164">アダプターがサーバーへのメッセージを正常に送信されたり、一方向の要求が中断されました。</span><span class="sxs-lookup"><span data-stu-id="4bf97-164">The adapter successfully submitted the message into the server or a one-way request is suspended.</span></span> <span data-ttu-id="4bf97-165">アダプターは、一方向 HTTP 受信ポートからの HTTP 応答でこの状態コードを返します。</span><span class="sxs-lookup"><span data-stu-id="4bf97-165">The adapter returns this status code on the HTTP response from a one way HTTP receive port.</span></span>  
  
-   <span data-ttu-id="4bf97-166">**401 アクセス拒否されました。**</span><span class="sxs-lookup"><span data-stu-id="4bf97-166">**401 Access Denied.**</span></span> <span data-ttu-id="4bf97-167">HTTP 要求を受信した認証要求の受信ポートとセキュリティ チェックをそのメッセージが失敗しました。</span><span class="sxs-lookup"><span data-stu-id="4bf97-167">The HTTP request is received on an authentication-required receive port and the security check for that message failed.</span></span> <span data-ttu-id="4bf97-168">たとえば、パーティが解決されませんでしたやメッセージは解読されませんでした。</span><span class="sxs-lookup"><span data-stu-id="4bf97-168">For example, the party was not resolved or the message was not decrypted.</span></span>  
  
-   <span data-ttu-id="4bf97-169">**500 内部サーバー エラーです。**</span><span class="sxs-lookup"><span data-stu-id="4bf97-169">**500 Internal Server Error.**</span></span> <span data-ttu-id="4bf97-170">HTTP 要求を処理する一般的なエラー。</span><span class="sxs-lookup"><span data-stu-id="4bf97-170">A general failure to process the HTTP request.</span></span> <span data-ttu-id="4bf97-171">しない限り、BizTalk Server によって、メッセージが中断されていない構成設定**失敗した要求を中断**に設定されている**True**双方向の受信ポート。</span><span class="sxs-lookup"><span data-stu-id="4bf97-171">The message is not suspended by BizTalk Server unless the configuration setting **Suspend Failed Requests** is set to **True** for a two-way receive port.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bf97-172">参照</span><span class="sxs-lookup"><span data-stu-id="4bf97-172">See Also</span></span>  
 [<span data-ttu-id="4bf97-173">HTTP アダプター</span><span class="sxs-lookup"><span data-stu-id="4bf97-173">HTTP Adapter</span></span>](../core/http-adapter.md)