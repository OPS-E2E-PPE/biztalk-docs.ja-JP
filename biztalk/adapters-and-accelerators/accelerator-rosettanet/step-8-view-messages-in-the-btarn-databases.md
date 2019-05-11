---
title: 手順 8:BTARN データベース内のメッセージの表示 |Microsoft Docs
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
ms.openlocfilehash: 94f9b676c2f8ea8c212a4ded6f50ee9037cad6ea
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280546"
---
# <a name="step-8-view-messages-in-the-btarn-databases"></a><span data-ttu-id="318e9-102">手順 8:BTARN データベース内のメッセージの表示</span><span class="sxs-lookup"><span data-stu-id="318e9-102">Step 8: View Messages in the BTARN Databases</span></span>
<span data-ttu-id="318e9-103">この手順で、Microsoft® に格納されている基幹業務 (LOB) メッセージを表示する SQL クエリ アナライザーを使用する[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]ループバック シナリオが正しく動作していることを確認するデータベース。</span><span class="sxs-lookup"><span data-stu-id="318e9-103">In this step, you use SQL Query Analyzer to view line-of-business (LOB) messages stored in the Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] database to verify that your loop-back scenario is working correctly.</span></span>  
  
 <span data-ttu-id="318e9-104">LOB アプリケーション後ユーティリティが LOB メッセージを生成しに送信[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]、(ホーム) のイニシエーターおよびレスポンダー (パートナー) に対して次のイベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="318e9-104">After the LOB Application utility generates an LOB message and submits it to [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)], the following events occur for the initiator (home) and the responder (partner):</span></span>  
  
 <span data-ttu-id="318e9-105">開始側ワークフロー</span><span class="sxs-lookup"><span data-stu-id="318e9-105">Initiator Workflow</span></span>  
  
- <span data-ttu-id="318e9-106">SubmitRNIF の MessagesFromLOB テーブルに LOB メッセージの送信、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]データ データベース。</span><span class="sxs-lookup"><span data-stu-id="318e9-106">SubmitRNIF submits the LOB message to the MessagesFromLOB table of the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] DATA database.</span></span>  
  
- <span data-ttu-id="318e9-107">SQL アダプターでは、受信場所がメッセージを取得し、メッセージ ボックス データベースに配信します。</span><span class="sxs-lookup"><span data-stu-id="318e9-107">The SQL adapter receive location picks up the message and delivers it to the MessageBox database.</span></span> <span data-ttu-id="318e9-108">SQL アダプターは、時間の実行中に 1 つのメッセージを取得、`GetMessagesFromLOB`ストアド プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="318e9-108">The SQL adapter picks up one message at a time running the `GetMessagesFromLOB` stored procedure.</span></span>  
  
- <span data-ttu-id="318e9-109">プライベート開始側はメッセージ ボックス データベースからメッセージを取得し、昇格させた追加のコンテキスト プロパティをメッセージ ボックス データベースにもう一度削除します。</span><span class="sxs-lookup"><span data-stu-id="318e9-109">The private initiator picks the message from the MessageBox database and then drops it again to the MessageBox database with additional promoted context properties.</span></span>  
  
- <span data-ttu-id="318e9-110">パブリック開始側は、サブスクリプション フィルターに基づいて、メッセージ ボックス データベースからメッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="318e9-110">The public initiator picks the message from the MessageBox database based on the subscription filter.</span></span>  
  
- <span data-ttu-id="318e9-111">HTTP では、サブスクリプションに基づいて、RNIFSend パイプラインでポートによって取得、メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="318e9-111">The HTTP send port picks the message with the RNIFSend pipeline based on the subscriptions.</span></span> <span data-ttu-id="318e9-112">MessageStorageOut テーブルにメッセージを保存、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]非否認のアーカイブ データベースを RNIFSend.aspx ページにメッセージを送信するとします。</span><span class="sxs-lookup"><span data-stu-id="318e9-112">It saves the message in the MessageStorageOut table of the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Archive database for non-repudiation, and then sends the message over to the RNIFSend.aspx page.</span></span>  
  
- <span data-ttu-id="318e9-113">RNIFSend.aspx ページは、メッセージ (パートナー組織の URL) の最終的な送信先を含むクエリ文字列変数で MIME でエンコードされたメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="318e9-113">The RNIFSend.aspx page receives the MIME-encoded message with query string variables that include the final destination of the message (partner organization URL).</span></span>  
  
  <span data-ttu-id="318e9-114">応答側ワークフロー</span><span class="sxs-lookup"><span data-stu-id="318e9-114">Responder Workflow</span></span>  
  
