---
title: SOAP 送信アダプタ |Microsoft Docs
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
ms.openlocfilehash: 7bd63c7ad8c121cbbaf086be4bff9dd1fbc1becc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244360"
---
# <a name="soap-send-adapter"></a>SOAP 送信アダプタ
Web サービスを呼び出すには、SOAP 送信アダプタを使用します。 SOAP 送信アダプタは、メッセージ コンテキストをプロキシの名前を取得する BizTalk メッセージ オブジェクトを読み取って、関連付けられている外部 Web サービス プロキシを呼び出します。  
  
## <a name="client-authentication-for-the-soap-send-adapter"></a>クライアント認証、soap 送信アダプター  
 SOAP 送信アダプタは、次の認証の種類のいずれかを使用して、移行先サーバーで認証を行います。  
  
- **匿名です。** 既定の設定です。  
  
- **基本的な。** SOAP 接続で、プレーンテキストでユーザー名とパスワードを送信します。  
  
- **ダイジェスト。** SOAP 接続では、暗号化された形式でユーザー名とパスワードを送信します。  
  
- **Kerberos または NTLM。** ユーザー名もパスワードも、SOAP 接続経由では送信されません。 SOAP アダプタは常に、SOAP 送信アダプタがこの認証の種類に対して実行するプロセスの資格情報を使用します。  
  
  さらに、SOAP 送信アダプタできるクライアント、Web サーバーに Secure Sockets Layer (SSL) 証明書、サーバーが必要ですか受け付ける場合。  
  
  SOAP 送信アダプタへの要求にメッセージを受信すると、エンタープライズ シングル サインオン (SSO) を有効にした場合、 **SSOTicket**プロパティ、アダプターは、検証し、チケットを引き換えるには、SSO サーバーに接続します。 SOAP アダプターが、チケットを検証した後は復号化し、関連システムの資格情報は、資格情報ストアから取得されます。 SOAP アダプターは、関連システムに接続する資格情報を使用し、SOAP 要求が処理されます。  
  
## <a name="client-certificates-for-the-soap-send-adapter"></a>クライアント証明書を SOAP 送信アダプター  
 SOAP 送信アダプタを受け付けるか、クライアント証明書を必要とするサーバーをセキュリティで保護された接続を確立できます。 クライアント証明書を指定する場合、SOAP 送信アダプタが使用、証明書を必要とするか、クライアント証明書をそのまま使用するサーバーに接続するときにします。 クライアント証明書を指定しない、移行先サーバーにクライアント証明書が必要な場合は、SOAP 送信アダプターがメッセージの送信に失敗して、標準の再試行ロジックに従っています。  
  
 SOAP 送信アダプタのクライアント証明書を使用するアカウントの個人用ストア、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロセスが実行されています。 SOAP アダプターでは、その拇印によって証明書を指定します。 SOAP 送信アダプタは、何らかの理由で証明書の読み込みに失敗した場合、送信中だったメッセージは中断されます。  
  
## <a name="negative-acknowledgement-nack-messages-generated-for-failed-transmissions-by-the-http-or-soap-adapters"></a>HTTP アダプタまたは SOAP アダプタによる送信の失敗の生成される否定受信確認 (NACK) メッセージ  
 メッセージの送信が正常にとき、BizTalk メッセージング エンジンは配信通知が有効になっている場合、メッセージ ボックス データベースに関連付けられた受信確認 (ACK) メッセージを公開します。 同様に、BizTalk メッセージング エンジンによってメッセージが中断またはと、オーケストレーション エンジンによってオーケストレーションが中断された[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージ ボックスに関連付けられた否定受信確認 (NACK) メッセージがパブリッシュされます。 NACK メッセージには、コンテキスト プロパティと SOAP エラーで構成されるメッセージのボディ部が含まれています。 SOAP エラーを含む場合は、HTTP または SOAP アダプターの送信に失敗したためには、NACK メッセージが生成、**ヘッダー**要素と**本文**先 Web からの応答の要素サーバー。 SOAP 送信に失敗したに対して生成される NACK の SOAP エラーの例を次に示します。  
  
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
>  **ヘッダー**要素と**本文**要素は 48 KB に制限されています。 **ヘッダー**要素は、制限を超えないサイズの最も近いの完全なヘッダー値のペアに丸められます。 **本文**要素は 48 KB に切り捨てられます。  
  
> [!NOTE]
>  NACK メッセージと ACK メッセージは、それらのメッセージに一致するサブスクリプションがなければ破棄されます。 これらのメッセージはメッセージング エンジンによって中断されません。  
  
 NACK メッセージをサブスクライブするには、次のいずれかの操作を実行します。  
  
1. 適切なメッセージ コンテキスト プロパティのフィルタを含む送信ポートを作成します。 参照してください**メッセージ コンテキスト プロパティ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]システム メッセージ コンテキスト プロパティの一覧を含めてメッセージの受信確認に関連します。  
  
2. マークされたオーケストレーション ポートから送信**配信通知 = 送信済み**します。 オーケストレーション ポートが付いている場合**配信通知 = 送信済み**オーケストレーションは ACK または NACK に送信されたメッセージを受信するまで待機します。 NACK が生成された場合、NACK はオーケストレーションにルーティングされ、オーケストレーションからは DeliveryFailureException がスローされます。 DeliveryFailureException は、NACK メッセージ本文に含まれている SOAP エラーからシリアル化解除されます。 オーケストレーションに返された SOAP エラーから例外メッセージ文字列を取得するには、DeliveryFailureException を SoapException にキャストし、SOAP の Detail セクションから InnerXml にアクセスします。 この処理を行うためのコード例を次に示します。  
  
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
 [SOAP アダプターのセキュリティに関する推奨事項](../core/soap-adapter-security-recommendations.md)