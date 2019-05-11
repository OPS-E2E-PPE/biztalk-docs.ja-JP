---
title: AS2 の処理に関する既知の問題 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 941111d8-b394-4648-a675-e4a8f118a84b
caps.latest.revision: 40
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 389184d177fe1b192db22660bdf382a6e64f37bf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65329386"
---
# <a name="known-issues-with-as2-processing"></a><span data-ttu-id="5bc71-102">AS2 の処理に関する既知の問題</span><span class="sxs-lookup"><span data-stu-id="5bc71-102">Known Issues with AS2 Processing</span></span>
<span data-ttu-id="5bc71-103">このセクションには、BizTalk Server AS2 ソリューションに関する既知の問題を説明するトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5bc71-103">This section contains topics that describe known issues with BizTalk Server AS2 solutions.</span></span>  
  
## <a name="as2-processing-not-supported-on-64-bit-computers"></a><span data-ttu-id="5bc71-104">AS2 処理の 64 ビット コンピューターでサポートされていません</span><span class="sxs-lookup"><span data-stu-id="5bc71-104">AS2 Processing Not Supported on 64-Bit Computers</span></span>  
 <span data-ttu-id="5bc71-105">BizTalk Server AS2 ソリューションは、64 ビット コンピューターではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="5bc71-105">The BizTalk Server AS2 solution is not supported on 64-bit computers.</span></span> <span data-ttu-id="5bc71-106">64 ビット コンピューターでの WOW64 エミュレーターで実行されているときに、32 ビット コンピューターで、または AS2 処理のみ機能します。</span><span class="sxs-lookup"><span data-stu-id="5bc71-106">AS2 processing only works on 32-bit computers or when running under the WOW64 emulator on 64-bit computers.</span></span>  
  
## <a name="the-as2-receive-pipelines-require-the-account-that-the-biztalk-isolated-host-instance-process-is-running-under-to-be-part-of-the-biztalk-application-users-group"></a><span data-ttu-id="5bc71-107">AS2 受信パイプラインが、BizTalk 分離ホスト インスタンス プロセスで実行されているに含まれて、BizTalk アプリケーション ユーザー グループのアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="5bc71-107">The AS2 Receive Pipelines Require the Account that the BizTalk Isolated Host Instance Process is Running Under to Be Part of the BizTalk Application Users Group</span></span>  
 <span data-ttu-id="5bc71-108">AS2EdiReceive または AS2Receive パイプラインを使用している場合は、BizTalk 分離ホスト インスタンス プロセスは、BizTalk Application Users グループで実行されているユーザー アカウントを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5bc71-108">If you are using the AS2EdiReceive or AS2Receive pipeline, you must add the user account that the BizTalk Isolated Host Instance process is running under to the BizTalk Application Users group.</span></span> <span data-ttu-id="5bc71-109">AS2EdiReceive と AS2Receive パイプラインは、BizTalk 分離ホスト インスタンス プロセスで実行します。</span><span class="sxs-lookup"><span data-stu-id="5bc71-109">The AS2EdiReceive and AS2Receive pipelines execute in the BizTalk Isolated Host Instance process.</span></span>  
  
