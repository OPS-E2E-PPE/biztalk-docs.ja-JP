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
# <a name="soap-send-adapter"></a><span data-ttu-id="f3695-102">SOAP 送信アダプタ</span><span class="sxs-lookup"><span data-stu-id="f3695-102">SOAP Send Adapter</span></span>
<span data-ttu-id="f3695-103">SOAP 送信アダプタは、Web サービスを呼び出すときに使用します。</span><span class="sxs-lookup"><span data-stu-id="f3695-103">You use the SOAP send adapter to call a Web service.</span></span> <span data-ttu-id="f3695-104">SOAP 送信アダプタは、BizTalk メッセージ オブジェクトのメッセージ コンテキストを読み取ってプロキシ名を取得し、関連付けられた外部の Web サービス プロキシを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="f3695-104">The SOAP send adapter reads the message context on the BizTalk Message object to get the proxy name and calls the associated external Web service proxy.</span></span>  
  
## <a name="client-authentication-for-the-soap-send-adapter"></a><span data-ttu-id="f3695-105">SOAP 送信アダプタのクライアント認証</span><span class="sxs-lookup"><span data-stu-id="f3695-105">Client Authentication for the SOAP Send Adapter</span></span>  
 <span data-ttu-id="f3695-106">SOAP 送信アダプタは、送信先のサーバーでの認証に、次のいずれかの認証の種類を使用します。</span><span class="sxs-lookup"><span data-stu-id="f3695-106">The SOAP send adapter authenticates with the destination server by using one of the following authentication types:</span></span>  
  
-   <span data-ttu-id="f3695-107">**匿名です。**</span><span class="sxs-lookup"><span data-stu-id="f3695-107">**Anonymous.**</span></span> <span data-ttu-id="f3695-108">既定の設定です。</span><span class="sxs-lookup"><span data-stu-id="f3695-108">The default setting.</span></span>  
  
-   <span data-ttu-id="f3695-109">**基本的な。**</span><span class="sxs-lookup"><span data-stu-id="f3695-109">**Basic.**</span></span> <span data-ttu-id="f3695-110">SOAP 接続で、プレーンテキストでユーザー名とパスワードを送信します。</span><span class="sxs-lookup"><span data-stu-id="f3695-110">The SOAP connection sends the user name and password in plain text.</span></span>  
  
-   <span data-ttu-id="f3695-111">**ダイジェストします。**</span><span class="sxs-lookup"><span data-stu-id="f3695-111">**Digest.**</span></span> <span data-ttu-id="f3695-112">SOAP 接続で、暗号化形式でユーザー名とパスワードを送信します。</span><span class="sxs-lookup"><span data-stu-id="f3695-112">The SOAP connection sends the user name and password in an encrypted format.</span></span>  
  
