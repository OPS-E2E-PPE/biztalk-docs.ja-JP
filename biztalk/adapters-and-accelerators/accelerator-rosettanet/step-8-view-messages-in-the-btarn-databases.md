---
title: '手順 8: BTARN データベース内のメッセージの表示 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, viewing
- loopback tutorial, viewing messages
- databases, viewing messages
ms.assetid: c549670c-4428-483c-906c-eff163ddef9a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 018bd2515dc2c363474c8058a861fd763cb73352
ms.sourcegitcommit: 436ebffd959a9c4bdaafd4da9a5843c59a018eb7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2018
ms.locfileid: "34855445"
---
# <a name="step-8-view-messages-in-the-btarn-databases"></a><span data-ttu-id="576b8-102">手順 8: BTARN データベース内のメッセージの表示</span><span class="sxs-lookup"><span data-stu-id="576b8-102">Step 8: View Messages in the BTARN Databases</span></span>
<span data-ttu-id="576b8-103">ここでは、ループバック シナリオが正しく動作していることを確認するために、SQL クエリ アナライザーを使用して、[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] データベースに格納されている基幹業務 (LOB) メッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="576b8-103">In this step, you use SQL Query Analyzer to view line-of-business (LOB) messages stored in the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] database to verify that your loop-back scenario is working correctly.</span></span>  
  
 <span data-ttu-id="576b8-104">LOB アプリケーション ユーティリティが LOB メッセージを生成し、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] に送信した後、開始側 (ホーム) と応答側 (パートナー) で次のイベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="576b8-104">After the LOB Application utility generates an LOB message and submits it to [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)], the following events occur for the initiator (home) and the responder (partner):</span></span>  
  
 <span data-ttu-id="576b8-105">開始側ワークフロー</span><span class="sxs-lookup"><span data-stu-id="576b8-105">Initiator Workflow</span></span>  
  
-   <span data-ttu-id="576b8-106">SubmitRNIF が、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] DATA データベースの MessagesFromLOB テーブルに LOB メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="576b8-106">SubmitRNIF submits the LOB message to the MessagesFromLOB table of the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] DATA database.</span></span>  
  
-   <span data-ttu-id="576b8-107">SQL アダプター受信場所がメッセージを取得し、MessageBox データベースに配信します。</span><span class="sxs-lookup"><span data-stu-id="576b8-107">The SQL adapter receive location picks up the message and delivers it to the MessageBox database.</span></span> <span data-ttu-id="576b8-108">SQL アダプターは `GetMessagesFromLOB` ストアド プロシージャを実行して、一度に 1 つのメッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="576b8-108">The SQL adapter picks up one message at a time running the `GetMessagesFromLOB` stored procedure.</span></span>  
  
-   <span data-ttu-id="576b8-109">プライベート開始側が MessageBox データベースからメッセージを取得し、追加で昇格されたコンテキスト プロパティを付けて MessageBox データベースに再度ドロップします。</span><span class="sxs-lookup"><span data-stu-id="576b8-109">The private initiator picks the message from the MessageBox database and then drops it again to the MessageBox database with additional promoted context properties.</span></span>  
  
-   <span data-ttu-id="576b8-110">パブリック開始側がサブスクリプション フィルターに基づいて、MessageBox データベースからメッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="576b8-110">The public initiator picks the message from the MessageBox database based on the subscription filter.</span></span>  
  