- [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] <span data-ttu-id="318e9-115">MIME でデコードされたラッパーを除去する RNIFReceive.aspx ページに RNIF メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="318e9-115">sends the RNIF message to the RNIFReceive.aspx page where the MIME-decoded wrapper is removed.</span></span> <span data-ttu-id="318e9-116">同期または非同期のどちらかとして識別されるメッセージを転送し、同期または非同期のいずれかの受信場所 (RNIF_Sync_Receive または RNIF_Async_Receive)。</span><span class="sxs-lookup"><span data-stu-id="318e9-116">The message is identified as either synchronous or asynchronous, and then forwarded to either the synchronous or asynchronous receive location (RNIF_Sync_Receive or RNIF_Async_Receive).</span></span>  
  
- <span data-ttu-id="318e9-117">HTTP の否認不可用 MessageStorageIn テーブル内の場所の最初の保存、メッセージのワイヤ形式を受信、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]アーカイブ データベース。</span><span class="sxs-lookup"><span data-stu-id="318e9-117">The HTTP receive location first saves the wire format of the message in the MessageStorageIn table for non-repudiation of the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Archive database.</span></span> <span data-ttu-id="318e9-118">HTTP 受信場所をデコードし、(RNIF 2.0) の復号化、その署名を検証、XML メッセージの部分を逆アセンブル、承認、シグネチャに基づいており、昇格された正しいプロパティを付けて MessageBox データベースにドロップします</span><span class="sxs-lookup"><span data-stu-id="318e9-118">The HTTP receive location then decodes, decrypts (for RNIF 2.0), validates on its signature, disassembles the XML message parts, authorizes based on the signature, and then drops it in the MessageBox database with the correct promoted properties</span></span>  
  
- <span data-ttu-id="318e9-119">パブリック応答側は、ベースのサブスクリプションでは、メッセージ部分を取得、それを検証してから、正しい RNIF 規格に基づいてメッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="318e9-119">The public responder picks the message parts based on subscription, and then validates and processes the message based on the correct RNIF standard.</span></span> <span data-ttu-id="318e9-120">Service content 部では、正しいコンテキスト プロパティをメッセージ ボックス データベースにメッセージを削除します。</span><span class="sxs-lookup"><span data-stu-id="318e9-120">The service content part drops the message into the MessageBox database with the correct context properties.</span></span>  
  
- <span data-ttu-id="318e9-121">SQL 送信ポートは、サブスクリプション フィルターに基づいてメッセージ。</span><span class="sxs-lookup"><span data-stu-id="318e9-121">The SQL send port picks the message based on the subscription filter.</span></span> <span data-ttu-id="318e9-122">MessagesToLOB テーブルにメッセージを保存し、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]データ データベース。</span><span class="sxs-lookup"><span data-stu-id="318e9-122">It then saves the message in the MessagesToLOB table of the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] DATA database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="318e9-123">応答側では、パブリック応答側は受信確認または例外シグナルを発信側に生成する責任を負います。</span><span class="sxs-lookup"><span data-stu-id="318e9-123">On the responder side, the Public Responder is responsible for generating the acknowledgement receipt or the exception signal back to the initiator.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] <span data-ttu-id="318e9-124">MessagesFromLOB テーブルには、シグナル メッセージは保存されません。</span><span class="sxs-lookup"><span data-stu-id="318e9-124">does not save the signal message in the MessagesFromLOB table.</span></span> <span data-ttu-id="318e9-125">これは、LOB アプリケーションがシグナル メッセージを生成しないためです。</span><span class="sxs-lookup"><span data-stu-id="318e9-125">This is because the LOB application does not generate the signal message.</span></span> <span data-ttu-id="318e9-126">プライベート応答側アクションのメッセージが今後と[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]MessagesToLOB テーブルに保存します。</span><span class="sxs-lookup"><span data-stu-id="318e9-126">The Action message will continue through the Private Responder, and [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] saves it to the MessagesToLOB table.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="318e9-127">ダブル アクション Pip の応答側に LOB が応答メッセージを生成する責任を負います。</span><span class="sxs-lookup"><span data-stu-id="318e9-127">For double-action PIPs, the LOB on the responder side is responsible for generating a response message.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] <span data-ttu-id="318e9-128">開始側プロセスと同じプロセスを経由する MessagesFromLOB テーブルにドロップします。</span><span class="sxs-lookup"><span data-stu-id="318e9-128">drops it to the MessagesFromLOB table to go through the same process as the initiator-side process.</span></span> <span data-ttu-id="318e9-129">ここで、開始側パブリック開始側プロセスでは、戻る応答メッセージの受信確認または例外シグナルのために送信します。</span><span class="sxs-lookup"><span data-stu-id="318e9-129">In this case, the Public Initiator Process on the initiator side sends back an acknowledgement receipt or exception signal for the response message.</span></span>  
  