-   <span data-ttu-id="f3695-113">**Kerberos または NTLM。**</span><span class="sxs-lookup"><span data-stu-id="f3695-113">**Kerberos or NTLM.**</span></span> <span data-ttu-id="f3695-114">ユーザー名もパスワードも、SOAP 接続経由では送信されません。</span><span class="sxs-lookup"><span data-stu-id="f3695-114">Neither the user name nor the password is sent over a SOAP connection.</span></span> <span data-ttu-id="f3695-115">SOAP アダプタは常に、SOAP 送信アダプタがこの認証の種類に対して実行するプロセスの資格情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="f3695-115">The SOAP adapter always uses the credentials of the process under which the SOAP send adapter runs for this authentication type.</span></span>  
  
 <span data-ttu-id="f3695-116">また、SOAP 送信アダプタでは、Web サーバーでクライアントの Secure Sockets Layer (SSL) 証明書を必要としているか受け付ける場合に、Web サーバーに SSL 証明書を提供できます。</span><span class="sxs-lookup"><span data-stu-id="f3695-116">Additionally, the SOAP send adapter can provide a client Secure Sockets Layer (SSL) certificate to the Web server if the server requires or accepts it.</span></span>  
  
 <span data-ttu-id="f3695-117">SOAP 送信アダプタへの要求にメッセージを受信すると、エンタープライズ シングル サインオン (SSO) が有効な場合、 **SSOTicket**プロパティ、アダプターが、SSO サーバーを検証し、チケットを引き換えるに接続します。</span><span class="sxs-lookup"><span data-stu-id="f3695-117">If you enabled Enterprise Single Sign-On (SSO), when the SOAP send adapter receives a message with the request to the **SSOTicket** property, the adapter connects to an SSO server to validate and redeem the ticket.</span></span> <span data-ttu-id="f3695-118">チケットの検証後、チケットは解読され、関連システムの資格情報が資格情報ストアから取得されます。</span><span class="sxs-lookup"><span data-stu-id="f3695-118">After the SOAP adapter validates the ticket, it is decrypted and the credentials for the affiliate system are retrieved from the credential store.</span></span> <span data-ttu-id="f3695-119">その後、SOAP アダプタが資格情報を使用して関連システムに接続し、SOAP 要求が処理されます。</span><span class="sxs-lookup"><span data-stu-id="f3695-119">The SOAP adapter then uses the credentials to connect to the affiliate system, and the SOAP request is processed.</span></span>  
  
## <a name="client-certificates-for-the-soap-send-adapter"></a><span data-ttu-id="f3695-120">SOAP 送信アダプタのクライアント証明書</span><span class="sxs-lookup"><span data-stu-id="f3695-120">Client Certificates for the SOAP Send Adapter</span></span>  
 <span data-ttu-id="f3695-121">SOAP 送信アダプタでは、クライアント証明書を受け付けるか必要とするサーバー間に、セキュリティで保護された接続を確立できます。</span><span class="sxs-lookup"><span data-stu-id="f3695-121">The SOAP send adapter can establish a secure connection with servers that accept or require client certificates.</span></span> <span data-ttu-id="f3695-122">クライアント証明書を指定した場合、SOAP 送信アダプタではクライアント証明書を必要とするか受け付けるサーバーに接続するときに、この証明書を使用します。</span><span class="sxs-lookup"><span data-stu-id="f3695-122">If you specify a client certificate, the SOAP send adapter uses the certificate when connecting with servers that require or accept client certificates.</span></span> <span data-ttu-id="f3695-123">クライアント証明書を指定しなかった場合に、送信先のサーバーでクライアント証明書が要求されると、SOAP 送信アダプタはメッセージの送信に失敗し、標準の再試行ロジックが実行されます。</span><span class="sxs-lookup"><span data-stu-id="f3695-123">If you do not specify a client certificate and the destination server requires client certificates, the SOAP send adapter fails to send the message and follows the standard retry logic.</span></span>  
  
 <span data-ttu-id="f3695-124">SOAP 送信アダプターでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] プロセスの実行に使用されているアカウントの個人用ストアにあるクライアント証明書を使用します。</span><span class="sxs-lookup"><span data-stu-id="f3695-124">The SOAP send adapter uses the client certificate from the Personal store of the account under which the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] process is running.</span></span> <span data-ttu-id="f3695-125">SOAP アダプタは拇印によって証明書を特定します。</span><span class="sxs-lookup"><span data-stu-id="f3695-125">The SOAP adapter specifies the certificate by its thumbprint.</span></span> <span data-ttu-id="f3695-126">SOAP 送信アダプタによる証明書の読み込みが何らかの理由で失敗した場合、送信中だったメッセージは中断されます。</span><span class="sxs-lookup"><span data-stu-id="f3695-126">If the SOAP send adapter fails to load the certificate for any reason, the message that it was sending is suspended.</span></span>  
  
