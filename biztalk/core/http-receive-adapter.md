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
# <a name="http-receive-adapter"></a>HTTP 受信アダプター
HTTP 受信アダプターの受信場所では、BizTalk Server 管理コンソールで構成された個別の URL です。  
  
 HTTP を構成するクライアントから非同期の送信または同期送信アダプターを受信します。 非同期送信は一方向の送信と同期通信は 2 つの方法または要求-応答送信します。  
  
 受信要求の認証と承認の IIS のセキュリティを使用するとします。  
  
## <a name="http-get-and-http-post-requests"></a>HTTP GET と HTTP POST 要求  
 HTTP 受信アダプターは 2 つの方法でメッセージを受信することができます: HTTP POST 要求または HTTP GET 要求でします。  
  
 HTTP は受信アダプター、HTTP POST 要求でメッセージを取得、次の一連のイベントが発生します。  
  
1. BizTalk Server で構成されている URL では、受信場所で新しいメッセージを受信します。  
  
2. 受信アダプターは、サーバーにメッセージを送信できるように、BizTalk メッセージ オブジェクトを作成します。  
  
3. 受信アダプターが 1 つだけの一部で、BizTalk メッセージ オブジェクトを作成します-ボディ部。  
  
4. メッセージが読み取りおよびサーバーに正常に送信された後、HTTP の受信要求が受理されたことを示すクライアントに HTTP コード 202 がバックアップ アダプターは。  
  
    必要に応じて、HTTP の受信アダプターは、HTTP 応答でメッセージの関連付けトークンを送信することができます。 この関連付けトークンでは、BizTalk Server 内でメッセージを表します。 場合は、HTTP 受信場所が要求-応答ポートでは、アダプターは、応答メッセージと共に成功コード 200 を返します。  
  
   ときに、HTTP アダプター プロセスから受信したメッセージを HTTP GET 要求、受信アダプターは BizTalk メッセージ オブジェクトを作成し、BizTalk メッセージのボディ部に HTTP GET 要求のデコードされたクエリ文字列を格納します。 HTTP アダプターは、次のアルゴリズムを使用して BizTalk メッセージのボディ部に配置されているクエリ文字列を選択します。  
  
-   HTTP 受信アダプターが HTTP GET 要求を受け取る、区切り記号として疑問符 (?) 記号を使用して 2 つの部分に、受信 URI 文字列を分割。  
  
-   疑問符 () 区切り記号の前に、の部分である URI 文字列の最初の部分がコピーされる、 **InboundTransportLocation**メッセージ コンテキストのプロパティ。 **InboundTransportLocation**プロパティは、BizTalk Server がメッセージを受信する場所を一意に識別します。 エンジンでは、このプロパティを使用して、メッセージ対して稼働する受信場所を決定します。  
  
-   HTTP アダプターは、URI 文字列、疑問符 () 区切り記号の後の部品の残りの部分しデコードし、BizTalk メッセージのボディ部にコピーします。  
  
-   空の HTTP GET または HTTP POST 操作が HTTP で受信した場合は、受信アダプター、拒否されます。  
  
## <a name="http-receive-adapter-processing-of-a-get-request"></a>HTTP 受信アダプターの GET 要求の処理  
 HTTP が HTTP GET 要求で受信したアダプター プロセス メッセージを受信する方法の例を次に示します。 この例では、HTTP 受信アダプターが構成されている次の 2 つの受信場所。  
  
```  
/vroot/BTSHTTPReceive.dll  
/vroot/BTSHTTPReceive.dll?LocationID=1  
```  
  
1.  クライアントの次の HTTP GET 要求を指定します。  
  
    ```  
    http://servername/vroot/BTSHTTPReceive.dll?LocationID=1  
    ```  
  
     実行する操作によって、HTTP 受信アダプターは、次のようにします。  
  
     設定、 **InboundTransportLocation**プロパティを/vroot/BTSHTTPReceive.dll、および BizTalk メッセージ オブジェクト ボディ部を LocationID と等しく、メッセージ コンテキストに 1 を = です。  
  
2.  クライアントの次の HTTP GET 要求を指定します。  
  
    ```  
    http://servername/vroot/BTSHTTPReceive.dll?LocationID=1&MyParam=My%20Value  
    ```  
  
     実行する操作によって、HTTP 受信アダプターは、次のようにします。  
  
     設定、 **InboundTransportLocation**プロパティを/vroot/BTSHTTPReceive.dll に、BizTalk メッセージ オブジェクトのボディ部を LocationID = 1 & MyParam = My Value です。  
  
