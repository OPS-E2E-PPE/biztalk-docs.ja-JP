---
title: "AS2 処理に関する既知の問題 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 941111d8-b394-4648-a675-e4a8f118a84b
caps.latest.revision: "40"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64899c184f8cbe405684387b8f1c2a6230204624
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="known-issues-with-as2-processing"></a><span data-ttu-id="0e078-102">AS2 の処理に関する既知の問題</span><span class="sxs-lookup"><span data-stu-id="0e078-102">Known Issues with AS2 Processing</span></span>
<span data-ttu-id="0e078-103">ここには、[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] AS2 ソリューションの既知の問題について説明するトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0e078-103">This section contains topics that describe known issues with [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] AS2 solutions.</span></span>  
  
## <a name="as2-processing-not-supported-on-64-bit-computers"></a><span data-ttu-id="0e078-104">AS2 処理が 64 ビット コンピューターに対応していない</span><span class="sxs-lookup"><span data-stu-id="0e078-104">AS2 Processing Not Supported on 64-Bit Computers</span></span>  
 <span data-ttu-id="0e078-105">[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] AS2 ソリューションは、64 ビット コンピューターに対応していません。</span><span class="sxs-lookup"><span data-stu-id="0e078-105">The [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] AS2 solution is not supported on 64-bit computers.</span></span> <span data-ttu-id="0e078-106">AS2 処理を正しく行えるのは、32 ビット コンピューターで実行する場合、または 64 ビット コンピューター上の WOW64 エミュレーターで実行する場合のみです。</span><span class="sxs-lookup"><span data-stu-id="0e078-106">AS2 processing only works on 32-bit computers or when running under the WOW64 emulator on 64-bit computers.</span></span>  
  
## <a name="the-as2-receive-pipelines-require-the-account-that-the-biztalk-isolated-host-instance-process-is-running-under-to-be-part-of-the-biztalk-application-users-group"></a><span data-ttu-id="0e078-107">AS2 受信パイプラインでは、BizTalk 分離ホスト インスタンス プロセスの実行に使用するアカウントが BizTalk アプリケーション ユーザー グループに含まれていることが必要</span><span class="sxs-lookup"><span data-stu-id="0e078-107">The AS2 Receive Pipelines Require the Account that the BizTalk Isolated Host Instance Process is Running Under to Be Part of the BizTalk Application Users Group</span></span>  
 <span data-ttu-id="0e078-108">AS2EdiReceive パイプラインまたは AS2Receive パイプラインを使用する場合は、BizTalk Application Users グループに、BizTalk 分離ホスト インスタンス プロセスが実行されているユーザー アカウントを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e078-108">If you are using the AS2EdiReceive or AS2Receive pipeline, you must add the user account that the BizTalk Isolated Host Instance process is running under to the BizTalk Application Users group.</span></span> <span data-ttu-id="0e078-109">AS2EdiReceive パイプラインと AS2Receive パイプラインは、BizTalk 分離ホスト インスタンス プロセスで実行されます。</span><span class="sxs-lookup"><span data-stu-id="0e078-109">The AS2EdiReceive and AS2Receive pipelines execute in the BizTalk Isolated Host Instance process.</span></span>  
  