## <a name="negative-acknowledgement-nack-messages-generated-for-failed-transmissions-by-the-http-or-soap-adapters"></a><span data-ttu-id="f3695-127">HTTP アダプタまたは SOAP アダプタによる送信が失敗した場合に生成される否定受信確認 (NACK) メッセージ</span><span class="sxs-lookup"><span data-stu-id="f3695-127">Negative Acknowledgement (NACK) Messages Generated for Failed Transmissions by the HTTP or SOAP Adapters</span></span>  
 <span data-ttu-id="f3695-128">配信通知を有効にしている場合、メッセージが正常に送信されると、BizTalk メッセージング エンジンからメッセージ ボックス データベースに、関連付けられた受信確認 (ACK) メッセージがパブリッシュされます。</span><span class="sxs-lookup"><span data-stu-id="f3695-128">When a message is successfully transmitted, the BizTalk Messaging Engine publishes an associated Acknowledgement (ACK) message to the MessageBox database if delivery notifications are enabled.</span></span> <span data-ttu-id="f3695-129">同様に、BizTalk メッセージング エンジンによってメッセージが中断されたり、オーケストレーション エンジンによってオーケストレーションが中断された場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は関連付けられた否定受信確認 (NACK) メッセージを MessageBox にパブリッシュします。</span><span class="sxs-lookup"><span data-stu-id="f3695-129">Likewise, when a message is suspended by the BizTalk Messaging Engine or an orchestration is suspended by the orchestration engine, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] publishes an associated Negative Acknowledgement (NACK) message to the MessageBox.</span></span> <span data-ttu-id="f3695-130">NACK メッセージには、コンテキスト プロパティおよび SOAP エラーで構成されるメッセージのボディ部が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f3695-130">The NACK message contains context properties and a message body part consisting of a SOAP fault.</span></span> <span data-ttu-id="f3695-131">NACK メッセージが生成される場合、HTTP アダプタまたは SOAP アダプタから送信が失敗したため、SOAP エラーを含む、**ヘッダー**要素および**本文**発行先の Web からの応答の要素サーバー。</span><span class="sxs-lookup"><span data-stu-id="f3695-131">If the NACK message is generated due to a failed transmission from the HTTP or SOAP adapters, the SOAP fault contains the **Headers** element and the **Body** element of the response from the destination Web server.</span></span> <span data-ttu-id="f3695-132">SOAP 送信が失敗した場合に生成される NACK の SOAP エラーの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f3695-132">The following is an example of the SOAP fault in a NACK generated for a failed SOAP transmission:</span></span>  
  
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
>  <span data-ttu-id="f3695-133">**ヘッダー**要素および**本文**要素は 48 KB に制限されます。</span><span class="sxs-lookup"><span data-stu-id="f3695-133">The **Headers** element and the **Body** element are limited to 48 KB.</span></span> <span data-ttu-id="f3695-134">**ヘッダー**要素は、上限を超えずに最も近いの完全なヘッダー値のペアに丸められます。</span><span class="sxs-lookup"><span data-stu-id="f3695-134">The **Headers** element is rounded to the nearest complete header value pair without exceeding the limit.</span></span> <span data-ttu-id="f3695-135">**本文**要素は 48 KB に切り捨てられます。</span><span class="sxs-lookup"><span data-stu-id="f3695-135">The **Body** element is truncated to 48 KB.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f3695-136">NACK メッセージと ACK メッセージは、それらのメッセージに一致するサブスクリプションがなければ破棄されます。</span><span class="sxs-lookup"><span data-stu-id="f3695-136">NACK and ACK messages are discarded if there are no matching subscriptions for them.</span></span> <span data-ttu-id="f3695-137">これらのメッセージがメッセージング エンジンによって中断されることはありません。</span><span class="sxs-lookup"><span data-stu-id="f3695-137">NACK and ACK messages are not suspended by the Messaging Engine.</span></span>  
  
 <span data-ttu-id="f3695-138">NACK メッセージをサブスクライブするには、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="f3695-138">To subscribe to a NACK message, you can do one of the following:</span></span>  
  
