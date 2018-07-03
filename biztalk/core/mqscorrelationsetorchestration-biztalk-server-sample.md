---
title: MQSCorrelationSetOrchestration (BizTalk Server サンプル) |Microsoft Docs
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
- examples, messages
- messages, examples
- MQSeries adapters, examples
ms.assetid: fcda65d0-e3ec-4ead-978d-3904903b8762
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d0057e9a9276de5eb3724f1af298822b03065a3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011779"
---
# <a name="mqscorrelationsetorchestration-biztalk-server-sample"></a><span data-ttu-id="54439-102">MQSCorrelationSetOrchestration (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="54439-102">MQSCorrelationSetOrchestration (BizTalk Server Sample)</span></span>
<span data-ttu-id="54439-103">MQSCorrelationSetOrchestration サンプルは、実行中のオーケストレーションに MQSeries キューをルーティングして戻すために送信されるメッセージを関連付けるための MQSeries 関連付け識別子を使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="54439-103">The MQSCorrelationSetOrchestration sample demonstrates how to use the MQSeries correlation identifier for correlating messages sent to an MQSeries queue back to a running orchestration.</span></span> <span data-ttu-id="54439-104">オーケストレーションが、識別子の値を使用して MQSeries 関連付け識別子とメッセージを設定、 **MQMD_CorrelId**と**MQMD_MsgID**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="54439-104">The orchestration sets the MQSeries correlation identifier and message identifier values using the **MQMD_CorrelId** and **MQMD_MsgID** properties.</span></span> <span data-ttu-id="54439-105">MQSeries キュー マネージャーは、MessageID の値をメッセージの CorrelationID プロパティにコピーします。</span><span class="sxs-lookup"><span data-stu-id="54439-105">The MQSeries Queue Manager copies the MessageID value to the CorrelationID property of the message.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="54439-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="54439-106">Prerequisites</span></span>  
 <span data-ttu-id="54439-107">このサンプルでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を実行しているのと同じサーバー上に IBM WebSphere MQSeries がインストールされていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="54439-107">This sample assumes that you have installed IBM WebSphere MQSeries on the same server that you are running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  

## <a name="what-this-sample-does"></a><span data-ttu-id="54439-108">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="54439-108">What This Sample Does</span></span>  
 <span data-ttu-id="54439-109">このサンプルは、IBM WebSphere MQSeries サーバーに送信されるメッセージにメッセージ識別子と関連付け識別子を設定する方法について示します。</span><span class="sxs-lookup"><span data-stu-id="54439-109">This sample illustrates how to set a message identifier and correlation identifier in a message sent to an IBM WebSphere MQSeries Server.</span></span> <span data-ttu-id="54439-110">これは、実行中のオーケストレーションにルーティングして戻すメッセージを関連付けるための 1 つの方法として挙げられます。</span><span class="sxs-lookup"><span data-stu-id="54439-110">This is one method that can be used to correlate a message back to a running orchestration instance.</span></span> <span data-ttu-id="54439-111">MQSeries キュー マネージャーはメッセージを受信すると、その MessageID の値をメッセージの CorrelationID プロパティにコピーします。</span><span class="sxs-lookup"><span data-stu-id="54439-111">When the MQSeries Queue Manager receives the message it copies the MessageID value to the CorrelationID property of the message.</span></span> <span data-ttu-id="54439-112">この CorrelationID (**MQMD_CorrelId**) を使用して、オーケストレーションの MQSeries の応答メッセージを MQSeries にメッセージを送信するために使用するインスタンスに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="54439-112">This CorrelationID (**MQMD_CorrelId**) is then used in the orchestration to associate the response message on MQSeries with the instance used to send messages to MQSeries.</span></span>  

## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="54439-113">このサンプルのデザイン方法とその理由</span><span class="sxs-lookup"><span data-stu-id="54439-113">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="54439-114">このサンプルは、オーケストレーションで処理中のドキュメントを MQSeries キューに送信可能であり (多くの場合、追加の処理を行うため)、実行中のオーケストレーションにルーティングして戻されるというシナリオを示します。</span><span class="sxs-lookup"><span data-stu-id="54439-114">This sample illustrates a scenario in which a document that is being processed by an orchestration can be sent to an MQSeries queue (presumably for additional processing) and returned back to the running orchestration.</span></span>  

