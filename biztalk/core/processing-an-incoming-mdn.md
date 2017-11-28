---
title: "受信 MDN の処理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fd78e84c-4989-47e4-b95b-80582084ddec
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e599e9ebbc7a05a466cc047d891699222c2dabac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="processing-an-incoming-mdn"></a><span data-ttu-id="ec38a-102">受信 MDN の処理</span><span class="sxs-lookup"><span data-stu-id="ec38a-102">Processing an Incoming MDN</span></span>
<span data-ttu-id="ec38a-103">AS2 受信パイプライン (AS2EDIReceive と AS2Receive) は、AS2 メッセージ受信者であるパーティのアグリーメント プロパティに基づいて受信 MDN を処理します。</span><span class="sxs-lookup"><span data-stu-id="ec38a-103">The AS2 receive pipelines (AS2EDIReceive and AS2Receive) process an incoming MDN based upon the agreement properties for the party as an AS2 message receiver.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="ec38a-104"> により、送信 AS2 メッセージに対して MDN が自動的に関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="ec38a-104"> automatically correlates the MDN to the outgoing AS2 message.</span></span>  
  
 <span data-ttu-id="ec38a-105">各パイプラインが実行する手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ec38a-105">The steps each pipeline performs are as follows:</span></span>  
  
-   <span data-ttu-id="ec38a-106">AS2 を照合することによって、送信元パーティを決定-メッセージの AS2 ヘッダーの値が AS2 の値からのリストから、**識別子**の一方向の AS2 アグリーメント タブのページ、 **アグリーメントのプロパティ**  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="ec38a-106">Determines the sending party by matching the AS2-From value in the AS2 header of the message with the value for AS2-From list in the **Identifiers** page of the one-way AS2 agreement tab of the **Agreement Properties** dialog box.</span></span> <span data-ttu-id="ec38a-107">一致するものが見つからない場合、パイプラインは処理を中止し、例外を発生させます。</span><span class="sxs-lookup"><span data-stu-id="ec38a-107">If a match is not found, the pipeline aborts processing and raises an exception.</span></span>  
  
-   <span data-ttu-id="ec38a-108">次の AS2 プロパティをコンテキストに昇格します。</span><span class="sxs-lookup"><span data-stu-id="ec38a-108">Promotes the following AS2 properties to the context:</span></span>  
  
    -   <span data-ttu-id="ec38a-109">IsAS2FailedMessage</span><span class="sxs-lookup"><span data-stu-id="ec38a-109">IsAS2FailedMessage</span></span>  
  
    -   <span data-ttu-id="ec38a-110">DispositionType</span><span class="sxs-lookup"><span data-stu-id="ec38a-110">DispositionType</span></span>  
  
    -   <span data-ttu-id="ec38a-111">GenerateAsynchronous200OKOnly</span><span class="sxs-lookup"><span data-stu-id="ec38a-111">GenerateAsynchronous200OKOnly</span></span>  
  
    -   <span data-ttu-id="ec38a-112">IsAS2MdnResponseMessage</span><span class="sxs-lookup"><span data-stu-id="ec38a-112">IsAS2MdnResponseMessage</span></span>  
  
    -   <span data-ttu-id="ec38a-113">IsAS2MessageSigned</span><span class="sxs-lookup"><span data-stu-id="ec38a-113">IsAS2MessageSigned</span></span>  
  
    -   <span data-ttu-id="ec38a-114">OriginalMessageId</span><span class="sxs-lookup"><span data-stu-id="ec38a-114">OriginalMessageId</span></span>  
  
    -   <span data-ttu-id="ec38a-115">ReceivedContentMic</span><span class="sxs-lookup"><span data-stu-id="ec38a-115">ReceivedContentMic</span></span>  
  
    -   <span data-ttu-id="ec38a-116">DispositionMode</span><span class="sxs-lookup"><span data-stu-id="ec38a-116">DispositionMode</span></span>  
  
    -   <span data-ttu-id="ec38a-117">MessageId</span><span class="sxs-lookup"><span data-stu-id="ec38a-117">MessageId</span></span>  
  
-   <span data-ttu-id="ec38a-118">メッセージのすべての HTTP ヘッダーに InboundHttpHeaders プロパティを設定し、メッセージのコンテキストに昇格させます。</span><span class="sxs-lookup"><span data-stu-id="ec38a-118">Sets the InboundHttpHeaders property to all the HTTP headers of the message, and promotes it to the context of the message.</span></span>  
  
