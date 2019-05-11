---
title: 受信 MDN の処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fd78e84c-4989-47e4-b95b-80582084ddec
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63d575f78d41fdf4cb6e3902354bf218579faad7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65299878"
---
# <a name="processing-an-incoming-mdn"></a><span data-ttu-id="44661-102">受信 MDN の処理</span><span class="sxs-lookup"><span data-stu-id="44661-102">Processing an Incoming MDN</span></span>
<span data-ttu-id="44661-103">AS2 は、アグリーメントのプロパティとして、AS2 メッセージ受信者のパーティのに基づいて受信 MDN をパイプライン (AS2EDIReceive と AS2Receive) プロセスを受信します。</span><span class="sxs-lookup"><span data-stu-id="44661-103">The AS2 receive pipelines (AS2EDIReceive and AS2Receive) process an incoming MDN based upon the agreement properties for the party as an AS2 message receiver.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="44661-104">送信 AS2 メッセージに対して MDN が自動的に関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="44661-104">automatically correlates the MDN to the outgoing AS2 message.</span></span>  
  
 <span data-ttu-id="44661-105">各パイプラインの実行手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="44661-105">The steps each pipeline performs are as follows:</span></span>  
  
-   <span data-ttu-id="44661-106">AS2 を照合することによって、送信元パーティを決定します-メッセージの AS2 ヘッダーの値が AS2 の値からのリストから、**識別子**の一方向の AS2 アグリーメント タブのページ、 **アグリーメントのプロパティ**  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="44661-106">Determines the sending party by matching the AS2-From value in the AS2 header of the message with the value for AS2-From list in the **Identifiers** page of the one-way AS2 agreement tab of the **Agreement Properties** dialog box.</span></span> <span data-ttu-id="44661-107">一致が見つからない場合、パイプラインは処理を中止し、例外を発生させます。</span><span class="sxs-lookup"><span data-stu-id="44661-107">If a match is not found, the pipeline aborts processing and raises an exception.</span></span>  
  
-   <span data-ttu-id="44661-108">コンテキストには、次の AS2 プロパティを昇格するには。</span><span class="sxs-lookup"><span data-stu-id="44661-108">Promotes the following AS2 properties to the context:</span></span>  
  
    -   <span data-ttu-id="44661-109">IsAS2FailedMessage</span><span class="sxs-lookup"><span data-stu-id="44661-109">IsAS2FailedMessage</span></span>  
  
    -   <span data-ttu-id="44661-110">DispositionType</span><span class="sxs-lookup"><span data-stu-id="44661-110">DispositionType</span></span>  
  
    -   <span data-ttu-id="44661-111">GenerateAsynchronous200OKOnly</span><span class="sxs-lookup"><span data-stu-id="44661-111">GenerateAsynchronous200OKOnly</span></span>  
  
    -   <span data-ttu-id="44661-112">IsAS2MdnResponseMessage</span><span class="sxs-lookup"><span data-stu-id="44661-112">IsAS2MdnResponseMessage</span></span>  
  
    -   <span data-ttu-id="44661-113">IsAS2MessageSigned</span><span class="sxs-lookup"><span data-stu-id="44661-113">IsAS2MessageSigned</span></span>  
  
    -   <span data-ttu-id="44661-114">OriginalMessageId</span><span class="sxs-lookup"><span data-stu-id="44661-114">OriginalMessageId</span></span>  
  
    -   <span data-ttu-id="44661-115">ReceivedContentMic</span><span class="sxs-lookup"><span data-stu-id="44661-115">ReceivedContentMic</span></span>  
  
    -   <span data-ttu-id="44661-116">DispositionMode</span><span class="sxs-lookup"><span data-stu-id="44661-116">DispositionMode</span></span>  
  
    -   <span data-ttu-id="44661-117">メッセージ Id</span><span class="sxs-lookup"><span data-stu-id="44661-117">MessageId</span></span>  
  
-   <span data-ttu-id="44661-118">メッセージのすべての HTTP ヘッダーに InboundHttpHeaders プロパティを設定して、メッセージのコンテキストに昇格させます。</span><span class="sxs-lookup"><span data-stu-id="44661-118">Sets the InboundHttpHeaders property to all the HTTP headers of the message, and promotes it to the context of the message.</span></span>  
  
