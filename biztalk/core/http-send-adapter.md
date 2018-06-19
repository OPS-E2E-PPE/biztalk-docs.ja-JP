---
title: HTTP 送信アダプタ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e69308b4-421f-4d7c-b9bb-ee086df03272
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce8bfdfd380fac422f79ba175ae075a94f313dec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257978"
---
# <a name="http-send-adapter"></a>HTTP 送信アダプタ
HTTP 送信アダプターは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] からメッセージを取得して、HTTP POST 要求で送信先 URL に送信します。 メッセージの内容は BizTalk メッセージ オブジェクトのボディ部から取得します。 BizTalk メッセージ オブジェクトの他のすべての部分は無視されます。  
  
 メッセージが送信先の URL に送信され、BizTalk メッセージング エンジンで HTTP 成功状態コードを受け取ると、メッセージはメッセージ ボックス データベースから削除されます。  
  
 HTTP メッセージのリダイレクトがサポートされており、送信ポートに構成できます。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、HTTP 送信アダプターを BizTalk のネイティブ アプリケーションとしてホストします。 HTTP 送信アダプタでは、一方向のメッセージ送信と、送信請求 - 応答の送信をサポートします。 HTTP 送信アダプタの送信場所は、送信ポートで構成する一意の URL です。 この一意の URL には、ベース URL に付加したクエリ文字列を含めることができます。  
  
## <a name="batching-support-for-the-http-send-adapter"></a>HTTP 送信アダプタのバッチ処理のサポート  
 HTTP 送信アダプタは、バッチ操作をサポートしていません。  
  
## <a name="chunked-encoding-support-for-the-http-send-adapter"></a>HTTP 送信アダプタのチャンク エンコードのサポート  
 場合、**有効チャンク エンコード**構成オプションを有効にし、HTTP 送信アダプタは、要求のサイズが 8 KB を超える場合は、チャンク エンコードを使用して要求メッセージを送信します。 HTTP プロキシ サーバーを使用している場合、チャンク エンコードは使用されず、データは常に段階的に処理されてから送信されます。 **有効チャンク エンコード**構成オプションが既定で有効にします。  
  
 送信アダプタで応答メッセージを受信するとき、チャンク エンコードが行われたボディ部を含んだ応答メッセージを受信できます。  
  
## <a name="client-authentication-for-the-http-send-adapter"></a>HTTP 送信アダプタのクライアント認証  
 HTTP 送信アダプタは、送信先のサーバーでの認証に、次のいずれかの認証の種類を使用します。  
  
-   **匿名です。** : 送信先サーバーに接続するとき、資格情報が送信されません。 送信サーバーで匿名認証を許可している場合、送信サーバーで構成されている匿名アカウントの資格情報が使用されます。  
  
-   **基本的な。** : HTTP 接続で、プレーンテキストでユーザー名とパスワードを送信します。  
  
-   **ダイジェストします。** : HTTP 接続で、暗号化形式でパスワードを送信します。  
  
-   **Kerberos。** ユーザー名もパスワードも HTTP 接続で送信されません。 この認証の種類には、HTTP 送信アダプタが実行するプロセスの資格情報が使用されます。  
  
 また、HTTP 送信アダプタでは、Web サーバーでクライアントの Secure Sockets Layer (SSL) 証明書を必要としているか受け付ける場合に、Web サーバーに SSL 証明書を提供できます。  
  
## <a name="client-certificates-for-the-http-send-adapter"></a>HTTP 送信アダプタのクライアント証明書  
 HTTP 送信アダプタでは、クライアント証明書を受け付けるか必要とするサーバー間に、セキュリティで保護された接続を確立できます。 クライアント証明書を指定した場合、HTTP 送信アダプタではクライアント証明書を必要とするか受け付けるサーバーに接続するときに、この証明書を使用します。 クライアント証明書を指定しなかった場合に、送信先のサーバーでクライアント証明書を要求された場合、HTTP 送信アダプタはメッセージの送信に失敗し、標準の再試行ロジックが実行されます。  
  
 HTTP 送信アダプターでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] プロセスの実行に使用されているアカウントの個人用ストアにあるクライアント証明書を使用します。 証明書は拇印によって指定します。 HTTP 送信アダプタによる証明書の読み込みが何らかの理由で失敗した場合、送信中だったメッセージは中断されます。  
  
