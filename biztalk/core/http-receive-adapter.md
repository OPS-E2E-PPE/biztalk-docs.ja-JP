---
title: "HTTP 受信アダプター |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- certificates, HTTP adapters
- HTTP adapters, client certificates
- HTTP adapters, POST requests
- HTTP adapters, GET requests
- HTTP adapters, batching
- HTTP adapters, suspending failed requests
- HTTP adapters, chunked encoding
- messages, batching
- HTTP GET requests, about HTTP GET requests
- HTTP GET requests, process flow
- batching, messages
- HTTP adapters, process flow
- HTTP POST requests
- HTTP adapters, status codes
- chuncked encoding, receive adapters
- HTTP GET requests
- batching, HTTP adapters
ms.assetid: 9008833c-5a02-4fb4-a43e-09ca28a21eff
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ed0c24184d35a836435db3a09202551b7b50ddd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="http-receive-adapter"></a>HTTP 受信アダプター
HTTP 受信アダプターの受信場所は、BizTalk Server 管理コンソールで構成された個別の URL です。  
  
 HTTP 受信アダプターは、クライアントからの非同期送信用にも同期送信用にも構成できます。 非同期送信は一方向の送信、同期通信は双方向または要求 - 応答の送信です。  
  
 受信要求の認証および承認には、IIS セキュリティを使用します。  
  
## <a name="http-get-and-http-post-requests"></a>HTTP GET 要求および HTTP POST 要求  
 HTTP 受信アダプターは、次の 2 つの異なる方法でメッセージを受信することができます、HTTP POST 要求または HTTP GET 要求でします。  
  
 HTTP 受信アダプターが HTTP POST 要求でメッセージを取得すると、次のような一連のイベントが発生します。  
  
1.  BizTalk Server で構成された URL は、受信場所で新しいメッセージを受信します。  
  
2.  受信アダプターは、メッセージをサーバーに送信できるように、BizTalk メッセージ オブジェクトを作成します。  
  
3.  受信アダプターは、1 つだけの部分を含む BizTalk メッセージ オブジェクトを作成する — ボディ部。  
  
4.  メッセージの読み取りおよびサーバーへの送信が正常に完了した後、HTTP 受信アダプターからクライアントに、要求が受理されたことを示す HTTP コード 202 が返されます。  
  
     必要に応じて、HTTP 受信アダプターは、HTTP 応答でメッセージの関連付けトークンを送信できます。 この関連付けトークンは、BizTalk Server 内のメッセージを表します。 HTTP 受信場所が要求 - 応答のポートの場合、アダプターから、応答メッセージと共に成功コード 200 が返されます。  
  
 HTTP 受信アダプターで HTTP GET 要求からのメッセージを処理する場合、受信アダプターによって、BizTalk メッセージ オブジェクトが作成され、HTTP GET 要求のデコードされたクエリ文字列が BizTalk メッセージのボディ部に配置されます。 HTTP アダプターは、次のアルゴリズムを使用して、BizTalk メッセージのボディ部に配置されるクエリ文字列を選択します。  
  
-   HTTP 受信アダプターで HTTP GET 要求を受信する場合、受信 URI 文字列を 2 つに分割します。その際、区切り記号として疑問符 (?) を使用します。  
  
-   疑問符 (?) の区切り記号の前に、の部分であり、URI 文字列の最初の部分にコピーされます、 **InboundTransportLocation**メッセージ コンテキストのプロパティです。 **InboundTransportLocation**プロパティは、BizTalk Server がメッセージを受信場所を一意に識別します。 エンジンは、このプロパティを使用して、メッセージ対して稼働する受信場所を判別します。  
  
-   HTTP アダプターは、残りの URI 文字列、つまり、区切り記号である疑問符より後の部分を取得し、デコードして BizTalk メッセージのボディ部にコピーします。  
  
-   空の HTTP GET または HTTP POST 操作は、HTTP 受信アダプターで受信されると、拒否されます。  
  
## <a name="http-receive-adapter-processing-of-a-get-request"></a>HTTP 受信アダプターによる GET 要求の処理  
 HTTP GET 要求が受け取ったメッセージを HTTP 受信アダプターで処理する方法の例を次に示します。 この例では、HTTP 受信アダプターが次の 2 つの受信場所で構成されていると想定しています。  
  
```  
/vroot/BTSHTTPReceive.dll  
/vroot/BTSHTTPReceive.dll?LocationID=1  
```  
  
1.  クライアントは次の HTTP GET 要求を受け取ります。  
  
    ```  
    http://servername/vroot/BTSHTTPReceive.dll?LocationID=1  
    ```  
  
     HTTP 受信アダプターによって行われる操作は次のとおりです。  
  
     設定、 **InboundTransportLocation**プロパティを/vroot/BTSHTTPReceive.dll に設定し、BizTalk メッセージ オブジェクト ボディ部を LocationID 等しいメッセージ コンテキストで 1 を = です。  
  