-   <span data-ttu-id="576b8-111">HTTP 送信ポートがサブスクリプションに基づいて、RNIFSend パイプラインでメッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="576b8-111">The HTTP send port picks the message with the RNIFSend pipeline based on the subscriptions.</span></span> <span data-ttu-id="576b8-112">HTTP 送信ポートは、否認不可用の [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Archive データベースの MessageStorageOut テーブルにメッセージを格納した後、メッセージを RNIFSend.aspx ページに送信します。</span><span class="sxs-lookup"><span data-stu-id="576b8-112">It saves the message in the MessageStorageOut table of the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Archive database for non-repudiation, and then sends the message over to the RNIFSend.aspx page.</span></span>  
  
-   <span data-ttu-id="576b8-113">RNIFSend.aspx ページは、メッセージの最終送信先 (取引先組織の URL) を含むクエリ文字列変数付きの MIME でエンコードされたメッセージを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="576b8-113">The RNIFSend.aspx page receives the MIME-encoded message with query string variables that include the final destination of the message (partner organization URL).</span></span>  
  
 <span data-ttu-id="576b8-114">応答側ワークフロー</span><span class="sxs-lookup"><span data-stu-id="576b8-114">Responder Workflow</span></span>  
  
-   [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="576b8-115"> が RNIF メッセージを RNIFReceive.aspx ページに送信します。RNIFReceive.aspx ページでは、MIME でデコードされたラッパーが削除されます。</span><span class="sxs-lookup"><span data-stu-id="576b8-115"> sends the RNIF message to the RNIFReceive.aspx page where the MIME-decoded wrapper is removed.</span></span> <span data-ttu-id="576b8-116">メッセージは、同期メッセージまたは非同期メッセージのいずれかとして識別された後、同期または非同期の受信場所 (RNIF_Sync_Receive または RNIF_Async_Receive) に転送されます。</span><span class="sxs-lookup"><span data-stu-id="576b8-116">The message is identified as either synchronous or asynchronous, and then forwarded to either the synchronous or asynchronous receive location (RNIF_Sync_Receive or RNIF_Async_Receive).</span></span>  
  
-   <span data-ttu-id="576b8-117">まず、HTTP 受信場所が、ワイヤ形式のメッセージを [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Archive データベースの否認不可用 MessageStorageIn テーブルに格納します。</span><span class="sxs-lookup"><span data-stu-id="576b8-117">The HTTP receive location first saves the wire format of the message in the MessageStorageIn table for non-repudiation of the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Archive database.</span></span> <span data-ttu-id="576b8-118">次に HTTP 受信場所は、デコードおよび暗号化の解除を実行して (RNIF 2.0 の場合)、その署名を検証します。次に XML メッセージ部を逆アセンブルし、署名に基づいて承認してから、昇格された正しいプロパティを付けて MessageBox データベースにドロップします。</span><span class="sxs-lookup"><span data-stu-id="576b8-118">The HTTP receive location then decodes, decrypts (for RNIF 2.0), validates on its signature, disassembles the XML message parts, authorizes based on the signature, and then drops it in the MessageBox database with the correct promoted properties</span></span>  
  
-   <span data-ttu-id="576b8-119">パブリック応答側が、サブスクリプションに基づいてメッセージ部を取得し、正しい RNIF 規格に基づいてメッセージを検証および処理します。</span><span class="sxs-lookup"><span data-stu-id="576b8-119">The public responder picks the message parts based on subscription, and then validates and processes the message based on the correct RNIF standard.</span></span> <span data-ttu-id="576b8-120">Service Content 部が、メッセージに正しいコンテキスト プロパティを付けて MessageBox データベースにドロップします。</span><span class="sxs-lookup"><span data-stu-id="576b8-120">The service content part drops the message into the MessageBox database with the correct context properties.</span></span>  
  
-   <span data-ttu-id="576b8-121">SQL 送信ポートがサブスクリプション フィルターに基づいてメッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="576b8-121">The SQL send port picks the message based on the subscription filter.</span></span> <span data-ttu-id="576b8-122">次に、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] DATA データベースの MessagesToLOB テーブルにメッセージを格納します。</span><span class="sxs-lookup"><span data-stu-id="576b8-122">It then saves the message in the MessagesToLOB table of the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] DATA database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="576b8-123">応答側パブリック応答側は受信確認または例外シグナル、発信側に戻れるの生成を担当します。</span><span class="sxs-lookup"><span data-stu-id="576b8-123">On the responder side, the Public Responder is responsible for generating the acknowledgement receipt or the exception signal back to the initiator.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="576b8-124"> MessagesFromLOB テーブルには、シグナル メッセージは保存されません。</span><span class="sxs-lookup"><span data-stu-id="576b8-124"> does not save the signal message in the MessagesFromLOB table.</span></span> <span data-ttu-id="576b8-125">これは、LOB アプリケーションがシグナル メッセージを生成しないためです。</span><span class="sxs-lookup"><span data-stu-id="576b8-125">This is because the LOB application does not generate the signal message.</span></span> <span data-ttu-id="576b8-126">アクション メッセージはプライベート応答側を経由し、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] によって MessagesToLOB テーブルに格納されます。</span><span class="sxs-lookup"><span data-stu-id="576b8-126">The Action message will continue through the Private Responder, and [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] saves it to the MessagesToLOB table.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="576b8-127">ダブル アクション Pip の応答側の LOB は応答メッセージを生成します。</span><span class="sxs-lookup"><span data-stu-id="576b8-127">For double-action PIPs, the LOB on the responder side is responsible for generating a response message.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="576b8-128"> 開始側プロセスと同じプロセスを経由する MessagesFromLOB テーブルにドロップします。</span><span class="sxs-lookup"><span data-stu-id="576b8-128"> drops it to the MessagesFromLOB table to go through the same process as the initiator-side process.</span></span> <span data-ttu-id="576b8-129">この場合、開始側のパブリック開始側プロセスが、応答メッセージの受信確認または例外シグナルを送信します。</span><span class="sxs-lookup"><span data-stu-id="576b8-129">In this case, the Public Initiator Process on the initiator side sends back an acknowledgement receipt or exception signal for the response message.</span></span>  
  