## <a name="an-empty-receipt-delivery-option-header-will-cause-an-mdn-to-be-sent-synchronously"></a><span data-ttu-id="5bc71-110">Receipt-delivery-option ヘッダーが空白になります、MDN を同期的に送信します。</span><span class="sxs-lookup"><span data-stu-id="5bc71-110">An Empty Receipt-Delivery-Option Header Will Cause an MDN to Be Sent Synchronously</span></span>  
 <span data-ttu-id="5bc71-111">AS2Receive パイプラインが受信メッセージの receipt-delivery-option ヘッダーが空白を非同期 MDN が要求された場合は、パイプラインは、非同期 MDN 要求を無視します。</span><span class="sxs-lookup"><span data-stu-id="5bc71-111">If the AS2Receive pipeline receives a message with an empty receipt-delivery-option header, and an asynchronous MDN is requested, the pipeline will ignore the asynchronous MDN request.</span></span> <span data-ttu-id="5bc71-112">同期 MDN を代わりに、返信、イベント ログと AS2 状態レポート (有効な) 場合、エラーが送信されます。</span><span class="sxs-lookup"><span data-stu-id="5bc71-112">It will send back a synchronous MDN instead, and post an error in the event log and in AS2 status reporting (if it is enabled).</span></span> <span data-ttu-id="5bc71-113">これは、「受信メッセージのプロパティを上書きする」プロパティが選択されていない場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="5bc71-113">This occurs if the "Override inbound message properties" property is not selected.</span></span> <span data-ttu-id="5bc71-114">そのプロパティを選択した場合は、パーティの Receipt-delivery-option プロパティの値を持つメッセージのメッセージの Receipt-delivery-option ヘッダーを AS2 のプロパティ ダイアログ ボックスの AS2 メッセージの送信者 ページとしてオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="5bc71-114">If that property were selected, it would override the Receipt-Delivery-Option header in the message with the value of the Receipt-Delivery-Option property in the Party as AS2 Message Sender page of the AS2 Properties dialog box.</span></span>  
  
 <span data-ttu-id="5bc71-115">このインスタンスでの receipt-delivery-option ヘッダーが空であるため、AS2Receive パイプラインはありません非同期接続経由でへの MDN 応答を送信するアドレス。</span><span class="sxs-lookup"><span data-stu-id="5bc71-115">In this instance, because the receipt-delivery-option header is empty, the AS2Receive pipeline does not have an address to send the MDN response to over an asynchronous connection.</span></span> <span data-ttu-id="5bc71-116">ただし、パイプラインは、まだ、同期接続が開いてその接続を介して、MDN を送信します。</span><span class="sxs-lookup"><span data-stu-id="5bc71-116">However, the pipeline still has an open synchronous connection, so it will send the MDN back over that connection.</span></span> <span data-ttu-id="5bc71-117">一方向である場合は、受信ポート、BizTalk Server は、HTTP 200OK メッセージを送信した後で接続を閉じます。</span><span class="sxs-lookup"><span data-stu-id="5bc71-117">If it is a one-way receive port, BizTalk Server will close the connection after sending the HTTP 200OK message.</span></span>  
  
## <a name="use-of-unfolded-and-folded-http-line-headers"></a><span data-ttu-id="5bc71-118">展開された、折りたたまれた HTTP 行ヘッダーを使用して</span><span class="sxs-lookup"><span data-stu-id="5bc71-118">Use of Unfolded and Folded HTTP Line Headers</span></span>  
 <span data-ttu-id="5bc71-119">最大の相互運用性、AS2 メッセージの展開された HTTP 行ヘッダーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5bc71-119">For maximum interoperability, you should use unfolded HTTP line headers for AS2 messages.</span></span> <span data-ttu-id="5bc71-120">インフォメーション サービス (IIS) 7.0 には、展開された HTTP ヘッダーだけがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="5bc71-120">Information Services (IIS) 7.0 supports only unfolded HTTP headers.</span></span> <span data-ttu-id="5bc71-121">IIS 6.0 では、2 つ折りと折りたたまれたヘッダーをサポートします。</span><span class="sxs-lookup"><span data-stu-id="5bc71-121">IIS 6.0 supports folded and unfolded headers.</span></span> <span data-ttu-id="5bc71-122">ただし、すべてのシステムは、ため、このようなシステムの折りたたまれた行を使用する必要があります、80 以上の文字を 1 行のヘッダーをサポートできます。</span><span class="sxs-lookup"><span data-stu-id="5bc71-122">However, not all systems can support headers with more than 80 characters per line, so for such systems folded lines should be used.</span></span>  
  
 <span data-ttu-id="5bc71-123">BizTalk Server における AS2 の既定値は、展開された HTTP 行ヘッダーです。</span><span class="sxs-lookup"><span data-stu-id="5bc71-123">The default for AS2 in BizTalk Server is unfolded HTTP line headers.</span></span>  
  
## <a name="party-resolution-can-be-affected-by-a-localized-name"></a><span data-ttu-id="5bc71-124">パーティの解決はローカライズされた名前によって影響を受けることができます。</span><span class="sxs-lookup"><span data-stu-id="5bc71-124">Party Resolution Can Be Affected by a Localized Name</span></span>  
 <span data-ttu-id="5bc71-125">BizTalk Server では、送信 AS2 メッセージのパーティの解決を実行し、パーティの解決がメッセージ ヘッダー内のローカライズされた値によって影響を受けることができます。</span><span class="sxs-lookup"><span data-stu-id="5bc71-125">When BizTalk Server performs party resolution on an outbound AS2 message, the party resolution can be affected by a localized value in the message headers.</span></span> <span data-ttu-id="5bc71-126">場合、AS2 の既定では英語のパーティ名、および AS2 の値に設定されているため、AS2 のプロパティ ダイアログ ボックスの AS2 メッセージの受信者 ページで、パーティのプロパティをパーティに-英語以外の名前に設定されているメッセージの AS2 ヘッダーにし、一致が見つかりません。</span><span class="sxs-lookup"><span data-stu-id="5bc71-126">If the AS2-To party property in the Party as AS2 Message Receiver page of the AS2 Properties dialog box is set by default to an English party name, and the value in the AS2-To header of the AS2 message is set to a non-English name, then the match will not be found.</span></span>  
  