-   <span data-ttu-id="ec38a-119">MDN のコピー (ワイヤ形式) を作成し、否認不可データベース (BizTalkDTADb データベースの EdiMessageContent テーブル) に保存します (一方向の AS2 アグリーメントのプロパティで有効になっている場合)。</span><span class="sxs-lookup"><span data-stu-id="ec38a-119">Makes a copy of the MDN (in wire format), and stores the copy in the non-repudiation database (the EdiMessageContent table of the BizTalkDTADb database), if enabled in the one-way AS2 agreement properties.</span></span>  
  
-   <span data-ttu-id="ec38a-120">署名の確認を含む MIME 処理を実行します (署名付き MDN の場合)。</span><span class="sxs-lookup"><span data-stu-id="ec38a-120">Performs MIME processing, including verifying the signature if the MDN was signed.</span></span>  
  
-   <span data-ttu-id="ec38a-121">MDN のメッセージ整合性チェック (MIC) を、元のメッセージが送信されるときに AS2Send パイプラインによって算出されたデータ ストアの MIC と比較します (該当する場合)。</span><span class="sxs-lookup"><span data-stu-id="ec38a-121">Compares the MIC (Message Integrity Check) in the MDN with the MIC in the data store that was computed by the AS2Send pipeline when it sent out the original message (if applicable).</span></span> <span data-ttu-id="ec38a-122">詳細については、次を参照してください。 [MDN メッセージ](../core/mdn-messages.md)です。</span><span class="sxs-lookup"><span data-stu-id="ec38a-122">For more information, see [MDN Messages](../core/mdn-messages.md).</span></span>  
  
-   <span data-ttu-id="ec38a-123">否認不可データベースに関連付けのエントリを作成します。</span><span class="sxs-lookup"><span data-stu-id="ec38a-123">Makes correlation entries in the non-repudiation database.</span></span>  
  
-   <span data-ttu-id="ec38a-124">場合を除き、MDN を削除、**メッセージ ボックスに受信 MDN をルーティング/配信用処理**にプロパティを設定、**送信者の MDN 設定**の一方向の AS2 アグリーメント タブのページ、 **アグリーメントのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="ec38a-124">Deletes the MDN, unless the **Process inbound MDN into MessageBox for routing/delivery options** property is set in the **Sender MDN Settings** page of the one-way AS2 agreement tab of the **Agreement Properties** dialog box.</span></span>  
  
-   <span data-ttu-id="ec38a-125">場合、**メッセージ ボックスに受信 MDN をルーティング/配信用処理**にプロパティを設定、**送信者の MDN 設定**の一方向の AS2 アグリーメント タブのページ、**アグリーメントのプロパティ**ダイアログ ボックスで、受信パイプラインをパススルー メッセージとして AS2 デコーダーを経由してワイヤ形式で MDN をルーティングし、MessageBox にドロップします。</span><span class="sxs-lookup"><span data-stu-id="ec38a-125">If the **Process inbound MDN into MessageBox for routing/delivery options** property is set in the **Sender MDN Settings** page of the one-way AS2 agreement tab of the **Agreement Properties** dialog box, the receive pipeline routes the MDN in wire format through the AS2 Decoder as a passthrough message and drops it into the MessageBox.</span></span> <span data-ttu-id="ec38a-126">ワイヤ形式の MDN には、すべての HTTP ヘッダーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ec38a-126">The MDN in wire format contains all HTTP headers.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ec38a-127">送信ポートを設定して、メッセージ ボックスにドロップされた受信 MDN へのサブスクライブを行うようにできます。</span><span class="sxs-lookup"><span data-stu-id="ec38a-127">You can set up a send port to subscribe to a received MDN that has been dropped into the MessageBox.</span></span> <span data-ttu-id="ec38a-128">受信された MDN をサブスクライブするには、送信ポート フィルターを `IsAS2MdnResponseMessage==True` に設定します。</span><span class="sxs-lookup"><span data-stu-id="ec38a-128">To subscribe to the received MDN, set the send port filter to `IsAS2MdnResponseMessage==True`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ec38a-129">受信 MDN の処理に AS2EdiReceive パイプラインを使用する場合することはできませんに MDN をルーティング、メッセージ ボックス データベースを設定して、**メッセージ ボックスに受信 MDN をルーティング/配信用処理**プロパティに、**送信者の MDN設定**の一方向の AS2 アグリーメント タブのページ、**アグリーメントのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="ec38a-129">If you use the AS2EdiReceive pipeline to process a received MDN, you cannot route the MDN into the MessageBox by setting the **Process inbound MDN into MessageBox for routing/delivery options** property in the **Sender MDN Settings** page of the one-way AS2 agreement tab of the **Agreement Properties** dialog box.</span></span> <span data-ttu-id="ec38a-130">操作を行うとすると、MDN を処理できない EDI デコーダーに対して MDN が渡されるために、EDI エラーが発生するされます。</span><span class="sxs-lookup"><span data-stu-id="ec38a-130">Trying to do so will result in an EDI error because the MDN will be passed to the EDI Decoder, which cannot process an MDN.</span></span> <span data-ttu-id="ec38a-131">MDN がメッセージ ボックスに送信されないと、AS2 デコーダーは MDN を利用 (消費) するため、MDN は EDI デコーダーに渡されません。</span><span class="sxs-lookup"><span data-stu-id="ec38a-131">If the MDN is not sent to the MessageBox, the AS2Decoder will consume the MDN, so it will not be passed to the EDI Decoder.</span></span>  
  
