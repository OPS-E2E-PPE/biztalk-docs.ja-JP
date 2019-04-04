---
title: POP3 アダプターについて | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- POP3 adapters, availability
- authenticating, POP3 adapters
- POP3 adapters, data duplication
- data duplication
- POP3 adapters, receive adapters
- high availability, POP3 adapters
- POP3 adapters, supported platforms
- POP3 adapters, authenticating
- POP3 adapters, algorithims
- receive adapters, POP3 adapters
ms.assetid: 05e9598b-cdfe-4216-b6bf-1b84f8ddfeae
caps.latest.revision: 30
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aa0f4679cb898f9ce2c4008505bd1ec4a2540dab
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974331"
---
# <a name="what-is-the-pop3-adapter"></a><span data-ttu-id="865da-103">POP3 アダプターについて</span><span class="sxs-lookup"><span data-stu-id="865da-103">What Is the POP3 Adapter?</span></span>
<span data-ttu-id="865da-104">このセクションでは POP3 受信アダプターについて説明します。</span><span class="sxs-lookup"><span data-stu-id="865da-104">This section describes the POP3 receive adapter.</span></span>  
  
## <a name="pop3-receive-adapter"></a><span data-ttu-id="865da-105">POP3 受信アダプター</span><span class="sxs-lookup"><span data-stu-id="865da-105">POP3 Receive Adapter</span></span>  
 <span data-ttu-id="865da-106">POP3 受信アダプターを使用すると、POP3 に対応したメールボックスから BizTalk Server にデータを移動できます。</span><span class="sxs-lookup"><span data-stu-id="865da-106">The POP3 receive adapter enables you to move data from a POP3-enabled mailbox to BizTalk Server.</span></span>  
  
 <span data-ttu-id="865da-107">POP3 受信アダプターの主な機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="865da-107">The key features of the POP3 receive adapter are:</span></span>  
  
-   <span data-ttu-id="865da-108">要求時に POP3 サーバーのメールボックスからファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="865da-108">Pulling files from the POP3 server mailbox on demand.</span></span>  
  
-   <span data-ttu-id="865da-109">構成可能なスケジュールに基づいてポーリングを実行します。</span><span class="sxs-lookup"><span data-stu-id="865da-109">Running polls based on a configurable schedule.</span></span>  
  
-   <span data-ttu-id="865da-110">POP3 サーバーのメールボックスにポーリングし、BizTalk Server にデータを直接送信します。</span><span class="sxs-lookup"><span data-stu-id="865da-110">Polling the POP3 server mailbox and sending data directly to BizTalk Server.</span></span>  
  
-   <span data-ttu-id="865da-111">POP3 サーバーのメールボックスを、IP アドレスまたはホスト名、ポート、ユーザー名、およびパスワードで指定します。</span><span class="sxs-lookup"><span data-stu-id="865da-111">Specifying the POP3 server mailbox as an IP address or host name, port, user name, and password.</span></span>  
  
-   <span data-ttu-id="865da-112">Secure Sockets Layer (SSL) 接続が必要なメール サーバーから電子メールをダウンロードする機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="865da-112">Ability to download e-mail from mail servers that require Secure Sockets Layer (SSL) connections.</span></span>  
  
-   <span data-ttu-id="865da-113">ファイル配信を保証します。</span><span class="sxs-lookup"><span data-stu-id="865da-113">Guaranteed file delivery.</span></span>  
  
-   <span data-ttu-id="865da-114">暗黙的な MIME 処理を行います。</span><span class="sxs-lookup"><span data-stu-id="865da-114">Implicit MIME processing.</span></span> <span data-ttu-id="865da-115">POP3 アダプターの使用時は、受信パイプラインで MIME デコーダーを使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="865da-115">It is not necessary to use a MIME decoder in a receive pipeline when using the POP3 adapter.</span></span>  
  
## <a name="pop3-adapter-supported-platforms"></a><span data-ttu-id="865da-116">POP3 アダプターがサポートされているプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="865da-116">POP3 Adapter Supported Platforms</span></span>  
 <span data-ttu-id="865da-117">POP3 アダプターは、次の RFC に準拠する、すべての POP3 サーバーで動作するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="865da-117">The POP3 adapter is designed to work with any POP3 servers that conform to the following RFCs:</span></span>  
  