### <a name="to-view-messages-in-the-btarn-databases"></a><span data-ttu-id="576b8-130">BTARN データベース内のメッセージを表示するには</span><span class="sxs-lookup"><span data-stu-id="576b8-130">To view messages in the BTARN databases</span></span>  
  
1.  <span data-ttu-id="576b8-131">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft SQL Server\<バージョン\>**、クリックして**SQL ServerManagement Studio**です。</span><span class="sxs-lookup"><span data-stu-id="576b8-131">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server \<version\>**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="576b8-132">[サーバー] ダイアログ ボックスへの接続でクリックして**接続**です。</span><span class="sxs-lookup"><span data-stu-id="576b8-132">In the Connect to Server dialog box, click **Connect**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="576b8-133">オブジェクト エクスプローラー ペインで、SQL Server エージェントが開始されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="576b8-133">In the Object Explorer pane, verify that the SQL Server Agent is started.</span></span> <span data-ttu-id="576b8-134">いない場合を右クリックし**SQL Server エージェント**、 をクリック**開始**です。</span><span class="sxs-lookup"><span data-stu-id="576b8-134">If not, right-click **SQL Server Agent**, and click **Start**.</span></span>  
  
3.  <span data-ttu-id="576b8-135">Microsoft SQL Server Management Studio でクリックして**新しいクエリ**です。</span><span class="sxs-lookup"><span data-stu-id="576b8-135">In the Microsoft SQL Server Management Studio, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="576b8-136">空のクエリ ウィンドウに以下を入力します。</span><span class="sxs-lookup"><span data-stu-id="576b8-136">In the Blank Query window, type the following:</span></span>  
  
    ```  
    use BTARNArchive  
    SELECT * FROM         MessageStorageIn ORDER BY TIMECREATED ASC  
    SELECT * FROM         MessageStorageOut ORDER BY TIMECREATED ASC  
  
    use BTARNData  
    SELECT     * FROM         MessagesFromLOB ORDER BY TIMECREATED ASC  
    SELECT     * FROM         MessagesToLOB ORDER BY TIMECREATED ASC  
    SELECT     * FROM         Attachments ORDER BY TIMECREATED ASC  
    ```  
  
5.  <span data-ttu-id="576b8-137">Microsoft SQL Server Management Studio でクリックして**Execute**です。</span><span class="sxs-lookup"><span data-stu-id="576b8-137">In the Microsoft SQL Server Management Studio, click **Execute**.</span></span>  
  
 <span data-ttu-id="576b8-138">MessagesFromLOB テーブル内のアクション メッセージが表示されます。数分後 (この時間はシステム構成によって異なります) にクエリを再度実行すると、MessageCategory 値が AsyncAckSignal (25) および AsyncAction (10) である 2 つのメッセージが MessagesToLOB テーブルに生成されて表示されます。</span><span class="sxs-lookup"><span data-stu-id="576b8-138">You will see an action message in the MessagesFromLOB table, and if you run the query again in several minutes (time may vary depending on your system configuration), you will see two messages generated in the MessagesToLOB table with MessageCategory values of AsyncAckSignal (25) and AsyncAction (10).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="576b8-139">参照</span><span class="sxs-lookup"><span data-stu-id="576b8-139">See Also</span></span>  
 <span data-ttu-id="576b8-140">[ループバック](../../adapters-and-accelerators/accelerator-rosettanet/loopback.md) </span><span class="sxs-lookup"><span data-stu-id="576b8-140">[Loopback](../../adapters-and-accelerators/accelerator-rosettanet/loopback.md) </span></span>  
 [<span data-ttu-id="576b8-141">ループバックのチュートリアル</span><span class="sxs-lookup"><span data-stu-id="576b8-141">Loopback Tutorial</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/loopback-tutorial.md)