## <a name="single-sign-on-support-for-the-http-adapter"></a>HTTP アダプタのシングル サインオンのサポート  
 BizTalk 管理コンソールを使用して、HTTP 受信場所または送信ポートで使用するエンタープライズ シングル サインオン (SSO) を構成できます。 ここでは、SSO と HTTP アダプタの連携について説明します。  
  
 **受信場所が、HTTP 用のシングル サインオンのサポート**  
  
 Microsoft インターネット インフォメーション サービス (IIS) では、Web クライアントから HTTP 要求を受信すると、ユーザーを認証します。 ISAPI (Internet Server API) 拡張によって Microsoft Windows ユーザーの権限を借用し、SSO 資格情報ストアを呼び出して、暗号化されたチケットを取得します。 このチケットとして格納されている、 **SSOTicket**メッセージのコンテキストのプロパティです。  
  
 パススルー シナリオでは、BizTalk メッセージング エンジンによって、メッセージ ボックス データベースにメッセージが送信されます。 アダプターは、メッセージ ボックス データベースからメッセージを受信、HTTP アダプターを呼び出す、 **ISSOTicket.RedeemTicket メソッド**からバックエンド資格情報を取得するアプリケーションの名前と共に暗号化されたチケットを使用して、SSO ストア。 その後、外部の資格情報を使用してバックエンド システムに接続し、要求が処理されます。 関連アプリケーションの詳細については、次を参照してください。 [SSO 関連アプリケーション](../core/sso-affiliate-applications.md)です。  
  
 オーケストレーションがアダプタを呼び出すシナリオでは、BizTalk メッセージング エンジンによって、メッセージ ボックス データベースにこのメッセージが送信されます。 オーケストレーションで、ことを確認する必要があります両方、 **SSOTicket**コンテキスト プロパティ、および**Microsoft.BizTalk.XLANGs.BTXEngine.OriginatorSID**チケットを格納するメッセージのコンテキスト プロパティには保持されます。 アダプターでは、このメッセージを受信、メッセージ ボックス データベースから、呼び出し**RedeemTicket**暗号化されたチケットを SSO ストアからバックエンド資格情報を取得します。 スケジュールをデザインするユーザーは、このプロパティをメッセージに明示的にコピーしてください。  
  
 **HTTP 送信アダプター用のシングル サインオンのサポート**  
  
 SSO が有効になっている場合は、受信すると HTTP 送信ポートを含むメッセージ、 **Secure**を検証し、関連アプリケーションのチケットを引き換える SSO サーバーを呼び出し、プロパティ、します。 SSO を呼び出してチケットを引き換える作業は、関連アプリケーションのアプリケーション管理者、関連管理者、または SSO 管理者が行います。 その後、SSO によってチケットが解読され、バックエンド資格情報を取得します。 パススルーおよびオーケストレーションのシナリオは、HTTP 送信ポートのシナリオと同一です。  
  
 既定では HTTP 送信ポートの SSO は無効です。 HTTP 送信ポートの SSO を有効にする方法の詳細については、次を参照してください。 [HTTP 送信ポートを構成する](../core/configuring-an-http-send-port.md)です。  
  
> [!NOTE]
>  シングル サインオンは、基本認証およびダイジェスト認証のみで使用できます。  
  
 HTTP 受信アダプタおよび送信アダプタのシングル サインオンのサポートを正しく実装するには、以下の条件を満たす必要があります。  
  
-   次の場所に、同一のユーザー アカウントを指定する必要があります。  
  
    -   HTTP 受信アダプターで監視している IIS 仮想ディレクトリの、アプリケーション プール ID (IIS 7.0) またはホスト元 COM+ アプリケーションの ID。 HTTP の IIS 構成の詳細については、受信場所を参照してください[HTTP の受信場所の IIS を構成する方法](../core/how-to-configure-iis-for-an-http-receive-location.md)です。  
  
    -   HTTP アダプターで実行されている分離ホスト インスタンスで使用するログオン資格情報。 ホスト インスタンスのログオン資格情報を構成する方法については、次を参照してください。[ホスト インスタンスのプロパティを変更する方法](../core/how-to-modify-host-instance-properties.md)です。  
  
-   HTTP アダプタが使用する分離ホストは、信頼されている認証として構成する必要があります。 信頼されている認証としてホストを構成する方法については、次を参照してください。[ホストのプロパティを変更する方法](../core/how-to-modify-host-properties.md)です。  
  
## <a name="negative-acknowledgment-nack-messages-generated-for-failed-transmissions-by-the-http-or-soap-adapter"></a>HTTP アダプタまたは SOAP アダプタによる送信が失敗した場合に生成される否定受信確認応答 (NACK) メッセージ  
 メッセージの送信が正常に場合、BizTalk メッセージング エンジンは配信通知が有効になっている場合、メッセージ ボックスに、関連付けられた受信確認 (ACK) メッセージを発行します。 同様に、BizTalk メッセージング エンジンによってメッセージが中断されたり、オーケストレーション エンジンによってオーケストレーションが中断された場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] により、関連付けられた否定受信確認応答 (NACK) メッセージがメッセージ ボックスにパブリッシュされます。 NACK メッセージには、コンテキスト プロパティと、SOAP エラーで構成されるメッセージのボディ部が含まれます。 HTTP アダプタまたは SOAP アダプタからの送信に失敗したことが原因で NACK メッセージが生成された場合、SOAP エラーには、送信先の Web サーバーからの応答の Headers 要素および Body 要素が含まれます。 SOAP 送信が失敗した場合に生成される NACK の HTTP エラーの例を次に示します。  
  
