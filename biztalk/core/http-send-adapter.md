---
title: HTTP 送信アダプタ |Microsoft Docs
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
ms.openlocfilehash: f2ddd2a3fa4b8bb2f97e25809121fa11b1f473f1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999643"
---
# <a name="http-send-adapter"></a><span data-ttu-id="36462-102">HTTP 送信アダプタ</span><span class="sxs-lookup"><span data-stu-id="36462-102">HTTP Send Adapter</span></span>
<span data-ttu-id="36462-103">HTTP 送信アダプターは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] からメッセージを取得して、HTTP POST 要求で送信先 URL に送信します。</span><span class="sxs-lookup"><span data-stu-id="36462-103">The HTTP send adapter gets messages from [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and sends them to a destination URL on an HTTP POST request.</span></span> <span data-ttu-id="36462-104">メッセージの内容は BizTalk メッセージ オブジェクトのボディ部から取得します。</span><span class="sxs-lookup"><span data-stu-id="36462-104">The HTTP send adapter gets the message content from the body part of the BizTalk Message object.</span></span> <span data-ttu-id="36462-105">BizTalk メッセージ オブジェクトの他のすべての部分は無視されます。</span><span class="sxs-lookup"><span data-stu-id="36462-105">The HTTP send adapter ignores all other parts of the BizTalk Message object.</span></span>  
  
 <span data-ttu-id="36462-106">メッセージが送信先の URL に送信され、BizTalk メッセージング エンジンで HTTP 成功状態コードを受け取ると、メッセージはメッセージ ボックス データベースから削除されます。</span><span class="sxs-lookup"><span data-stu-id="36462-106">After the adapter sends the message to a destination URL and the BizTalk Messaging Engine receives the HTTP success status code, the HTTP send adapter deletes the message from the MessageBox database.</span></span>  
  
 <span data-ttu-id="36462-107">HTTP メッセージのリダイレクトがサポートされており、送信ポートに構成できます。</span><span class="sxs-lookup"><span data-stu-id="36462-107">Redirection of HTTP messages is supported and can be configured on the send port.</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="36462-108">では、HTTP 送信アダプターを BizTalk のネイティブ アプリケーションとしてホストします。</span><span class="sxs-lookup"><span data-stu-id="36462-108">hosts the HTTP send adapter as a native BizTalk application.</span></span> <span data-ttu-id="36462-109">HTTP 送信アダプタでは、一方向のメッセージ送信と、送信請求 - 応答の送信をサポートします。</span><span class="sxs-lookup"><span data-stu-id="36462-109">It supports one-way sending of messages as well a solicit-response transmission.</span></span> <span data-ttu-id="36462-110">HTTP 送信アダプタの送信場所は、送信ポートで構成する一意の URL です。</span><span class="sxs-lookup"><span data-stu-id="36462-110">The send location for the HTTP send adapter is a distinct URL that you configure through the send port.</span></span> <span data-ttu-id="36462-111">この一意の URL には、ベース URL に付加したクエリ文字列を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="36462-111">This unique URL can include query strings appended to the base URL.</span></span>  
  
## <a name="batching-support-for-the-http-send-adapter"></a><span data-ttu-id="36462-112">HTTP 送信アダプタのバッチ処理のサポート</span><span class="sxs-lookup"><span data-stu-id="36462-112">Batching Support for the HTTP Send Adapter</span></span>  
 <span data-ttu-id="36462-113">HTTP 送信アダプタは、バッチ操作をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="36462-113">The HTTP send adapter does not support batching operations.</span></span>  
  
## <a name="chunked-encoding-support-for-the-http-send-adapter"></a><span data-ttu-id="36462-114">HTTP 送信アダプタのチャンク エンコードのサポート</span><span class="sxs-lookup"><span data-stu-id="36462-114">Chunked Encoding Support for the HTTP Send Adapter</span></span>  
 <span data-ttu-id="36462-115">場合、**チャンク エンコードを有効にする**構成オプションを有効にし、HTTP 送信アダプターが要求のサイズが 8 KB を超える場合は、チャンク エンコードを使用して要求メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="36462-115">If the **Enable chunked encoding** configuration option is enabled, then the HTTP send adapter sends request messages using chunked encoding if the request size exceeds 8 KB.</span></span> <span data-ttu-id="36462-116">HTTP プロキシ サーバーを使用している場合、チャンク エンコードは使用されず、データは常に段階的に処理されてから送信されます。</span><span class="sxs-lookup"><span data-stu-id="36462-116">If the HTTP proxy server is used, the HTTP send adapter does not use chunked encoding and always stages the data before sending.</span></span> <span data-ttu-id="36462-117">**チャンク エンコードを有効にする**構成オプションが既定で有効にします。</span><span class="sxs-lookup"><span data-stu-id="36462-117">The **Enable chunked encoding** configuration option is enabled by default.</span></span>  
  
 <span data-ttu-id="36462-118">送信アダプタで応答メッセージを受信するとき、チャンク エンコードが行われたボディ部を含んだ応答メッセージを受信できます。</span><span class="sxs-lookup"><span data-stu-id="36462-118">When the send adapter receives a response message, it can accept response messages with a chunked encoded body part.</span></span>  
  
## <a name="client-authentication-for-the-http-send-adapter"></a><span data-ttu-id="36462-119">HTTP 送信アダプタのクライアント認証</span><span class="sxs-lookup"><span data-stu-id="36462-119">Client Authentication for the HTTP Send Adapter</span></span>  
 <span data-ttu-id="36462-120">HTTP 送信アダプタは、送信先のサーバーでの認証に、次のいずれかの認証の種類を使用します。</span><span class="sxs-lookup"><span data-stu-id="36462-120">The HTTP send adapter authenticates with the destination server by using one of the following authentication types:</span></span>  
  
- <span data-ttu-id="36462-121">**匿名です。**</span><span class="sxs-lookup"><span data-stu-id="36462-121">**Anonymous.**</span></span> <span data-ttu-id="36462-122">: 送信先サーバーに接続するとき、資格情報が送信されません。</span><span class="sxs-lookup"><span data-stu-id="36462-122">The HTTP adapter does not send any credentials when connecting to the destination server.</span></span> <span data-ttu-id="36462-123">送信サーバーで匿名認証を許可している場合、送信サーバーで構成されている匿名アカウントの資格情報が使用されます。</span><span class="sxs-lookup"><span data-stu-id="36462-123">If the destination server permits anonymous authentication then the credentials of the configured anonymous account on the destination server are used.</span></span>  
  
- <span data-ttu-id="36462-124">**基本的な。**</span><span class="sxs-lookup"><span data-stu-id="36462-124">**Basic.**</span></span> <span data-ttu-id="36462-125">: HTTP 接続で、プレーンテキストでユーザー名とパスワードを送信します。</span><span class="sxs-lookup"><span data-stu-id="36462-125">The HTTP adapter sends the user name and password over an HTTP connection in plain text.</span></span>  
  
- <span data-ttu-id="36462-126">**ダイジェスト。**</span><span class="sxs-lookup"><span data-stu-id="36462-126">**Digest.**</span></span> <span data-ttu-id="36462-127">: HTTP 接続で、暗号化形式でパスワードを送信します。</span><span class="sxs-lookup"><span data-stu-id="36462-127">The HTTP adapter sends passwords in an encrypted format over the HTTP connection.</span></span>  
  
- <span data-ttu-id="36462-128">**Kerberos。**</span><span class="sxs-lookup"><span data-stu-id="36462-128">**Kerberos.**</span></span> <span data-ttu-id="36462-129">ユーザー名もパスワードも HTTP 接続で送信されません。</span><span class="sxs-lookup"><span data-stu-id="36462-129">Neither the user name nor the password is sent over an HTTP connection.</span></span> <span data-ttu-id="36462-130">この認証の種類には、HTTP 送信アダプタが実行するプロセスの資格情報が使用されます。</span><span class="sxs-lookup"><span data-stu-id="36462-130">The HTTP adapter uses the credentials of the process under which the HTTP send adapter runs for this authentication type.</span></span>  
  
  <span data-ttu-id="36462-131">また、HTTP 送信アダプタでは、Web サーバーでクライアントの Secure Sockets Layer (SSL) 証明書を必要としているか受け付ける場合に、Web サーバーに SSL 証明書を提供できます。</span><span class="sxs-lookup"><span data-stu-id="36462-131">Additionally, the HTTP send adapter can provide a client Secure Sockets Layer (SSL) certificate to the Web server if the server requires or accepts it.</span></span>  
  
## <a name="client-certificates-for-the-http-send-adapter"></a><span data-ttu-id="36462-132">HTTP 送信アダプタのクライアント証明書</span><span class="sxs-lookup"><span data-stu-id="36462-132">Client Certificates for the HTTP Send Adapter</span></span>  
 <span data-ttu-id="36462-133">HTTP 送信アダプタでは、クライアント証明書を受け付けるか必要とするサーバー間に、セキュリティで保護された接続を確立できます。</span><span class="sxs-lookup"><span data-stu-id="36462-133">The HTTP send adapter can establish a secure connection with servers that accept or require client certificates.</span></span> <span data-ttu-id="36462-134">クライアント証明書を指定した場合、HTTP 送信アダプタではクライアント証明書を必要とするか受け付けるサーバーに接続するときに、この証明書を使用します。</span><span class="sxs-lookup"><span data-stu-id="36462-134">If a client certificate is specified, the HTTP send adapter uses the certificate when connecting with servers that require or accept client certificates.</span></span> <span data-ttu-id="36462-135">クライアント証明書を指定しなかった場合に、送信先のサーバーでクライアント証明書を要求された場合、HTTP 送信アダプタはメッセージの送信に失敗し、標準の再試行ロジックが実行されます。</span><span class="sxs-lookup"><span data-stu-id="36462-135">If the client certificate is not specified and the destination server requires client certificates, the HTTP send adapter fails to send the message and follows the standard retry logic.</span></span>  
  
 <span data-ttu-id="36462-136">HTTP 送信アダプターでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] プロセスの実行に使用されているアカウントの個人用ストアにあるクライアント証明書を使用します。</span><span class="sxs-lookup"><span data-stu-id="36462-136">The HTTP send adapter uses the client certificate from the personal store of the account under which the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] process is running.</span></span> <span data-ttu-id="36462-137">証明書は拇印によって指定します。</span><span class="sxs-lookup"><span data-stu-id="36462-137">The certificate is specified by its thumbprint.</span></span> <span data-ttu-id="36462-138">HTTP 送信アダプタによる証明書の読み込みが何らかの理由で失敗した場合、送信中だったメッセージは中断されます。</span><span class="sxs-lookup"><span data-stu-id="36462-138">If the HTTP send adapter fails to load the certificate for any reason, the message that it was sending is suspended.</span></span>  
  