## <a name="as2-message-size-limitation"></a><span data-ttu-id="5bc71-127">AS2 メッセージのサイズ制限</span><span class="sxs-lookup"><span data-stu-id="5bc71-127">AS2 Message Size Limitation</span></span>  
 <span data-ttu-id="5bc71-128">暗号化された AS2 メッセージは、処理するために 96 メガバイト数よりも小さい必要があります。</span><span class="sxs-lookup"><span data-stu-id="5bc71-128">Encrypted AS2 messages should be smaller than 96 megabytes in order to be processed.</span></span> <span data-ttu-id="5bc71-129">AS2Receive と AS2EdiReceive パイプラインの一部である AS2 デコーダーでは、この制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="5bc71-129">This limitation is imposed by the AS2 Decoder, which is the part of the AS2Receive and AS2EdiReceive pipelines.</span></span>  
  
 <span data-ttu-id="5bc71-130">このサイズの制限を回避する方法の 1 つは、AS2 メッセージを圧縮すると、前に、暗号化されているため、圧縮を使用します。</span><span class="sxs-lookup"><span data-stu-id="5bc71-130">One way to work around this size limitation is to use compression, because an AS2 message is compressed before it is encrypted.</span></span>  
  
## <a name="biztalk-edi-application-must-not-be-modified"></a><span data-ttu-id="5bc71-131">BizTalk EDI アプリケーションを変更する必要がありません。</span><span class="sxs-lookup"><span data-stu-id="5bc71-131">BizTalk EDI Application Must Not Be Modified</span></span>  
 <span data-ttu-id="5bc71-132">BizTalk EDI アプリケーションのアイテムを変更または削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5bc71-132">Artifacts in the BizTalk EDI Application must not be modified or deleted.</span></span> <span data-ttu-id="5bc71-133">このアプリケーションが変更された場合は、構成を解除し、EDI および AS2 機能を再構成して、元のアプリケーションを復元する方法はありません。</span><span class="sxs-lookup"><span data-stu-id="5bc71-133">If this application is modified, there is no way for you to revert to the original application by unconfiguring and reconfiguring the EDI and AS2 features.</span></span>  
  
## <a name="partner-may-reject-multipart-messages"></a><span data-ttu-id="5bc71-134">パートナーがマルチパート メッセージを拒否します。</span><span class="sxs-lookup"><span data-stu-id="5bc71-134">Partner May Reject Multipart Messages</span></span>  
 <span data-ttu-id="5bc71-135">**現象**</span><span class="sxs-lookup"><span data-stu-id="5bc71-135">**Symptom**</span></span>  
  
 <span data-ttu-id="5bc71-136">送信パイプライン、AS2 を使用してマルチパート メッセージを送信する場合、パートナーが不足している Content-type MIME ヘッダーによりメッセージを拒否します。</span><span class="sxs-lookup"><span data-stu-id="5bc71-136">When sending multipart messages using the AS2 send pipeline, your partner may reject the message due to a missing Content-Type MIME header.</span></span>  
  
 <span data-ttu-id="5bc71-137">**考えられる原因**</span><span class="sxs-lookup"><span data-stu-id="5bc71-137">**Possible Cause**</span></span>  
  
 <span data-ttu-id="5bc71-138">コンテンツの種類は、各ボディ部のマルチパート メッセージに存在することができる省略可能なヘッダーです。</span><span class="sxs-lookup"><span data-stu-id="5bc71-138">Content-Type is an optional header that can be present for each body part in a multipart message.</span></span> <span data-ttu-id="5bc71-139">一部のパートナーでは、このヘッダーが各ボディ部、およびセットの特定のコンテンツの種類に存在することが必要です。</span><span class="sxs-lookup"><span data-stu-id="5bc71-139">Some partners require that this header is present for each body part, and set to a specific content-type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5bc71-140">すべての添付ファイルには、コンテンツの種類プロパティの設定はありません。 ただし、メッセージの本文は、AS2 送信パイプラインで設定するコンテンツの種類プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="5bc71-140">The body of the message will have the Content-Type property set by the AS2 send pipeline, however any attachments will not have the Content-Type property set.</span></span>  
  
 <span data-ttu-id="5bc71-141">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="5bc71-141">**Resolution**</span></span>  
  
 <span data-ttu-id="5bc71-142">パートナーは、各ボディ部の Content-type ヘッダーの値を必要とする場合は、このプロパティを設定するカスタム パイプライン コンポーネントを作成および送信パイプラインでコンポーネントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5bc71-142">If your partner requires the Content-Type header value for each body part, you must create a custom pipeline component that sets this property and use the component in the send pipeline.</span></span>  
  