## <a name="an-empty-receipt-delivery-option-header-will-cause-an-mdn-to-be-sent-synchronously"></a><span data-ttu-id="0e078-110">Receipt-Delivery-Option ヘッダーを空白にすると、MDN が同期送信される</span><span class="sxs-lookup"><span data-stu-id="0e078-110">An Empty Receipt-Delivery-Option Header Will Cause an MDN to Be Sent Synchronously</span></span>  
 <span data-ttu-id="0e078-111">Receipt-Delivery-Option ヘッダーが空白のメッセージを AS2Receive パイプラインが受信した場合に、非同期 MDN が要求されると、このパイプラインは非同期 MDN 要求を無視します。</span><span class="sxs-lookup"><span data-stu-id="0e078-111">If the AS2Receive pipeline receives a message with an empty receipt-delivery-option header, and an asynchronous MDN is requested, the pipeline will ignore the asynchronous MDN request.</span></span> <span data-ttu-id="0e078-112">パイプラインは、代わりに同期 MDN を返して、イベント ログと AS2 状態レポート (有効になっている場合) にエラーを送信します。</span><span class="sxs-lookup"><span data-stu-id="0e078-112">It will send back a synchronous MDN instead, and post an error in the event log and in AS2 status reporting (if it is enabled).</span></span> <span data-ttu-id="0e078-113">この問題は、"受信メッセージのプロパティを上書きする" プロパティが選択されていない場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="0e078-113">This occurs if the "Override inbound message properties" property is not selected.</span></span> <span data-ttu-id="0e078-114">このプロパティを選択した場合、メッセージ内の Receipt-Delivery-Option ヘッダーは、[AS2 のプロパティ] ダイアログ ボックスの [パーティ - AS2 メッセージの送信者] ページにある Receipt-Delivery-Option プロパティの値で上書きされます。</span><span class="sxs-lookup"><span data-stu-id="0e078-114">If that property were selected, it would override the Receipt-Delivery-Option header in the message with the value of the Receipt-Delivery-Option property in the Party as AS2 Message Sender page of the AS2 Properties dialog box.</span></span>  
  
 <span data-ttu-id="0e078-115">この場合、Receipt-Delivery-Option ヘッダーが空白なので、AS2Receive パイプラインには非同期接続を介した MDN 応答の送信先アドレスが指定されていません。</span><span class="sxs-lookup"><span data-stu-id="0e078-115">In this instance, because the receipt-delivery-option header is empty, the AS2Receive pipeline does not have an address to send the MDN response to over an asynchronous connection.</span></span> <span data-ttu-id="0e078-116">ただし、パイプラインの同期接続は開かれたままなので、MDN は同期接続を介して送り返されます。</span><span class="sxs-lookup"><span data-stu-id="0e078-116">However, the pipeline still has an open synchronous connection, so it will send the MDN back over that connection.</span></span> <span data-ttu-id="0e078-117">これが一方向の受信ポートの場合、BizTalk Server は、HTTP 200OK メッセージを送信した後で接続を閉じます。</span><span class="sxs-lookup"><span data-stu-id="0e078-117">If it is a one-way receive port, BizTalk Server will close the connection after sending the HTTP 200OK message.</span></span>  
  
## <a name="use-of-unfolded-and-folded-http-line-headers"></a><span data-ttu-id="0e078-118">展開された HTTP 行ヘッダーと折りたたまれた HTTP 行ヘッダーの使用</span><span class="sxs-lookup"><span data-stu-id="0e078-118">Use of Unfolded and Folded HTTP Line Headers</span></span>  
 <span data-ttu-id="0e078-119">相互運用性を最大化するには、展開された HTTP 行ヘッダーを AS2 メッセージに対して使用します。</span><span class="sxs-lookup"><span data-stu-id="0e078-119">For maximum interoperability, you should use unfolded HTTP line headers for AS2 messages.</span></span> <span data-ttu-id="0e078-120">インフォメーション サービス (IIS) 7.0 は展開された HTTP ヘッダーにのみ対応しています。</span><span class="sxs-lookup"><span data-stu-id="0e078-120">Information Services (IIS) 7.0 supports only unfolded HTTP headers.</span></span> <span data-ttu-id="0e078-121">IIS 6.0 は展開されたヘッダーと折りたたまれたヘッダーに対応しています。</span><span class="sxs-lookup"><span data-stu-id="0e078-121">IIS 6.0 supports folded and unfolded headers.</span></span> <span data-ttu-id="0e078-122">ただし、一部のシステムは、1 行あたりの文字数が 80 を上回るヘッダーに対応していません。そのため、これらのシステムでは、折りたたまれた行を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e078-122">However, not all systems can support headers with more than 80 characters per line, so for such systems folded lines should be used.</span></span>  
  
 <span data-ttu-id="0e078-123">[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] の AS2 の既定値は展開された HTTP 行ヘッダーです。</span><span class="sxs-lookup"><span data-stu-id="0e078-123">The default for AS2 in [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] is unfolded HTTP line headers.</span></span>  
  
## <a name="party-resolution-can-be-affected-by-a-localized-name"></a><span data-ttu-id="0e078-124">ローカライズされた名前がパーティの解決に影響する場合がある</span><span class="sxs-lookup"><span data-stu-id="0e078-124">Party Resolution Can Be Affected by a Localized Name</span></span>  
 <span data-ttu-id="0e078-125">BizTalk Server が送信 AS2 メッセージに対してパーティの解決を実行すると、メッセージ ヘッダー内のローカライズされた値がパーティの解決に影響する場合があります。</span><span class="sxs-lookup"><span data-stu-id="0e078-125">When BizTalk Server performs party resolution on an outbound AS2 message, the party resolution can be affected by a localized value in the message headers.</span></span> <span data-ttu-id="0e078-126">[AS2 のプロパティ] ダイアログ ボックスの [パーティ - AS2 メッセージの受信者] ページにある AS2-To パーティ プロパティが既定で英語のパーティ名に設定されている場合に、AS2 メッセージの AS2-To ヘッダー内の値が英語以外の名前に設定されていると、一致した項目は見つかりません。</span><span class="sxs-lookup"><span data-stu-id="0e078-126">If the AS2-To party property in the Party as AS2 Message Receiver page of the AS2 Properties dialog box is set by default to an English party name, and the value in the AS2-To header of the AS2 message is set to a non-English name, then the match will not be found.</span></span>  
  