- <span data-ttu-id="865da-118">**RFC 1939 します。**</span><span class="sxs-lookup"><span data-stu-id="865da-118">**RFC 1939.**</span></span> <span data-ttu-id="865da-119">Post Office Protocol Version 3 (を参照してください[ http://go.microsoft.com/fwlink/?LinkId=58808 ](http://go.microsoft.com/fwlink/?LinkId=58808))</span><span class="sxs-lookup"><span data-stu-id="865da-119">Post Office Protocol Version 3 (see [http://go.microsoft.com/fwlink/?LinkId=58808](http://go.microsoft.com/fwlink/?LinkId=58808))</span></span>  
  
- <span data-ttu-id="865da-120">**RFC 1734 します。**</span><span class="sxs-lookup"><span data-stu-id="865da-120">**RFC 1734.**</span></span> <span data-ttu-id="865da-121">POP3 AUTHentication command (を参照してください[ http://go.microsoft.com/fwlink/?LinkId=58809 ](http://go.microsoft.com/fwlink/?LinkId=58809))</span><span class="sxs-lookup"><span data-stu-id="865da-121">POP3 AUTHentication command (see [http://go.microsoft.com/fwlink/?LinkId=58809](http://go.microsoft.com/fwlink/?LinkId=58809))</span></span>  
  
- <span data-ttu-id="865da-122">**RFC 2045 します。**</span><span class="sxs-lookup"><span data-stu-id="865da-122">**RFC 2045.**</span></span> <span data-ttu-id="865da-123">Multipurpose Internet Mail Extensions (MIME) Part One: 形式 of Internet Message Bodies (を参照してください[ http://go.microsoft.com/fwlink/?LinkId=58810 ](http://go.microsoft.com/fwlink/?LinkId=58810))</span><span class="sxs-lookup"><span data-stu-id="865da-123">Multipurpose Internet Mail Extensions (MIME) Part One: Format of Internet Message Bodies (see [http://go.microsoft.com/fwlink/?LinkId=58810](http://go.microsoft.com/fwlink/?LinkId=58810))</span></span>  
  
- <span data-ttu-id="865da-124">**RFC 2046 です。**</span><span class="sxs-lookup"><span data-stu-id="865da-124">**RFC 2046.**</span></span> <span data-ttu-id="865da-125">Multipurpose Internet Mail Extensions (MIME) Part Two: メディアの種類 (を参照してください[ http://go.microsoft.com/fwlink/?LinkId=58811 ](http://go.microsoft.com/fwlink/?LinkId=58811))</span><span class="sxs-lookup"><span data-stu-id="865da-125">Multipurpose Internet Mail Extensions (MIME) Part Two: Media Types (see [http://go.microsoft.com/fwlink/?LinkId=58811](http://go.microsoft.com/fwlink/?LinkId=58811))</span></span>  
  
- <span data-ttu-id="865da-126">**RFC 2047 です。**</span><span class="sxs-lookup"><span data-stu-id="865da-126">**RFC 2047.**</span></span> <span data-ttu-id="865da-127">MIME (Multipurpose Internet Mail Extensions) Part Three: の Message Header Extensions for NON-ASCII Text (を参照してください[ http://go.microsoft.com/fwlink/?LinkId=58812 ](http://go.microsoft.com/fwlink/?LinkId=58812))</span><span class="sxs-lookup"><span data-stu-id="865da-127">MIME (Multipurpose Internet Mail Extensions) Part Three: Message Header Extensions for Non-ASCII Text (see [http://go.microsoft.com/fwlink/?LinkId=58812](http://go.microsoft.com/fwlink/?LinkId=58812))</span></span>  
  
  <span data-ttu-id="865da-128">POP3 アダプターは、Microsoft Exchange Server 2003 に対して十分にテストされています。</span><span class="sxs-lookup"><span data-stu-id="865da-128">The POP3 adapter was tested extensively against Microsoft Exchange Server 2003.</span></span>  
  
## <a name="considerations-for-preventing-data-duplication-when-using-the-pop3-adapter"></a><span data-ttu-id="865da-129">POP3 アダプターの使用時にデータの重複を防ぐための考慮事項</span><span class="sxs-lookup"><span data-stu-id="865da-129">Considerations for Preventing Data Duplication When Using the POP3 Adapter</span></span>  
 <span data-ttu-id="865da-130">POP3 アダプターはトランザクション アダプターではないため、同じメッセージの複数のコピーを処理することがあります。これにより、データの重複が発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="865da-130">The POP3 adapter is not a transactional adapter and therefore is subject to processing multiple copies of the same message, potentially causing data duplication.</span></span> <span data-ttu-id="865da-131">次のシナリオでは、POP3 アダプターによってメッセージの重複したコピーが配信される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="865da-131">It is possible that the POP3 adapter will deliver duplicate copies of a message in the following scenarios:</span></span>  
  
-   <span data-ttu-id="865da-132">POP3 アダプターは、処理のために電子メールが BizTalk Server に正常に送信された後、POP3 アダプターが監視するように構成されているメールボックスから毎回電子メールを削除します。</span><span class="sxs-lookup"><span data-stu-id="865da-132">The POP3 adapter always deletes e-mails from the mailbox that it is configured to monitor after the e-mail has been successfully submitted to BizTalk Server for processing.</span></span> <span data-ttu-id="865da-133">POP3 アダプターがメールボックスから電子メールを取得し、処理のために BizTalk Server に送信した後、その電子メールをメールボックスから削除できなかった場合、次に POP3 アダプターからメールボックスへのポーリングが行われるときに、その電子メールは BizTalk Server に再送信されます。</span><span class="sxs-lookup"><span data-stu-id="865da-133">If the POP3 adapter retrieves an e-mail from a mailbox, submits the e-mail to BizTalk Server for processing, and fails to delete the e-mail from the mailbox, the e-mail will be resubmitted to BizTalk Server the next time that the POP3 adapter polls the mailbox.</span></span>  
  
-   <span data-ttu-id="865da-134">異なる BizTalk ホスト インスタンスにある POP3 アダプターの複数のインスタンスで同じメールボックスが同時に監視されていて、POP3 サーバーでメールボックスに対する複数の同時接続が許可されている場合、アダプターがメッセージの重複したコピーを配信することがあります。</span><span class="sxs-lookup"><span data-stu-id="865da-134">If multiple instances of the POP3 adapter in separate BizTalk Host instances are monitoring the same mailbox simultaneously and the POP3 server allows multiple concurrent connections to its mailboxes, then the adapter may deliver duplicate copies of messages.</span></span>  
  
## <a name="high-availability-for-the-pop3-adapter"></a><span data-ttu-id="865da-135">POP3 アダプターの高可用性</span><span class="sxs-lookup"><span data-stu-id="865da-135">High Availability for the POP3 Adapter</span></span>  
 <span data-ttu-id="865da-136">一部の POP3 サーバーでは、特定のメールボックスに対する複数の同時接続を許可しています。</span><span class="sxs-lookup"><span data-stu-id="865da-136">Some POP3 servers permit multiple concurrent connections to a given mailbox.</span></span> <span data-ttu-id="865da-137">POP3 アダプターの複数のインスタンスが、そのような POP3 サーバー上のメールボックスからメールを取得するように構成されている場合、データの重複が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="865da-137">If more than one instance of the POP3 adapter is configured to retrieve mail from a mailbox on such a POP3 server then data duplication can occur.</span></span> <span data-ttu-id="865da-138">このため、複数の同時接続を許可しているメールボックスからメールを取得するように構成する POP3 アダプターのインスタンスは、1 つのみにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="865da-138">Therefore you should configure only one instance of the POP3 adapter to retrieve mail from a mailbox that permits multiple concurrent connections.</span></span>  
  
 <span data-ttu-id="865da-139">このシナリオの POP3 アダプターにフォールト トレランスを提供するには、単一の POP3 アダプターの受信ハンドラーを、クラスター化された BizTalk ホストで実行されるように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="865da-139">To provide fault tolerance for the POP3 adapter in this scenario, a single POP3 adapter receive handler should be configured to run in a clustered BizTalk Host.</span></span> <span data-ttu-id="865da-140">詳細については、[されたクラスター化されたホストでアダプター ハンドラーの実行に関する考慮事項](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="865da-140">For more information see [Considerations for Running Adapter Handlers within a Clustered Host](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md).</span></span>  
  
## <a name="authentication-warnings-when-multiple-instances-of-the-pop3-adapter-connect-to-the-same-mailbox"></a><span data-ttu-id="865da-141">POP3 アダプターの複数のインスタンスから同じメールボックスへの接続が行われたときに発生する認証警告</span><span class="sxs-lookup"><span data-stu-id="865da-141">Authentication Warnings When Multiple Instances of the POP3 Adapter Connect to the Same Mailbox</span></span>  
 <span data-ttu-id="865da-142">BizTalk Server が、POP3 アダプターの複数のインスタンスで同じメールボックスからメールを取得するように構成されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="865da-142">BizTalk Server may be configured to have more than one instance of the POP3 adapter retrieve mail from the same mailbox.</span></span> <span data-ttu-id="865da-143">そのような場合、一部の POP3 サーバーで使用されているロック メカニズムが原因で、BizTalk Server アプリケーション ログに認証警告が記録される場合があります。</span><span class="sxs-lookup"><span data-stu-id="865da-143">In such a case, it is possible that authentication warnings may be generated in the BizTalk Server Application log because of the locking mechanism employed by some POP3 servers.</span></span> <span data-ttu-id="865da-144">これらの警告による POP3 アダプターの機能への影響はありません。そのため、このシナリオではこれらの警告を無視してもかまいません。</span><span class="sxs-lookup"><span data-stu-id="865da-144">These warnings will have no impact on the POP3 adapter functionality and can be safely ignored in this scenario.</span></span>  
  
## <a name="encrypted-messages-received-by-the-pop3-adapter-that-are-sent-to-the-suspended-queue-may-be-viewable-in-clear-text"></a><span data-ttu-id="865da-145">POP3 アダプターで受信して保留キューに送信する暗号化されたメッセージはクリア テキストで表示可能</span><span class="sxs-lookup"><span data-stu-id="865da-145">Encrypted Messages Received by the POP3 Adapter that are sent to the Suspended Queue may be Viewable in Clear Text</span></span>  
 <span data-ttu-id="865da-146">デジタル暗号化された電子メールが POP3 アダプターで復号化されるように構成できます。</span><span class="sxs-lookup"><span data-stu-id="865da-146">You can configure the POP3 adapter to decrypt digitally encrypted e-mails.</span></span> <span data-ttu-id="865da-147">これは、設定で、 **MIME デコードの適用**プロパティを**True**の受信場所を使用して、POP3 アダプター。</span><span class="sxs-lookup"><span data-stu-id="865da-147">This is done by setting the **Apply MIME Decoding** property to **True** for receive locations that use the POP3 adapter.</span></span> <span data-ttu-id="865da-148">POP3 アダプターがデジタル暗号化された電子メールを受信した場合、 **MIME デコードの適用**受信場所のプロパティに設定されて**True** POP3 アダプターが、次のように、電子メールの暗号化を解除しようとしています。 その後。</span><span class="sxs-lookup"><span data-stu-id="865da-148">If the POP3 Adapter receives a digitally encrypted e-mail and the **Apply MIME Decoding** property for the receive location is set to **True** then the POP3 adapter attempts to decrypt the e-mail as follows:</span></span>  
  
- <span data-ttu-id="865da-149">POP3 アダプターは、電子メールの暗号化に使用されたパブリック証明書に一致するプライベート証明書を検索します。</span><span class="sxs-lookup"><span data-stu-id="865da-149">The POP3 Adapter searches for a private certificate that matches the public certificate used to encrypt the e-mail.</span></span> <span data-ttu-id="865da-150">プライベート証明書は、POP3 受信ハンドラーがバインドされているホスト インスタンスが動作しているサーバーの個人証明書ストアにあります。</span><span class="sxs-lookup"><span data-stu-id="865da-150">The private certificate must be in the Personal certificate store of the server that is running the host instance that the POP3 receive handler is bound to.</span></span>  
  
- <span data-ttu-id="865da-151">対応するプライベート証明書が見つかると、POP3 アダプターはその証明書を使用して電子メール メッセージを復号化します。</span><span class="sxs-lookup"><span data-stu-id="865da-151">If the POP3 Adapter locates a corresponding private certificate, it uses the private certificate to decrypt the e-mail message.</span></span>  
  
- <span data-ttu-id="865da-152">電子メールが復号化され、BizTalk メッセージ ボックスに保存されます。</span><span class="sxs-lookup"><span data-stu-id="865da-152">The e-mail is decrypted and persisted to the BizTalk MessageBox.</span></span>  
  
  <span data-ttu-id="865da-153">復号化されたメッセージが BizTalk メッセージボックスに保存された後で保留されている場合、そのメッセージの内容は、BizTalk 保留キューからクリア テキストで表示できます。</span><span class="sxs-lookup"><span data-stu-id="865da-153">If a message is suspended after being decrypted and persisted to the BizTalk MessageBox, the contents of the message will be visible in clear text in the BizTalk suspended queue.</span></span>  
  
  <span data-ttu-id="865da-154">保留キュー内のセキュリティで保護されたメッセージ テキストを表示不可にする必要がある場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="865da-154">If you need to prevent the display of secure message text in the suspended queue, follow these steps:</span></span>  
  
- <span data-ttu-id="865da-155">設定、 **MIME デコードの適用**プロパティを**False**を使用して、POP3 アダプターの受信場所と、SMIME パイプライン コンポーネントを使用するパイプラインでメッセージを復号化します。</span><span class="sxs-lookup"><span data-stu-id="865da-155">Set the **Apply MIME Decoding** property to **False** for receive locations that use the POP3 adapter and decrypt the message in a pipeline with the SMIME pipeline component.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="865da-156">この方法により、電子メール固有のプロパティをメッセージ コンテキストに昇格させることができなくなります。</span><span class="sxs-lookup"><span data-stu-id="865da-156">This approach will prevent you from being able to promote e-mail specific properties to the message context.</span></span>  
  
- <span data-ttu-id="865da-157">電子メール固有のプロパティをメッセージ コンテキストに昇格させる必要がある場合は、暗号化されたメッセージが保留キューにルーティングされた後も暗号化された状態を維持できるように、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="865da-157">If you need to promote e-mail specific properties to the message context and ensure that encrypted messages remain encrypted if they are routed to the suspended queue, follow these steps:</span></span>  
  
  -   <span data-ttu-id="865da-158">オプションをオンに**失敗したメッセージのルーティングを有効にする**POP3 アダプターを使用する受信場所を格納する受信ポートにします。</span><span class="sxs-lookup"><span data-stu-id="865da-158">Check the option to **Enable routing for failed messages** on the receive port that houses the receive location(s) that use the POP3 adapter.</span></span>  
  
  -   <span data-ttu-id="865da-159">POP3 アダプターを使用する受信場所を格納する受信ポートへの配信が失敗したメッセージをサブスクライブするために、オーケストレーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="865da-159">Create an orchestration to subscribe to messages that fail delivery to the receive port that houses the receive location(s) that use the POP3 adapter.</span></span>  
  
  -   <span data-ttu-id="865da-160">SMIME パイプライン コンポーネントを使用してパイプライン内のメッセージを暗号化する送信ポートで、オーケストレーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="865da-160">Configure the orchestration with a send port that encrypts the message in a pipeline using the SMIME pipeline component.</span></span>  
  
  -   <span data-ttu-id="865da-161">オーケストレーション インスタンスおよびメッセージを保留する中断図形でオーケストレーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="865da-161">Configure the orchestration with a suspend shape to suspend the orchestration instance and the message.</span></span>  
  
  -   <span data-ttu-id="865da-162">オーケストレーションを構築して展開し、展開したオーケストレーションを適切な受信ポートにバインドします。</span><span class="sxs-lookup"><span data-stu-id="865da-162">Build and deploy the orchestration, bind the deployed orchestration to the appropriate receive port.</span></span>  
  
## <a name="maximum-message-size-supported-by-the-pop3-adapter"></a><span data-ttu-id="865da-163">POP3 アダプターによってサポートされているメッセージの最大サイズ</span><span class="sxs-lookup"><span data-stu-id="865da-163">Maximum Message Size Supported by the POP3 Adapter</span></span>  
 <span data-ttu-id="865da-164">POP3 アダプターでは、最大 50 MB のメッセージを受信できることをテスト済みで、このサイズがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="865da-164">The POP3 adapter has been tested with and supports receiving messages up to 50 MB in size.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="865da-165">参照</span><span class="sxs-lookup"><span data-stu-id="865da-165">See Also</span></span>  
 [<span data-ttu-id="865da-166">POP3 アダプター</span><span class="sxs-lookup"><span data-stu-id="865da-166">POP3 Adapter</span></span>](../core/pop3-adapter.md)