-   <span data-ttu-id="44661-119">MDN のコピー (ワイヤ形式) を作成し、一方向の AS2 アグリーメント プロパティで有効になっている場合は、否認不可データベース (BizTalkDTADb データベースの EdiMessageContent テーブル) にコピーを格納します。</span><span class="sxs-lookup"><span data-stu-id="44661-119">Makes a copy of the MDN (in wire format), and stores the copy in the non-repudiation database (the EdiMessageContent table of the BizTalkDTADb database), if enabled in the one-way AS2 agreement properties.</span></span>  
  
-   <span data-ttu-id="44661-120">MDN が署名されている場合、署名の検証を含む MIME 処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="44661-120">Performs MIME processing, including verifying the signature if the MDN was signed.</span></span>  
  
-   <span data-ttu-id="44661-121">(該当する) 場合、元のメッセージを送信された場合、AS2Send パイプラインによって計算されたデータ ストア内の MIC MDN の MIC (メッセージ整合性チェック) を比較します。</span><span class="sxs-lookup"><span data-stu-id="44661-121">Compares the MIC (Message Integrity Check) in the MDN with the MIC in the data store that was computed by the AS2Send pipeline when it sent out the original message (if applicable).</span></span> <span data-ttu-id="44661-122">詳細については、次を参照してください。 [MDN メッセージ](../core/mdn-messages.md)します。</span><span class="sxs-lookup"><span data-stu-id="44661-122">For more information, see [MDN Messages](../core/mdn-messages.md).</span></span>  
  
-   <span data-ttu-id="44661-123">否認不可データベースに関連付けのエントリを作成します。</span><span class="sxs-lookup"><span data-stu-id="44661-123">Makes correlation entries in the non-repudiation database.</span></span>  
  
-   <span data-ttu-id="44661-124">場合を除き、MDN を削除、 **MessageBox にルーティング/配信の受信 MDN を処理する**プロパティで設定されて、**送信者の MDN 設定**の一方向の AS2 アグリーメント タブのページ、 **アグリーメントのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="44661-124">Deletes the MDN, unless the **Process inbound MDN into MessageBox for routing/delivery options** property is set in the **Sender MDN Settings** page of the one-way AS2 agreement tab of the **Agreement Properties** dialog box.</span></span>  
  
-   <span data-ttu-id="44661-125">場合、 **MessageBox にルーティング/配信の受信 MDN を処理する**プロパティで設定されて、**送信者の MDN 設定**の一方向の AS2 アグリーメント タブのページ、**アグリーメントのプロパティ**  ダイアログ ボックスで、受信パイプラインが MDN をパススルー メッセージとして AS2 デコーダを経由してワイヤ形式でルーティングし、を MessageBox にドロップします。</span><span class="sxs-lookup"><span data-stu-id="44661-125">If the **Process inbound MDN into MessageBox for routing/delivery options** property is set in the **Sender MDN Settings** page of the one-way AS2 agreement tab of the **Agreement Properties** dialog box, the receive pipeline routes the MDN in wire format through the AS2 Decoder as a passthrough message and drops it into the MessageBox.</span></span> <span data-ttu-id="44661-126">MDN ワイヤ形式にはには、すべての HTTP ヘッダーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="44661-126">The MDN in wire format contains all HTTP headers.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="44661-127">MessageBox にドロップされた受信 MDN をサブスクライブする送信ポートを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="44661-127">You can set up a send port to subscribe to a received MDN that has been dropped into the MessageBox.</span></span> <span data-ttu-id="44661-128">受信 MDN をサブスクライブ送信ポート フィルターを設定します。`IsAS2MdnResponseMessage==True`します。</span><span class="sxs-lookup"><span data-stu-id="44661-128">To subscribe to the received MDN, set the send port filter to `IsAS2MdnResponseMessage==True`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="44661-129">場合は、AS2EdiReceive パイプラインを使用して受信 MDN を処理することはできません MDN をルーティングするメッセージ ボックスに設定して、 **MessageBox にルーティング/配信の受信 MDN を処理する**プロパティ、**送信者の MDN設定**の一方向の AS2 アグリーメント タブのページ、**アグリーメントのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="44661-129">If you use the AS2EdiReceive pipeline to process a received MDN, you cannot route the MDN into the MessageBox by setting the **Process inbound MDN into MessageBox for routing/delivery options** property in the **Sender MDN Settings** page of the one-way AS2 agreement tab of the **Agreement Properties** dialog box.</span></span> <span data-ttu-id="44661-130">操作を実行しようと、MDN は、MDN を処理できない EDI デコーダーに渡されるために、EDI エラーが発生するがします。</span><span class="sxs-lookup"><span data-stu-id="44661-130">Trying to do so will result in an EDI error because the MDN will be passed to the EDI Decoder, which cannot process an MDN.</span></span> <span data-ttu-id="44661-131">メッセージ ボックスに MDN が送信されない場合、AS2Decoder は EDI デコーダーに渡されませんので、MDN を消費します。</span><span class="sxs-lookup"><span data-stu-id="44661-131">If the MDN is not sent to the MessageBox, the AS2Decoder will consume the MDN, so it will not be passed to the EDI Decoder.</span></span>  
  