## <a name="as2-message-size-limitation"></a><span data-ttu-id="0e078-127">AS2 メッセージのサイズ制限</span><span class="sxs-lookup"><span data-stu-id="0e078-127">AS2 Message Size Limitation</span></span>  
 <span data-ttu-id="0e078-128">暗号化された AS2 メッセージは、サイズが 96 MB 未満でないと処理されません。</span><span class="sxs-lookup"><span data-stu-id="0e078-128">Encrypted AS2 messages should be smaller than 96 megabytes in order to be processed.</span></span> <span data-ttu-id="0e078-129">この制限は、AS2Receive パイプラインと AS2EdiReceive パイプラインに含まれている AS2 デコーダーによるものです。</span><span class="sxs-lookup"><span data-stu-id="0e078-129">This limitation is imposed by the AS2 Decoder, which is the part of the AS2Receive and AS2EdiReceive pipelines.</span></span>  
  
 <span data-ttu-id="0e078-130">AS2 メッセージは圧縮されてから暗号化されるので、圧縮機能を使用すると、このサイズ制限を回避できます。</span><span class="sxs-lookup"><span data-stu-id="0e078-130">One way to work around this size limitation is to use compression, because an AS2 message is compressed before it is encrypted.</span></span>  
  
## <a name="biztalk-edi-application-must-not-be-modified"></a><span data-ttu-id="0e078-131">BizTalk EDI アプリケーションを変更できない</span><span class="sxs-lookup"><span data-stu-id="0e078-131">BizTalk EDI Application Must Not Be Modified</span></span>  
 <span data-ttu-id="0e078-132">BizTalk EDI アプリケーション内のアイテムは、変更または削除できません。</span><span class="sxs-lookup"><span data-stu-id="0e078-132">Artifacts in the BizTalk EDI Application must not be modified or deleted.</span></span> <span data-ttu-id="0e078-133">このアプリケーションを変更すると、EDI 機能や AS2 機能の構成を解除して再構成しても、元のアプリケーションを復元することはできません。</span><span class="sxs-lookup"><span data-stu-id="0e078-133">If this application is modified, there is no way for you to revert to the original application by unconfiguring and reconfiguring the EDI and AS2 features.</span></span>  
  
## <a name="partner-may-reject-multipart-messages"></a><span data-ttu-id="0e078-134">パートナーがマルチパート メッセージを拒否することがある</span><span class="sxs-lookup"><span data-stu-id="0e078-134">Partner May Reject Multipart Messages</span></span>  
 <span data-ttu-id="0e078-135">**現象**</span><span class="sxs-lookup"><span data-stu-id="0e078-135">**Symptom**</span></span>  
  
 <span data-ttu-id="0e078-136">AS2 送信パイプラインを使用してマルチパート メッセージを送信する場合、Content-Type MIME ヘッダーがないため、パートナーがメッセージを拒否することがあります。</span><span class="sxs-lookup"><span data-stu-id="0e078-136">When sending multipart messages using the AS2 send pipeline, your partner may reject the message due to a missing Content-Type MIME header.</span></span>  
  
 <span data-ttu-id="0e078-137">**考えられる原因**</span><span class="sxs-lookup"><span data-stu-id="0e078-137">**Possible Cause**</span></span>  
  
 <span data-ttu-id="0e078-138">Content-Type は、マルチパート メッセージの各ボディ部に配置できる省略可能なヘッダーです。</span><span class="sxs-lookup"><span data-stu-id="0e078-138">Content-Type is an optional header that can be present for each body part in a multipart message.</span></span> <span data-ttu-id="0e078-139">パートナーによっては、このヘッダーが各ボディ部に存在し、特定のコンテンツの種類に設定されていることを要求します。</span><span class="sxs-lookup"><span data-stu-id="0e078-139">Some partners require that this header is present for each body part, and set to a specific content-type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0e078-140">メッセージの本文には AS2 送信パイプラインによって Content-Type プロパティが設定されますが、添付ファイルには Content-Type プロパティが設定されません。</span><span class="sxs-lookup"><span data-stu-id="0e078-140">The body of the message will have the Content-Type property set by the AS2 send pipeline, however any attachments will not have the Content-Type property set.</span></span>  
  
 <span data-ttu-id="0e078-141">**解決策**</span><span class="sxs-lookup"><span data-stu-id="0e078-141">**Resolution**</span></span>  
  
 <span data-ttu-id="0e078-142">パートナーが各ボディ部の Content-Type ヘッダー値を要求する場合、このプロパティを設定するカスタム パイプライン コンポーネントを作成し、送信パイプラインでこのコンポーネントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e078-142">If your partner requires the Content-Type header value for each body part, you must create a custom pipeline component that sets this property and use the component in the send pipeline.</span></span>  
  