## <a name="single-sign-on-support-for-the-http-adapter"></a><span data-ttu-id="36462-139">HTTP アダプタのシングル サインオンのサポート</span><span class="sxs-lookup"><span data-stu-id="36462-139">Single Sign-On Support for the HTTP Adapter</span></span>  
 <span data-ttu-id="36462-140">BizTalk 管理コンソールを使用して、HTTP 受信場所または送信ポートで使用するエンタープライズ シングル サインオン (SSO) を構成できます。</span><span class="sxs-lookup"><span data-stu-id="36462-140">You can configure Enterprise Single Sign-On (SSO) for use with the HTTP receive location or send port by using BizTalk Administration console.</span></span> <span data-ttu-id="36462-141">ここでは、SSO と HTTP アダプタの連携について説明します。</span><span class="sxs-lookup"><span data-stu-id="36462-141">This topic describes how SSO works with the HTTP adapter.</span></span>  
  
 <span data-ttu-id="36462-142">**受信場所、HTTP 用のシングル サインオン サポート**</span><span class="sxs-lookup"><span data-stu-id="36462-142">**Single Sign-On Support for the HTTP Receive Location**</span></span>  
  
 <span data-ttu-id="36462-143">Microsoft インターネット インフォメーション サービス (IIS) では、Web クライアントから HTTP 要求を受信すると、ユーザーを認証します。</span><span class="sxs-lookup"><span data-stu-id="36462-143">When an HTTP request is received by Microsoft Internet Information Services (IIS) from a Web client, IIS authenticates the user.</span></span> <span data-ttu-id="36462-144">ISAPI (Internet Server API) 拡張によって Microsoft Windows ユーザーの権限を借用し、SSO 資格情報ストアを呼び出して、暗号化されたチケットを取得します。</span><span class="sxs-lookup"><span data-stu-id="36462-144">The Internet Server Application Programming Interface (ISAPI) extension impersonates the Microsoft Windows user and then calls the SSO credential store to obtain an encrypted ticket.</span></span> <span data-ttu-id="36462-145">このチケットとして格納されている、 **SSOTicket**メッセージのコンテキストのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="36462-145">This ticket is stored as the **SSOTicket** property in the context of the message.</span></span>  
  
 <span data-ttu-id="36462-146">パススルー シナリオでは、BizTalk メッセージング エンジンによって、メッセージ ボックス データベースにメッセージが送信されます。</span><span class="sxs-lookup"><span data-stu-id="36462-146">In the pass-through scenario, the BizTalk Messaging Engine directs the message to the MessageBox database.</span></span> <span data-ttu-id="36462-147">アダプターはメッセージを受信、メッセージ ボックス データベースから、HTTP アダプターが呼び出す、 **ISSOTicket.RedeemTicket メソッド**からバックエンド資格情報を取得するアプリケーション名と共に、暗号化されたチケットと、SSO ストア。</span><span class="sxs-lookup"><span data-stu-id="36462-147">When the adapter receives the message from the MessageBox database, the HTTP adapter calls the **ISSOTicket.RedeemTicket Method** with the encrypted ticket along with the application name to retrieve the back-end credentials from the SSO store.</span></span> <span data-ttu-id="36462-148">その後、外部の資格情報を使用してバックエンド システムに接続し、要求が処理されます。</span><span class="sxs-lookup"><span data-stu-id="36462-148">The HTTP adapter then uses the external credentials to connect to the back-end system and process the request.</span></span> <span data-ttu-id="36462-149">関連アプリケーションの詳細については、[SSO 関連アプリケーション](../core/sso-affiliate-applications.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36462-149">For more information about the affiliate applications, see [SSO Affiliate Applications](../core/sso-affiliate-applications.md).</span></span>  
  
 <span data-ttu-id="36462-150">オーケストレーションがアダプタを呼び出すシナリオでは、BizTalk メッセージング エンジンによって、メッセージ ボックス データベースにこのメッセージが送信されます。</span><span class="sxs-lookup"><span data-stu-id="36462-150">In the scenario where an orchestration invokes the adapter, the BizTalk Messaging Engine sends this message to the MessageBox database.</span></span> <span data-ttu-id="36462-151">オーケストレーションで、ことを確認します両方、 **SSOTicket**コンテキスト プロパティと**Microsoft.BizTalk.XLANGs.BTXEngine.OriginatorSID**チケットを格納しているメッセージのコンテキスト プロパティには維持されます。</span><span class="sxs-lookup"><span data-stu-id="36462-151">The orchestration should ensure that both the **SSOTicket** context property and the **Microsoft.BizTalk.XLANGs.BTXEngine.OriginatorSID** context property of the message that contains the ticket are maintained.</span></span> <span data-ttu-id="36462-152">アダプターは、メッセージ ボックス データベースからこのメッセージを受信、アダプターが呼び出し**RedeemTicket**バックエンド資格情報を SSO ストアから取得する暗号化されたチケットを使用します。</span><span class="sxs-lookup"><span data-stu-id="36462-152">When the adapter receives this message from the MessageBox database, the adapter calls **RedeemTicket** with the encrypted ticket to retrieve the back-end credentials from the SSO store.</span></span> <span data-ttu-id="36462-153">スケジュールをデザインするユーザーは、このプロパティをメッセージに明示的にコピーしてください。</span><span class="sxs-lookup"><span data-stu-id="36462-153">The user designing the schedule should specifically copy this property to the message.</span></span>  
  
 <span data-ttu-id="36462-154">**HTTP 送信アダプター用のシングル サインオンのサポート**</span><span class="sxs-lookup"><span data-stu-id="36462-154">**Single Sign-On Support for the HTTP Send Adapters**</span></span>  
  
 <span data-ttu-id="36462-155">SSO が有効になっている場合と HTTP 送信ポートを含むメッセージを受信、 **Secure**プロパティを検証し、関連アプリケーションのチケットを引き換える SSO サーバーを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="36462-155">If SSO is enabled, when an HTTP send port receives a message with the **Secure** property, it calls the SSO server to validate and redeem the ticket for an affiliate application.</span></span> <span data-ttu-id="36462-156">SSO を呼び出してチケットを引き換える作業は、関連アプリケーションのアプリケーション管理者、関連管理者、または SSO 管理者が行います。</span><span class="sxs-lookup"><span data-stu-id="36462-156">The administration application, affiliate administrators, or SSO administrators for the affiliate application can call SSO to redeem a ticket.</span></span> <span data-ttu-id="36462-157">その後、SSO によってチケットが解読され、バックエンド資格情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="36462-157">SSO then decrypts the ticket and obtains the back-end credentials.</span></span> <span data-ttu-id="36462-158">パススルーおよびオーケストレーションのシナリオは、HTTP 送信ポートのシナリオと同一です。</span><span class="sxs-lookup"><span data-stu-id="36462-158">The pass-through and orchestration scenario are the same as for the HTTP send port.</span></span>  
  
 <span data-ttu-id="36462-159">既定では HTTP 送信ポートの SSO は無効です。</span><span class="sxs-lookup"><span data-stu-id="36462-159">By default, SSO is disabled for the HTTP send port.</span></span> <span data-ttu-id="36462-160">HTTP 送信ポートの SSO を有効にする方法の詳細については、[HTTP 送信ポートの構成](../core/configuring-an-http-send-port.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36462-160">For more information about enabling SSO for the HTTP send port, see [Configuring an HTTP Send Port](../core/configuring-an-http-send-port.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="36462-161">シングル サインオンは、基本認証およびダイジェスト認証のみで使用できます。</span><span class="sxs-lookup"><span data-stu-id="36462-161">You can only use Single Sign-On with basic and digest authentication.</span></span>  
  
 <span data-ttu-id="36462-162">HTTP 受信アダプタおよび送信アダプタのシングル サインオンのサポートを正しく実装するには、以下の条件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="36462-162">To correctly implement Single Sign On support for the HTTP receive and send adapter the following conditions must be met:</span></span>  
  
-   <span data-ttu-id="36462-163">次の場所に、同一のユーザー アカウントを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36462-163">The same user account must be specified in the following places:</span></span>  
  
    -   <span data-ttu-id="36462-164">HTTP 受信アダプターで監視している IIS 仮想ディレクトリの、アプリケーション プール ID (IIS 7.0) またはホスト元 COM+ アプリケーションの ID。</span><span class="sxs-lookup"><span data-stu-id="36462-164">The application pool identity (IIS 7.0) or hosting COM+ application identity for the IIS virtual directory that is monitored by the HTTP receive adapter.</span></span> <span data-ttu-id="36462-165">HTTP の IIS の構成の詳細については、受信場所を参照してください[IIS の HTTP 受信場所を構成する方法](../core/how-to-configure-iis-for-an-http-receive-location.md)します。</span><span class="sxs-lookup"><span data-stu-id="36462-165">For more information about configuring IIS for HTTP receive locations, see [How to Configure IIS for an HTTP Receive Location](../core/how-to-configure-iis-for-an-http-receive-location.md).</span></span>  
  
    -   <span data-ttu-id="36462-166">HTTP アダプターがで実行されている分離ホスト インスタンス用に使用するログオン資格情報。</span><span class="sxs-lookup"><span data-stu-id="36462-166">The logon credentials used for the isolated host instance that the HTTP adapter is running in.</span></span> <span data-ttu-id="36462-167">ホスト インスタンスのログオン資格情報を構成する方法については、[ホスト インスタンスのプロパティを変更する方法](../core/how-to-modify-host-instance-properties.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36462-167">For information about how to configure the logon credentials for a host instance, see [How to Modify Host Instance Properties](../core/how-to-modify-host-instance-properties.md).</span></span>  
  
-   <span data-ttu-id="36462-168">HTTP アダプタが使用する分離ホストは、信頼されている認証として構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36462-168">The isolated host that the HTTP adapter is using must be configured as Authentication Trusted.</span></span> <span data-ttu-id="36462-169">信頼されている認証としてホストを構成する方法については、[ホスト プロパティを変更する方法](../core/how-to-modify-host-properties.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36462-169">For information about how to configure a host as Authentication Trusted, see [How to Modify Host Properties](../core/how-to-modify-host-properties.md).</span></span>  
  
## <a name="negative-acknowledgment-nack-messages-generated-for-failed-transmissions-by-the-http-or-soap-adapter"></a><span data-ttu-id="36462-170">HTTP アダプタまたは SOAP アダプタによる送信が失敗した場合に生成される否定受信確認応答 (NACK) メッセージ</span><span class="sxs-lookup"><span data-stu-id="36462-170">Negative Acknowledgment (NACK) Messages Generated for Failed Transmissions by the HTTP or SOAP Adapter</span></span>  
 <span data-ttu-id="36462-171">メッセージの送信が正常にとき、BizTalk メッセージング エンジンは配信通知が有効になっている場合、メッセージ ボックスに、関連付けられている受信確認 (ACK) メッセージを公開します。</span><span class="sxs-lookup"><span data-stu-id="36462-171">When a message is successfully transmitted, the BizTalk Messaging Engine publishes an associated acknowledgment (ACK) message to the MessageBox if delivery notifications are enabled.</span></span> <span data-ttu-id="36462-172">同様に、BizTalk メッセージング エンジンによってメッセージが中断されたり、オーケストレーション エンジンによってオーケストレーションが中断された場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] により、関連付けられた否定受信確認応答 (NACK) メッセージがメッセージ ボックスにパブリッシュされます。</span><span class="sxs-lookup"><span data-stu-id="36462-172">Likewise, when a message is suspended by the BizTalk Messaging Engine or an orchestration is suspended by the orchestration engine, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] publishes an associated negative acknowledgment (NACK) message to the MessageBox.</span></span> <span data-ttu-id="36462-173">NACK メッセージには、コンテキスト プロパティと、SOAP エラーで構成されるメッセージのボディ部が含まれます。</span><span class="sxs-lookup"><span data-stu-id="36462-173">The NACK message contains context properties and a message body part that consists of a SOAP fault.</span></span> <span data-ttu-id="36462-174">HTTP アダプタまたは SOAP アダプタからの送信に失敗したことが原因で NACK メッセージが生成された場合、SOAP エラーには、送信先の Web サーバーからの応答の Headers 要素および Body 要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="36462-174">If the NACK message is generated due to a failed transmission from the HTTP or SOAP adapter, the SOAP fault contains the Headers element and the Body element of the response from the destination Web server.</span></span> <span data-ttu-id="36462-175">SOAP 送信が失敗した場合に生成される NACK の HTTP エラーの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="36462-175">The following is an example of the SOAP fault in a NACK generated for a failed HTTP transmission:</span></span>  
  
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
>  <span data-ttu-id="36462-176">Headers 要素および Body 要素は、48 KB に制限されています。</span><span class="sxs-lookup"><span data-stu-id="36462-176">The Headers element and the Body element are limited to 48 KB.</span></span> <span data-ttu-id="36462-177">Headers 要素は、制限を超えないサイズで、最も完全に近いヘッダー値の組み合わせになるよう丸められます。</span><span class="sxs-lookup"><span data-stu-id="36462-177">The Headers element is rounded to the nearest complete header value pair without exceeding the limit.</span></span> <span data-ttu-id="36462-178">Body 要素は 48 KB に切り捨てられます。</span><span class="sxs-lookup"><span data-stu-id="36462-178">The Body element is truncated to 48 KB.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="36462-179">NACK メッセージと ACK メッセージは、それらのメッセージに一致するサブスクリプションがなければ破棄されます。</span><span class="sxs-lookup"><span data-stu-id="36462-179">NACK and ACK messages are discarded if there are no matching subscriptions for them.</span></span> <span data-ttu-id="36462-180">これらのメッセージが BizTalk メッセージング エンジンによって中断されることはありません。</span><span class="sxs-lookup"><span data-stu-id="36462-180">NACK and ACK messages are not suspended by the BizTalk Messaging Engine.</span></span>  
  
 <span data-ttu-id="36462-181">NACK メッセージをサブスクライブするには、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="36462-181">To subscribe to a NACK message, you can do one of the following:</span></span>  
  
- <span data-ttu-id="36462-182">適切なメッセージ コンテキスト プロパティのフィルタを含む送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="36462-182">Create a send port with a filter for the appropriate message context property.</span></span> <span data-ttu-id="36462-183">参照してください**メッセージ コンテキスト プロパティ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]システム メッセージ コンテキスト プロパティの一覧を含めてメッセージの受信確認に関連します。</span><span class="sxs-lookup"><span data-stu-id="36462-183">See **Message Context Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)] for a listing of system message context properties including those related to message acknowledgment.</span></span>  
  