## <a name="when-receiving-multipart-messages-the-first-part-is-considered-the-body"></a><span data-ttu-id="5bc71-143">マルチパート メッセージの受信、最初の部分と見なされるタイミング本文</span><span class="sxs-lookup"><span data-stu-id="5bc71-143">When Receiving Multipart Messages, the First Part is Considered the Body</span></span>  
 <span data-ttu-id="5bc71-144">**現象**</span><span class="sxs-lookup"><span data-stu-id="5bc71-144">**Symptom**</span></span>  
  
 <span data-ttu-id="5bc71-145">マルチパートの AS2 メッセージの受信時[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可能性があります誤認する添付ファイルのいずれかのメッセージ本文として。</span><span class="sxs-lookup"><span data-stu-id="5bc71-145">When receiving a multipart AS2 message, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] may incorrectly identify one of the attachments as the message body.</span></span>  
  
 <span data-ttu-id="5bc71-146">**考えられる原因**</span><span class="sxs-lookup"><span data-stu-id="5bc71-146">**Possible Cause**</span></span>  
  
 <span data-ttu-id="5bc71-147">マルチパート/関連メッセージの MIME ヘッダー、省略可能な場合がありますを指定する部分の 'start' のパラメーターは、パーツのコンテンツ ID を指定して、メッセージの本文として扱う必要があります。</span><span class="sxs-lookup"><span data-stu-id="5bc71-147">The MIME header of a multipart/related message may contain an optional ‘start’ parameter that indicates which of the parts should be treated as the body of the message by specifying the Content-ID of the part.</span></span> <span data-ttu-id="5bc71-148">Start パラメーターが存在しない場合は、最初の部分がメッセージの本文を検討してください。</span><span class="sxs-lookup"><span data-stu-id="5bc71-148">If the start parameter is not present, the first part should be considered the body of the message.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="5bc71-149">メッセージの本文として最初の部分は常に扱いますが存在する場合は、start パラメーターを考慮しません。</span><span class="sxs-lookup"><span data-stu-id="5bc71-149">does not honor the start parameter if it is present, and will always treat the first part as the body of the message.</span></span>  
  
 <span data-ttu-id="5bc71-150">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="5bc71-150">**Resolution**</span></span>  
  
 <span data-ttu-id="5bc71-151">パートナーがマルチパート/関連メッセージの最初の部分として本文を送信できるように、メッセージの本文を正しく識別するパイプライン コンポーネントを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5bc71-151">If your partner is unable to send the body as the first part of the multipart/related message, you must create a pipeline component that correctly identifies the body of the message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bc71-152">参照</span><span class="sxs-lookup"><span data-stu-id="5bc71-152">See Also</span></span>  
 <span data-ttu-id="5bc71-153">[EDI および AS2 ソリューションのトラブルシューティング](../core/troubleshooting-edi-and-as2-solutions.md) </span><span class="sxs-lookup"><span data-stu-id="5bc71-153">[Troubleshooting EDI and AS2 Solutions](../core/troubleshooting-edi-and-as2-solutions.md) </span></span>  
 <span data-ttu-id="5bc71-154">[AS2 ソリューションのアーキテクチャ](../core/as2-solution-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="5bc71-154">[AS2 Solution Architecture](../core/as2-solution-architecture.md) </span></span>  
 [<span data-ttu-id="5bc71-155">BizTalk Server AS2 ソリューションの開発と構成</span><span class="sxs-lookup"><span data-stu-id="5bc71-155">Developing and Configuring BizTalk Server AS2 Solutions</span></span>](../core/developing-and-configuring-biztalk-server-as2-solutions.md)