## <a name="message-integrity-check"></a><span data-ttu-id="ec38a-132">メッセージ整合性チェック</span><span class="sxs-lookup"><span data-stu-id="ec38a-132">Message Integrity Check</span></span>  
 <span data-ttu-id="ec38a-133">メッセージ整合性チェック (MIC) は、MDN が元の送信メッセージに関連付けられていることを検証するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="ec38a-133">The Message Integrity Check (MIC) is used to verify that an MDN correlates to the original sent message.</span></span> <span data-ttu-id="ec38a-134">AS2Send 送信パイプラインは、元の AS2 メッセージを生成するときにメッセージ ペイロードから MIC を計算し、算出した MIC をデータ ストアに格納します。</span><span class="sxs-lookup"><span data-stu-id="ec38a-134">The AS2Send send pipeline calculates the MIC from the message payload when it generates the original AS2 message, and stores the MIC in the data store.</span></span> <span data-ttu-id="ec38a-135">MDN が要求されている場合、元のメッセージの受信者は MIC を生成して MDN に追加します。</span><span class="sxs-lookup"><span data-stu-id="ec38a-135">When an MDN is required, the recipient of the original message generates an MIC and adds it to the MDN.</span></span> <span data-ttu-id="ec38a-136">AS2MdnReceive 受信パイプラインが MDN を受信したとき、署名付き MDN が要求されている場合は、MDN 内の MIC がデータ ストア内の MIC に対して比較されます。</span><span class="sxs-lookup"><span data-stu-id="ec38a-136">When the AS2MdnReceive receive pipeline receives the MDN, if a signed MDN was requested, it compares the MIC in the MDN with the MIC in the data store.</span></span>  
  
 <span data-ttu-id="ec38a-137">MDN 内の MIC とデータ ストア内の MIC が一致しない場合、転送中または受信パーティがメッセージを受信するときにエラーが発生したことを示します。</span><span class="sxs-lookup"><span data-stu-id="ec38a-137">A mismatch between the MIC in the MDN and the MIC in the data store indicates that there was an error during transmission or receipt of the message by the receiving party.</span></span> <span data-ttu-id="ec38a-138">このようなエラーの場合、次の値が報告されます。</span><span class="sxs-lookup"><span data-stu-id="ec38a-138">The values reported in such a failure are the following:</span></span>  
  
-   <span data-ttu-id="ec38a-139">AS2DispositionType: 失敗</span><span class="sxs-lookup"><span data-stu-id="ec38a-139">AS2DispositionType: Failed</span></span>  
  
-   <span data-ttu-id="ec38a-140">AS2DispositionModifierExtensionType: エラー</span><span class="sxs-lookup"><span data-stu-id="ec38a-140">AS2DispositionModifierExtensionType: Error</span></span>  
  
-   <span data-ttu-id="ec38a-141">AS2DispositionModifierExtensionDescription: 整合性チェックに失敗しました</span><span class="sxs-lookup"><span data-stu-id="ec38a-141">AS2DispositionModifierExtensionDescription: Integrity Check Failed</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec38a-142">参照</span><span class="sxs-lookup"><span data-stu-id="ec38a-142">See Also</span></span>  
 <span data-ttu-id="ec38a-143">[BizTalk Server が AS2 メッセージを受信する方法](../core/how-biztalk-server-receives-as2-messages.md) </span><span class="sxs-lookup"><span data-stu-id="ec38a-143">[How BizTalk Server Receives AS2 Messages](../core/how-biztalk-server-receives-as2-messages.md) </span></span>  
 [<span data-ttu-id="ec38a-144">MDN メッセージ</span><span class="sxs-lookup"><span data-stu-id="ec38a-144">MDN Messages</span></span>](../core/mdn-messages.md)