- <span data-ttu-id="36462-184">マークされたオーケストレーション ポートから送信**配信通知 = 送信済み**します。</span><span class="sxs-lookup"><span data-stu-id="36462-184">Send from an orchestration port marked with **Delivery Notification = Transmitted**.</span></span> <span data-ttu-id="36462-185">オーケストレーション ポートが付いている場合**配信通知 = 送信済み**オーケストレーションは ACK または NACK に送信されたメッセージを受信するまで待機します。</span><span class="sxs-lookup"><span data-stu-id="36462-185">If an orchestration port is marked with **Delivery Notification = Transmitted**, the orchestration will wait until it receives either an ACK or a NACK for the message that was transmitted.</span></span> <span data-ttu-id="36462-186">NACK が生成された場合、NACK はオーケストレーションにルーティングされ、オーケストレーションからは DeliveryFailureException がスローされます。</span><span class="sxs-lookup"><span data-stu-id="36462-186">If a NACK is generated then it will be routed to the orchestration and the orchestration will throw a DeliveryFailureException.</span></span> <span data-ttu-id="36462-187">DeliveryFailureException は、NACK メッセージ本文に含まれている SOAP エラーからシリアル化解除されます。</span><span class="sxs-lookup"><span data-stu-id="36462-187">The DeliveryFailureException is deserialized from the SOAP fault that is contained within the NACK message body.</span></span> <span data-ttu-id="36462-188">オーケストレーションに返された SOAP エラーから例外メッセージ文字列を取得するには、DeliveryFailureException を SoapException にキャストし、SOAP の Detail セクションから InnerXml にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="36462-188">To retrieve the exception message string from the SOAP fault that is returned to the orchestration, cast the DeliveryFailureException to a SoapException and then access the InnerXml from the SOAP Detail section.</span></span> <span data-ttu-id="36462-189">この処理を行うためのコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="36462-189">The following code sample demonstrates how to do this:</span></span>  
  
  ```  
  // Cast the DeliveryFailureException to a SoapException…  
  System.Web.Services.Protocols.SoapException se = (System.Web.Services.Protocols.SoapException)e.InnerException;  
  System.Diagnostics.Trace.WriteLine(se.Detail.InnerXml);  
  //e is an Microsoft.XLANGs.BaseTypes.DeliveryFailureException  
  //object type created in an Exception handler  
  
  ```  
  
   <span data-ttu-id="36462-190">上記のコード例は、次のような XML フラグメントを返します。</span><span class="sxs-lookup"><span data-stu-id="36462-190">The code sample above will return an XML fragment similar to the following:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="36462-191">参照</span><span class="sxs-lookup"><span data-stu-id="36462-191">See Also</span></span>  
 [<span data-ttu-id="36462-192">HTTP アダプター</span><span class="sxs-lookup"><span data-stu-id="36462-192">HTTP Adapter</span></span>](../core/http-adapter.md)  
<span data-ttu-id="36462-193">**SSO の COM オブジェクト** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="36462-193">**SSO COM objects** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>