## <a name="when-receiving-multipart-messages-the-first-part-is-considered-the-body"></a><span data-ttu-id="0e078-143">マルチパート メッセージの受信時に最初の部分が本文と見なされる</span><span class="sxs-lookup"><span data-stu-id="0e078-143">When Receiving Multipart Messages, the First Part is Considered the Body</span></span>  
 <span data-ttu-id="0e078-144">**現象**</span><span class="sxs-lookup"><span data-stu-id="0e078-144">**Symptom**</span></span>  
  
 <span data-ttu-id="0e078-145">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、マルチパート AS2 メッセージの受信時に、添付ファイルの 1 つを間違ってメッセージ本文と識別することがあります。</span><span class="sxs-lookup"><span data-stu-id="0e078-145">When receiving a multipart AS2 message, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] may incorrectly identify one of the attachments as the message body.</span></span>  
  
 <span data-ttu-id="0e078-146">**考えられる原因**</span><span class="sxs-lookup"><span data-stu-id="0e078-146">**Possible Cause**</span></span>  
  
 <span data-ttu-id="0e078-147">マルチパート/関連メッセージの MIME ヘッダーには、どの部分をメッセージの本文として扱うかを示す、省略可能な "start" パラメーターが含まれていることがあります (その部分の Content-ID を指定)。</span><span class="sxs-lookup"><span data-stu-id="0e078-147">The MIME header of a multipart/related message may contain an optional ‘start’ parameter that indicates which of the parts should be treated as the body of the message by specifying the Content-ID of the part.</span></span> <span data-ttu-id="0e078-148">Start パラメーターが存在しない場合は、最初の部分がメッセージの本文を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="0e078-148">If the start parameter is not present, the first part should be considered the body of the message.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="0e078-149">存在し、メッセージの本文として最初の部分を処理は常には、start パラメーターを考慮しません。</span><span class="sxs-lookup"><span data-stu-id="0e078-149"> does not honor the start parameter if it is present, and will always treat the first part as the body of the message.</span></span>  
  
 <span data-ttu-id="0e078-150">**解決策**</span><span class="sxs-lookup"><span data-stu-id="0e078-150">**Resolution**</span></span>  
  
 <span data-ttu-id="0e078-151">パートナーがマルチパート/関連メッセージの最初の部分として本文を送信できない場合、メッセージの本文を正しく識別するパイプライン コンポーネントを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e078-151">If your partner is unable to send the body as the first part of the multipart/related message, you must create a pipeline component that correctly identifies the body of the message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e078-152">参照</span><span class="sxs-lookup"><span data-stu-id="0e078-152">See Also</span></span>  
 <span data-ttu-id="0e078-153">[EDI および AS2 ソリューションのトラブルシューティング](../core/troubleshooting-edi-and-as2-solutions.md) </span><span class="sxs-lookup"><span data-stu-id="0e078-153">[Troubleshooting EDI and AS2 Solutions](../core/troubleshooting-edi-and-as2-solutions.md) </span></span>  
 <span data-ttu-id="0e078-154">[AS2 ソリューションのアーキテクチャ](../core/as2-solution-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="0e078-154">[AS2 Solution Architecture](../core/as2-solution-architecture.md) </span></span>  
 [<span data-ttu-id="0e078-155">開発と BizTalk Server AS2 ソリューションの構成</span><span class="sxs-lookup"><span data-stu-id="0e078-155">Developing and Configuring BizTalk Server AS2 Solutions</span></span>](../core/developing-and-configuring-biztalk-server-as2-solutions.md)