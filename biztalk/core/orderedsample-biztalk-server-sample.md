---
title: "OrderedSample (BizTalk Server サンプル) |Microsoft ドキュメント"
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
- MQSeries adapters, examples
ms.assetid: 7e59ff43-d425-40cd-9725-af13084f83d9
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf7b0de69005957a333e0c4f884e748e6ab5bbe9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="orderedsample-biztalk-server-sample"></a><span data-ttu-id="c497b-102">OrderedSample (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="c497b-102">OrderedSample (BizTalk Server Sample)</span></span>
<span data-ttu-id="c497b-103">OrderedSample サンプルは、オーケストレーションを使用して、順序付けられた一連のメッセージをラウンド トリップ方式で送受信する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c497b-103">The OrderedSample sample demonstrates how to use an orchestration to receive and send an ordered series of messages in a round-trip fashion.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="c497b-104">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="c497b-104">What This Sample Does</span></span>  
 <span data-ttu-id="c497b-105">このサンプルでは、サンプルにメッセージを配信する MQSeries キューにメッセージがあることを前提とします。</span><span class="sxs-lookup"><span data-stu-id="c497b-105">The sample assumes there are messages in the MQSeries queue from which it receives messages.</span></span> <span data-ttu-id="c497b-106">MQSeries キューのメッセージは、アダプターによって順番に読み取られて [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に送信されます。</span><span class="sxs-lookup"><span data-stu-id="c497b-106">When the adapter reads the messages from MQSeries queue, it reads them in-order and submits them to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="c497b-107">オーケストレーションで受信ポート**mqreceive**がその**順次配送**プロパティに設定**True**です。</span><span class="sxs-lookup"><span data-stu-id="c497b-107">The receive port in the orchestration, **mqreceive**, has its **Ordered Delivery** property set to **True**.</span></span>  
  
 <span data-ttu-id="c497b-108">送信側では、オーケストレーションによってメッセージが送信され、配信通知の受信後に次のメッセージが送信されます。</span><span class="sxs-lookup"><span data-stu-id="c497b-108">For the send side, the orchestration sends a message and then waits for a delivery notification before sending the next message.</span></span> <span data-ttu-id="c497b-109">送信ポート**mqsend**がその**配信通知**プロパティに設定**送信**です。</span><span class="sxs-lookup"><span data-stu-id="c497b-109">The send port, **mqsend** has its **Delivery Notification** property set to **Transmitted**.</span></span> <span data-ttu-id="c497b-110">サンプルをシンプルにするために、オーケストレーションでは無限ループが使用されています。</span><span class="sxs-lookup"><span data-stu-id="c497b-110">To keep the example simple, the orchestration uses an infinite loop.</span></span>  
  
 <span data-ttu-id="c497b-111">オーケストレーションでは、メッセージのバッチおよび 1 つのメッセージを受信できます。</span><span class="sxs-lookup"><span data-stu-id="c497b-111">The orchestration can receive batches of messages and single messages.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="c497b-112">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="c497b-112">Where to Find This Sample</span></span>  
 <span data-ttu-id="c497b-113">*\<サンプル パス >*\AdaptersUsage\MQSeriesAdapter\OrderedSample</span><span class="sxs-lookup"><span data-stu-id="c497b-113">*\<Samples Path>*\AdaptersUsage\MQSeriesAdapter\OrderedSample</span></span>  
  
 <span data-ttu-id="c497b-114">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="c497b-114">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="c497b-115">ファイル</span><span class="sxs-lookup"><span data-stu-id="c497b-115">File</span></span>|<span data-ttu-id="c497b-116">Description</span><span class="sxs-lookup"><span data-stu-id="c497b-116">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="c497b-117">OrderedReceiveSend.btproj,</span><span class="sxs-lookup"><span data-stu-id="c497b-117">OrderedReceiveSend.btproj,</span></span><br /><br /> <span data-ttu-id="c497b-118">OrderedReceiveSend.sln</span><span class="sxs-lookup"><span data-stu-id="c497b-118">OrderedReceiveSend.sln</span></span>|<span data-ttu-id="c497b-119">アプリケーションのプロジェクトおよびソリューション ファイル。</span><span class="sxs-lookup"><span data-stu-id="c497b-119">Project and solution files for the application.</span></span>|  
|<span data-ttu-id="c497b-120">OrderedReceiveSendOrchestration.odx</span><span class="sxs-lookup"><span data-stu-id="c497b-120">OrderedReceiveSendOrchestration.odx</span></span>|<span data-ttu-id="c497b-121">アプリケーションのオーケストレーション。</span><span class="sxs-lookup"><span data-stu-id="c497b-121">The orchestration of the application.</span></span>|  
|<span data-ttu-id="c497b-122">OrderedSample.snk</span><span class="sxs-lookup"><span data-stu-id="c497b-122">OrderedSample.snk</span></span>|<span data-ttu-id="c497b-123">厳密な名前のキー ファイル。</span><span class="sxs-lookup"><span data-stu-id="c497b-123">The strong naming key file.</span></span>|  
|<span data-ttu-id="c497b-124">**Setup.bat**</span><span class="sxs-lookup"><span data-stu-id="c497b-124">**Setup.bat**</span></span>|<span data-ttu-id="c497b-125">このサンプルを作成および初期化します。</span><span class="sxs-lookup"><span data-stu-id="c497b-125">Builds and initializes this sample.</span></span>|  
  
## <a name="building-and-running-the-sample"></a><span data-ttu-id="c497b-126">サンプルのビルドと実行</span><span class="sxs-lookup"><span data-stu-id="c497b-126">Building and Running the Sample</span></span>  
  
#### <a name="to-build-and-deploy-the-sample"></a><span data-ttu-id="c497b-127">サンプルをビルドして展開するには</span><span class="sxs-lookup"><span data-stu-id="c497b-127">To build and deploy the sample</span></span>  
  
1.  <span data-ttu-id="c497b-128">コマンド ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="c497b-128">In a command window, navigate to the following folder:</span></span>  
  
     `<Samples Path>\AdaptersUsage\MQSeriesAdapter\OrderedSample`  
  
2.  <span data-ttu-id="c497b-129">次の操作を実行する Setup.bat ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="c497b-129">Run the file Setup.bat, which performs the following actions:</span></span>  
  
    1.  <span data-ttu-id="c497b-130">プロジェクトの厳密な名前のキー ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="c497b-130">Creates a strong name key for the project.</span></span>  
  
    2.  <span data-ttu-id="c497b-131">オーケストレーション プロジェクトをコンパイルして展開します。</span><span class="sxs-lookup"><span data-stu-id="c497b-131">Compiles and deploys the orchestration project.</span></span>  
  
 <span data-ttu-id="c497b-132">MQSeries Server for Windows のインストールに必要なアクセス許可を持っている場合は、アダプターのダイアログ ボックスを使用して MQSeries キューを作成できるため、次の手順を省略できます。</span><span class="sxs-lookup"><span data-stu-id="c497b-132">If you have the required permissions to the MQSeries Server for Windows installation, you can create the MQSeries queue through the adapter dialog boxes, and can skip the next procedure.</span></span> <span data-ttu-id="c497b-133">必要なアクセス許可がない場合は、IBM WebSphere MQ エクスプローラーを使用してキューを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c497b-133">If you do not have such access, you can create the queue using the IBM WebSphere MQ Explorer.</span></span> <span data-ttu-id="c497b-134">WebSphere MQ エクスプローラーを使用してキューを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c497b-134">To create the queues through the WebSphere MQ Explorer, complete the following steps.</span></span>  
  
## <a name="creating-the-mqseries-queues-through-the-websphere-mq-explorer"></a><span data-ttu-id="c497b-135">WebSphere MQ エクスプローラーを使用した MQSeries キューの作成</span><span class="sxs-lookup"><span data-stu-id="c497b-135">Creating the MQSeries Queues Through the WebSphere MQ Explorer</span></span>  
  
#### <a name="to-create-the-mqseries-queues-through-the-websphere-mq-explorer"></a><span data-ttu-id="c497b-136">WebSphere MQ エクスプ ローラーを使用して MQSeries キューを作成するには</span><span class="sxs-lookup"><span data-stu-id="c497b-136">To create the MQSeries queues through the WebSphere MQ Explorer</span></span>  
  
1.  <span data-ttu-id="c497b-137">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**IBM WebSphere MQ**、順にクリック**WebSphere MQ エクスプ ローラー**です。</span><span class="sxs-lookup"><span data-stu-id="c497b-137">Click **Start**, point to **All Programs**, point to **IBM WebSphere MQ**, and then click **WebSphere MQ Explorer**.</span></span>  
  
2.  <span data-ttu-id="c497b-138">ダブルクリックして**キュー マネージャー**、順にダブルクリックし、**既定のキュー マネージャー**です。</span><span class="sxs-lookup"><span data-stu-id="c497b-138">Double-click **Queue Managers**, and then double-click the **default queue manager**.</span></span> <span data-ttu-id="c497b-139">通常、既定のキュー マネージャーの名前は QM_<コンピューター名> です。<コンピューター名> は、使用しているコンピューターの名前です。</span><span class="sxs-lookup"><span data-stu-id="c497b-139">The default queue manager is typically named QM_<machine_name> where machine_name is the name of your computer.</span></span>  
  
3.  <span data-ttu-id="c497b-140">右クリック**キュー**、 をポイント**新規**、クリックして**ローカル キュー**です。</span><span class="sxs-lookup"><span data-stu-id="c497b-140">Right-click **Queues**, point to **New**, and then click **Local Queue**.</span></span>  
  
4.  <span data-ttu-id="c497b-141">**ローカル キューの作成**ダイアログ ボックスで、**キュー名**、型**"queue1"**、クリックして**[ok]**です。</span><span class="sxs-lookup"><span data-stu-id="c497b-141">In **Create Local Queue** dialog box, in **Queue Name**, type **"queue1"**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="c497b-142">右クリック**キュー**をクリックして**新規**、順にクリック**ローカル キュー**です。</span><span class="sxs-lookup"><span data-stu-id="c497b-142">Right-click **Queues**, click **New**, and then click **Local Queue**.</span></span>  
  
6.  <span data-ttu-id="c497b-143">**ローカル キューの作成**ダイアログ ボックスで、**キュー名**、型**queue2**、クリックして**[ok]**です。</span><span class="sxs-lookup"><span data-stu-id="c497b-143">In the **Create Local Queue** dialog box, in **Queue Name**, type **"queue2"**, and then click **OK**.</span></span>  
  
## <a name="creating-the-receive-location-and-the-mqseries-queue"></a><span data-ttu-id="c497b-144">受信場所と MQSeries キューの作成</span><span class="sxs-lookup"><span data-stu-id="c497b-144">Creating the Receive Location and the MQSeries Queue</span></span>  
 <span data-ttu-id="c497b-145">この手順では、MQSeries へのメッセージ送信および MQSeries からの関連メッセージの受信を行うための送信ポートと受信場所を作成します。</span><span class="sxs-lookup"><span data-stu-id="c497b-145">This procedure creates the send port and receive location to send the message to and receive the correlation message from MQSeries.</span></span> <span data-ttu-id="c497b-146">MQSeries キューは、受信場所がまだ作成されていない場合に受信場所を作成したときにも作成されます。</span><span class="sxs-lookup"><span data-stu-id="c497b-146">The MQSeries queue will also be created when you create the receive location if not already created.</span></span>  
  
#### <a name="to-create-the-receive-location-and-the-mqseries-queue"></a><span data-ttu-id="c497b-147">受信場所と MQSeries キューを作成するには</span><span class="sxs-lookup"><span data-stu-id="c497b-147">To create the receive location and the MQSeries queue</span></span>  
  
1.  <span data-ttu-id="c497b-148">BizTalk Server 管理コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="c497b-148">Open the BizTalk Server Administration console.</span></span>  
  
2.  <span data-ttu-id="c497b-149">展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、し、必要なアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="c497b-149">Expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the required application.</span></span>  
  
3.  <span data-ttu-id="c497b-150">右クリック**受信ポート**、 をポイント**新規**、クリックして**一方向の受信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="c497b-150">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
4.  <span data-ttu-id="c497b-151">**一方向受信ポートのプロパティ** ダイアログ ボックスで、**名前**ボックスに「 **OrderedSampleReceive**  をクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="c497b-151">In the **One-way Receive Port Properties** dialog box type, in the **Name** box type **OrderedSampleReceive** and click **OK**.</span></span>  
  
5.  <span data-ttu-id="c497b-152">左側のウィンドウでをクリックして**受信場所** タブをクリックして**新規**です。</span><span class="sxs-lookup"><span data-stu-id="c497b-152">In the left pane, click **Receive Locations** tab, and then click **New**.</span></span>  
  
6.  <span data-ttu-id="c497b-153">**受信場所のプロパティ** ダイアログ ボックスで、**名前**ボックスに「"**OrderedSampleReceiveLocation**"です。</span><span class="sxs-lookup"><span data-stu-id="c497b-153">In the **Receive Location Properties** dialog box, in the **Name** box type "**OrderedSampleReceiveLocation**".</span></span>  
  
7.  <span data-ttu-id="c497b-154">**トランスポートの種類**ボックスで、 **MQSeries**です。</span><span class="sxs-lookup"><span data-stu-id="c497b-154">In the **Transport Type** box, select **MQSeries**.</span></span>  
  
8.  <span data-ttu-id="c497b-155">**受信ハンドラー**ボックスで、 **BizTalkServerApplication**です。</span><span class="sxs-lookup"><span data-stu-id="c497b-155">In the **Receive Handler** box, select **BizTalkServerApplication**.</span></span>  
  
9. <span data-ttu-id="c497b-156">**受信パイプライン**ボックスで、 **Microsoft.BizTalk.DefaultPipelines.PassThruReceive**です。</span><span class="sxs-lookup"><span data-stu-id="c497b-156">In the **Receive pipeline** box, select **Microsoft.BizTalk.DefaultPipelines.PassThruReceive**.</span></span>  
  
10. <span data-ttu-id="c497b-157">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="c497b-157">Click **Configure**.</span></span>  
  
11. <span data-ttu-id="c497b-158">**MQSeries トランスポートのプロパティ** ダイアログ ボックスで、**のポーリング間隔**ボックスに、入力**「10」**です。</span><span class="sxs-lookup"><span data-stu-id="c497b-158">In the **MQSeries Transport Properties** dialog box, in the **Polling Interval** box, type **"10"**.</span></span>  
  
12. <span data-ttu-id="c497b-159">**キュー定義**ボックスで、クリックして、**省略記号 (...)**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c497b-159">In the **Queue Definition** box, click the **ellipsis (…)** button.</span></span>  
  
13. <span data-ttu-id="c497b-160">**キュー定義** ダイアログ ボックスで、**サーバー名**ボックスに、コンピューター名を入力します。</span><span class="sxs-lookup"><span data-stu-id="c497b-160">In the **Queue Definition** dialog box, in the **Server Name** box, type your computer name.</span></span>  
  
14. <span data-ttu-id="c497b-161">**キュー マネージャー**ボックスで、選択、**既定のキュー マネージャー**です。</span><span class="sxs-lookup"><span data-stu-id="c497b-161">In the **Queue Manager** box, select the **default queue manager**.</span></span>  
  
15. <span data-ttu-id="c497b-162">**キュー**ボックスに、入力" **queue1**"、クリックして**エクスポート**です。</span><span class="sxs-lookup"><span data-stu-id="c497b-162">In the **Queue** box, type " **queue1**", and then click **Export**.</span></span>  
  
16. <span data-ttu-id="c497b-163">**エクスポート**ダイアログ ボックスで、をクリックして**キューの作成**、順にクリック**[ok]**または**完了**すべてのダイアログ ボックスを終了します。</span><span class="sxs-lookup"><span data-stu-id="c497b-163">In the **Export** dialog box, click **Create Queue**, and then click **OK** or **Done** until you have exited all dialog boxes.</span></span>  
  
## <a name="creating-the-send-port-and-mqseries-queue"></a><span data-ttu-id="c497b-164">送信ポートと MQSeries キューの作成</span><span class="sxs-lookup"><span data-stu-id="c497b-164">Creating the Send Port and MQSeries Queue</span></span>  
  
#### <a name="to-create-the-send-port-and-mqseries-queue"></a><span data-ttu-id="c497b-165">送信ポートと MQSeries キューを作成するには</span><span class="sxs-lookup"><span data-stu-id="c497b-165">To create the send port and MQSeries queue</span></span>  
  
1.  <span data-ttu-id="c497b-166">右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な一方向送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="c497b-166">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="c497b-167">**静的ポートのプロパティ** ダイアログ ボックスで、**名前**ボックスに、入力"**OrderedSampleSend**"です。</span><span class="sxs-lookup"><span data-stu-id="c497b-167">In the **Static Port Properties** dialog box type, in the **Name** box, type "**OrderedSampleSend**".</span></span>  
  
3.  <span data-ttu-id="c497b-168">**トランスポートの種類**ボックスで、 **MQSeries**です。</span><span class="sxs-lookup"><span data-stu-id="c497b-168">In the **Transport Type** box, select **MQSeries**.</span></span>  
  
4.  <span data-ttu-id="c497b-169">**送信パイプライン**ボックスで、 **Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**です。</span><span class="sxs-lookup"><span data-stu-id="c497b-169">In the **Send pipeline** box, select **Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**.</span></span>  
  
5.  <span data-ttu-id="c497b-170">をクリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="c497b-170">Click **Configure**.</span></span>  
  
6.  <span data-ttu-id="c497b-171">**MQSeries トランスポートのプロパティ** ダイアログ ボックスで、**キュー定義**ボックスで、クリックして、**省略記号 (...)**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c497b-171">In the **MQSeries Transport Properties** dialog box, in the **Queue Definition** box, click the **ellipsis (…)** button.</span></span>  
  
7.  <span data-ttu-id="c497b-172">**キュー定義** ダイアログ ボックスで、**サーバー名**ボックスに、コンピューター名を入力します。</span><span class="sxs-lookup"><span data-stu-id="c497b-172">In the **Queue Definition** dialog box, in the **Server Name** box, type your computer name.</span></span>  
  
8.  <span data-ttu-id="c497b-173">**キュー マネージャー**ボックスで、選択、**既定のキュー マネージャー**です。</span><span class="sxs-lookup"><span data-stu-id="c497b-173">In the **Queue Manager** box, select the **default queue manager**.</span></span>  
  
9. <span data-ttu-id="c497b-174">**キュー**ボックスに、入力" **queue2**"、クリックして**エクスポート**です。</span><span class="sxs-lookup"><span data-stu-id="c497b-174">In the **Queue** box, type " **queue2**", and then click **Export**.</span></span>  
  
10. <span data-ttu-id="c497b-175">**エクスポート**ダイアログ ボックスで、をクリックして**キューの作成**、順にクリック**[ok]**または**完了**すべてのダイアログ ボックスを終了します。</span><span class="sxs-lookup"><span data-stu-id="c497b-175">In the **Export** dialog box, click **Create Queue**, and then click **OK** or **Done** until you have exited all dialog boxes.</span></span>  
  
#### <a name="to-enable-the-receive-location-and-start-the-send-port"></a><span data-ttu-id="c497b-176">受信場所を有効にして送信ポートを開始するには</span><span class="sxs-lookup"><span data-stu-id="c497b-176">To enable the receive location and start the send port</span></span>  
  
1.  <span data-ttu-id="c497b-177">BizTalk Server 管理コンソールで **受信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="c497b-177">In the BizTalk Server Administration console, click **Receive Ports**.</span></span>  
  
2.  <span data-ttu-id="c497b-178">詳細ウィンドウで右クリックし、 **MQIn**受信場所をクリックして**を有効にする**です。</span><span class="sxs-lookup"><span data-stu-id="c497b-178">In the details pane, right-click the **MQIn** receive location and click **Enable**.</span></span>  
  
3.  <span data-ttu-id="c497b-179">詳細ウィンドウで右クリックし、 **MQOut**送信ポートをクリックして**を開始します。**</span><span class="sxs-lookup"><span data-stu-id="c497b-179">In the details pane, right-click the **MQOut** send port and click **Start.**</span></span>  
  
#### <a name="to-bind-and-start-the-orchestration"></a><span data-ttu-id="c497b-180">バインドし、オーケストレーションの開始</span><span class="sxs-lookup"><span data-stu-id="c497b-180">To bind and start the Orchestration</span></span>  
  
1.  <span data-ttu-id="c497b-181">BizTalk Server 管理コンソールで、展開、**オーケストレーション**フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="c497b-181">In the BizTalk Server Administration console, expand the **Orchestrations** folder.</span></span>  
  
2.  <span data-ttu-id="c497b-182">ダブルクリックして、 **OrderedSampleOrchestration**オーケストレーション、およびクリック**バインド**です。</span><span class="sxs-lookup"><span data-stu-id="c497b-182">Double-click the **OrderedSampleOrchestration** orchestration, and then click  **Bindings**.</span></span>  
  
3.  <span data-ttu-id="c497b-183">オーケストレーション ポートを、以下の送信ポートおよび受信場所にバインドします。</span><span class="sxs-lookup"><span data-stu-id="c497b-183">Bind the orchestration ports to the following send ports and receive locations:</span></span>  
  
    |<span data-ttu-id="c497b-184">オーケストレーション ポート</span><span class="sxs-lookup"><span data-stu-id="c497b-184">Orchestration Port</span></span>|<span data-ttu-id="c497b-185">メッセージ ポート/受信場所</span><span class="sxs-lookup"><span data-stu-id="c497b-185">Messaging Port / Receive Location</span></span>|  
    |------------------------|----------------------------------------|  
    |<span data-ttu-id="c497b-186">mqreceive</span><span class="sxs-lookup"><span data-stu-id="c497b-186">mqreceive</span></span>|<span data-ttu-id="c497b-187">OrderedSampleReceive</span><span class="sxs-lookup"><span data-stu-id="c497b-187">OrderedSampleReceive</span></span>|  
    |<span data-ttu-id="c497b-188">mqsend</span><span class="sxs-lookup"><span data-stu-id="c497b-188">mqsend</span></span>|<span data-ttu-id="c497b-189">OrderedSampleSend</span><span class="sxs-lookup"><span data-stu-id="c497b-189">OrderedSampleSend</span></span>|  
  
4.  <span data-ttu-id="c497b-190">をクリックして**ホスト**です。</span><span class="sxs-lookup"><span data-stu-id="c497b-190">Click **Host**.</span></span>  
  
5.  <span data-ttu-id="c497b-191">**ホスト**ボックスで、 **BizTalkServerApplication**、 をクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="c497b-191">In the **Host** box, select **BizTalkServerApplication**, and click **OK**.</span></span>  
  
6.  <span data-ttu-id="c497b-192">右クリックして、**オーケストレーション** をクリック**開始**です。</span><span class="sxs-lookup"><span data-stu-id="c497b-192">Right click the **Orchestration** and click **Start**.</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="c497b-193">サンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="c497b-193">To run the sample</span></span>  
  
1.  <span data-ttu-id="c497b-194">オーケストレーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="c497b-194">Start the orchestration.</span></span>  
  
2.  <span data-ttu-id="c497b-195">受信場所で読み取るよう構成した MQSeries キューにメッセージを配置します。</span><span class="sxs-lookup"><span data-stu-id="c497b-195">Put messages into the MQSeries queue from which you have configured the receive location to read.</span></span>  
  
3.  <span data-ttu-id="c497b-196">送信ポートでメッセージを送信するよう構成した送信キューのメッセージを WebSphere MQ エクスプローラーで表示します。</span><span class="sxs-lookup"><span data-stu-id="c497b-196">View the messages in WebSphere MQ Explorer in the send queue to which you have configured the send port to send messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c497b-197">参照</span><span class="sxs-lookup"><span data-stu-id="c497b-197">See Also</span></span>  
 [<span data-ttu-id="c497b-198">MQSeries アダプタ サンプル</span><span class="sxs-lookup"><span data-stu-id="c497b-198">MQSeries Adapter Samples</span></span>](../core/mqseries-adapter-samples.md)