---
title: WCF アダプタについて | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 18ca8535-3386-4018-8b5b-d32bdb9ebf70
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e57efe686b72fa42a173eb4f28bb8fb92a899b9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012275"
---
# <a name="what-are-the-wcf-adapters"></a><span data-ttu-id="a406a-103">WCF アダプタについて</span><span class="sxs-lookup"><span data-stu-id="a406a-103">What Are the WCF Adapters?</span></span>
<span data-ttu-id="a406a-104">Windows Communication Foundation (WCF) アダプタには、受信アダプタと送信アダプタの 2 つがあります。</span><span class="sxs-lookup"><span data-stu-id="a406a-104">There are two Windows Communication Foundation (WCF) adapters—a receive adapter and a send adapter.</span></span> <span data-ttu-id="a406a-105">WCF 受信アダプタは、WCF サービス要求を受信するために使用します。</span><span class="sxs-lookup"><span data-stu-id="a406a-105">You use the WCF receive adapter to receive WCF service requests.</span></span> <span data-ttu-id="a406a-106">WCF 受信アダプタは、要求の受信、BizTalk メッセージ オブジェクトの作成、および関連するプロパティのメッセージ コンテキストへの昇格を行います。</span><span class="sxs-lookup"><span data-stu-id="a406a-106">The WCF receive adapter receives a request, creates a BizTalk Message object, and promotes the associated properties to the message context.</span></span> <span data-ttu-id="a406a-107">WCF 送信アダプタは、WCF サービスを呼び出すときに使用します。</span><span class="sxs-lookup"><span data-stu-id="a406a-107">You use the WCF send adapter to call a WCF service.</span></span> <span data-ttu-id="a406a-108">WCF 送信アダプタは、型宣言が不要なコントラクトを使用して WCF サービスを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a406a-108">The WCF send adapter calls the WCF services through the typeless contracts.</span></span>  

> [!NOTE]
>  <span data-ttu-id="a406a-109">WCF アダプタは、リモート プロシージャ コール (RPC) スタイルの Web サービスの使用をサポートしていません。これは、WCF アダプタがメッセージ部分の要素を使用しているメッセージ要素ではなく、メッセージの種類を RPC スタイルの Web サービスが参照するためです。</span><span class="sxs-lookup"><span data-stu-id="a406a-109">The WCF adapters do not support consuming Remote Procedure Call (RPC)-style Web services because the message parts in RPC-style Web services are referring to the message types rather than the message elements where WCF adapters are using elements for the message parts.</span></span> <span data-ttu-id="a406a-110">BizTalk プロジェクトで Web サービスを使用する場合、Web 参照の追加ウィザードを使用して RPC スタイルの Web サービスを追加することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a406a-110">We recommend that you add the RPC-style Web services through Add Web Reference wizard for consuming the Web services in BizTalk projects.</span></span>  

