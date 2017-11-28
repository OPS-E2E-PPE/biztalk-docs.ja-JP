---
title: "MQSCorrelationSetOrchestrationWithSolicitResponse (BizTalk Server サンプル) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- examples, MQSeries adapters
- orchestrations, examples
- examples, orchestrations
- examples, messages
- messages, examples
- MQSeries adapters, examples
ms.assetid: 5127d743-bb79-4e97-a2f3-446892e1bfa0
caps.latest.revision: "29"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2665967e27cf708fcdbbddf61a7b66c619757223
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="mqscorrelationsetorchestrationwithsolicitresponse-biztalk-server-sample"></a><span data-ttu-id="e0e68-102">MQSCorrelationSetOrchestrationWithSolicitResponse (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="e0e68-102">MQSCorrelationSetOrchestrationWithSolicitResponse (BizTalk Server Sample)</span></span>
<span data-ttu-id="e0e68-103">MQSCorrelationSetOrchestrationWithSolicitResponse サンプルでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ではなく、MQSeries Server によって作成された関連付け識別子を使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e0e68-103">The MQSCorrelationSetOrchestrationWithSolicitResponse sample demonstrates how to use a correlation identifier produced by the MQSeries Server instead of by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="e0e68-104">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="e0e68-104">What This Sample Does</span></span>  
 <span data-ttu-id="e0e68-105">オーケストレーションが送信メッセージに空の値が、 **MQMD_MsgID**メッセージ ヘッダーのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="e0e68-105">The orchestration sends a message with an empty value for the **MQMD_MsgID** property in the message header.</span></span> <span data-ttu-id="e0e68-106">MQSeries MessageID と CorrelationID を生成してメッセージを返すに割り当てられている値を持つ**MQMD_MsgID**と**MQMD_CorrelId**送信請求-応答の応答の一部として送信アダプターのポート.</span><span class="sxs-lookup"><span data-stu-id="e0e68-106">MQSeries generates the MessageID and CorrelationID and returns a message with a value assigned to **MQMD_MsgID** and **MQMD_CorrelId** as part of the response in the solicit-response send port of the adapter.</span></span> <span data-ttu-id="e0e68-107">オーケストレーションは、関連付けセットを初期化するために生成された関連付け識別子を使用しをチェックして受信場所を次のように、その後でその関連付けセット、 **MQMD_CorrelId**メッセージのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="e0e68-107">The orchestration uses the generated correlation identifier to initialize the correlation set and follows the correlation set in a subsequent receive location by checking the **MQMD_CorrelId** property of the message.</span></span> <span data-ttu-id="e0e68-108">アダプターがまた関連付け識別子を割り当てます**BizTalk_CorrelationID**オーケストレーションで使用することもできます。 これです。</span><span class="sxs-lookup"><span data-stu-id="e0e68-108">The adapter also assigns the correlation identifier to **BizTalk_CorrelationID**, which you could also use in an orchestration.</span></span> <span data-ttu-id="e0e68-109">詳細については、アダプターと関連付け識別子を使用して、次を参照してください。[を相互に関連付けるメッセージを使用して要求/応答](../core/correlating-messages-using-request-reply.md)です。</span><span class="sxs-lookup"><span data-stu-id="e0e68-109">For more information about using correlation identifiers with the adapter, see [Correlating Messages Using Request-Reply](../core/correlating-messages-using-request-reply.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e0e68-110">この方法を使用するオーケストレーションでは、MQSeries Server からのメッセージを関連付け識別子より前に受信すると、問題が発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="e0e68-110">Orchestrations using this technique may experience problems if the message from the MQSeries Server arrives before the correlation identifier.</span></span> <span data-ttu-id="e0e68-111">オーケストレーションをデザインするときは、MQSeries Server が関連付け識別子を返すことができるよう、処理時間を十分にとるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="e0e68-111">Make sure that you design your orchestrations to allow enough time for the MQSeries Server to return the correlation identifier.</span></span> <span data-ttu-id="e0e68-112">この例では、このような競合状態が発生する可能性については考慮していません。</span><span class="sxs-lookup"><span data-stu-id="e0e68-112">This example does not consider this possible race condition.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="e0e68-113">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="e0e68-113">Where to Find This Sample</span></span>  
 <span data-ttu-id="e0e68-114">*\<サンプル パス >*\AdaptersUsage\MQSeriesAdapter\MQSCorrelationSetOrchestrationWithSolicitResponse</span><span class="sxs-lookup"><span data-stu-id="e0e68-114">*\<Samples Path>*\AdaptersUsage\MQSeriesAdapter\MQSCorrelationSetOrchestrationWithSolicitResponse</span></span>  
  
 <span data-ttu-id="e0e68-115">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="e0e68-115">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="e0e68-116">**ファイル**</span><span class="sxs-lookup"><span data-stu-id="e0e68-116">**File**</span></span>|<span data-ttu-id="e0e68-117">**Description**</span><span class="sxs-lookup"><span data-stu-id="e0e68-117">**Description**</span></span>|  
|--------------|---------------------|  
|<span data-ttu-id="e0e68-118">**MQSCorrelationSolicitResponse.btproj、**</span><span class="sxs-lookup"><span data-stu-id="e0e68-118">**MQSCorrelationSolicitResponse.btproj,**</span></span><br /><br /> <span data-ttu-id="e0e68-119">**[Mqscorrelationsolicitresponse.sln]**</span><span class="sxs-lookup"><span data-stu-id="e0e68-119">**MQSCorrelationSolicitResponse.sln**</span></span>|<span data-ttu-id="e0e68-120">アプリケーションのプロジェクトおよびソリューション ファイル。</span><span class="sxs-lookup"><span data-stu-id="e0e68-120">Project and solution files for the application.</span></span>|  
|<span data-ttu-id="e0e68-121">**[Mqscorrelationsolicitresponse.odx]**</span><span class="sxs-lookup"><span data-stu-id="e0e68-121">**MQSCorrelationSolicitResponse.odx**</span></span>|<span data-ttu-id="e0e68-122">アプリケーションの BizTalk オーケストレーション ファイル。</span><span class="sxs-lookup"><span data-stu-id="e0e68-122">The BizTalk orchestration file for the application.</span></span>|  
|<span data-ttu-id="e0e68-123">**MQSCorrelationSolicitResponse.snk**</span><span class="sxs-lookup"><span data-stu-id="e0e68-123">**MQSCorrelationSolicitResponse.snk**</span></span>|<span data-ttu-id="e0e68-124">厳密な名前のキー ファイル。</span><span class="sxs-lookup"><span data-stu-id="e0e68-124">The strong naming key file.</span></span>|  
|<span data-ttu-id="e0e68-125">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="e0e68-125">Setup.bat</span></span>|<span data-ttu-id="e0e68-126">このサンプルを作成および初期化します。</span><span class="sxs-lookup"><span data-stu-id="e0e68-126">Builds and initializes this sample.</span></span>|  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="e0e68-127">このサンプルの使用方法</span><span class="sxs-lookup"><span data-stu-id="e0e68-127">How to Use This Sample</span></span>  
 <span data-ttu-id="e0e68-128">アプリケーションを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e0e68-128">To create the application, you must complete the following steps:</span></span>  
  
-   <span data-ttu-id="e0e68-129">MQSeries キューを 2 つ作成します。</span><span class="sxs-lookup"><span data-stu-id="e0e68-129">Create two MQSeries queues.</span></span>  
  
-   <span data-ttu-id="e0e68-130">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 受信場所と送信ポートを設定します。</span><span class="sxs-lookup"><span data-stu-id="e0e68-130">Set up a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive location and send port.</span></span>  
  
-   <span data-ttu-id="e0e68-131">受信場所を有効化します。</span><span class="sxs-lookup"><span data-stu-id="e0e68-131">Enable the receive location.</span></span>  
  
-   <span data-ttu-id="e0e68-132">送信ポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="e0e68-132">Start the send port.</span></span>  
  
-   <span data-ttu-id="e0e68-133">必要なフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="e0e68-133">Create the appropriate folders.</span></span>  
  
-   <span data-ttu-id="e0e68-134">オーケストレーションを変更します。</span><span class="sxs-lookup"><span data-stu-id="e0e68-134">Modify the orchestration.</span></span>  
  
-   <span data-ttu-id="e0e68-135">オーケストレーションを展開してバインドし、開始します。</span><span class="sxs-lookup"><span data-stu-id="e0e68-135">Deploy, bind and start the orchestration.</span></span>  
  
 <span data-ttu-id="e0e68-136">MQSeries Server for Windows のインストールに必要なアクセス許可を持っている場合は、アダプターのダイアログ ボックスを使用して MQSeries キューを作成できるため、次の手順を省略できます。</span><span class="sxs-lookup"><span data-stu-id="e0e68-136">If you have the required permissions to the MQSeries Server for Windows installation, you can create the MQSeries queue through the adapter dialog boxes, and can skip the next procedure.</span></span> <span data-ttu-id="e0e68-137">必要なアクセス許可がない場合は、IBM WebSphere MQ エクスプローラーを使用してキューを作成できます。</span><span class="sxs-lookup"><span data-stu-id="e0e68-137">If you do not have such access, you can create the queue using the IBM WebSphere MQ Explorer.</span></span> <span data-ttu-id="e0e68-138">WebSphere MQ エクスプローラーを使用してキューを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e0e68-138">To create the queues through the WebSphere MQ Explorer, complete the following steps.</span></span>  
  
## <a name="creating-the-mqseries-queues-through-the-websphere-mq-explorer"></a><span data-ttu-id="e0e68-139">WebSphere MQ エクスプローラーを使用した MQSeries キューの作成</span><span class="sxs-lookup"><span data-stu-id="e0e68-139">Creating the MQSeries Queues Through the WebSphere MQ Explorer</span></span>  
  
#### <a name="to-create-the-mqseries-queues-through-the-websphere-mq-explorer"></a><span data-ttu-id="e0e68-140">WebSphere MQ エクスプ ローラーを使用して MQSeries キューを作成するには</span><span class="sxs-lookup"><span data-stu-id="e0e68-140">To create the MQSeries queues through the WebSphere MQ Explorer</span></span>  
  
1.  <span data-ttu-id="e0e68-141">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**IBM WebSphere MQ**、順にクリック**WebSphere MQ エクスプ ローラー**です。</span><span class="sxs-lookup"><span data-stu-id="e0e68-141">Click **Start**, point to **All Programs**, point to **IBM WebSphere MQ**, and then click **WebSphere MQ Explorer**.</span></span>  
  
2.  <span data-ttu-id="e0e68-142">ダブルクリックして**キュー マネージャー**、し、既定のキュー マネージャーをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="e0e68-142">Double-click **Queue Managers**, and then double-click the default queue manager.</span></span> <span data-ttu-id="e0e68-143">既定のキュー マネージャーの名前は通常**qm _***< machine_name >*場所*machine_name*お使いのコンピューターの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="e0e68-143">The default queue manager is typically named **QM_***<machine_name>* where *machine_name* is the name of your computer.</span></span>  
  
3.  <span data-ttu-id="e0e68-144">右クリック**キュー**、 をポイント**新規**、クリックして**ローカル キュー**です。</span><span class="sxs-lookup"><span data-stu-id="e0e68-144">Right-click **Queues**, point to **New**, and then click **Local Queue**.</span></span>  
  
4.  <span data-ttu-id="e0e68-145">**ローカル キューの作成**ダイアログ ボックスで、**キュー名**「replytoq」、および [] をクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="e0e68-145">In **Create Local Queue** dialog box, in **Queue Name**, type "REPLYTOQ", and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="e0e68-146">右クリック**キュー**をクリックして**新規**、順にクリック**ローカル キュー**です。</span><span class="sxs-lookup"><span data-stu-id="e0e68-146">Right-click **Queues**, click **New**, and then click **Local Queue**.</span></span>  
  
6.  <span data-ttu-id="e0e68-147">**ローカル キューの作成**ダイアログ ボックスで、**キュー名**「solicitresponseq」、および [] をクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="e0e68-147">In the **Create Local Queue** dialog box, in **Queue Name**, type "SOLICITRESPONSEQ", and then click **OK**.</span></span>  
  
## <a name="creating-the-receive-location-and-the-mqseries-queue"></a><span data-ttu-id="e0e68-148">受信場所と MQSeries キューの作成</span><span class="sxs-lookup"><span data-stu-id="e0e68-148">Creating the Receive Location and the MQSeries Queue</span></span>  
 <span data-ttu-id="e0e68-149">この手順では、MQSeries へのメッセージ送信および MQSeries からの関連メッセージの受信を行うための送信ポートと受信場所を作成します。</span><span class="sxs-lookup"><span data-stu-id="e0e68-149">This procedure creates the send port and receive location to send the message to and receive the correlation message from MQSeries.</span></span> <span data-ttu-id="e0e68-150">MQSeries キューは、受信場所がまだ作成されていない場合に受信場所を作成したときにも作成されます。</span><span class="sxs-lookup"><span data-stu-id="e0e68-150">The MQSeries queue will also be created when you create the receive location if not already created.</span></span>  
  
#### <a name="to-create-the-receive-location-and-the-mqseries-queue"></a><span data-ttu-id="e0e68-151">受信場所と MQSeries キューを作成するには</span><span class="sxs-lookup"><span data-stu-id="e0e68-151">To create the receive location and the MQSeries queue</span></span>  
  
1.  <span data-ttu-id="e0e68-152">BizTalk Server 管理コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="e0e68-152">Open the BizTalk Server Administration console.</span></span>  
  
2.  <span data-ttu-id="e0e68-153">展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、し、必要なアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="e0e68-153">Expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the required application.</span></span>  
  
3.  <span data-ttu-id="e0e68-154">右クリック**受信ポート**、 をポイント**新規**、クリックして**一方向の受信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="e0e68-154">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
4.  <span data-ttu-id="e0e68-155">**一方向受信ポートのプロパティ** ダイアログ ボックスで、**名前**ボックスに「MQReply」を入力し、 をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="e0e68-155">In the **One-way Receive Port Properties** dialog box, in the **Name** box, type "MQReply", and click **OK**.</span></span>  
  
5.  <span data-ttu-id="e0e68-156">左側のウィンドウでをクリックして**受信場所** タブをクリックして**新規**です。</span><span class="sxs-lookup"><span data-stu-id="e0e68-156">In the left pane, click **Receive Locations** tab, and then click **New**.</span></span>  
  
6.  <span data-ttu-id="e0e68-157">**受信場所のプロパティ** ダイアログ ボックスで、**名前**ボックスに「mqreply」です。</span><span class="sxs-lookup"><span data-stu-id="e0e68-157">In the **Receive Location Properties** dialog box, in the **Name** box, type "MQReply”.</span></span>  
  
7.  <span data-ttu-id="e0e68-158">**トランスポートの種類**ボックスで、 **MQSeries**です。</span><span class="sxs-lookup"><span data-stu-id="e0e68-158">In the **Transport Type** box, select **MQSeries**.</span></span>  
  
8.  <span data-ttu-id="e0e68-159">**受信ハンドラー**ボックスで、 **BizTalkServerApplication**です。</span><span class="sxs-lookup"><span data-stu-id="e0e68-159">In the **Receive Handler** box, select **BizTalkServerApplication**.</span></span>  
  
9. <span data-ttu-id="e0e68-160">**受信パイプライン**ボックスで、 **Microsoft.BizTalk.DefaultPipelines.PassThruReceive**です。</span><span class="sxs-lookup"><span data-stu-id="e0e68-160">In the **Receive pipeline** box, select **Microsoft.BizTalk.DefaultPipelines.PassThruReceive**.</span></span>  
  
10. <span data-ttu-id="e0e68-161">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="e0e68-161">Click **Configure**.</span></span>  
  
11. <span data-ttu-id="e0e68-162">**MQSeries トランスポートのプロパティ** ダイアログ ボックスで、**のポーリング間隔**ボックスに、「10」を入力します。</span><span class="sxs-lookup"><span data-stu-id="e0e68-162">In the **MQSeries Transport Properties** dialog box, in the **Polling Interval** box, type "10".</span></span>  
  
12. <span data-ttu-id="e0e68-163">**キュー定義**ボックスで、省略記号 (...) ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e0e68-163">In the **Queue Definition** box, click the ellipsis (…) button.</span></span>  
  
13. <span data-ttu-id="e0e68-164">**キュー定義** ダイアログ ボックスで、**サーバー名**ボックスに、コンピューター名を入力します。</span><span class="sxs-lookup"><span data-stu-id="e0e68-164">In the **Queue Definition** dialog box, in the **Server Name** box, type your computer name.</span></span>  
  
14. <span data-ttu-id="e0e68-165">**キュー マネージャー**ボックスで、既定のキュー マネージャーを選択します。</span><span class="sxs-lookup"><span data-stu-id="e0e68-165">In the **Queue Manager** box, select the default queue manager.</span></span>  
  
15. <span data-ttu-id="e0e68-166">**キュー**ボックスで「replytoq」をクリック**エクスポート**です。</span><span class="sxs-lookup"><span data-stu-id="e0e68-166">In the **Queue** box, type " REPLYTOQ", and then click **Export**.</span></span>  
  
16. <span data-ttu-id="e0e68-167">**エクスポート**ダイアログ ボックスで、をクリックして**キューの作成**、順にクリック**[ok]**または**完了**すべてのダイアログ ボックスを終了します。</span><span class="sxs-lookup"><span data-stu-id="e0e68-167">In the **Export** dialog box, click **Create Queue**, and then click**OK**or **Done** until you have exited all dialog boxes.</span></span>  
  
## <a name="creating-the-send-port-and-mqseries-queue"></a><span data-ttu-id="e0e68-168">送信ポートと MQSeries キューの作成</span><span class="sxs-lookup"><span data-stu-id="e0e68-168">Creating the Send Port and MQSeries Queue</span></span>  
  
#### <a name="to-create-the-send-port-and-mqseries-queue"></a><span data-ttu-id="e0e68-169">送信ポートと MQSeries キューを作成するには</span><span class="sxs-lookup"><span data-stu-id="e0e68-169">To create the send port and MQSeries queue</span></span>  
  
1.  <span data-ttu-id="e0e68-170">右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な一方向送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="e0e68-170">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="e0e68-171">**送信ポートのプロパティ** ダイアログ ボックスで、**名前**ボックスに「mqsolicitresponse"です。</span><span class="sxs-lookup"><span data-stu-id="e0e68-171">In the **Send Port Properties** dialog box, in the **Name** box, type "MQSolicitResponse".</span></span>  
  
3.  <span data-ttu-id="e0e68-172">**トランスポートの種類**ボックスで、 **MQSeries**です。</span><span class="sxs-lookup"><span data-stu-id="e0e68-172">In the **Transport Type** box, select **MQSeries**.</span></span>  
  
4.  <span data-ttu-id="e0e68-173">**送信パイプライン**ボックスで、 **Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**です。</span><span class="sxs-lookup"><span data-stu-id="e0e68-173">In the **Send pipeline** box, select **Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**.</span></span>  
  
5.  <span data-ttu-id="e0e68-174">**受信パイプライン**ボックスで、 **Microsoft.BizTalk.DefaultPipelines.PassThruReceive**です。</span><span class="sxs-lookup"><span data-stu-id="e0e68-174">In the **Receive pipeline** box, select **Microsoft.BizTalk.DefaultPipelines.PassThruReceive**.</span></span>  
  
6.  <span data-ttu-id="e0e68-175">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="e0e68-175">Click **Configure**.</span></span>  
  
7.  <span data-ttu-id="e0e68-176">**MQSeries トランスポートのプロパティ** ダイアログ ボックスで、**キュー定義**ボックスで、省略記号 (...) ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e0e68-176">In the **MQSeries Transport Properties** dialog box, in the **Queue Definition** box, click the ellipsis (…) button.</span></span>  
  
8.  <span data-ttu-id="e0e68-177">**キュー定義** ダイアログ ボックスで、**サーバー名**ボックスに、コンピューター名を入力します。</span><span class="sxs-lookup"><span data-stu-id="e0e68-177">In the **Queue Definition** dialog box, in the **Server Name** box, type your computer name.</span></span>  
  
9. <span data-ttu-id="e0e68-178">**キュー マネージャー**ボックスで、既定のキュー マネージャーを選択します。</span><span class="sxs-lookup"><span data-stu-id="e0e68-178">In the **Queue Manager** box, select the default queue manager.</span></span>  
  
10. <span data-ttu-id="e0e68-179">**キュー**ボックスで「solicitresponseq」をクリック**エクスポート**です。</span><span class="sxs-lookup"><span data-stu-id="e0e68-179">In the **Queue** box, type " SOLICITRESPONSEQ", and then click **Export**.</span></span>  
  
11. <span data-ttu-id="e0e68-180">[エクスポート] ダイアログ ボックスで、**キューの作成**をクリックし、 **[ok]**または**実行**すべてのダイアログ ボックスを終了します。</span><span class="sxs-lookup"><span data-stu-id="e0e68-180">In the Export dialog box, click **Create Queue**, and then click **OK** or **Done** until you have exited all dialog boxes.</span></span>  
  
## <a name="enabling-the-receive-location-and-starting-the-send-port"></a><span data-ttu-id="e0e68-181">受信場所の有効化と送信ポートの開始</span><span class="sxs-lookup"><span data-stu-id="e0e68-181">Enabling the Receive Location and Starting the Send Port</span></span>  
 <span data-ttu-id="e0e68-182">この手順では、オーケストレーション内でファイルを受信するために必要なフォルダーを作成し、関連付けられたメッセージと応答メッセージを出力フォルダーに送信します。</span><span class="sxs-lookup"><span data-stu-id="e0e68-182">This procedure creates the folders required to receive the file into the orchestration and sends the correlated message and response message to the output folders.</span></span>  
  
#### <a name="to-enable-the-receive-location-and-start-the-send-port"></a><span data-ttu-id="e0e68-183">受信場所を有効にして送信ポートを開始するには</span><span class="sxs-lookup"><span data-stu-id="e0e68-183">To enable the receive location and start the send port</span></span>  
  
1.  <span data-ttu-id="e0e68-184">BizTalk Server 管理コンソールで **受信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="e0e68-184">In the BizTalk Server Administration console, click **Receive Ports**.</span></span>  
  
2.  <span data-ttu-id="e0e68-185">詳細ウィンドウで右クリックし、 **MQIn**受信場所をクリックして**を有効にする**です。</span><span class="sxs-lookup"><span data-stu-id="e0e68-185">In the details pane, right-click the **MQIn** receive location and click **Enable**.</span></span>  
  
3.  <span data-ttu-id="e0e68-186">詳細ウィンドウで右クリックし、 **MQOut**送信ポートをクリックして**を開始します。**</span><span class="sxs-lookup"><span data-stu-id="e0e68-186">In the details pane, right-click the **MQOut** send port and click **Start.**</span></span>  
  
## <a name="creating-the-folders-used-by-the-application"></a><span data-ttu-id="e0e68-187">アプリケーションが使用するフォルダーの作成</span><span class="sxs-lookup"><span data-stu-id="e0e68-187">Creating the Folders Used by the Application</span></span>  
  
#### <a name="to-create-the-folders-used-by-the-application"></a><span data-ttu-id="e0e68-188">アプリケーションが使用するフォルダーを作成するには</span><span class="sxs-lookup"><span data-stu-id="e0e68-188">To create the folders used by the application</span></span>  
  
1.  <span data-ttu-id="e0e68-189">C:\ ドライブに "temp" という名前のフォルダーが存在しない場合は、これを作成します。</span><span class="sxs-lookup"><span data-stu-id="e0e68-189">If one does not already exist, create a folder named "temp" on your C:\ drive.</span></span>  
  
2.  <span data-ttu-id="e0e68-190">フォルダーを作成、 **C:\temp** "Pickup2"、"Dropit2"、および"MoveIt"という名前のディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="e0e68-190">Create folders under the **C:\temp** directory named "Pickup2", "Dropit2", and "MoveIt".</span></span>  
  
## <a name="modifying-the-orchestration-used-by-the-application"></a><span data-ttu-id="e0e68-191">アプリケーションが使用するオーケストレーションの変更</span><span class="sxs-lookup"><span data-stu-id="e0e68-191">Modifying the Orchestration Used by the Application</span></span>  
 <span data-ttu-id="e0e68-192">この手順では、アプリケーションが使用するオーケストレーションを変更します。</span><span class="sxs-lookup"><span data-stu-id="e0e68-192">This procedure modifies the orchestration used by the application.</span></span>  
  
||  
|-|  
|<span data-ttu-id="e0e68-193">アプリケーションが使用するオーケストレーションを変更するには</span><span class="sxs-lookup"><span data-stu-id="e0e68-193">To modify the Orchestration used by the application</span></span>|  
|<span data-ttu-id="e0e68-194">Microsoft で[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、ソリューション ファイルをダブルクリックして**[mqscorrelationsolicitresponse.sln]**ソリューションを開きます。</span><span class="sxs-lookup"><span data-stu-id="e0e68-194">- In Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], double-click the solution file, **MQSCorrelationSolicitResponse.sln**, to open the solution.</span></span><br /><br /> <span data-ttu-id="e0e68-195">のソリューション エクスプ ローラー ペインで、元オーケストレーションをダブルクリックします**mqscorrelationsolicitresponse.odx**オーケストレーションを表示します。</span><span class="sxs-lookup"><span data-stu-id="e0e68-195">- From the Solution Explorer pane, double-click the orchestration **MQSCorrelationSolicitResponse.odx** to view the orchestration.</span></span><br /><br /> <span data-ttu-id="e0e68-196">-メッセージの割り当て図形をダブルクリックして**MessageAssignment_1** BizTalk 式エディターを起動します。</span><span class="sxs-lookup"><span data-stu-id="e0e68-196">- Double-click the message assignment shape **MessageAssignment_1** to launch the BizTalk Expression Editor.</span></span><br /><br /> <span data-ttu-id="e0e68-197">-次の式の該当する MQSeries キュー マネージャー名を入力してください。</span><span class="sxs-lookup"><span data-stu-id="e0e68-197">- Enter the appropriate MQSeries queue manager name for the following expression:</span></span><br /><br /> `MQSeriesRequestSendMessage(MQSeries.MQMD_ReplyToQMgr) = "QM_<machine_name>";`<br /><br /> <span data-ttu-id="e0e68-198">-最初の 100 バイトだけではなく、元のメッセージの内容全体を格納する BizTalk から送信される応答メッセージの希望する場合は、BizTalk 式エディターで次の行を変更します。</span><span class="sxs-lookup"><span data-stu-id="e0e68-198">- If you would like for the response message sent from BizTalk to contain the entire contents of the original message instead of only the first 100 bytes, modify the following line in the BizTalk Expression Editor.</span></span><br /><br /> <span data-ttu-id="e0e68-199">-元の行。</span><span class="sxs-lookup"><span data-stu-id="e0e68-199">- Original line:</span></span><br /><br /> `MQSeriesRequestSendMessage(MQSeries.MQMD_Report) = 768;`<br /><br /> <span data-ttu-id="e0e68-200">変更後:</span><span class="sxs-lookup"><span data-stu-id="e0e68-200">Change to:</span></span><br /><br /> `MQSeriesRequestSendMessage(MQSeries.MQMD_Report) = 1792;`<br /><br /> <span data-ttu-id="e0e68-201">BizTalk 式エディターには、をクリックして**OK**を変更した式を保存します。</span><span class="sxs-lookup"><span data-stu-id="e0e68-201">- In the BizTalk Expression Editor, click **OK** to save the modified expression.</span></span><br /><br /> <span data-ttu-id="e0e68-202">- [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]**ファイル**、し、**すべて保存**です。</span><span class="sxs-lookup"><span data-stu-id="e0e68-202">- In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], select **File**, and then select **Save All**.</span></span>|  
  
## <a name="building-and-deploying-the-sample"></a><span data-ttu-id="e0e68-203">ビルドと展開のサンプル</span><span class="sxs-lookup"><span data-stu-id="e0e68-203">Building and Deploying the Sample</span></span>  
 <span data-ttu-id="e0e68-204">この手順では、このアプリケーションで使用するオーケストレーションを含むソリューションをビルドして展開します。</span><span class="sxs-lookup"><span data-stu-id="e0e68-204">This procedure builds and deploys the solution that contains the orchestration used in this application.</span></span>  
  
#### <a name="to-build-and-deploy-the-sample"></a><span data-ttu-id="e0e68-205">サンプルをビルドして展開するには</span><span class="sxs-lookup"><span data-stu-id="e0e68-205">To build and deploy the sample</span></span>  
  
1.  <span data-ttu-id="e0e68-206">コマンド ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="e0e68-206">In a command window, navigate to the following folder:</span></span>  
  
     `<Samples Path>\AdaptersUsage\MQSeriesAdapter\MQSCorrelationSetOrchestrationWithSolicitResponse`  
  
2.  <span data-ttu-id="e0e68-207">次の操作を実行する Setup.bat ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="e0e68-207">Run the file Setup.bat, which performs the following actions:</span></span>  
  
    1.  <span data-ttu-id="e0e68-208">プロジェクトの厳密な名前のキー ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="e0e68-208">Creates a strong name key for the project.</span></span>  
  
    2.  <span data-ttu-id="e0e68-209">オーケストレーション プロジェクトをコンパイルして展開します。</span><span class="sxs-lookup"><span data-stu-id="e0e68-209">Compiles and deploys the orchestration project.</span></span>  
  
    3.  <span data-ttu-id="e0e68-210">ファイル アダプター用の送信ポートと受信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="e0e68-210">Creates a send port and a receive port with the File adapter.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e0e68-211">このオーケストレーションでは、ファイル アダプターとのファイルの送受信に使用するバインドが指定されているため、オーケストレーションの展開時には、ファイルをオーケストレーション内で受信し、関連付けメッセージと応答メッセージを出力するために必要な送信ポート、受信ポート、および受信場所が作成されます。</span><span class="sxs-lookup"><span data-stu-id="e0e68-211">Since this orchestration specifies the bindings for sending and receiving files with the file adapter, when you deploy the orchestration the necessary send ports, receive port, and receive location will be created for receiving a file into the orchestration and outputting the correlation message and the response message.</span></span>  
  
## <a name="binding-and-starting-the-orchestration"></a><span data-ttu-id="e0e68-212">バインドとオーケストレーションの開始</span><span class="sxs-lookup"><span data-stu-id="e0e68-212">Binding and Starting the Orchestration</span></span>  
 <span data-ttu-id="e0e68-213">この手順では、ホスト、適切な送信ポート、および受信場所にオーケストレーションをバインドします。</span><span class="sxs-lookup"><span data-stu-id="e0e68-213">This procedure binds the orchestration to the host and appropriate send ports and receive locations.</span></span>  
  
#### <a name="to-bind-and-start-the-orchestration"></a><span data-ttu-id="e0e68-214">バインドし、オーケストレーションの開始</span><span class="sxs-lookup"><span data-stu-id="e0e68-214">To bind and start the orchestration</span></span>  
  
1.  <span data-ttu-id="e0e68-215">BizTalk Server 管理コンソールで、展開、**オーケストレーション**フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="e0e68-215">In the BizTalk Server Administration console, expand the **Orchestrations** folder.</span></span>  
  
2.  <span data-ttu-id="e0e68-216">詳細ウィンドウで右クリックし、 **[mqscorrelationsolicitresponse]**オーケストレーションとクリック**バインド**です。</span><span class="sxs-lookup"><span data-stu-id="e0e68-216">In the details pane, right-click the **MQSCorrelationSolicitResponse** orchestration and click **Bind**.</span></span>  
  
3.  <span data-ttu-id="e0e68-217">オーケストレーション ポートを、以下の送信ポートおよび受信場所にバインドします。</span><span class="sxs-lookup"><span data-stu-id="e0e68-217">Bind the orchestration ports to the following send ports and receive locations:</span></span>  
  
    |<span data-ttu-id="e0e68-218">**オーケストレーション ポート**</span><span class="sxs-lookup"><span data-stu-id="e0e68-218">**Orchestration Port**</span></span>|<span data-ttu-id="e0e68-219">**メッセージ ポート/受信場所**</span><span class="sxs-lookup"><span data-stu-id="e0e68-219">**Messaging Port / Receive Location**</span></span>|  
    |----------------------------|--------------------------------------------|  
    |<span data-ttu-id="e0e68-220">FileReceivePort</span><span class="sxs-lookup"><span data-stu-id="e0e68-220">FileReceivePort</span></span>|<span data-ttu-id="e0e68-221">MQSCorrelationSolicitResponse.Orchestration.FileReceivePort</span><span class="sxs-lookup"><span data-stu-id="e0e68-221">MQSCorrelationSolicitResponse.Orchestration.FileReceivePort</span></span>|  
    |<span data-ttu-id="e0e68-222">MQSeriesResponseReceivePort</span><span class="sxs-lookup"><span data-stu-id="e0e68-222">MQSeriesResponseReceivePort</span></span>|<span data-ttu-id="e0e68-223">MQReply</span><span class="sxs-lookup"><span data-stu-id="e0e68-223">MQReply</span></span>|  
    |<span data-ttu-id="e0e68-224">SolicitResponsePort</span><span class="sxs-lookup"><span data-stu-id="e0e68-224">SolicitResponsePort</span></span>|<span data-ttu-id="e0e68-225">MQSolicitResponse</span><span class="sxs-lookup"><span data-stu-id="e0e68-225">MQSolicitResponse</span></span>|  
    |<span data-ttu-id="e0e68-226">TempPort</span><span class="sxs-lookup"><span data-stu-id="e0e68-226">TempPort</span></span>|<span data-ttu-id="e0e68-227">MQSCorrelationSolicitResponse.Orchestration.TempPort</span><span class="sxs-lookup"><span data-stu-id="e0e68-227">MQSCorrelationSolicitResponse.Orchestration.TempPort</span></span>|  
    |<span data-ttu-id="e0e68-228">FileSendPort</span><span class="sxs-lookup"><span data-stu-id="e0e68-228">FileSendPort</span></span>|<span data-ttu-id="e0e68-229">MQSCorrelationSolicitResponse.Orchestration.FileSendPort</span><span class="sxs-lookup"><span data-stu-id="e0e68-229">MQSCorrelationSolicitResponse.Orchestration.FileSendPort</span></span>|  
  
4.  <span data-ttu-id="e0e68-230">をクリックして**ホスト**です。</span><span class="sxs-lookup"><span data-stu-id="e0e68-230">Click **Host**.</span></span>  
  
5.  <span data-ttu-id="e0e68-231">**ホスト**ボックスで、 **BizTalkServerApplication**  をクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="e0e68-231">In the **Host** box, select **BizTalkServerApplication** and click **OK**.</span></span>  
  
6.  <span data-ttu-id="e0e68-232">**送信ポート**を右クリックして**mqscorrelationsolicitresponse.orchestration.tempport**、し、**開始**です。</span><span class="sxs-lookup"><span data-stu-id="e0e68-232">In **Send Ports**, right-click **MQSCorrelationSolicitResponse.Orchestration.TempPort**, and then select **Start**.</span></span>  
  
7.  <span data-ttu-id="e0e68-233">**送信ポート**を右クリックして**mqscorrelationsolicitresponse.orchestration.filesendport**、し、**開始**です。</span><span class="sxs-lookup"><span data-stu-id="e0e68-233">In **Send Ports**, right-click **MQSCorrelationSolicitResponse.Orchestration.FileSendPort**, and then select **Start**.</span></span>  
  
8.  <span data-ttu-id="e0e68-234">**受信場所**を右クリックして**mqscorrelationsolicitresponse.orchestration.filereceiveport**、し、**を有効にする**です。</span><span class="sxs-lookup"><span data-stu-id="e0e68-234">In **Receive Locations**, right-click **MQSCorrelationSolicitResponse.Orchestration.FileReceivePort**, and then select **Enable**.</span></span>  
  
9. <span data-ttu-id="e0e68-235">オーケストレーションを右クリックし、をクリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="e0e68-235">Right-click the orchestration and click **Start**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e0e68-236">オーケストレーションを開始すると、オーケストレーションの参加も自動的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="e0e68-236">Starting the orchestration also automatically enlists the orchestration.</span></span>  
  
## <a name="testing-the-application"></a><span data-ttu-id="e0e68-237">アプリケーションのテスト</span><span class="sxs-lookup"><span data-stu-id="e0e68-237">Testing the Application</span></span>  
 <span data-ttu-id="e0e68-238">この手順では、アプリケーションをテストします。</span><span class="sxs-lookup"><span data-stu-id="e0e68-238">This procedure tests the application.</span></span>  
  
#### <a name="to-test-the-application"></a><span data-ttu-id="e0e68-239">アプリケーションをテストするには</span><span class="sxs-lookup"><span data-stu-id="e0e68-239">To test the application</span></span>  
  
1.  <span data-ttu-id="e0e68-240">ファイルの put、 **C:\Temp\Pickup2**フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="e0e68-240">Put a file in the **C:\Temp\Pickup2** folder.</span></span>  
  
2.  <span data-ttu-id="e0e68-241">内のファイルを調べて、 **C:\Temp\Dropit2**フォルダーおよび**C:\Temp\Moveit**フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="e0e68-241">Examine the files in the **C:\Temp\Dropit2** folder and the **C:\Temp\Moveit**folder.</span></span>  
  
    -   <span data-ttu-id="e0e68-242">**C:\Temp\Dropit2**フォルダーは、最初の取得されたメッセージのコピーを含める必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="e0e68-242">The **C:\Temp\Dropit2** folder should contain a copy of the message that was originally picked up by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
    -   <span data-ttu-id="e0e68-243">**C:\Temp\Moveit**フォルダーは、メッセージ識別子 (MQMD_MsgId) と関連付け識別子 (MQMD_CorrelId) を含む応答ドキュメントを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0e68-243">The **C:\Temp\Moveit**folder should contain a response document with the message identifier (MQMD_MsgId) and the correlation identifier (MQMD_CorrelId).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e0e68-244">無効にした場合、 **MQReply**受信場所、WebSphere MQ エクスプ ローラーでメッセージを確認し、メッセージ識別子と関連付け識別子が設定されていることができます。</span><span class="sxs-lookup"><span data-stu-id="e0e68-244">If you disable the **MQReply** receive location, you can examine the message in WebSphere MQ Explorer and see that the message and correlation identifiers are set.</span></span> <span data-ttu-id="e0e68-245">これを行うには、起動、 **WebSphere MQ エクスプ ローラー**で配置されているメッセージを確認し、 **REPLYTOQ**キュー。</span><span class="sxs-lookup"><span data-stu-id="e0e68-245">To do this, launch the **WebSphere MQ Explorer** and examine the message placed in the **REPLYTOQ** queue.</span></span> <span data-ttu-id="e0e68-246">メッセージ識別子と関連付け識別子が表示されます、**識別子**のタブ、 **Messageproperties**  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="e0e68-246">The message and correlation identifiers are displayed on the **Identifiers** tab of the **Messageproperties** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0e68-247">参照</span><span class="sxs-lookup"><span data-stu-id="e0e68-247">See Also</span></span>  
 <span data-ttu-id="e0e68-248">[要求/応答を使用してメッセージを相互に関連付ける](../core/correlating-messages-using-request-reply.md) </span><span class="sxs-lookup"><span data-stu-id="e0e68-248">[Correlating Messages Using Request-Reply](../core/correlating-messages-using-request-reply.md) </span></span>  
 [<span data-ttu-id="e0e68-249">MQSeries アダプタ サンプル</span><span class="sxs-lookup"><span data-stu-id="e0e68-249">MQSeries Adapter Samples</span></span>](../core/mqseries-adapter-samples.md)