```  
<SOAP:Envelope xmlns:SOAP="http://schemas.xmlsoap.org/soap/envelope/" SOAP:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/">  
   <SOAP:Body>  
      <SOAP:Fault>  
         <faultcode>Microsoft BizTalk Server Negative Acknowledgment</faultcode>   
         <faultstring>An error occurred while processing the message, refer to the details section for more information</faultstring>   
         <faultactor>http://localhost/receivestandard.asp</faultactor>   
         <detail>  
            <ns0:NACK Type="NACK" xmlns:ns0="http://schema.microsoft.com/BizTalk/2003/NACKMessage.xsd">  
            <NAckID>{4E646707-03AA-4493-95C7-A64B09E2987D}</NAckID>  
            <ErrorCode>0x80131600</ErrorCode>  
            <ErrorCategory>0</ErrorCategory>  
            <ErrorDescription>The remote server returned an error: (404) Not Found.</ErrorDescription>  
            <ErrorDetail>  
            <HttpErrorDetail xmlns="http://schema.microsoft.com/BizTalk/2006/HttpErrorDetails.xsd">  
               <Headers>Server: Microsoft-IIS/5.1 Date: Wed, 21 Apr 2005 00:27:47 GMT X-Powered-By: ASP.NET Connection: close Content-Type: text/html Content-Length: 67 </Headers>  
               <Body>We could not locate the page you requested. Please check the URL.</Body>  
            </HttpErrorDetail>  
            </ErrorDetail>  
            </ns0:NACK>  
         </detail>  
      </SOAP:Fault>  
   </SOAP:Body>  
</SOAP:Envelope>  
```  
  
> [!NOTE]
>  Headers 要素および Body 要素は、48 KB に制限されています。 Headers 要素は、制限を超えないサイズで、最も完全に近いヘッダー値の組み合わせになるよう丸められます。 Body 要素は 48 KB に切り捨てられます。  
  
> [!NOTE]
>  NACK メッセージと ACK メッセージは、それらのメッセージに一致するサブスクリプションがなければ破棄されます。 これらのメッセージが BizTalk メッセージング エンジンによって中断されることはありません。  
  
 NACK メッセージをサブスクライブするには、次のいずれかの操作を実行します。  
  
-   適切なメッセージ コンテキスト プロパティのフィルタを含む送信ポートを作成します。 参照してください**メッセージ コンテキスト プロパティ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]システム メッセージ コンテキスト プロパティの一覧については、関連する警告などメッセージの受信確認します。  
  
-   マークされたオーケストレーション ポートから送信**配信通知 = 送信済み**です。 オーケストレーション ポートが付いている場合**配信通知 = 送信済み**オーケストレーションは ACK または送信されたメッセージの NACK を受信するまで待機します。 NACK が生成された場合、NACK はオーケストレーションにルーティングされ、オーケストレーションからは DeliveryFailureException がスローされます。 DeliveryFailureException は、NACK メッセージ本文に含まれている SOAP エラーからシリアル化解除されます。 オーケストレーションに返された SOAP エラーから例外メッセージ文字列を取得するには、DeliveryFailureException を SoapException にキャストし、SOAP の Detail セクションから InnerXml にアクセスします。 この処理を行うためのコード例を次に示します。  
  
    ```  
    // Cast the DeliveryFailureException to a SoapException…  
    System.Web.Services.Protocols.SoapException se = (System.Web.Services.Protocols.SoapException)e.InnerException;  
    System.Diagnostics.Trace.WriteLine(se.Detail.InnerXml);  
    //e is an Microsoft.XLANGs.BaseTypes.DeliveryFailureException  
    //object type created in an Exception handler  
  
    ```  
  
     上記のコード例は、次のような XML フラグメントを返します。  
  
    ```  
    <ns0:NACK Type="NACK" xmlns:ns0="http://schema.microsoft.com/BizTalk/2003/NACKMessage.xsd">  
    <NAckID>{4E646707-03AA-4493-95C7-A64B09E2987D}</NAckID>  
    <ErrorCode>0x80131600</ErrorCode>  
    <ErrorCategory>0</ErrorCategory>  
    <ErrorDescription>The remote server returned an error: (404) Not Found.</ErrorDescription>  
    <ErrorDetail>  
    <HttpErrorDetail xmlns="http://schema.microsoft.com/BizTalk/2006/HttpErrorDetails.xsd">  
       <Headers>Server: Microsoft-IIS/5.1 Date: Wed, 21 Apr 2005 00:27:47 GMT X-Powered-By: ASP.NET Connection: close Content-Type: text/html Content-Length: 67 </Headers>  
       <Body>We could not locate the page you requested. Please check the URL.</Body>  
    </HttpErrorDetail>  
    </ErrorDetail>  
    </ns0:NACK>  
    ```  
  
## <a name="see-also"></a>参照  
 [HTTP アダプター](../core/http-adapter.md)  
**SSO の COM オブジェクト**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]