## <a name="web-services-standards-support"></a><span data-ttu-id="a406a-111">Web サービスの標準サポート</span><span class="sxs-lookup"><span data-stu-id="a406a-111">Web Services Standards Support</span></span>  
 <span data-ttu-id="a406a-112">WCF アダプタは、WS-Addressing、WS-Security、WS-AtomicTransaction など、WS 標準のサポートを提供しています。</span><span class="sxs-lookup"><span data-stu-id="a406a-112">WCF adapters provide the support for WS-\* standards such as WS-Addressing, WS-Security, and WS-AtomicTransaction.</span></span> <span data-ttu-id="a406a-113">WCF アダプタの現在のリリースでは、WS-ReliableMessaging はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="a406a-113">WS-ReliableMessaging is not supported in this release of the WCF adapters.</span></span> <span data-ttu-id="a406a-114">WCF でサポートされている仕様の一覧は、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=88314](http://go.microsoft.com/fwlink/?LinkId=88314)します。</span><span class="sxs-lookup"><span data-stu-id="a406a-114">For a list of specifications supported by WCF, see [http://go.microsoft.com/fwlink/?LinkId=88314](http://go.microsoft.com/fwlink/?LinkId=88314).</span></span>  

### <a name="ws-addressing"></a><span data-ttu-id="a406a-115">WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="a406a-115">WS-Addressing</span></span>  
 <span data-ttu-id="a406a-116">WCF アダプタは、WCF が提供している WS-Addressing 標準サポートに依存します。</span><span class="sxs-lookup"><span data-stu-id="a406a-116">WCF adapters rely on the WS-Addressing standard support that is provided by WCF.</span></span> <span data-ttu-id="a406a-117">WCF アダプタでは、次の機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a406a-117">The following features are available in WCF adapters:</span></span>  

-   <span data-ttu-id="a406a-118">メタデータ交換要求時に取得される送信ポートのエンドポイント アドレスの構成</span><span class="sxs-lookup"><span data-stu-id="a406a-118">Configuration of the send port endpoint address obtained during the metadata exchange request.</span></span>  

-   <span data-ttu-id="a406a-119">送信ポートのエンドポイント アドレス用のアドレス指定ヘッダーの構成</span><span class="sxs-lookup"><span data-stu-id="a406a-119">Configuration of the addressing headers for the send port endpoint address.</span></span>  

-   <span data-ttu-id="a406a-120">BizTalk 受信場所で公開されるエンドポイント用のアドレス指定ヘッダーの構成</span><span class="sxs-lookup"><span data-stu-id="a406a-120">Configuration of the addressing headers for the endpoint exposed in the BizTalk receive location.</span></span>  

### <a name="ws-security"></a><span data-ttu-id="a406a-121">WS-Security</span><span class="sxs-lookup"><span data-stu-id="a406a-121">WS-Security</span></span>  
 <span data-ttu-id="a406a-122">WCF アダプタは、WCF が提供しているセキュリティ標準サポートに依存します。</span><span class="sxs-lookup"><span data-stu-id="a406a-122">WCF adapters rely on the security standards support that is provided by WCF.</span></span> <span data-ttu-id="a406a-123">WCF アダプタでは、次の標準がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a406a-123">The following standards are supported in WCF adapters:</span></span>  

-   <span data-ttu-id="a406a-124">Web Services Security: SOAP Message Security (Ws-security) 1.0 および 1.1</span><span class="sxs-lookup"><span data-stu-id="a406a-124">Web Services Security: SOAP Message Security (WS-Security) 1.0 and 1.1</span></span>  

-   <span data-ttu-id="a406a-125">Web Services Secure Conversation Language (WS-SecureConversation)</span><span class="sxs-lookup"><span data-stu-id="a406a-125">Web Services Secure Conversation Language (WS-SecureConversation)</span></span>  

-   <span data-ttu-id="a406a-126">Web Services Trust Language (WS-Trust)</span><span class="sxs-lookup"><span data-stu-id="a406a-126">Web Services Trust Language (WS-Trust)</span></span>  

-   <span data-ttu-id="a406a-127">Web Services Security X.509 Certificate Token Profile</span><span class="sxs-lookup"><span data-stu-id="a406a-127">Web Services Security X.509 Certificate Token Profile</span></span>  

-   <span data-ttu-id="a406a-128">Web Services Security Username Token Profile 1.0</span><span class="sxs-lookup"><span data-stu-id="a406a-128">Web Services Security Username Token Profile 1.0</span></span>  

-   <span data-ttu-id="a406a-129">Web Services Security Kerberos Token Profile 1.0</span><span class="sxs-lookup"><span data-stu-id="a406a-129">Web Services Security Kerberos Token Profile 1.0</span></span>  

#### <a name="service-authentication-types"></a><span data-ttu-id="a406a-130">サービス認証の種類</span><span class="sxs-lookup"><span data-stu-id="a406a-130">Service Authentication Types</span></span>  
 <span data-ttu-id="a406a-131">次の WCF サービス認証の種類がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a406a-131">The following WCF service authentication types are supported:</span></span>  

-   <span data-ttu-id="a406a-132">なし</span><span class="sxs-lookup"><span data-stu-id="a406a-132">None</span></span>  

-   <span data-ttu-id="a406a-133">Windows</span><span class="sxs-lookup"><span data-stu-id="a406a-133">Windows</span></span>  

-   <span data-ttu-id="a406a-134">Certificate</span><span class="sxs-lookup"><span data-stu-id="a406a-134">Certificate</span></span>  

#### <a name="client-authentication-types"></a><span data-ttu-id="a406a-135">クライアント認証の種類</span><span class="sxs-lookup"><span data-stu-id="a406a-135">Client Authentication Types</span></span>  
 <span data-ttu-id="a406a-136">次の WCF クライアント認証の種類がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a406a-136">The following WCF client authentication types are supported:</span></span>  

-   <span data-ttu-id="a406a-137">匿名</span><span class="sxs-lookup"><span data-stu-id="a406a-137">Anonymous</span></span>  

-   <span data-ttu-id="a406a-138">UserName</span><span class="sxs-lookup"><span data-stu-id="a406a-138">UserName</span></span>  

-   <span data-ttu-id="a406a-139">Windows</span><span class="sxs-lookup"><span data-stu-id="a406a-139">Windows</span></span>  

-   <span data-ttu-id="a406a-140">Certificate</span><span class="sxs-lookup"><span data-stu-id="a406a-140">Certificate</span></span>  

#### <a name="security-modes"></a><span data-ttu-id="a406a-141">セキュリティ モード</span><span class="sxs-lookup"><span data-stu-id="a406a-141">Security Modes</span></span>  
 <span data-ttu-id="a406a-142">次のセキュリティ モードがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a406a-142">The following security modes are supported:</span></span>  

-   <span data-ttu-id="a406a-143">[Transport]</span><span class="sxs-lookup"><span data-stu-id="a406a-143">Transport</span></span>  

-   <span data-ttu-id="a406a-144">メッセージ</span><span class="sxs-lookup"><span data-stu-id="a406a-144">Message</span></span>  

-   <span data-ttu-id="a406a-145">Mixed (トランスポート レベルのセキュリティとメッセージ レベルの認証)</span><span class="sxs-lookup"><span data-stu-id="a406a-145">Mixed (transport-level security and message-level authentication)</span></span>  

### <a name="ws-atomictransaction"></a><span data-ttu-id="a406a-146">WS-AtomicTransaction</span><span class="sxs-lookup"><span data-stu-id="a406a-146">WS-AtomicTransaction</span></span>  
 <span data-ttu-id="a406a-147">WCF-WsHttp、WCF-NetTcp、および WCF-NetMsmq の各アダプタは WS-AtomicTransaction プロトコルをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="a406a-147">The WCF-WsHttp, WCF-NetTcp, and WCF-NetMsmq adapters support the WS-AtomicTransaction protocol.</span></span> <span data-ttu-id="a406a-148">このサポートにより次のシナリオが有効となります。</span><span class="sxs-lookup"><span data-stu-id="a406a-148">This support allows the following scenarios:</span></span>  

-   <span data-ttu-id="a406a-149">メッセージ ボックス データベースへのメッセージのトランザクション送信</span><span class="sxs-lookup"><span data-stu-id="a406a-149">Transactional submission of messages to the MessageBox database.</span></span>  

-   <span data-ttu-id="a406a-150">メッセージ ボックス データベースからのメッセージのトランザクション送信</span><span class="sxs-lookup"><span data-stu-id="a406a-150">Transactional transmission of messages from the MessageBox to a transactional destination.</span></span>  

> [!NOTE]
>  <span data-ttu-id="a406a-151">トランザクション スコープは、メッセージ ボックスにより制限されます。</span><span class="sxs-lookup"><span data-stu-id="a406a-151">The transactional scope is limited by the MessageBox.</span></span> <span data-ttu-id="a406a-152">たとえば、BizTalk オーケストレーションはクライアントのトランザクションに参加できません。</span><span class="sxs-lookup"><span data-stu-id="a406a-152">For example, a BizTalk orchestration cannot participate in a client’s transaction.</span></span> <span data-ttu-id="a406a-153">同様に、送信先エンドポイントは、BizTalk オーケストレーションが開始したトランザクションに参加できません。</span><span class="sxs-lookup"><span data-stu-id="a406a-153">Similarly, a destination endpoint cannot participate in a transaction that is initiated by a BizTalk orchestration.</span></span>  

#### <a name="transactional-submission"></a><span data-ttu-id="a406a-154">トランザクション送信</span><span class="sxs-lookup"><span data-stu-id="a406a-154">Transactional Submission</span></span>  
 <span data-ttu-id="a406a-155">選択して、Wcf-wshttp、Wcf-nettcp アダプターの BizTalk Server へのトランザクション送信が有効になって、**トランザクションを有効にする**受信場所のトランスポート プロパティ ダイアログ ボックスのチェック ボックス。</span><span class="sxs-lookup"><span data-stu-id="a406a-155">For the WCF-WsHttp and WCF-NetTcp adapters, transactional submission to BizTalk Server is enabled by selecting the **Enable transactions** check box in the receive location transport properties dialog box.</span></span> <span data-ttu-id="a406a-156">Wcf-netmsmq アダプターの場合、**トランザクション** チェック ボックスは既定で選択されます。</span><span class="sxs-lookup"><span data-stu-id="a406a-156">For the WCF-NetMsmq adapter, the **Transactional** check box is selected by default.</span></span> <span data-ttu-id="a406a-157">メッセージの抽出元のメッセージ キューがトランザクションとして指定されていない場合、このチェック ボックスをオフにする必要があります。オフにしないと、エラー メッセージを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="a406a-157">If the message queues from which you are pulling messages are not marked as transactional, you need to clear this check box; otherwise, you will receive an error message.</span></span>  

 <span data-ttu-id="a406a-158">トランザクション機能が有効の場合、クライアントのトランザクションを使用して、メッセージがメッセージ ボックス データベースに送信されます。</span><span class="sxs-lookup"><span data-stu-id="a406a-158">If the transaction functionality is enabled, messages are submitted to the MessageBox database by using clients’ transactions.</span></span> <span data-ttu-id="a406a-159">クライアントがトランザクションのスコープ外のメッセージを送信しようとすると、アダプタはそのクライアントに例外を返します。</span><span class="sxs-lookup"><span data-stu-id="a406a-159">If a client attempts to submit the messages outside the transactional scope, the adapter will return an exception back to the client.</span></span> <span data-ttu-id="a406a-160">ただし、メッセージは中断されません。</span><span class="sxs-lookup"><span data-stu-id="a406a-160">However, no messages will be suspended.</span></span> <span data-ttu-id="a406a-161">トランザクション機能が無効の場合、クライアントのトランザクションを使用せずに、メッセージがメッセージ ボックスに送信されます。</span><span class="sxs-lookup"><span data-stu-id="a406a-161">If the transaction functionality is disabled, messages are submitted to the MessageBox without using clients’ transactions.</span></span> <span data-ttu-id="a406a-162">クライアントがトランザクション スコープ内のメッセージを送信しようとすると、アダプタはそのクライアントに例外を返し、メッセージは中断されません。</span><span class="sxs-lookup"><span data-stu-id="a406a-162">If a client attempts to submit messages inside the transactional scope, the adapter will return an exception back to the client, and no messages will be suspended.</span></span>  

#### <a name="transactions-and-receive-location-type"></a><span data-ttu-id="a406a-163">トランザクションと受信場所の種類</span><span class="sxs-lookup"><span data-stu-id="a406a-163">Transactions and Receive Location Type</span></span>  
 <span data-ttu-id="a406a-164">トランザクション送信は、一方向の受信場所に対してのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="a406a-164">Transactional submission is available only for one-way receive locations.</span></span> <span data-ttu-id="a406a-165">クライアントが、双方向の受信場所に対し、トランザクション スコープ内のメッセージを送信しようとすると、例外がそのクライアントに返され、メッセージは中断されません。</span><span class="sxs-lookup"><span data-stu-id="a406a-165">If a client attempts to submit messages in a transactional scope for a two-way receive location, an exception will be returned back to the client, and no messages will be suspended.</span></span>  

#### <a name="transactional-transmission"></a><span data-ttu-id="a406a-166">トランザクション送信</span><span class="sxs-lookup"><span data-stu-id="a406a-166">Transactional Transmission</span></span>  
 <span data-ttu-id="a406a-167">選択して、Wcf-wshttp、Wcf-nettcp アダプターの BizTalk Server からのトランザクション送信が有効になって、**トランザクションを有効にする**送信ポート トランスポートのプロパティ ダイアログ ボックスのチェック ボックス。</span><span class="sxs-lookup"><span data-stu-id="a406a-167">For the WCF-WsHttp and WCF-NetTcp adapters, transactional transmission from BizTalk Server is enabled by selecting the **Enable transactions** check box in the send port transport properties dialog box.</span></span> <span data-ttu-id="a406a-168">Wcf-netmsmq アダプターの場合、**トランザクション** チェック ボックスは既定で選択されます。</span><span class="sxs-lookup"><span data-stu-id="a406a-168">For the WCF-NetMsmq adapter, the **Transactional** check box is selected by default.</span></span> <span data-ttu-id="a406a-169">メッセージの送信先のメッセージ キューがトランザクションとして指定されていない場合、このチェック ボックスをオフにする必要があります。オフにしないと、エラー メッセージを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="a406a-169">If the message queues to which you are sending messages are not marked as transactional, you need to clear this check box; otherwise, you will receive an error message.</span></span>  

 <span data-ttu-id="a406a-170">トランザクション機能が有効の場合、トランザクションでメッセージが送信され、そのメッセージがメッセージ ボックス データベースから削除されます。</span><span class="sxs-lookup"><span data-stu-id="a406a-170">If the transaction functionality is enabled, messages are transmitted and deleted from the MessageBox database under transaction.</span></span> <span data-ttu-id="a406a-171">メッセージ受信後、送信先サービスがなんらかの操作を実行した場合、メッセージはメッセージ ボックスから削除されず、トランザクションは中止され、サービスのすべてのトランザクション操作がロールバックされます。</span><span class="sxs-lookup"><span data-stu-id="a406a-171">If the destination service has performed any work after receiving the message, and the message is not deleted from the MessageBox, then the transaction will be aborted and all transaction work on the service will be rolled back.</span></span> <span data-ttu-id="a406a-172">トランザクション機能が無効の場合、トランザクションを使用せずにメッセージが送信され、そのメッセージがメッセージ ボックスから削除されます。</span><span class="sxs-lookup"><span data-stu-id="a406a-172">If the transaction functionality is disabled, messages are transmitted and deleted from the MessageBox without using transactions.</span></span>  

## <a name="single-sign-on-support"></a><span data-ttu-id="a406a-173">シングル サインオンのサポート</span><span class="sxs-lookup"><span data-stu-id="a406a-173">Single Sign-On Support</span></span>  
 <span data-ttu-id="a406a-174">エンタープライズ シングル サインオン (SSO) チケットを借用および取得することで、SSO を WCF アダプタで使用できます。</span><span class="sxs-lookup"><span data-stu-id="a406a-174">You can impersonate and acquire the Enterprise Single Sign-On (SSO) ticket for using SSO with WCF adapters.</span></span> <span data-ttu-id="a406a-175">WCF アダプタで SSO を使用する方法の詳細については、次を参照してください。 [WCF アダプターのシングル サインオン サポート](../core/single-sign-on-support-for-the-wcf-adapters.md)します。</span><span class="sxs-lookup"><span data-stu-id="a406a-175">For more information about how to use SSO with WCF adapters, see [Single Sign-On Support for the WCF Adapters](../core/single-sign-on-support-for-the-wcf-adapters.md).</span></span>  

 <span data-ttu-id="a406a-176">次の表に、WCF 受信アダプタで SSO サポートを使用する場合にサポートされないシナリオを示します。</span><span class="sxs-lookup"><span data-stu-id="a406a-176">The following table summarizes the scenarios that are not supported when using SSO support with the WCF receive adapters.</span></span>  

|<span data-ttu-id="a406a-177">[セキュリティ モード]</span><span class="sxs-lookup"><span data-stu-id="a406a-177">Security mode</span></span>|<span data-ttu-id="a406a-178">資格情報</span><span class="sxs-lookup"><span data-stu-id="a406a-178">Credential</span></span>|  
|-------------------|----------------|  
|<span data-ttu-id="a406a-179">なし</span><span class="sxs-lookup"><span data-stu-id="a406a-179">None</span></span>|<span data-ttu-id="a406a-180">なし</span><span class="sxs-lookup"><span data-stu-id="a406a-180">None</span></span>|  
|<span data-ttu-id="a406a-181">[Transport]</span><span class="sxs-lookup"><span data-stu-id="a406a-181">Transport</span></span>|<span data-ttu-id="a406a-182">なし</span><span class="sxs-lookup"><span data-stu-id="a406a-182">None</span></span>|  
|<span data-ttu-id="a406a-183">メッセージ</span><span class="sxs-lookup"><span data-stu-id="a406a-183">Message</span></span>|<span data-ttu-id="a406a-184">なし</span><span class="sxs-lookup"><span data-stu-id="a406a-184">None</span></span>|  
|<span data-ttu-id="a406a-185">TransportWithMessageCredentials</span><span class="sxs-lookup"><span data-stu-id="a406a-185">TransportWithMessageCredentials</span></span>|<span data-ttu-id="a406a-186">なし</span><span class="sxs-lookup"><span data-stu-id="a406a-186">None</span></span>|  
|<span data-ttu-id="a406a-187">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="a406a-187">TransportCredentialOnly</span></span>|<span data-ttu-id="a406a-188">なし</span><span class="sxs-lookup"><span data-stu-id="a406a-188">None</span></span>|  

## <a name="wcf-extensibility"></a><span data-ttu-id="a406a-189">WCF 拡張機能</span><span class="sxs-lookup"><span data-stu-id="a406a-189">WCF Extensibility</span></span>  
 <span data-ttu-id="a406a-190">次の拡張機能を開発し、WCF-Custom アダプタおよび WCF-CustomIsolated アダプタでこれらの拡張機能を使用することで、WCF の機能を拡張できます。</span><span class="sxs-lookup"><span data-stu-id="a406a-190">You can extend the functionality of WCF by developing the following extensions and using them with the WCF-Custom and WCF-CustomIsolated adapters:</span></span>  

-   <span data-ttu-id="a406a-191">カスタム バインド</span><span class="sxs-lookup"><span data-stu-id="a406a-191">Custom bindings</span></span>  

-   <span data-ttu-id="a406a-192">カスタム バインド要素</span><span class="sxs-lookup"><span data-stu-id="a406a-192">Custom binding elements</span></span>  

### <a name="custom-bindings"></a><span data-ttu-id="a406a-193">カスタム バインド</span><span class="sxs-lookup"><span data-stu-id="a406a-193">Custom Bindings</span></span>  
 <span data-ttu-id="a406a-194">カスタム バインドを開発するには、特定の使用シナリオのために構成プロパティのサブセットを公開するコンテナ内に個々のバインド要素をパッケージ化します。</span><span class="sxs-lookup"><span data-stu-id="a406a-194">Custom bindings are developed by packaging individual binding elements into a container that exposes a subset of the configuration properties for a particular usage scenario.</span></span> <span data-ttu-id="a406a-195">アセンブリをグローバル アセンブリ キャッシュ (GAC) 内にインストールし、その後、拡張機能の要素をコンピュータの構成ファイルに追加することで、バインド拡張機能を登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a406a-195">You need to register the binding extension by installing the assembly into the global assembly cache (GAC) and then adding the extension element to the machine configuration file.</span></span> <span data-ttu-id="a406a-196">カスタム バインドを使用するには、BizTalk グループ内のすべてのサーバーでバインドを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a406a-196">To use the custom bindings, you need to set up the binding on every server in the BizTalk group.</span></span> <span data-ttu-id="a406a-197">バインドは、インストールすると、WCF-Custom アダプタおよび WCF-CustomIsolated アダプタによって認識されるようになります。</span><span class="sxs-lookup"><span data-stu-id="a406a-197">After the binding is installed, it will be visible to the WCF-Custom and WCF-CustomIsolated adapters.</span></span> <span data-ttu-id="a406a-198">WCF-Custom アダプタと WCF-CustomIsolated アダプタは、バインド構成要素に対しリフレクションを使用することで、バインド構成プロパティを取得します。</span><span class="sxs-lookup"><span data-stu-id="a406a-198">The WCF-Custom and WCF-CustomIsolated adapters will get the binding configuration properties by using reflection on the binding configuration elements.</span></span>  

### <a name="custom-binding-elements"></a><span data-ttu-id="a406a-199">カスタム バインド要素</span><span class="sxs-lookup"><span data-stu-id="a406a-199">Custom Binding Elements</span></span>  
 <span data-ttu-id="a406a-200">カスタム バインド要素は、特定のトランスポート チャネル コンポーネントを追加または変更することで開発します。</span><span class="sxs-lookup"><span data-stu-id="a406a-200">Custom binding elements are developed by adding or modifying certain transport channel components.</span></span> <span data-ttu-id="a406a-201">たとえば、カスタム圧縮解除コンポーネントをバインド要素としてパッケージ化したり、UDP トランスポートをバインド要素として表したりします。</span><span class="sxs-lookup"><span data-stu-id="a406a-201">For example, a custom decompression component is packaged as a binding element, or a UDP transport is represented as a binding element.</span></span> <span data-ttu-id="a406a-202">これらのバインド要素は、WCF アダプタ内で使用できます。</span><span class="sxs-lookup"><span data-stu-id="a406a-202">These binding elements can be used inside the WCF adapters.</span></span> <span data-ttu-id="a406a-203">他の既定要素またはカスタム バインド要素と組み合わせて、カスタム バインド要素を使用するチャネル スタックを定義できます。</span><span class="sxs-lookup"><span data-stu-id="a406a-203">You can define a channel stack that uses the custom binding element in combination with other out-of-box or custom binding elements.</span></span> <span data-ttu-id="a406a-204">アセンブリを GAC 内にインストールし、その後、拡張機能の要素をコンピュータの構成ファイルに追加することで、バインド要素拡張機能を登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a406a-204">You need to register the binding element extension by installing the assembly into the GAC and then adding the extension element to the machine configuration file.</span></span> <span data-ttu-id="a406a-205">カスタム バインドを使用するには、BizTalk グループ内のすべてのサーバーでバインドを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a406a-205">To use the custom bindings, you need to set up the binding on every server in the BizTalk group.</span></span> <span data-ttu-id="a406a-206">カスタム バインド要素を使用する選択、 **CustomBinding**バインドの種類を追加、変更、または目的の順序でバインド要素を再配置します。</span><span class="sxs-lookup"><span data-stu-id="a406a-206">To use the custom binding elements, you can select the **CustomBinding** binding type and then add, modify, or rearrange the binding elements in a desired order.</span></span>  

## <a name="in-this-section"></a><span data-ttu-id="a406a-207">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="a406a-207">In This Section</span></span>  

-   [<span data-ttu-id="a406a-208">WCF 受信アダプター</span><span class="sxs-lookup"><span data-stu-id="a406a-208">WCF Receive Adapter</span></span>](../core/wcf-receive-adapter.md)  

-   [<span data-ttu-id="a406a-209">WCF 送信アダプター</span><span class="sxs-lookup"><span data-stu-id="a406a-209">WCF Send Adapter</span></span>](../core/wcf-send-adapter.md)  

## <a name="see-also"></a><span data-ttu-id="a406a-210">参照</span><span class="sxs-lookup"><span data-stu-id="a406a-210">See Also</span></span>  
- [<span data-ttu-id="a406a-211">WCF アダプター</span><span class="sxs-lookup"><span data-stu-id="a406a-211">WCF Adapters</span></span>](../core/wcf-adapters.md)   
- <span data-ttu-id="a406a-212">**WCF アダプタ サービス コントラクトのリファレンス** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="a406a-212">**WCF Adapters Service Contract Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