3.  クライアントの次の HTTP GET 要求を指定します。  
  
    ```  
    http://servername/vroot/BTSHTTPReceive.dll  
    ```  
  
     実行する操作によって、HTTP 受信アダプターは、次のように +。  
  
     HTTP GET 要求の形式が誤っているために要求を拒否します。  
  
## <a name="batching-support-for-the-http-receive-adapter"></a>バッチ処理の HTTP 受信アダプタのサポート  
 HTTP 受信アダプターがバッチ内のサーバーにメッセージを送信します。 HTTP アダプターで構成できるサーバーへのメッセージを送信するために使用するバッチのサイズは受信ハンドラーです。  
  
## <a name="http-receive-adapter-support-for-suspending-failed-requests"></a>失敗した要求を中断する前に HTTP の受信アダプターのサポート  
 BizTalk Server の HTTP 受信アダプターが構成の設定、**失敗した要求を中断**、受信パイプラインが失敗、マッピング、障害によって着信処理に失敗した場合、HTTP 要求で動作を制御する、またはルーティングに失敗しました。 設定では、2 つの値があります。  
  
-   **False です。** これが既定の設定です。 HTTP 受信アダプターでは、受信パイプライン、マッピング エラーの場合、またはルーティングの障害によって着信処理に失敗したメッセージが破棄されます。 さらに、エラー状態コード 401 または 500 は、クライアントに送信されます。 
  
-   **True です。** HTTP 受信アダプターは、受信パイプライン、マッピング エラーの場合、またはルーティングの障害によって着信処理に失敗したメッセージを中断します。 一方向受信ポート、 **Accepted**ステータス コード 202 がクライアントに送信します。 双方向受信ポート、**エラー**状態コード 500 をクライアントに送信します。  
  
## <a name="chunked-encoding-support-for-the-http-receive-adapter"></a>チャンク エンコードのサポート、http 受信アダプター  
 HTTP 受信アダプターは、チャンク エンコードされたメッセージ本文と HTTP 要求を受け入れます。 チャンク エンコードを使用して本文のサイズが 4 KB を超える場合は、応答メッセージを送信する受信アダプター。 説明した DWORD レジストリ エントリを設定して、オフにすることができますチャンク エンコード[HTTP アダプターの構成およびチューニング パラメーター](../core/http-adapter-configuration-and-tuning-parameters.md)  
  
## <a name="client-certificates-for-the-http-receive-adapter"></a>クライアント証明書を HTTP 受信アダプター  
 クライアント証明書でセキュリティで保護された接続が使用されるたびに、HTTP 受信場所、HTTP 受信アダプターは、取得、クライアント証明書の拇印から Microsoft インターネット インフォメーション サービス (IIS) と、すべてのメッセージのメッセージ コンテキストに追加しますその場所で HTTPS 経由で受信します。 HTTP は、アダプター セットの次のシステム プロパティが表示されます。  
  
```  
SourcePartyEvidenceQualifier = "Certificate"  
SourcePartyEvidence = <certificate thumbprint>  
```  
  
## <a name="status-codes-returned-by-the-http-receive-adapter"></a>HTTP によって返されるステータス コードの受信アダプター  
 次の一覧には、状態が含まれています。 受信アダプターを、HTTP によって返されるコード。  
  
-   **200 OK をクリックします。** 正常に、アダプターは、要求メッセージを処理し、応答を生成します。 アダプターは、HTTP 応答で HTTP 要求-応答ポートからこの状態コードを返します。  
  
-   **202 メッセージが受け入れられます。** アダプターがサーバーへのメッセージを正常に送信されたり、一方向の要求が中断されました。 アダプターは、一方向 HTTP 受信ポートからの HTTP 応答でこの状態コードを返します。  
  
-   **401 アクセス拒否されました。** HTTP 要求を受信した認証要求の受信ポートとセキュリティ チェックをそのメッセージが失敗しました。 たとえば、パーティが解決されませんでしたやメッセージは解読されませんでした。  
  
-   **500 内部サーバー エラーです。** HTTP 要求を処理する一般的なエラー。 しない限り、BizTalk Server によって、メッセージが中断されていない構成設定**失敗した要求を中断**に設定されている**True**双方向の受信ポート。  
  
## <a name="see-also"></a>参照  
 [HTTP アダプター](../core/http-adapter.md)