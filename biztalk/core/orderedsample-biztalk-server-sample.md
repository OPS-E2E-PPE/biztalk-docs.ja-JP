---
title: OrderedSample (BizTalk Server サンプル) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, MQSeries adapters
- orchestrations, examples
- examples, orchestrations
- MQSeries adapters, examples
ms.assetid: 7e59ff43-d425-40cd-9725-af13084f83d9
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96a8cd43f80e9bf6ef7b5a2628f276aa7ef6829c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013099"
---
# <a name="orderedsample-biztalk-server-sample"></a><span data-ttu-id="9c43e-102">OrderedSample (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="9c43e-102">OrderedSample (BizTalk Server Sample)</span></span>
<span data-ttu-id="9c43e-103">OrderedSample サンプルは、オーケストレーションを使用して、順序付けられた一連のメッセージをラウンド トリップ方式で送受信する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="9c43e-103">The OrderedSample sample demonstrates how to use an orchestration to receive and send an ordered series of messages in a round-trip fashion.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="9c43e-104">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="9c43e-104">What This Sample Does</span></span>  
 <span data-ttu-id="9c43e-105">このサンプルでは、サンプルにメッセージを配信する MQSeries キューにメッセージがあることを前提とします。</span><span class="sxs-lookup"><span data-stu-id="9c43e-105">The sample assumes there are messages in the MQSeries queue from which it receives messages.</span></span> <span data-ttu-id="9c43e-106">MQSeries キューのメッセージは、アダプターによって順番に読み取られて [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に送信されます。</span><span class="sxs-lookup"><span data-stu-id="9c43e-106">When the adapter reads the messages from MQSeries queue, it reads them in-order and submits them to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="9c43e-107">オーケストレーションで受信ポート**mqreceive**がその**順次配送**プロパティに設定**True**します。</span><span class="sxs-lookup"><span data-stu-id="9c43e-107">The receive port in the orchestration, **mqreceive**, has its **Ordered Delivery** property set to **True**.</span></span>  
  
 <span data-ttu-id="9c43e-108">送信側では、オーケストレーションによってメッセージが送信され、配信通知の受信後に次のメッセージが送信されます。</span><span class="sxs-lookup"><span data-stu-id="9c43e-108">For the send side, the orchestration sends a message and then waits for a delivery notification before sending the next message.</span></span> <span data-ttu-id="9c43e-109">送信ポート、 **mqsend**がその**配信通知**プロパティに設定**送信**します。</span><span class="sxs-lookup"><span data-stu-id="9c43e-109">The send port, **mqsend** has its **Delivery Notification** property set to **Transmitted**.</span></span> <span data-ttu-id="9c43e-110">サンプルをシンプルにするために、オーケストレーションでは無限ループが使用されています。</span><span class="sxs-lookup"><span data-stu-id="9c43e-110">To keep the example simple, the orchestration uses an infinite loop.</span></span>  
  
 <span data-ttu-id="9c43e-111">オーケストレーションでは、メッセージのバッチおよび 1 つのメッセージを受信できます。</span><span class="sxs-lookup"><span data-stu-id="9c43e-111">The orchestration can receive batches of messages and single messages.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="9c43e-112">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="9c43e-112">Where to Find This Sample</span></span>  
 <span data-ttu-id="9c43e-113">*\<パスのサンプル\>* \AdaptersUsage\MQSeriesAdapter\OrderedSample</span><span class="sxs-lookup"><span data-stu-id="9c43e-113">*\<Samples Path\>* \AdaptersUsage\MQSeriesAdapter\OrderedSample</span></span>  
  
 <span data-ttu-id="9c43e-114">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="9c43e-114">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="9c43e-115">ファイル</span><span class="sxs-lookup"><span data-stu-id="9c43e-115">File</span></span>|<span data-ttu-id="9c43e-116">説明</span><span class="sxs-lookup"><span data-stu-id="9c43e-116">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="9c43e-117">OrderedReceiveSend.btproj,</span><span class="sxs-lookup"><span data-stu-id="9c43e-117">OrderedReceiveSend.btproj,</span></span><br /><br /> <span data-ttu-id="9c43e-118">OrderedReceiveSend.sln</span><span class="sxs-lookup"><span data-stu-id="9c43e-118">OrderedReceiveSend.sln</span></span>|<span data-ttu-id="9c43e-119">アプリケーションのプロジェクトおよびソリューション ファイル。</span><span class="sxs-lookup"><span data-stu-id="9c43e-119">Project and solution files for the application.</span></span>|  
|<span data-ttu-id="9c43e-120">OrderedReceiveSendOrchestration.odx</span><span class="sxs-lookup"><span data-stu-id="9c43e-120">OrderedReceiveSendOrchestration.odx</span></span>|<span data-ttu-id="9c43e-121">アプリケーションのオーケストレーション。</span><span class="sxs-lookup"><span data-stu-id="9c43e-121">The orchestration of the application.</span></span>|  
|<span data-ttu-id="9c43e-122">OrderedSample.snk</span><span class="sxs-lookup"><span data-stu-id="9c43e-122">OrderedSample.snk</span></span>|<span data-ttu-id="9c43e-123">厳密な名前のキー ファイル。</span><span class="sxs-lookup"><span data-stu-id="9c43e-123">The strong naming key file.</span></span>|  
|<span data-ttu-id="9c43e-124">**Setup.bat**</span><span class="sxs-lookup"><span data-stu-id="9c43e-124">**Setup.bat**</span></span>|<span data-ttu-id="9c43e-125">このサンプルを作成および初期化します。</span><span class="sxs-lookup"><span data-stu-id="9c43e-125">Builds and initializes this sample.</span></span>|  
  
## <a name="building-and-running-the-sample"></a><span data-ttu-id="9c43e-126">サンプルのビルドと実行</span><span class="sxs-lookup"><span data-stu-id="9c43e-126">Building and Running the Sample</span></span>  
  
#### <a name="to-build-and-deploy-the-sample"></a><span data-ttu-id="9c43e-127">サンプルをビルドして展開するには</span><span class="sxs-lookup"><span data-stu-id="9c43e-127">To build and deploy the sample</span></span>  
  
1. <span data-ttu-id="9c43e-128">コマンド ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="9c43e-128">In a command window, navigate to the following folder:</span></span>  
  
    `<Samples Path>\AdaptersUsage\MQSeriesAdapter\OrderedSample`  
  
2. <span data-ttu-id="9c43e-129">ファイルは、次の操作を実行します。 Setup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="9c43e-129">Run the file Setup.bat, which performs the following actions:</span></span>  
  
   1.  <span data-ttu-id="9c43e-130">プロジェクトの厳密な名前のキー ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="9c43e-130">Creates a strong name key for the project.</span></span>  
  
   2.  <span data-ttu-id="9c43e-131">オーケストレーション プロジェクトをコンパイルして展開します。</span><span class="sxs-lookup"><span data-stu-id="9c43e-131">Compiles and deploys the orchestration project.</span></span>  
  
   <span data-ttu-id="9c43e-132">MQSeries Server for Windows のインストールに必要なアクセス許可を持っている場合は、アダプターのダイアログ ボックスを使用して MQSeries キューを作成できるため、次の手順を省略できます。</span><span class="sxs-lookup"><span data-stu-id="9c43e-132">If you have the required permissions to the MQSeries Server for Windows installation, you can create the MQSeries queue through the adapter dialog boxes, and can skip the next procedure.</span></span> <span data-ttu-id="9c43e-133">必要なアクセス許可がない場合は、IBM WebSphere MQ エクスプローラーを使用してキューを作成できます。</span><span class="sxs-lookup"><span data-stu-id="9c43e-133">If you do not have such access, you can create the queue using the IBM WebSphere MQ Explorer.</span></span> <span data-ttu-id="9c43e-134">WebSphere MQ エクスプローラーを使用してキューを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9c43e-134">To create the queues through the WebSphere MQ Explorer, complete the following steps.</span></span>  
  
## <a name="creating-the-mqseries-queues-through-the-websphere-mq-explorer"></a><span data-ttu-id="9c43e-135">WebSphere MQ エクスプローラーを使用した MQSeries キューの作成</span><span class="sxs-lookup"><span data-stu-id="9c43e-135">Creating the MQSeries Queues Through the WebSphere MQ Explorer</span></span>  
  
#### <a name="to-create-the-mqseries-queues-through-the-websphere-mq-explorer"></a><span data-ttu-id="9c43e-136">WebSphere MQ エクスプ ローラーを使用した MQSeries キューを作成するには</span><span class="sxs-lookup"><span data-stu-id="9c43e-136">To create the MQSeries queues through the WebSphere MQ Explorer</span></span>  
  
1.  <span data-ttu-id="9c43e-137">クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**IBM WebSphere MQ**、順にクリックします**WebSphere MQ エクスプ ローラー**します。</span><span class="sxs-lookup"><span data-stu-id="9c43e-137">Click **Start**, point to **All Programs**, point to **IBM WebSphere MQ**, and then click **WebSphere MQ Explorer**.</span></span>  
  
2.  <span data-ttu-id="9c43e-138">ダブルクリック**キュー マネージャー**、し、ダブルクリック、**既定のキュー マネージャー**します。</span><span class="sxs-lookup"><span data-stu-id="9c43e-138">Double-click **Queue Managers**, and then double-click the **default queue manager**.</span></span> <span data-ttu-id="9c43e-139">通常、既定のキュー マネージャーの名前は QM_<コンピューター名> です。<コンピューター名> は、使用しているコンピューターの名前です。</span><span class="sxs-lookup"><span data-stu-id="9c43e-139">The default queue manager is typically named QM_<machine_name> where machine_name is the name of your computer.</span></span>  
  
3.  <span data-ttu-id="9c43e-140">右クリック**キュー**、 をポイント**新規**、 をクリックし、**ローカル キュー**します。</span><span class="sxs-lookup"><span data-stu-id="9c43e-140">Right-click **Queues**, point to **New**, and then click **Local Queue**.</span></span>  
  
4.  <span data-ttu-id="9c43e-141">**ローカル キューの作成** ダイアログ ボックスで**キュー名**、型 **"queue1"**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="9c43e-141">In **Create Local Queue** dialog box, in **Queue Name**, type **"queue1"**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="9c43e-142">右クリック**キュー**、 をクリックして**新規**、 をクリックし、**ローカル キュー**します。</span><span class="sxs-lookup"><span data-stu-id="9c43e-142">Right-click **Queues**, click **New**, and then click **Local Queue**.</span></span>  
  
6.  <span data-ttu-id="9c43e-143">**ローカル キューの作成** ダイアログ ボックスで**キュー名**、型**queue2**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="9c43e-143">In the **Create Local Queue** dialog box, in **Queue Name**, type **"queue2"**, and then click **OK**.</span></span>  
  
## <a name="creating-the-receive-location-and-the-mqseries-queue"></a><span data-ttu-id="9c43e-144">受信場所と MQSeries キューの作成</span><span class="sxs-lookup"><span data-stu-id="9c43e-144">Creating the Receive Location and the MQSeries Queue</span></span>  
 <span data-ttu-id="9c43e-145">この手順では、MQSeries へのメッセージ送信および MQSeries からの関連メッセージの受信を行うための送信ポートと受信場所を作成します。</span><span class="sxs-lookup"><span data-stu-id="9c43e-145">This procedure creates the send port and receive location to send the message to and receive the correlation message from MQSeries.</span></span> <span data-ttu-id="9c43e-146">MQSeries キューは、受信場所がまだ作成されていない場合に受信場所を作成したときにも作成されます。</span><span class="sxs-lookup"><span data-stu-id="9c43e-146">The MQSeries queue will also be created when you create the receive location if not already created.</span></span>  
  
#### <a name="to-create-the-receive-location-and-the-mqseries-queue"></a><span data-ttu-id="9c43e-147">受信場所と MQSeries キューを作成するには</span><span class="sxs-lookup"><span data-stu-id="9c43e-147">To create the receive location and the MQSeries queue</span></span>  
  
1.  <span data-ttu-id="9c43e-148">BizTalk Server 管理コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="9c43e-148">Open the BizTalk Server Administration console.</span></span>  
  
2.  <span data-ttu-id="9c43e-149">展開**BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、し、必要なアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="9c43e-149">Expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the required application.</span></span>  
  
3.  <span data-ttu-id="9c43e-150">右クリック**受信ポート**、 をポイント**新規**、 をクリックし、**一方向の受信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="9c43e-150">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
4.  <span data-ttu-id="9c43e-151">**一方向受信ポートのプロパティ** ダイアログ ボックスで、**名前**ボックスに「 **OrderedSampleReceive**  をクリック**OK**します。</span><span class="sxs-lookup"><span data-stu-id="9c43e-151">In the **One-way Receive Port Properties** dialog box type, in the **Name** box type **OrderedSampleReceive** and click **OK**.</span></span>  
  
5.  <span data-ttu-id="9c43e-152">左側のウィンドウで次のようにクリックします。**受信場所**タブをクリックし、[] をクリックし、**新規**します。</span><span class="sxs-lookup"><span data-stu-id="9c43e-152">In the left pane, click **Receive Locations** tab, and then click **New**.</span></span>  
  
6.  <span data-ttu-id="9c43e-153">**受信場所のプロパティ** ダイアログ ボックスで、**名前**ボックスに「"**OrderedSampleReceiveLocation**"。</span><span class="sxs-lookup"><span data-stu-id="9c43e-153">In the **Receive Location Properties** dialog box, in the **Name** box type "**OrderedSampleReceiveLocation**".</span></span>  
  
7.  <span data-ttu-id="9c43e-154">**トランスポートの種類**ボックスで、 **MQSeries**します。</span><span class="sxs-lookup"><span data-stu-id="9c43e-154">In the **Transport Type** box, select **MQSeries**.</span></span>  
  
8.  <span data-ttu-id="9c43e-155">**受信ハンドラー**ボックスで、 **BizTalkServerApplication**します。</span><span class="sxs-lookup"><span data-stu-id="9c43e-155">In the **Receive Handler** box, select **BizTalkServerApplication**.</span></span>  
  
9. <span data-ttu-id="9c43e-156">**受信パイプライン**ボックスで、 **Microsoft.BizTalk.DefaultPipelines.PassThruReceive**します。</span><span class="sxs-lookup"><span data-stu-id="9c43e-156">In the **Receive pipeline** box, select **Microsoft.BizTalk.DefaultPipelines.PassThruReceive**.</span></span>  
  
10. <span data-ttu-id="9c43e-157">クリックして**構成**します。</span><span class="sxs-lookup"><span data-stu-id="9c43e-157">Click **Configure**.</span></span>  
  
11. <span data-ttu-id="9c43e-158">**MQSeries トランスポートのプロパティ** ダイアログ ボックスで、**のポーリング間隔**ボックスに「 **「10」** します。</span><span class="sxs-lookup"><span data-stu-id="9c43e-158">In the **MQSeries Transport Properties** dialog box, in the **Polling Interval** box, type **"10"**.</span></span>  
  
12. <span data-ttu-id="9c43e-159">**キュー定義**ボックスで、、**省略記号 (...)** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c43e-159">In the **Queue Definition** box, click the **ellipsis (…)** button.</span></span>  
  
13. <span data-ttu-id="9c43e-160">**キュー定義** ダイアログ ボックスで、**サーバー名**ボックスに、コンピューター名を入力します。</span><span class="sxs-lookup"><span data-stu-id="9c43e-160">In the **Queue Definition** dialog box, in the **Server Name** box, type your computer name.</span></span>  
  
14. <span data-ttu-id="9c43e-161">**キュー マネージャー**ボックスで、選択、**既定のキュー マネージャー**します。</span><span class="sxs-lookup"><span data-stu-id="9c43e-161">In the **Queue Manager** box, select the **default queue manager**.</span></span>  
  
15. <span data-ttu-id="9c43e-162">**キュー**ボックスに「" **queue1**"、 をクリックし、**エクスポート**します。</span><span class="sxs-lookup"><span data-stu-id="9c43e-162">In the **Queue** box, type " **queue1**", and then click **Export**.</span></span>  
  
16. <span data-ttu-id="9c43e-163">**エクスポート**ダイアログ ボックスで、をクリックして**キューの作成**、順にクリックします **[ok]** または**完了**すべてのダイアログ ボックスを終了します。</span><span class="sxs-lookup"><span data-stu-id="9c43e-163">In the **Export** dialog box, click **Create Queue**, and then click **OK** or **Done** until you have exited all dialog boxes.</span></span>  
  
## <a name="creating-the-send-port-and-mqseries-queue"></a><span data-ttu-id="9c43e-164">送信ポートと MQSeries キューの作成</span><span class="sxs-lookup"><span data-stu-id="9c43e-164">Creating the Send Port and MQSeries Queue</span></span>  
  
#### <a name="to-create-the-send-port-and-mqseries-queue"></a><span data-ttu-id="9c43e-165">送信ポートと MQSeries キューを作成するには</span><span class="sxs-lookup"><span data-stu-id="9c43e-165">To create the send port and MQSeries queue</span></span>  
  
1.  <span data-ttu-id="9c43e-166">右クリック**送信ポート**、 をポイント**新規**、 をクリックし、**静的な一方向送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="9c43e-166">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="9c43e-167">**静的ポートのプロパティ** ダイアログ ボックスで、**名前**ボックスに「"**OrderedSampleSend**"。</span><span class="sxs-lookup"><span data-stu-id="9c43e-167">In the **Static Port Properties** dialog box type, in the **Name** box, type "**OrderedSampleSend**".</span></span>  
  
3.  <span data-ttu-id="9c43e-168">**トランスポートの種類**ボックスで、 **MQSeries**します。</span><span class="sxs-lookup"><span data-stu-id="9c43e-168">In the **Transport Type** box, select **MQSeries**.</span></span>  
  
4.  <span data-ttu-id="9c43e-169">**送信パイプライン**ボックスで、 **Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**します。</span><span class="sxs-lookup"><span data-stu-id="9c43e-169">In the **Send pipeline** box, select **Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**.</span></span>  
  
5.  <span data-ttu-id="9c43e-170">クリックして**構成**します。</span><span class="sxs-lookup"><span data-stu-id="9c43e-170">Click **Configure**.</span></span>  
  
6.  <span data-ttu-id="9c43e-171">**MQSeries トランスポートのプロパティ**] ダイアログ ボックスで、**キュー定義**ボックスで、[、**省略記号 (...)** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c43e-171">In the **MQSeries Transport Properties** dialog box, in the **Queue Definition** box, click the **ellipsis (…)** button.</span></span>  
  
7.  <span data-ttu-id="9c43e-172">**キュー定義** ダイアログ ボックスで、**サーバー名**ボックスに、コンピューター名を入力します。</span><span class="sxs-lookup"><span data-stu-id="9c43e-172">In the **Queue Definition** dialog box, in the **Server Name** box, type your computer name.</span></span>  
  
8.  <span data-ttu-id="9c43e-173">**キュー マネージャー**ボックスで、選択、**既定のキュー マネージャー**します。</span><span class="sxs-lookup"><span data-stu-id="9c43e-173">In the **Queue Manager** box, select the **default queue manager**.</span></span>  
  
9. <span data-ttu-id="9c43e-174">**キュー**ボックスに「" **queue2**"、 をクリックし、**エクスポート**します。</span><span class="sxs-lookup"><span data-stu-id="9c43e-174">In the **Queue** box, type " **queue2**", and then click **Export**.</span></span>  
  
10. <span data-ttu-id="9c43e-175">**エクスポート**ダイアログ ボックスで、をクリックして**キューの作成**、順にクリックします **[ok]** または**完了**すべてのダイアログ ボックスを終了します。</span><span class="sxs-lookup"><span data-stu-id="9c43e-175">In the **Export** dialog box, click **Create Queue**, and then click **OK** or **Done** until you have exited all dialog boxes.</span></span>  
  
#### <a name="to-enable-the-receive-location-and-start-the-send-port"></a><span data-ttu-id="9c43e-176">受信場所を有効にして送信ポートを開始するには</span><span class="sxs-lookup"><span data-stu-id="9c43e-176">To enable the receive location and start the send port</span></span>  
  
1.  <span data-ttu-id="9c43e-177">BizTalk Server 管理コンソールで、次のようにクリックします。**受信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="9c43e-177">In the BizTalk Server Administration console, click **Receive Ports**.</span></span>  
  
2.  <span data-ttu-id="9c43e-178">詳細ペインで右クリックし、 **MQIn**受信場所とクリックして**を有効にする**します。</span><span class="sxs-lookup"><span data-stu-id="9c43e-178">In the details pane, right-click the **MQIn** receive location and click **Enable**.</span></span>  
  
3.  <span data-ttu-id="9c43e-179">詳細ペインで右クリックし、 **MQOut**送信ポートを**を開始します。**</span><span class="sxs-lookup"><span data-stu-id="9c43e-179">In the details pane, right-click the **MQOut** send port and click **Start.**</span></span>  
  
#### <a name="to-bind-and-start-the-orchestration"></a><span data-ttu-id="9c43e-180">バインドし、オーケストレーションを開始するには</span><span class="sxs-lookup"><span data-stu-id="9c43e-180">To bind and start the Orchestration</span></span>  
  
1.  <span data-ttu-id="9c43e-181">BizTalk Server 管理コンソールで、**オーケストレーション**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="9c43e-181">In the BizTalk Server Administration console, expand the **Orchestrations** folder.</span></span>  
  
2.  <span data-ttu-id="9c43e-182">ダブルクリックして、 **OrderedSampleOrchestration**オーケストレーション、およびクリック**バインド**。</span><span class="sxs-lookup"><span data-stu-id="9c43e-182">Double-click the **OrderedSampleOrchestration** orchestration, and then click  **Bindings**.</span></span>  
  
3.  <span data-ttu-id="9c43e-183">オーケストレーション ポートを、以下の送信ポートおよび受信場所にバインドします。</span><span class="sxs-lookup"><span data-stu-id="9c43e-183">Bind the orchestration ports to the following send ports and receive locations:</span></span>  
  
    |<span data-ttu-id="9c43e-184">オーケストレーション ポート</span><span class="sxs-lookup"><span data-stu-id="9c43e-184">Orchestration Port</span></span>|<span data-ttu-id="9c43e-185">メッセージ ポート/受信場所</span><span class="sxs-lookup"><span data-stu-id="9c43e-185">Messaging Port / Receive Location</span></span>|  
    |------------------------|----------------------------------------|  
    |<span data-ttu-id="9c43e-186">mqreceive</span><span class="sxs-lookup"><span data-stu-id="9c43e-186">mqreceive</span></span>|<span data-ttu-id="9c43e-187">OrderedSampleReceive</span><span class="sxs-lookup"><span data-stu-id="9c43e-187">OrderedSampleReceive</span></span>|  
    |<span data-ttu-id="9c43e-188">mqsend</span><span class="sxs-lookup"><span data-stu-id="9c43e-188">mqsend</span></span>|<span data-ttu-id="9c43e-189">OrderedSampleSend</span><span class="sxs-lookup"><span data-stu-id="9c43e-189">OrderedSampleSend</span></span>|  
  
4.  <span data-ttu-id="9c43e-190">クリックして**ホスト**します。</span><span class="sxs-lookup"><span data-stu-id="9c43e-190">Click **Host**.</span></span>  
  
5.  <span data-ttu-id="9c43e-191">**ホスト**ボックスで、 **BizTalkServerApplication**、 をクリック**OK**します。</span><span class="sxs-lookup"><span data-stu-id="9c43e-191">In the **Host** box, select **BizTalkServerApplication**, and click **OK**.</span></span>  
  
6.  <span data-ttu-id="9c43e-192">右クリックして、**オーケストレーション**クリック**開始**。</span><span class="sxs-lookup"><span data-stu-id="9c43e-192">Right click the **Orchestration** and click **Start**.</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="9c43e-193">サンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="9c43e-193">To run the sample</span></span>  
  
1.  <span data-ttu-id="9c43e-194">オーケストレーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="9c43e-194">Start the orchestration.</span></span>  
  
2.  <span data-ttu-id="9c43e-195">受信場所で読み取るよう構成した MQSeries キューにメッセージを配置します。</span><span class="sxs-lookup"><span data-stu-id="9c43e-195">Put messages into the MQSeries queue from which you have configured the receive location to read.</span></span>  
  
3.  <span data-ttu-id="9c43e-196">送信ポートでメッセージを送信するよう構成した送信キューのメッセージを WebSphere MQ エクスプローラーで表示します。</span><span class="sxs-lookup"><span data-stu-id="9c43e-196">View the messages in WebSphere MQ Explorer in the send queue to which you have configured the send port to send messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c43e-197">参照</span><span class="sxs-lookup"><span data-stu-id="9c43e-197">See Also</span></span>  
 [<span data-ttu-id="9c43e-198">MQSeries アダプタ サンプル</span><span class="sxs-lookup"><span data-stu-id="9c43e-198">MQSeries Adapter Samples</span></span>](../core/mqseries-adapter-samples.md)