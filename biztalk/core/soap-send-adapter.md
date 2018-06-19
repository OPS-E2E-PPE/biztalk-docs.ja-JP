---
title: SOAP 送信アダプタ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4d65218d-516b-4e45-a824-272ef6ef298c
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f59babb164458f7a5d072809d038fb253482553d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278858"
---
# <a name="soap-send-adapter"></a>SOAP 送信アダプタ
SOAP 送信アダプタは、Web サービスを呼び出すときに使用します。 SOAP 送信アダプタは、BizTalk メッセージ オブジェクトのメッセージ コンテキストを読み取ってプロキシ名を取得し、関連付けられた外部の Web サービス プロキシを呼び出します。  
  
## <a name="client-authentication-for-the-soap-send-adapter"></a>SOAP 送信アダプタのクライアント認証  
 SOAP 送信アダプタは、送信先のサーバーでの認証に、次のいずれかの認証の種類を使用します。  
  
-   **匿名です。** 既定の設定です。  
  
-   **基本的な。** SOAP 接続で、プレーンテキストでユーザー名とパスワードを送信します。  
  
-   **ダイジェストします。** SOAP 接続で、暗号化形式でユーザー名とパスワードを送信します。  
  
-   **Kerberos または NTLM。** ユーザー名もパスワードも、SOAP 接続経由では送信されません。 SOAP アダプタは常に、SOAP 送信アダプタがこの認証の種類に対して実行するプロセスの資格情報を使用します。  
  
 また、SOAP 送信アダプタでは、Web サーバーでクライアントの Secure Sockets Layer (SSL) 証明書を必要としているか受け付ける場合に、Web サーバーに SSL 証明書を提供できます。  
  
 SOAP 送信アダプタへの要求にメッセージを受信すると、エンタープライズ シングル サインオン (SSO) が有効な場合、 **SSOTicket**プロパティ、アダプターが、SSO サーバーを検証し、チケットを引き換えるに接続します。 チケットの検証後、チケットは解読され、関連システムの資格情報が資格情報ストアから取得されます。 その後、SOAP アダプタが資格情報を使用して関連システムに接続し、SOAP 要求が処理されます。  
  
## <a name="client-certificates-for-the-soap-send-adapter"></a>SOAP 送信アダプタのクライアント証明書  
 SOAP 送信アダプタでは、クライアント証明書を受け付けるか必要とするサーバー間に、セキュリティで保護された接続を確立できます。 クライアント証明書を指定した場合、SOAP 送信アダプタではクライアント証明書を必要とするか受け付けるサーバーに接続するときに、この証明書を使用します。 クライアント証明書を指定しなかった場合に、送信先のサーバーでクライアント証明書が要求されると、SOAP 送信アダプタはメッセージの送信に失敗し、標準の再試行ロジックが実行されます。  
  
 SOAP 送信アダプターでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] プロセスの実行に使用されているアカウントの個人用ストアにあるクライアント証明書を使用します。 SOAP アダプタは拇印によって証明書を特定します。 SOAP 送信アダプタによる証明書の読み込みが何らかの理由で失敗した場合、送信中だったメッセージは中断されます。  
  
## <a name="negative-acknowledgement-nack-messages-generated-for-failed-transmissions-by-the-http-or-soap-adapters"></a>HTTP アダプタまたは SOAP アダプタによる送信が失敗した場合に生成される否定受信確認 (NACK) メッセージ  
 配信通知を有効にしている場合、メッセージが正常に送信されると、BizTalk メッセージング エンジンからメッセージ ボックス データベースに、関連付けられた受信確認 (ACK) メッセージがパブリッシュされます。 同様に、BizTalk メッセージング エンジンによってメッセージが中断されたり、オーケストレーション エンジンによってオーケストレーションが中断された場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は関連付けられた否定受信確認 (NACK) メッセージを MessageBox にパブリッシュします。 NACK メッセージには、コンテキスト プロパティおよび SOAP エラーで構成されるメッセージのボディ部が含まれます。 NACK メッセージが生成される場合、HTTP アダプタまたは SOAP アダプタから送信が失敗したため、SOAP エラーを含む、**ヘッダー**要素および**本文**発行先の Web からの応答の要素サーバー。 SOAP 送信が失敗した場合に生成される NACK の SOAP エラーの例を次に示します。  
  
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
>  **ヘッダー**要素および**本文**要素は 48 KB に制限されます。 **ヘッダー**要素は、上限を超えずに最も近いの完全なヘッダー値のペアに丸められます。 **本文**要素は 48 KB に切り捨てられます。  
  
> [!NOTE]
>  NACK メッセージと ACK メッセージは、それらのメッセージに一致するサブスクリプションがなければ破棄されます。 これらのメッセージがメッセージング エンジンによって中断されることはありません。  
  
 NACK メッセージをサブスクライブするには、次のいずれかの操作を実行します。  
  
1.  適切なメッセージ コンテキスト プロパティのフィルタを含む送信ポートを作成します。 参照してください**メッセージ コンテキスト プロパティ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]システム メッセージ コンテキスト プロパティの一覧については、関連する警告などメッセージの受信確認します。  
  
2.  マークされたオーケストレーション ポートから送信**配信通知 = 送信済み**です。 オーケストレーション ポートが付いている場合**配信通知 = 送信済み**オーケストレーションは ACK または送信されたメッセージの NACK を受信するまで待機します。 NACK が生成された場合、NACK はオーケストレーションにルーティングされ、オーケストレーションからは DeliveryFailureException がスローされます。 DeliveryFailureException は、NACK メッセージ本文に含まれている SOAP エラーからシリアル化解除されます。 オーケストレーションに返された SOAP エラーから例外メッセージ文字列を取得するには、DeliveryFailureException を SoapException にキャストし、SOAP の Detail セクションから InnerXml にアクセスします。 この処理を行うためのコード例を次に示します。  
  
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
 [SOAP アダプターとは何ですか。](../core/what-is-the-soap-adapter.md)   
 [SOAP アダプタのセキュリティに関する推奨事項](../core/soap-adapter-security-recommendations.md)