1.  <span data-ttu-id="f3695-139">適切なメッセージ コンテキスト プロパティのフィルタを含む送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="f3695-139">Create a send port with a filter for the appropriate message context property.</span></span> <span data-ttu-id="f3695-140">参照してください**メッセージ コンテキスト プロパティ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]システム メッセージ コンテキスト プロパティの一覧については、関連する警告などメッセージの受信確認します。</span><span class="sxs-lookup"><span data-stu-id="f3695-140">See **Message Context Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)] for a listing of system message context properties including those related to message acknowledgment.</span></span>  
  
2.  <span data-ttu-id="f3695-141">マークされたオーケストレーション ポートから送信**配信通知 = 送信済み**です。</span><span class="sxs-lookup"><span data-stu-id="f3695-141">Send from an orchestration port marked with **Delivery Notification = Transmitted**.</span></span> <span data-ttu-id="f3695-142">オーケストレーション ポートが付いている場合**配信通知 = 送信済み**オーケストレーションは ACK または送信されたメッセージの NACK を受信するまで待機します。</span><span class="sxs-lookup"><span data-stu-id="f3695-142">If an orchestration port is marked with **Delivery Notification = Transmitted**, the orchestration will wait until it receives either an ACK or a NACK for the message that was transmitted.</span></span> <span data-ttu-id="f3695-143">NACK が生成された場合、NACK はオーケストレーションにルーティングされ、オーケストレーションからは DeliveryFailureException がスローされます。</span><span class="sxs-lookup"><span data-stu-id="f3695-143">If a NACK is generated then it will be routed to the orchestration and the orchestration will throw a DeliveryFailureException.</span></span> <span data-ttu-id="f3695-144">DeliveryFailureException は、NACK メッセージ本文に含まれている SOAP エラーからシリアル化解除されます。</span><span class="sxs-lookup"><span data-stu-id="f3695-144">The DeliveryFailureException is deserialized from the SOAP fault that is contained within the NACK message body.</span></span> <span data-ttu-id="f3695-145">オーケストレーションに返された SOAP エラーから例外メッセージ文字列を取得するには、DeliveryFailureException を SoapException にキャストし、SOAP の Detail セクションから InnerXml にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="f3695-145">To retrieve the exception message string from the SOAP fault that is returned to the orchestration, cast the DeliveryFailureException to a SoapException and then access the InnerXml from the SOAP Detail section.</span></span> <span data-ttu-id="f3695-146">この処理を行うためのコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f3695-146">The following code sample demonstrates how to do this:</span></span>  
  
    ```  
    // Cast the DeliveryFailureException to a SoapException…  
    System.Web.Services.Protocols.SoapException se = (System.Web.Services.Protocols.SoapException)e.InnerException;  
    System.Diagnostics.Trace.WriteLine(se.Detail.InnerXml);  
    //e is an Microsoft.XLANGs.BaseTypes.DeliveryFailureException  
    //object type created in an Exception handler  
    ```  
  
     <span data-ttu-id="f3695-147">上記のコード例は、次のような XML フラグメントを返します。</span><span class="sxs-lookup"><span data-stu-id="f3695-147">The code sample above will return an XML fragment similar to the following:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f3695-148">参照</span><span class="sxs-lookup"><span data-stu-id="f3695-148">See Also</span></span>  
 <span data-ttu-id="f3695-149">[SOAP アダプターとは何ですか。](../core/what-is-the-soap-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="f3695-149">[What Is the SOAP Adapter?](../core/what-is-the-soap-adapter.md) </span></span>  
 [<span data-ttu-id="f3695-150">SOAP アダプタのセキュリティに関する推奨事項</span><span class="sxs-lookup"><span data-stu-id="f3695-150">SOAP Adapter Security Recommendations</span></span>](../core/soap-adapter-security-recommendations.md)