2.  クライアントは次の HTTP GET 要求を受け取ります。  
  
    ```  
    http://servername/vroot/BTSHTTPReceive.dll?LocationID=1&MyParam=My%20Value  
    ```  
  
     HTTP 受信アダプターによって行われる操作は次のとおりです。  
  
     設定、 **InboundTransportLocation**プロパティを/vroot/BTSHTTPReceive.dll に設定し、BizTalk メッセージ オブジェクトのボディ部を LocationID = 1 & MyParam = My Value です。  
  
3.  クライアントは次の HTTP GET 要求を受け取ります。  
  
    ```  
    http://servername/vroot/BTSHTTPReceive.dll  
    ```  
  
     実行する操作によって、HTTP 受信アダプターは、次のように +。  
  
     HTTP GET 要求の形式が誤っているため、要求を拒否します。  
  
## <a name="batching-support-for-the-http-receive-adapter"></a>HTTP 受信アダプターのバッチ処理のサポート  
 HTTP 受信アダプターは、メッセージをバッチ単位でサーバーに送信します。 サーバーへのメッセージ送信に使用されるバッチのサイズは、HTTP アダプターの受信ハンドラーで構成できます。  
  
## <a name="http-receive-adapter-support-for-suspending-failed-requests"></a>HTTP 受信アダプターによる、失敗した要求の中断のサポート  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP 受信アダプターが構成の設定、**失敗した要求の中断**マッピングの失敗が、受信パイプライン障害によって着信処理が失敗した場合は、HTTP 要求の動作を制御する、またはルーティングに失敗しました。 この設定には、次の 2 つの有効値があります。  
  
-   **場合は false。** これが既定の設定です。 HTTP 受信アダプターは、受信パイプライン、マッピング、またはルーティングの障害によって受信処理に失敗したメッセージを破棄します。 さらに、エラー状態コード 401 または 500 をクライアントに送信します。 これは、[!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)] の HTTP 受信アダプターと同じ動作です。  
  
-   **True です。** HTTP 受信アダプターは、受信パイプライン、マッピング、またはルーティングの障害によって着信処理に失敗したメッセージを中断します。 一方向受信ポート、 **Accepted**ステータス コード 202 がクライアントに送信します。 双方向受信ポート、**エラー**ステータス コード 500 をクライアントに送信します。  
  
## <a name="chunked-encoding-support-for-the-http-receive-adapter"></a>HTTP 受信アダプターのチャンク エンコードのサポート  
 HTTP 受信アダプターは、チャンク エンコードされたメッセージ本文を含む HTTP 要求を受け入れます。 受信アダプターでは、本文のサイズが 4 KB を超えると、チャンク エンコードを使用して応答メッセージを送信します。 説明した DWORD レジストリ エントリを設定して、オフにすることができますチャンク エンコード[HTTP アダプタの構成およびチューニング パラメータ](../core/http-adapter-configuration-and-tuning-parameters.md)  
  
## <a name="client-certificates-for-the-http-receive-adapter"></a>HTTP 受信アダプターのクライアント証明書  
 クライアント証明書とのセキュリティで保護された接続が HTTP 受信場所に使用されるたびに、HTTP 受信アダプターは、Microsoft インターネット インフォメーション サービス (IIS) からクライアント証明書の拇印を取得して、その場所で HTTPS 経由で受信したすべてのメッセージのメッセージ コンテキストに追加します。 HTTP 受信アダプターでは、次のシステム プロパティを設定します。  
  
```  
SourcePartyEvidenceQualifier = "Certificate"  
SourcePartyEvidence = <certificate thumbprint>  
```  
  
## <a name="status-codes-returned-by-the-http-receive-adapter"></a>HTTP 受信アダプターによって返される状態コード  
 次の一覧に、HTTP 受信アダプターによって返される状態コードを示します。  
  
-   **200 OK します。** アダプターは、正常に要求メッセージを処理して応答を生成しました。 アダプターは、HTTP 要求 - 応答ポートからの HTTP 応答でこの状態コードを返します。  
  
-   **202 メッセージが受け入れられます。** アダプターがメッセージをサーバーに正常に送信したか、一方向の要求が保留されました。 アダプターは、一方向の HTTP 受信ポートからの HTTP 応答でこの状態コードを返します。  
  
-   **401 アクセスが拒否されました。** HTTP 要求は認証が必要な受信ポートで受信され、そのメッセージのセキュリティ チェックに失敗しました。 たとえば、パーティが解決されなかったり、メッセージの暗号化が解除されていません。  
  
-   **500 内部サーバー エラーです。** HTTP 要求を処理する際に一般エラーが発生しました。 しない限り、BizTalk Server でメッセージが中断されていない構成設定**失敗した要求の中断**に設定されている**True**双方向の受信ポート。  
  
## <a name="see-also"></a>参照  
 [HTTP アダプター](../core/http-adapter.md)