## <a name="where-to-find-this-sample"></a><span data-ttu-id="54439-115">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="54439-115">Where to Find This Sample</span></span>  
 <span data-ttu-id="54439-116">*\<パスのサンプル\>* \AdaptersUsage\MQSeriesAdapter\MQSCorrelationSetOrchestration</span><span class="sxs-lookup"><span data-stu-id="54439-116">*\<Samples Path\>* \AdaptersUsage\MQSeriesAdapter\MQSCorrelationSetOrchestration</span></span>  

 <span data-ttu-id="54439-117">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="54439-117">The following table shows the files in this sample and describes their purpose.</span></span>  

|<span data-ttu-id="54439-118">**[最近使ったファイル]**</span><span class="sxs-lookup"><span data-stu-id="54439-118">**File**</span></span>|<span data-ttu-id="54439-119">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="54439-119">**Description**</span></span>|  
|--------------|---------------------|  
|<span data-ttu-id="54439-120">**MQSCorrelationSetOrchestration.btproj、**</span><span class="sxs-lookup"><span data-stu-id="54439-120">**MQSCorrelationSetOrchestration.btproj,**</span></span><br /><br /> <span data-ttu-id="54439-121">**MQSCorrelationSetOrchestration.sln**</span><span class="sxs-lookup"><span data-stu-id="54439-121">**MQSCorrelationSetOrchestration.sln**</span></span>|<span data-ttu-id="54439-122">アプリケーションのプロジェクトおよびソリューション ファイル。</span><span class="sxs-lookup"><span data-stu-id="54439-122">Project and solution files for the application.</span></span>|  
|<span data-ttu-id="54439-123">**MQSCorrelationSetOrchestration.odx**</span><span class="sxs-lookup"><span data-stu-id="54439-123">**MQSCorrelationSetOrchestration.odx**</span></span>|<span data-ttu-id="54439-124">アプリケーションのオーケストレーション。</span><span class="sxs-lookup"><span data-stu-id="54439-124">The orchestration of the application.</span></span>|  
|<span data-ttu-id="54439-125">**MQSCorrelationSetOrchestration.snk**</span><span class="sxs-lookup"><span data-stu-id="54439-125">**MQSCorrelationSetOrchestration.snk**</span></span>|<span data-ttu-id="54439-126">厳密な名前のキー ファイル。</span><span class="sxs-lookup"><span data-stu-id="54439-126">The strong naming key file.</span></span>|  
|<span data-ttu-id="54439-127">**Setup.bat**</span><span class="sxs-lookup"><span data-stu-id="54439-127">**Setup.bat**</span></span>|<span data-ttu-id="54439-128">このサンプルを作成および初期化します。</span><span class="sxs-lookup"><span data-stu-id="54439-128">Builds and initializes this sample.</span></span>|  

## <a name="how-to-use-this-sample"></a><span data-ttu-id="54439-129">このサンプルの使用方法</span><span class="sxs-lookup"><span data-stu-id="54439-129">How to Use This Sample</span></span>  
 <span data-ttu-id="54439-130">全体的なワークフローの 1 つのステップとして MQSeries サーバーにメッセージを送信する必要がある場合は、このサンプルで採用されているロジックを組み込みます。</span><span class="sxs-lookup"><span data-stu-id="54439-130">Incorporate the logic employed in this sample if you need to send a message to MQSeries Server as one of the steps in overall workflow.</span></span>  

### <a name="to-create-the-mqseries-queue-through-the-websphere-mq-explorer"></a><span data-ttu-id="54439-131">WebSphere MQ エクスプローラーを使用して MQSeries キューを作成するには</span><span class="sxs-lookup"><span data-stu-id="54439-131">To create the MQSeries queue through the WebSphere MQ Explorer</span></span>  

1.  <span data-ttu-id="54439-132">クリックして**開始**、 をポイント**プログラム**、 をポイント**IBM WebSphere MQ**、順にクリックします**WebSphere MQ エクスプ ローラー**します。</span><span class="sxs-lookup"><span data-stu-id="54439-132">Click **Start**, point to **Programs**, point to **IBM WebSphere MQ**, and then click **WebSphere MQ Explorer**.</span></span>  

2.  <span data-ttu-id="54439-133">ダブルクリック**キュー マネージャー**、し、既定のキュー マネージャーをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="54439-133">Double-click **Queue Managers**, and then double-click the default queue manager.</span></span> <span data-ttu-id="54439-134">通常、既定のキュー マネージャーの名前**qm _ < コンピューター名 >** 場所*machine_name*コンピューターの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="54439-134">The default queue manager is typically named **QM_<machine_name>** where *machine_name* is the name of your computer.</span></span>  