### <a name="to-view-messages-in-the-btarn-databases"></a><span data-ttu-id="318e9-130">BTARN データベース内のメッセージを表示するには</span><span class="sxs-lookup"><span data-stu-id="318e9-130">To view messages in the BTARN databases</span></span>  
  
1. <span data-ttu-id="318e9-131">クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft SQL Server\<バージョン\>**、順にクリックします**SQL ServerManagement Studio**します。</span><span class="sxs-lookup"><span data-stu-id="318e9-131">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server \<version\>**, and then click **SQL Server Management Studio**.</span></span>  
  
2. <span data-ttu-id="318e9-132">[サーバー] ダイアログ ボックスへの接続、クリックして**Connect**します。</span><span class="sxs-lookup"><span data-stu-id="318e9-132">In the Connect to Server dialog box, click **Connect**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="318e9-133">オブジェクト エクスプ ローラー ウィンドウで、SQL Server エージェントが開始されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="318e9-133">In the Object Explorer pane, verify that the SQL Server Agent is started.</span></span> <span data-ttu-id="318e9-134">ない場合を右クリックして**SQL Server エージェント**、 をクリック**開始**します。</span><span class="sxs-lookup"><span data-stu-id="318e9-134">If not, right-click **SQL Server Agent**, and click **Start**.</span></span>  
  
3. <span data-ttu-id="318e9-135">Microsoft SQL Server Management Studio で次のようにクリックします。**新しいクエリ**します。</span><span class="sxs-lookup"><span data-stu-id="318e9-135">In the Microsoft SQL Server Management Studio, click **New Query**.</span></span>  
  
4. <span data-ttu-id="318e9-136">空のクエリ ウィンドウで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="318e9-136">In the Blank Query window, type the following:</span></span>  
  
   ```  
   use BTARNArchive  
   SELECT * FROM         MessageStorageIn ORDER BY TIMECREATED ASC  
   SELECT * FROM         MessageStorageOut ORDER BY TIMECREATED ASC  
  
   use BTARNData  
   SELECT     * FROM         MessagesFromLOB ORDER BY TIMECREATED ASC  
   SELECT     * FROM         MessagesToLOB ORDER BY TIMECREATED ASC  
   SELECT     * FROM         Attachments ORDER BY TIMECREATED ASC  
   ```  
  
5. <span data-ttu-id="318e9-137">Microsoft SQL Server Management Studio で次のようにクリックします。 **Execute**します。</span><span class="sxs-lookup"><span data-stu-id="318e9-137">In the Microsoft SQL Server Management Studio, click **Execute**.</span></span>  
  
   <span data-ttu-id="318e9-138">MessagesFromLOB テーブル内のアクション メッセージは表示され (時刻は、システム構成によって異なる場合があります)、数分後にもう一度クエリを実行する場合は、MessageCategory 値を持つ MessagesToLOB テーブルで生成された 2 つのメッセージが表示されます。AsyncAckSignal (25) および AsyncAction (10)。</span><span class="sxs-lookup"><span data-stu-id="318e9-138">You will see an action message in the MessagesFromLOB table, and if you run the query again in several minutes (time may vary depending on your system configuration), you will see two messages generated in the MessagesToLOB table with MessageCategory values of AsyncAckSignal (25) and AsyncAction (10).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="318e9-139">参照</span><span class="sxs-lookup"><span data-stu-id="318e9-139">See Also</span></span>  
 <span data-ttu-id="318e9-140">[Loopback](../../adapters-and-accelerators/accelerator-rosettanet/loopback.md) </span><span class="sxs-lookup"><span data-stu-id="318e9-140">[Loopback](../../adapters-and-accelerators/accelerator-rosettanet/loopback.md) </span></span>  
 [<span data-ttu-id="318e9-141">ループバックのチュートリアル</span><span class="sxs-lookup"><span data-stu-id="318e9-141">Loopback Tutorial</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/loopback-tutorial.md)