## <a name="message-integrity-check"></a><span data-ttu-id="44661-132">メッセージの整合性チェック</span><span class="sxs-lookup"><span data-stu-id="44661-132">Message Integrity Check</span></span>  
 <span data-ttu-id="44661-133">メッセージ整合性チェック (MIC) は、MDN が元の送信メッセージに関連付けられている検証に使用されます。</span><span class="sxs-lookup"><span data-stu-id="44661-133">The Message Integrity Check (MIC) is used to verify that an MDN correlates to the original sent message.</span></span> <span data-ttu-id="44661-134">AS2Send 送信パイプラインは、元の AS2 メッセージを生成し、MIC をデータ ストアに格納する場合にメッセージ ペイロードから MIC を計算します。</span><span class="sxs-lookup"><span data-stu-id="44661-134">The AS2Send send pipeline calculates the MIC from the message payload when it generates the original AS2 message, and stores the MIC in the data store.</span></span> <span data-ttu-id="44661-135">MDN が必要な場合は、元のメッセージの受信者は MIC を生成し、MDN に追加します。</span><span class="sxs-lookup"><span data-stu-id="44661-135">When an MDN is required, the recipient of the original message generates an MIC and adds it to the MDN.</span></span> <span data-ttu-id="44661-136">AS2MdnReceive 受信と受信パイプラインが MDN を署名付き MDN が要求された場合、データ ストア内の MIC と、MDN 内の MIC と比較します。</span><span class="sxs-lookup"><span data-stu-id="44661-136">When the AS2MdnReceive receive pipeline receives the MDN, if a signed MDN was requested, it compares the MIC in the MDN with the MIC in the data store.</span></span>  
  
 <span data-ttu-id="44661-137">MDN 内の MIC とデータ ストア内の MIC の不一致は、送信または受信側パーティによるメッセージの受信中にエラーがあったことを示します。</span><span class="sxs-lookup"><span data-stu-id="44661-137">A mismatch between the MIC in the MDN and the MIC in the data store indicates that there was an error during transmission or receipt of the message by the receiving party.</span></span> <span data-ttu-id="44661-138">このようなエラーで報告された値以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="44661-138">The values reported in such a failure are the following:</span></span>  
  
-   <span data-ttu-id="44661-139">AS2DispositionType:失敗</span><span class="sxs-lookup"><span data-stu-id="44661-139">AS2DispositionType: Failed</span></span>  
  
-   <span data-ttu-id="44661-140">AS2DispositionModifierExtensionType:[エラー]</span><span class="sxs-lookup"><span data-stu-id="44661-140">AS2DispositionModifierExtensionType: Error</span></span>  
  
-   <span data-ttu-id="44661-141">AS2DispositionModifierExtensionDescription:整合性チェックに失敗しました</span><span class="sxs-lookup"><span data-stu-id="44661-141">AS2DispositionModifierExtensionDescription: Integrity Check Failed</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44661-142">参照</span><span class="sxs-lookup"><span data-stu-id="44661-142">See Also</span></span>  
 <span data-ttu-id="44661-143">[BizTalk Server が AS2 メッセージを受信する方法](../core/how-biztalk-server-receives-as2-messages.md) </span><span class="sxs-lookup"><span data-stu-id="44661-143">[How BizTalk Server Receives AS2 Messages](../core/how-biztalk-server-receives-as2-messages.md) </span></span>  
 [<span data-ttu-id="44661-144">MDN メッセージ</span><span class="sxs-lookup"><span data-stu-id="44661-144">MDN Messages</span></span>](../core/mdn-messages.md)