3.  <span data-ttu-id="54439-135">右クリック**キュー**、 をポイント**新規**、 をクリックし、**ローカル キュー**します。</span><span class="sxs-lookup"><span data-stu-id="54439-135">Right-click **Queues**, point to **New**, and then click **Local Queue**.</span></span>  

4.  <span data-ttu-id="54439-136">**ローカル キューの作成**] ダイアログ ボックスで**キュー名**"MQCorrelation"を入力し、[クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="54439-136">In **Create Local Queue** dialog box, in **Queue Name**, type "MQCorrelation", and then click **OK**.</span></span>  

### <a name="to-create-the-receive-location-and-the-mqseries-queue"></a><span data-ttu-id="54439-137">受信場所と MQSeries キューを作成するには</span><span class="sxs-lookup"><span data-stu-id="54439-137">To create the receive location and the MQSeries queue</span></span>  

1.  <span data-ttu-id="54439-138">BizTalk Server 管理コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="54439-138">Open the BizTalk Server Administration console.</span></span>  

2.  <span data-ttu-id="54439-139">展開**BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、し、必要なアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="54439-139">Expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the required application.</span></span>  

3.  <span data-ttu-id="54439-140">右クリック**受信ポート**、 をポイント**新規**、 をクリックし、**一方向の受信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="54439-140">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  

4.  <span data-ttu-id="54439-141">**一方向受信ポートのプロパティ** ダイアログ ボックスで、**名前**ボックスに「MQIn」を入力し、 をクリック**OK**します。</span><span class="sxs-lookup"><span data-stu-id="54439-141">In the **One-way Receive Port Properties** dialog box, in the **Name** box type "MQIn" and click **OK**.</span></span>  

5.  <span data-ttu-id="54439-142">左側のウィンドウで次のようにクリックします。**受信場所**タブをクリックし、[] をクリックし、**新規**します。</span><span class="sxs-lookup"><span data-stu-id="54439-142">In the left pane, click **Receive Locations** tab, and then click **New**.</span></span>  

6.  <span data-ttu-id="54439-143">**受信場所のプロパティ** ダイアログ ボックスで、**名前**ボックスに「MQIn」を入力します。</span><span class="sxs-lookup"><span data-stu-id="54439-143">In the **Receive Location Properties** dialog box, in the **Name** box, type "MQIn".</span></span>  

7.  <span data-ttu-id="54439-144">**トランスポートの種類**ボックスで、 **MQSeries**します。</span><span class="sxs-lookup"><span data-stu-id="54439-144">In the **Transport Type** box, select **MQSeries**.</span></span>  

8.  <span data-ttu-id="54439-145">**受信ハンドラー**ボックスで、 **BizTalkServerApplication**します。</span><span class="sxs-lookup"><span data-stu-id="54439-145">In the **Receive Handler** box, select **BizTalkServerApplication**.</span></span>  

9. <span data-ttu-id="54439-146">**受信パイプライン**ボックスで、 **Microsoft.BizTalk.DefaultPipelines.PassThruReceive**します。</span><span class="sxs-lookup"><span data-stu-id="54439-146">In the **Receive pipeline** box, select **Microsoft.BizTalk.DefaultPipelines.PassThruReceive**.</span></span>  

10. <span data-ttu-id="54439-147">クリックして**構成**します。</span><span class="sxs-lookup"><span data-stu-id="54439-147">Click **Configure**.</span></span>  

11. <span data-ttu-id="54439-148">**MQSeries トランスポートのプロパティ** ダイアログ ボックスで、**のポーリング間隔**ボックスに、「10」を入力します。</span><span class="sxs-lookup"><span data-stu-id="54439-148">In the **MQSeries Transport Properties** dialog box, in the **Polling Interval** box, type "10".</span></span>  

12. <span data-ttu-id="54439-149">**キュー定義**ボックスで、省略記号 (...) ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="54439-149">In the **Queue Definition** box, click the ellipsis (…) button.</span></span>  

13. <span data-ttu-id="54439-150">**キュー定義** ダイアログ ボックスで、**サーバー名**ボックスに、コンピューター名を入力します。</span><span class="sxs-lookup"><span data-stu-id="54439-150">In the **Queue Definition** dialog box, in the **Server Name** box, type your computer name.</span></span>  

14. <span data-ttu-id="54439-151">**キュー マネージャー**ボックスで、既定のキュー マネージャーを選択します。</span><span class="sxs-lookup"><span data-stu-id="54439-151">In the **Queue Manager** box, select the default queue manager.</span></span>  

15. <span data-ttu-id="54439-152">**キュー**ボックスに「MQCorrelation」を入力し、 クリック、**エクスポート**します。</span><span class="sxs-lookup"><span data-stu-id="54439-152">In the **Queue** box, type "MQCorrelation", and then click **Export**.</span></span>  

16. <span data-ttu-id="54439-153">**エクスポート**ダイアログ ボックスで、をクリックして**キューの作成**、順にクリックします **[ok]** または**完了**すべてのダイアログ ボックスを終了します。</span><span class="sxs-lookup"><span data-stu-id="54439-153">In the **Export** dialog box, click **Create Queue**, and then click**OK**or **Done** until you have exited all dialog boxes.</span></span>  

### <a name="to-create-the-send-port-to-mqseries"></a><span data-ttu-id="54439-154">MQSeries に対する送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="54439-154">To create the send port to MQSeries</span></span>  

1.  <span data-ttu-id="54439-155">右クリック**送信ポート**、 をポイント**新規**、 をクリックし、**静的な一方向送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="54439-155">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  

2.  <span data-ttu-id="54439-156">**送信ポートのプロパティ** ダイアログ ボックスで、**名前**ボックスに「mqout」.</span><span class="sxs-lookup"><span data-stu-id="54439-156">In the **Send Port Properties** dialog box, in the **Name** box, type "MQOut".</span></span>  

3.  <span data-ttu-id="54439-157">**トランスポートの種類**ボックスで、 **MQSeries**します。</span><span class="sxs-lookup"><span data-stu-id="54439-157">In the **Transport Type** box, select **MQSeries**.</span></span>  

4.  <span data-ttu-id="54439-158">**送信パイプライン**ボックスで、 **Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**します。</span><span class="sxs-lookup"><span data-stu-id="54439-158">In the **Send pipeline** box, select **Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**.</span></span>  

5.  <span data-ttu-id="54439-159">クリックして**構成**します。</span><span class="sxs-lookup"><span data-stu-id="54439-159">Click **Configure**.</span></span>  

6.  <span data-ttu-id="54439-160">**MQSeries トランスポートのプロパティ** ダイアログ ボックスで、**キュー定義**ボックスで、省略記号 (...) ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="54439-160">In the **MQSeries Transport Properties** dialog box, in the **Queue Definition** box, click the ellipsis (…) button.</span></span>  

7.  <span data-ttu-id="54439-161">**キュー定義** ダイアログ ボックスで、**サーバー名**ボックスに、コンピューター名を入力します。</span><span class="sxs-lookup"><span data-stu-id="54439-161">In the **Queue Definition** dialog box, in the **Server Name** box, type your computer name.</span></span>  

8.  <span data-ttu-id="54439-162">**キュー マネージャー**ボックスで、既定のキュー マネージャーを選択します。</span><span class="sxs-lookup"><span data-stu-id="54439-162">In the **Queue Manager** box, select the default queue manager.</span></span>  

9. <span data-ttu-id="54439-163">**キュー**ボックスに「MQCorrelation」を入力し、 クリック、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="54439-163">In the **Queue** box, type "MQCorrelation", and then click **OK**.</span></span>  

10. <span data-ttu-id="54439-164">クリックして**OK**すべてのダイアログ ボックスを終了します。</span><span class="sxs-lookup"><span data-stu-id="54439-164">Click **OK** until you have exited all dialog boxes.</span></span>  

### <a name="to-enable-the-receive-location-and-start-the-send-port"></a><span data-ttu-id="54439-165">受信場所を有効にして送信ポートを開始するには</span><span class="sxs-lookup"><span data-stu-id="54439-165">To enable the receive location and start the send port</span></span>  

1.  <span data-ttu-id="54439-166">BizTalk Server 管理コンソールで、次のようにクリックします。**受信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="54439-166">In the BizTalk Server Administration console, click **Receive Ports**.</span></span>  

2.  <span data-ttu-id="54439-167">詳細ペインで右クリックし、 **MQIn**受信場所とクリックして**を有効にする**します。</span><span class="sxs-lookup"><span data-stu-id="54439-167">In the details pane, right-click the **MQIn** receive location and click **Enable**.</span></span>  

3.  <span data-ttu-id="54439-168">詳細ペインで右クリックし、 **MQOut**送信ポートを**を開始します。**</span><span class="sxs-lookup"><span data-stu-id="54439-168">In the details pane, right-click the **MQOut** send port and click **Start.**</span></span>  

### <a name="to-create-the-folders-used-by-the-application"></a><span data-ttu-id="54439-169">アプリケーションが使用するフォルダーを作成するには</span><span class="sxs-lookup"><span data-stu-id="54439-169">To create the folders used by the application</span></span>  

1.  <span data-ttu-id="54439-170">**C:\\** ドライブは、存在しない場合、"temp"という名前のフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="54439-170">On your **C:\\** drive, create a folder named "temp" if it does not already exist.</span></span>  

2.  <span data-ttu-id="54439-171">で、 **C:\temp**ディレクトリ、"Pickup"および"Dropit"という名前のフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="54439-171">Under the **C:\temp** directory, create folders named "Pickup" and "Dropit".</span></span>  

### <a name="building-and-deploying-this-sample"></a><span data-ttu-id="54439-172">サンプルのビルドと展開</span><span class="sxs-lookup"><span data-stu-id="54439-172">Building and deploying this sample</span></span>  

1.  <span data-ttu-id="54439-173">コマンド ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="54439-173">In a command window, navigate to the following folder:</span></span>  

     `<Samples Path>\AdaptersUsage\MQSeriesAdapter\MQSCorrelationSetOrchestration`  

2.  <span data-ttu-id="54439-174">ファイルは、次の操作を実行します。 Setup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="54439-174">Run the file Setup.bat, which performs the following actions:</span></span>  

    1.  <span data-ttu-id="54439-175">プロジェクトの厳密な名前のキー ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="54439-175">Creates a strong name key for the project.</span></span>  

    2.  <span data-ttu-id="54439-176">オーケストレーション プロジェクトをコンパイルして展開します。</span><span class="sxs-lookup"><span data-stu-id="54439-176">Compiles and deploys the orchestration project.</span></span>  

    3.  <span data-ttu-id="54439-177">ファイル アダプター用の送信ポートと受信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="54439-177">Creates a send port and a receive port with the File adapter.</span></span>  

### <a name="bind-and-start-the-orchestration"></a><span data-ttu-id="54439-178">オーケストレーションのバインドと開始</span><span class="sxs-lookup"><span data-stu-id="54439-178">Bind and start the Orchestration</span></span>  

1.  <span data-ttu-id="54439-179">BizTalk Server 管理コンソールで、**オーケストレーション**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="54439-179">In the BizTalk Server Administration console, expand the **Orchestrations** folder.</span></span>  

2.  <span data-ttu-id="54439-180">詳細ペインで右クリックし、 **MQSCorrelationSetOrchestration**オーケストレーション、およびクリック**バインド**します。</span><span class="sxs-lookup"><span data-stu-id="54439-180">In the details pane, right-click the **MQSCorrelationSetOrchestration** orchestration, and then click **Bind**.</span></span>  

3.  <span data-ttu-id="54439-181">オーケストレーション ポートを、以下の送信ポートおよび受信場所にバインドします。</span><span class="sxs-lookup"><span data-stu-id="54439-181">Bind the orchestration ports to the following send ports and receive locations:</span></span>  

    |<span data-ttu-id="54439-182">**オーケストレーション ポート**</span><span class="sxs-lookup"><span data-stu-id="54439-182">**Orchestration Port**</span></span>|<span data-ttu-id="54439-183">**メッセージ ポート/受信場所**</span><span class="sxs-lookup"><span data-stu-id="54439-183">**Messaging Port / Receive Location**</span></span>|  
    |----------------------------|--------------------------------------------|  
    |<span data-ttu-id="54439-184">FileReceivePort</span><span class="sxs-lookup"><span data-stu-id="54439-184">FileReceivePort</span></span>|<span data-ttu-id="54439-185">MQSCorrelationSetOrchestration.FileReceivePort</span><span class="sxs-lookup"><span data-stu-id="54439-185">MQSCorrelationSetOrchestration.FileReceivePort</span></span>|  
    |<span data-ttu-id="54439-186">MQSeriesResponseReceivePort</span><span class="sxs-lookup"><span data-stu-id="54439-186">MQSeriesResponseReceivePort</span></span>|<span data-ttu-id="54439-187">MQIn</span><span class="sxs-lookup"><span data-stu-id="54439-187">MQIn</span></span>|  
    |<span data-ttu-id="54439-188">MQSeriesRequestSendPort</span><span class="sxs-lookup"><span data-stu-id="54439-188">MQSeriesRequestSendPort</span></span>|<span data-ttu-id="54439-189">MQOut</span><span class="sxs-lookup"><span data-stu-id="54439-189">MQOut</span></span>|  
    |<span data-ttu-id="54439-190">FileSendPort</span><span class="sxs-lookup"><span data-stu-id="54439-190">FileSendPort</span></span>|<span data-ttu-id="54439-191">MQSCorrelationSetOrchestration.FileSendPort</span><span class="sxs-lookup"><span data-stu-id="54439-191">MQSCorrelationSetOrchestration.FileSendPort</span></span>|  

4.  <span data-ttu-id="54439-192">クリックして**ホスト**します。</span><span class="sxs-lookup"><span data-stu-id="54439-192">Click **Host**.</span></span>  

5.  <span data-ttu-id="54439-193">**ホスト**ボックスで、 **BizTalkServerApplication**、 をクリック**OK**します。</span><span class="sxs-lookup"><span data-stu-id="54439-193">In the **Host** box, select **BizTalkServerApplication**, and click **OK**.</span></span>  

6.  <span data-ttu-id="54439-194">**送信ポート**、右クリック**mqscorrelationsetorchestration.filesendport**、し、**開始**します。</span><span class="sxs-lookup"><span data-stu-id="54439-194">In **Send Ports**, right-click **MQSCorrelationSetOrchestration.FileSendPort**, and then select **Start**.</span></span>  

7.  <span data-ttu-id="54439-195">**受信場所**を右クリックして **[mqscorrelationsetorchestration.filereceiveport]** 選び**を有効にする**します。</span><span class="sxs-lookup"><span data-stu-id="54439-195">In **Receive Locations**, right-click **MQSCorrelationSetOrchestration.FileReceivePort** and then select **Enable**.</span></span>  

8.  <span data-ttu-id="54439-196">オーケストレーションを右クリックし、をクリックして**開始**します。</span><span class="sxs-lookup"><span data-stu-id="54439-196">Right-click the orchestration and click **Start**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="54439-197">オーケストレーションを開始すると、オーケストレーションの参加も自動的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="54439-197">Starting the orchestration also automatically enlists the orchestration.</span></span>  

### <a name="to-test-the-application"></a><span data-ttu-id="54439-198">アプリケーションをテストするには</span><span class="sxs-lookup"><span data-stu-id="54439-198">To test the application</span></span>  

1.  <span data-ttu-id="54439-199">ファイルを配置、 **C:\Temp\Pickup**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="54439-199">Put a file into the **C:\Temp\Pickup** folder.</span></span>  

2.  <span data-ttu-id="54439-200">内のファイルを調べて、 **C:\Temp\Dropit**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="54439-200">Examine the file in the **C:\Temp\Dropit** folder.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="54439-201">無効にした場合、 **MQIn**受信場所は、WebSphere MQ エクスプ ローラーでメッセージを確認し、メッセージと関連付け識別子が設定されていることができます。</span><span class="sxs-lookup"><span data-stu-id="54439-201">If you disable the **MQIn** receive location, you can examine the message in WebSphere MQ Explorer and see that the message and correlation identifiers are set.</span></span> <span data-ttu-id="54439-202">これを行うには、起動、 **WebSphere MQ エクスプ ローラー**にメッセージを調べ、 **MQCorrelation**キュー。</span><span class="sxs-lookup"><span data-stu-id="54439-202">To do this, launch the **WebSphere MQ Explorer** and examine the message placed in the **MQCorrelation** queue.</span></span> <span data-ttu-id="54439-203">メッセージ識別子と関連付け識別子が表示されます、**識別子**のタブ、**メッセージ プロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="54439-203">The message and correlation identifiers are displayed on the **Identifiers** tab of the **Message properties** dialog box.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="54439-204">実稼働環境では、MQSeries キューに送信されるメッセージごとに一意の ID を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="54439-204">In a production scenario, you will want to assign a unique ID for each message that is sent to the MQSeries queue.</span></span> <span data-ttu-id="54439-205">これを行うには、オーケストレーションの式図形を変更します。</span><span class="sxs-lookup"><span data-stu-id="54439-205">This can be done by modifying the expression shape in the orchestration.</span></span> <span data-ttu-id="54439-206">次の行を変更してこれらのプロパティを一意の 24 バイト ID に設定します。</span><span class="sxs-lookup"><span data-stu-id="54439-206">Change the following lines to set these properties to a unique 24 byte ID:</span></span>  
    >   
    >  <span data-ttu-id="54439-207">MQSeriesRequestSendMessageModified(MQSeries.MQMD_MsgId) = "111213141516171819202122232425262728293031323334";</span><span class="sxs-lookup"><span data-stu-id="54439-207">MQSeriesRequestSendMessageModified(MQSeries.MQMD_MsgId) = "111213141516171819202122232425262728293031323334";</span></span>  
    >   
    >  <span data-ttu-id="54439-208">MQSeriesRequestSendMessageModified(MQSeries.MQMD_CorrelId) = "111213141516171819202122232425262728293031323334";</span><span class="sxs-lookup"><span data-stu-id="54439-208">MQSeriesRequestSendMessageModified(MQSeries.MQMD_CorrelId) = "111213141516171819202122232425262728293031323334";</span></span>  
    >   
    >  <span data-ttu-id="54439-209">これらのプロパティは、セクションを参照してください。 一意の 24 バイト ID を設定する場合**MQSeries に送信されるメッセージの一意の 24 バイト ID を作成する**します。</span><span class="sxs-lookup"><span data-stu-id="54439-209">If you want to set a unique 24 byte ID for these properties see the section **To create a unique 24 byte ID for messages sent to MQSeries**.</span></span>  

### <a name="to-create-a-unique-24-byte-id-for-messages-sent-to-mqseries"></a><span data-ttu-id="54439-210">MQSeries に送信されるメッセージに一意の 24 バイト ID を作成するには</span><span class="sxs-lookup"><span data-stu-id="54439-210">To create a unique 24 byte ID for messages sent to MQSeries</span></span>  

1. <span data-ttu-id="54439-211">新しい C# クラス ライブラリ プロジェクトを [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で作成します。</span><span class="sxs-lookup"><span data-stu-id="54439-211">Create a new C# class library project in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  

2. <span data-ttu-id="54439-212">クラスの .cs ファイルに次のコードを貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="54439-212">Paste the following code into the .cs file for the class:</span></span>  

   ```  
   using System;  
   using System.Collections.Generic;  
   using System.Text;  
   using System.Security.Cryptography;  

   namespace MQId  
   {[Serializable]  
       public class GetId  
       {  
           RNGCryptoServiceProvider randomCryptoString = new RNGCryptoServiceProvider();  

           public string getGuidstr()  
           {  
               byte[] newGuid = GetRandomData(24);  
               return ConvertToHex(newGuid);  
           }  

           private byte[] GetRandomData(int keySize)  
           {  
               byte[] randomData = new byte[keySize];  
               randomCryptoString.GetBytes(randomData);  
               return randomData;  
           }  

           private string ConvertToHex(byte[] key)  
           {  
               StringBuilder hexString = new StringBuilder();  
               for (int i = 0; i < key.Length; ++i)  
               {  
                   hexString.Append(String.Format("{0:X2}", key[i]));  
               }  
               return hexString.ToString();  
           }  
       }  
   }  
   ```  

3. <span data-ttu-id="54439-213">指定、**既定の名前空間**の**MQId**と**アセンブリ名**の**GetId**プロジェクトのプロパティで**アプリケーション**ページ。</span><span class="sxs-lookup"><span data-stu-id="54439-213">Specify a **Default namespace** of **MQId** and an **Assembly name** of **GetId** on the project properties **Application** page.</span></span>  

4. <span data-ttu-id="54439-214">プロジェクトのプロパティでアセンブリに署名する厳密な名前キー ファイルを指定**署名**ページし、プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="54439-214">Specify a strong name key file to sign the assembly on the project properties **Signing** page and then build the project.</span></span>  

5. <span data-ttu-id="54439-215">グローバル アセンブリ キャッシュ ツール (gacutil.exe) を使用して、コンパイルされたアセンブリを GAC に読み込むに (gacutil/i \<*コンパイル済み dll ファイルの名前*\>)。</span><span class="sxs-lookup"><span data-stu-id="54439-215">Use the global assembly cache tool (gacutil.exe) to load the compiled assembly into the GAC (gacutil /i \<*name of compiled dll file*\>).</span></span>  

6. <span data-ttu-id="54439-216">このサンプルの BizTalk プロジェクトに GetId アセンブリへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="54439-216">Add a reference to the GetId assembly in the BizTalk project for this sample.</span></span>  

7. <span data-ttu-id="54439-217">このサンプルで使用するオーケストレーションに 2 つの変数を追加します。</span><span class="sxs-lookup"><span data-stu-id="54439-217">Add two variables to the orchestration used in this sample:</span></span>  


   | <span data-ttu-id="54439-218">変数名 (ID)</span><span class="sxs-lookup"><span data-stu-id="54439-218">Variable name (Identifier)</span></span> |     <span data-ttu-id="54439-219">型</span><span class="sxs-lookup"><span data-stu-id="54439-219">Type</span></span>      |
   |----------------------------|---------------|
   |           <span data-ttu-id="54439-220">GetId</span><span class="sxs-lookup"><span data-stu-id="54439-220">GetId</span></span>            |  <span data-ttu-id="54439-221">MQId.GetId</span><span class="sxs-lookup"><span data-stu-id="54439-221">MQId.GetId</span></span>   |
   |          <span data-ttu-id="54439-222">strGuid</span><span class="sxs-lookup"><span data-stu-id="54439-222">strGuid</span></span>           | <span data-ttu-id="54439-223">System.String</span><span class="sxs-lookup"><span data-stu-id="54439-223">System.String</span></span> |


8. <span data-ttu-id="54439-224">このサンプルのオーケストレーションに使用する式図形に次のコードを貼り付けます。このコードで既存のコードを上書きします。</span><span class="sxs-lookup"><span data-stu-id="54439-224">Paste the following code into the expression shape used in the orchestration for this sample, this code should overwrite the existing code:</span></span>  

   ```  
   GetId = new MQId.GetId();  
   strGuid = GetId.getGuidstr();  
   MQSeriesRequestSendMessageModified = MQSeriesRequestSendMessage;  
   MQSeriesRequestSendMessageModified(MQSeries.MQMD_MsgId) = strGuid;  
   MQSeriesRequestSendMessageModified(MQSeries.MQMD_CorrelId) = strGuid;  
   ```  

9. <span data-ttu-id="54439-225">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールのオーケストレーションが展開済みの場合、停止して削除します。</span><span class="sxs-lookup"><span data-stu-id="54439-225">Stop and remove the orchestration in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console if it is already deployed.</span></span> <span data-ttu-id="54439-226">セクションの手順に従います**のビルドとこのサンプルをデプロイ**、**のバインドと開始オーケストレーション**と**アプリケーションをテストする**します。</span><span class="sxs-lookup"><span data-stu-id="54439-226">Then follow the steps in the sections **Building and deploying this sample**, **Bind and start the Orchestration** and **To test the application**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="54439-227">この方法で MQSeries に送信されるメッセージに一意の 24 バイト ID を作成しても、送信されるすべてのメッセージに対して一意の ID が 100% 保証されるわけではありません。ただし、メッセージ ID が重複する可能性は非常に低くなります。</span><span class="sxs-lookup"><span data-stu-id="54439-227">Use of this method to create a unique 24 byte ID for messages sent to MQSeries does not 100% guarantee unique IDs for all messages sent but the probability of duplicate message IDs is very low.</span></span> <span data-ttu-id="54439-228">ビジネス要件により、重複するメッセージ ID がないことを 100% 保証する必要がある場合、別のカスタム コードを使用してこの機能を確保する必要があります。</span><span class="sxs-lookup"><span data-stu-id="54439-228">If business needs require a 100% guarantee that no message IDs are duplicated then you will need to employ different custom code to ensure this functionality.</span></span>  

## <a name="classes-or-methods-used-in-this-sample"></a><span data-ttu-id="54439-229">このサンプルで使用されるクラスまたはメソッド</span><span class="sxs-lookup"><span data-stu-id="54439-229">Classes or Methods Used in This Sample</span></span>  
 <span data-ttu-id="54439-230">このサンプルでは、クラスやメソッドを明示的に使用しません。</span><span class="sxs-lookup"><span data-stu-id="54439-230">This sample does not make explicit use of any classes or methods.</span></span>  

## <a name="see-also"></a><span data-ttu-id="54439-231">参照</span><span class="sxs-lookup"><span data-stu-id="54439-231">See Also</span></span>  
 <span data-ttu-id="54439-232">[要求/応答を使用してメッセージの関連付け](../core/correlating-messages-using-request-reply.md) </span><span class="sxs-lookup"><span data-stu-id="54439-232">[Correlating Messages Using Request-Reply](../core/correlating-messages-using-request-reply.md) </span></span>  
 [<span data-ttu-id="54439-233">MQSeries アダプタ サンプル</span><span class="sxs-lookup"><span data-stu-id="54439-233">MQSeries Adapter Samples</span></span>](../core/mqseries-adapter-samples.md)