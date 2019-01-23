---
title: チュートリアル :MQSeries アダプターを使用する BizTalk アプリケーションの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IBM WebSphere MQ queues
- MQSeries adapters, tutorial
- MQSeries adapters, testing
- tutorials, MQSeries adapters
- MQSeries adapters, IBM WebSphere MQ queues
- testing, MQSeries adapters
- MQSeries adapters, queues
- configuring [MQSeries adapters], tutorial
ms.assetid: e9e169e4-d41c-4e5d-b165-7bd36b481f24
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d882ee7134861496266b0d18bb288e39e05bad29
ms.sourcegitcommit: 2d39bcd10a22c5945d97a03988ccdc62f6fb3c93
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2019
ms.locfileid: "54443391"
---
# <a name="walkthrough-creating-a-biztalk-application-that-uses-the-mqseries-adapter"></a><span data-ttu-id="839bf-102">チュートリアル :MQSeries アダプターを使用する BizTalk アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="839bf-102">Walkthrough: Creating a BizTalk Application That Uses the MQSeries Adapter</span></span>
<span data-ttu-id="839bf-103">このセクションでは、MQSeries アダプターを使用する簡単な Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリケーションを作成する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="839bf-103">This section takes you through creating a simple Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application that uses the MQSeries adapter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="839bf-104">このアプリケーションは、Windows プラットフォームのサーバー コンポーネントである IBM WebSphere MQ が BizTalk Server と同じコンピューターにインストールされていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="839bf-104">The application assumes that you have installed the IBM WebSphere MQ, server component for Windows platforms on the same computer as BizTalk Server.</span></span> <span data-ttu-id="839bf-105">また、送信ポートまたは受信場所をまだ作成していないことも前提としています。</span><span class="sxs-lookup"><span data-stu-id="839bf-105">It also assumes that you have not yet created any send ports or receive locations.</span></span> <span data-ttu-id="839bf-106">既存の送信ポートまたは受信場所がある場合、手順を実行する際に適切な名前に置き換えてください。</span><span class="sxs-lookup"><span data-stu-id="839bf-106">If you have existing send ports or receive locations, substitute appropriate names when you work through the steps.</span></span>  
  
 <span data-ttu-id="839bf-107">このアプリケーションは、受信場所と送信ポートのみを使用する、コンテンツベースの単純なルーティング アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="839bf-107">The application is a simple content-based routing application using only a receive location and a send port.</span></span> <span data-ttu-id="839bf-108">受信場所では、IBM WebSphere MQ キューから読み取りを行います。</span><span class="sxs-lookup"><span data-stu-id="839bf-108">The receive location reads from an IBM WebSphere MQ queue.</span></span> <span data-ttu-id="839bf-109">送信ポートは、受信場所からメッセージを取得して、そのメッセージを別の IBM WebSphere MQ キューに送信します。</span><span class="sxs-lookup"><span data-stu-id="839bf-109">The send port takes the message from the receive location and sends it to a different IBM WebSphere MQ queue.</span></span>  
  
 <span data-ttu-id="839bf-110">このアプリケーションを作成するには、IBM WebSphere MQ キューの作成、BizTalk Server の受信場所と送信ポートの設定、送信ポートの開始と受信場所の有効化、およびキューへのテスト メッセージの送信を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="839bf-110">To create the application, you have to create the IBM WebSphere MQ queues, set up the BizTalk Server receive location and send port, start the send port and enable the receive location, and put a test message in the queue.</span></span>  
  
 <span data-ttu-id="839bf-111">IBM WebSphere MQ のインストールに必要なアクセス許可を持っている場合は、アダプターのダイアログ ボックスを使用して IBM WebSphere MQ キューを作成できるため、次の手順を省略できます。</span><span class="sxs-lookup"><span data-stu-id="839bf-111">If you have the required permissions to the IBM WebSphere MQ installation, you can create the IBM WebSphere MQ queues through the adapter dialog boxes, and can skip the next procedure.</span></span> <span data-ttu-id="839bf-112">このようなアクセス許可を持っていない場合は、Windows プラットフォームのクライアント コンポーネントである IBM WebSphere MQ エクスプローラーを使用してキューを作成できます。</span><span class="sxs-lookup"><span data-stu-id="839bf-112">If you do not have such access, you can create the queues using the IBM WebSphere MQ, client components for Windows platforms Explorer.</span></span> <span data-ttu-id="839bf-113">IBM WebSphere MQ エクスプローラー スナップインを使用してキューを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="839bf-113">To create the queues through the IBM WebSphere MQ Explorer snap-in, perform the following procedure.</span></span>  
  
## <a name="to-create-the-ibm-websphere-mq-queues-through-the-ibm-websphere-mq-explorer"></a><span data-ttu-id="839bf-114">IBM WebSphere MQ エクスプローラーを使用して IBM WebSphere MQ キューを作成するには</span><span class="sxs-lookup"><span data-stu-id="839bf-114">To create the IBM WebSphere MQ queues through the IBM WebSphere MQ Explorer</span></span>  
 <span data-ttu-id="839bf-115">IBM WebSphere MQ エクスプローラーを使用して IBM WebSphere MQ キューを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="839bf-115">Follow these steps to create the IBM WebSphere MQ queues through the IBM WebSphere MQ Explorer:</span></span>  
  
1. <span data-ttu-id="839bf-116">クリックして**開始**、 をポイント**プログラム**、 をポイント**IBM WebSphere MQ**、順にクリックします**WebSphere MQ エクスプ ローラー**します。</span><span class="sxs-lookup"><span data-stu-id="839bf-116">Click **Start**, point to **Programs**, point to **IBM WebSphere MQ**, and then click **WebSphere MQ Explorer**.</span></span>  
  
2. <span data-ttu-id="839bf-117">ダブルクリック**キュー マネージャー**、し、既定のキュー マネージャーをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="839bf-117">Double-click **Queue Managers**, and then double-click the default queue manager.</span></span> <span data-ttu-id="839bf-118">通常、既定のキュー マネージャーの名前**qm _**_< machine_name >_ 場所*machine_name*コンピューターの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="839bf-118">The default queue manager is typically named **QM_**_<machine_name>_ where *machine_name* is the name of your computer.</span></span>  
  
3. <span data-ttu-id="839bf-119">右クリック**キュー**、 をポイント**新規**、 をクリックし、**ローカル キュー**します。</span><span class="sxs-lookup"><span data-stu-id="839bf-119">Right-click **Queues**, point to **New**, and then click **Local Queue**.</span></span>  
  
4. <span data-ttu-id="839bf-120">**ローカル キューの作成** ダイアログ ボックスで**キュー名**、型**BTStoMQS**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="839bf-120">In **Create Local Queue** dialog box, in **Queue Name**, type **BTStoMQS**, and then click **OK**.</span></span>  
  
5. <span data-ttu-id="839bf-121">右クリック**キュー**、 をポイント**新規**、 をクリックし、**ローカル キュー**します。</span><span class="sxs-lookup"><span data-stu-id="839bf-121">Right-click **Queues**, point to **New**, and then click **Local Queue**.</span></span>  
  
6. <span data-ttu-id="839bf-122">**ローカル キューの作成** ダイアログ ボックスで**キュー名**、型**MQStoBTS**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="839bf-122">In **Create Local Queue** dialog box, in **Queue Name**, type **MQStoBTS**, and then click **OK**.</span></span>  
  
   <span data-ttu-id="839bf-123">次の手順では、受信場所と送信ポートの作成、および送信ポートの開始と受信場所の有効化を行います。</span><span class="sxs-lookup"><span data-stu-id="839bf-123">The next steps create the receive location and the send port, and start the send port and enable the receive location.</span></span> <span data-ttu-id="839bf-124">IBM WebSphere MQ キューも作成します。</span><span class="sxs-lookup"><span data-stu-id="839bf-124">They also create the IBM WebSphere MQ queues.</span></span>  
  
## <a name="to-create-the-receive-location-and-the-mqseries-queue"></a><span data-ttu-id="839bf-125">受信場所と MQSeries キューを作成するには</span><span class="sxs-lookup"><span data-stu-id="839bf-125">To create the receive location and the MQSeries queue</span></span>  
 <span data-ttu-id="839bf-126">受信場所と MQSeries キューを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="839bf-126">Follow these steps to create the receive location and the MQSeries queue:</span></span>  
  
1.  <span data-ttu-id="839bf-127">BizTalk Server 管理コンソールで  **BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、既定値を順に展開アプリケーション (**BizTalk アプリケーション 1**既定)。</span><span class="sxs-lookup"><span data-stu-id="839bf-127">In the BizTalk Server Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the default application (**BizTalk Application 1** by default).</span></span>  
  
2.  <span data-ttu-id="839bf-128">右クリックし、**受信ポート**ノード、をクリックして**新規**を選択し、**一方向のポート**します。</span><span class="sxs-lookup"><span data-stu-id="839bf-128">Right-click the **Receive Ports** node, click **New**, and select **One-Way Port**.</span></span>  
  
3.  <span data-ttu-id="839bf-129">**受信ポートのプロパティ** ダイアログ ボックスで、**名前**ボックスに「 **MQStoBTS**します。</span><span class="sxs-lookup"><span data-stu-id="839bf-129">In the **Receive Port Properties** dialog box, in the **Name** box, type **MQStoBTS**.</span></span>  
  
4.  <span data-ttu-id="839bf-130">左側のウィンドウで次のようにクリックします。**受信場所**、右側のウィンドウで次のようにクリックします。**新規**します。</span><span class="sxs-lookup"><span data-stu-id="839bf-130">In the left pane, click **Receive Locations**, and in the right pane, click **New**.</span></span>  
  
5.  <span data-ttu-id="839bf-131">**受信場所のプロパティ** ダイアログ ボックスで、**名前**ボックスに「 **MQStoBTS**します。</span><span class="sxs-lookup"><span data-stu-id="839bf-131">In the **Receive Location Properties** dialog box, in the **Name** box, type **MQStoBTS**.</span></span>  
  
6.  <span data-ttu-id="839bf-132">選択**MQSeries**横にドロップダウン リストからリスト、**型**オプション。</span><span class="sxs-lookup"><span data-stu-id="839bf-132">Select **MQSeries** from the drop-down list next to the **Type** option.</span></span>  
  
7.  <span data-ttu-id="839bf-133">**トランスポート**セクションで、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="839bf-133">In the **Transport** section, click **Configure**.</span></span>  
  
8.  <span data-ttu-id="839bf-134">**MQSeries トランスポートのプロパティ** ダイアログ ボックスで、**のポーリング間隔**ボックスに「 **1**します。</span><span class="sxs-lookup"><span data-stu-id="839bf-134">In the **MQSeries Transport Properties** dialog box, in the **Polling Interval** box, type **1**.</span></span>  
  
9. <span data-ttu-id="839bf-135">**キュー定義**ボックスで、省略記号ボタンをクリックします (**.**) ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="839bf-135">In the **Queue Definition** box, click the ellipsis (**…**) button.</span></span>  
  
10. <span data-ttu-id="839bf-136">**キュー定義** ダイアログ ボックスで、**サーバー名**ボックスに、コンピューター名を入力します。</span><span class="sxs-lookup"><span data-stu-id="839bf-136">In the **Queue Definition** dialog box, in the **Server Name** box, type your computer name.</span></span>  
  
11. <span data-ttu-id="839bf-137">**キュー マネージャー**ボックスで、既定のキュー マネージャーを選択します。</span><span class="sxs-lookup"><span data-stu-id="839bf-137">In the **Queue Manager** box, select the default queue manager.</span></span>  
  
12. <span data-ttu-id="839bf-138">**キュー**ボックスに「 **MQStoBTS**、 をクリックし、**エクスポート**します。</span><span class="sxs-lookup"><span data-stu-id="839bf-138">In the **Queue** box, type **MQStoBTS**, and then click **Export**.</span></span>  
  
13. <span data-ttu-id="839bf-139">**エクスポート**ダイアログ ボックスで、をクリックして**Create Queue**、順にクリックします**ok**と**ok**に戻るにもう一度、**受信場所のプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="839bf-139">In the **Export** dialog box, click **Create Queue**,and then click **OK** and **OK** again to return to the **Receive Location Properties** dialog box.</span></span>  
  
14. <span data-ttu-id="839bf-140">**受信ハンドラー**ボックスで、 **BizTalkServerApplication**します。</span><span class="sxs-lookup"><span data-stu-id="839bf-140">In the **Receive Handler** box, select **BizTalkServerApplication**.</span></span>  
  
15. <span data-ttu-id="839bf-141">**受信パイプライン**ボックスで、 **PassThruReceive**します。</span><span class="sxs-lookup"><span data-stu-id="839bf-141">In the **Receive Pipeline** box, select **PassThruReceive**.</span></span>  
  
16. <span data-ttu-id="839bf-142">をクリックして**OK**変更を適用します。</span><span class="sxs-lookup"><span data-stu-id="839bf-142">Click **OK** to apply changes.</span></span>  
  
## <a name="to-create-the-send-port-and-the-mqseries-queue"></a><span data-ttu-id="839bf-143">送信ポートと MQSeries キューを作成するには</span><span class="sxs-lookup"><span data-stu-id="839bf-143">To create the send port and the MQSeries queue</span></span>  
 <span data-ttu-id="839bf-144">送信ポートと MQSeries キューを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="839bf-144">Follow these steps to create the send port and the MQSeries queue:</span></span>  
  
1.  <span data-ttu-id="839bf-145">右クリック**送信ポート**、 をクリックして**新規**、選び**静的な一方向送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="839bf-145">Right-click **Send Ports**, click **New**, and select **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="839bf-146">**送信ポートのプロパティ** ダイアログ ボックスで、**名前**ボックスに「 **BTStoMQS します。**</span><span class="sxs-lookup"><span data-stu-id="839bf-146">In the **Send Port Properties** dialog box, in the **Name** box, type **BTStoMQS.**</span></span>  
  
3.  <span data-ttu-id="839bf-147">選択**MQSeries**横にドロップダウン リストからリスト、**型**オプション。</span><span class="sxs-lookup"><span data-stu-id="839bf-147">Select **MQSeries** from the drop-down list next to the **Type** option.</span></span>  
  
4.  <span data-ttu-id="839bf-148">**トランスポート**セクションで、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="839bf-148">In the **Transport** section, click **Configure**.</span></span>  
  
5.  <span data-ttu-id="839bf-149">**MQSeries トランスポートのプロパティ** ダイアログ ボックスで、**キュー定義**ボックスで、省略記号ボタンをクリックします (**.**) ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="839bf-149">In the **MQSeries Transport Properties** dialog box, in the **Queue Definition** box, click the ellipsis (**…**) button.</span></span>  
  
6.  <span data-ttu-id="839bf-150">**キュー定義** ダイアログ ボックスで、**サーバー名**ボックスに、コンピューター名を入力します。</span><span class="sxs-lookup"><span data-stu-id="839bf-150">In the **Queue Definition** dialog box, in the **Server Name** box, type your computer name.</span></span>  
  
7.  <span data-ttu-id="839bf-151">**キュー マネージャー**ボックスで、既定のキュー マネージャーを選択します。</span><span class="sxs-lookup"><span data-stu-id="839bf-151">In the **Queue Manager** box, select the default queue manager.</span></span>  
  
8.  <span data-ttu-id="839bf-152">**キュー**ボックスに「 **BTStoMQS**、 をクリックし、**エクスポート**します。</span><span class="sxs-lookup"><span data-stu-id="839bf-152">In the **Queue** box, type **BTStoMQS**, and then click **Export**.</span></span>  
  
9. <span data-ttu-id="839bf-153">**エクスポート**ダイアログ ボックスで、をクリックして**キューの作成**、順にクリックします**ok**と**ok**に戻るにもう一度、**送信ポートプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="839bf-153">In the **Export** dialog box, click **Create Queue**, and then click **OK** and **OK** again to return to the **Send Port Properties** dialog box.</span></span>  
  
10. <span data-ttu-id="839bf-154">**送信パイプライン**ボックスで、 **PassThruTransmit**します。</span><span class="sxs-lookup"><span data-stu-id="839bf-154">In the **Send Pipeline** box, select **PassThruTransmit**.</span></span>  
  
11. <span data-ttu-id="839bf-155">クリックして選択**フィルター**左側のウィンドウでし、右側のウィンドウでフィルター オプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="839bf-155">Click to select **Filters** in the left pane, and then configure filter options in the right pane.</span></span>  
  
12. <span data-ttu-id="839bf-156">**プロパティ**ドロップダウン リストで、 **BTS します。ReceivePortName**します。</span><span class="sxs-lookup"><span data-stu-id="839bf-156">In the **Property** drop-down list, select **BTS.ReceivePortName**.</span></span>  
  
13. <span data-ttu-id="839bf-157">**値**ボックスに「 **MQStoBTS**します。</span><span class="sxs-lookup"><span data-stu-id="839bf-157">In the **Value** box, type **MQStoBTS**.</span></span>  
  
14. <span data-ttu-id="839bf-158">をクリックして**OK**変更を適用します。</span><span class="sxs-lookup"><span data-stu-id="839bf-158">Click **OK** to apply changes.</span></span>  
  
## <a name="to-enable-the-receive-location-and-start-the-send-port"></a><span data-ttu-id="839bf-159">受信場所を有効にして送信ポートを開始するには</span><span class="sxs-lookup"><span data-stu-id="839bf-159">To enable the receive location and start the send port</span></span>  
 <span data-ttu-id="839bf-160">受信場所を有効にし、送信ポートを開始するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="839bf-160">Follow these steps to enable the receive location and start the send port:</span></span>  
  
1. <span data-ttu-id="839bf-161">右クリックし、 **MQStoBTS**受信場所をクリックして**を有効にする**します。</span><span class="sxs-lookup"><span data-stu-id="839bf-161">Right-click the **MQStoBTS** receive location, and then click **Enable**.</span></span>  
  
2. <span data-ttu-id="839bf-162">右クリックし、 **BTStoMQS**送信ポート、およびクリックして**開始**します。</span><span class="sxs-lookup"><span data-stu-id="839bf-162">Right-click the **BTStoMQS** send port, and then click **Start**.</span></span>  
  
   <span data-ttu-id="839bf-163">次の手順では、テスト メッセージを受信キューに送信することにより、アプリケーションをテストします。</span><span class="sxs-lookup"><span data-stu-id="839bf-163">The next step is to test the application by sending a test message to the receive queue.</span></span>  
  
## <a name="to-test-the-application"></a><span data-ttu-id="839bf-164">アプリケーションをテストするには</span><span class="sxs-lookup"><span data-stu-id="839bf-164">To test the application</span></span>  
 <span data-ttu-id="839bf-165">アプリケーションをテストするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="839bf-165">Follow these steps to test the application:</span></span>  
  
1. <span data-ttu-id="839bf-166">クリックして**開始**、 をポイント**プログラム**、 をポイント**IBM WebSphere MQ**、順にクリックします**WebSphere MQ エクスプ ローラー**します。</span><span class="sxs-lookup"><span data-stu-id="839bf-166">Click **Start**, point to **Programs**, point to **IBM WebSphere MQ**, and then click **WebSphere MQ Explorer**.</span></span>  
  
2. <span data-ttu-id="839bf-167">右クリック**MQStoBTS**、 をクリックし、 **Put のテスト メッセージ**します。</span><span class="sxs-lookup"><span data-stu-id="839bf-167">Right-click **MQStoBTS**, and then click **Put Test Message**.</span></span>  
  
3. <span data-ttu-id="839bf-168">**メッセージ データ**ボックスに、テスト メッセージを入力します。</span><span class="sxs-lookup"><span data-stu-id="839bf-168">In the **Message Data** box, type a test message.</span></span> <span data-ttu-id="839bf-169">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="839bf-169">Click **OK**.</span></span>  
  
   <span data-ttu-id="839bf-170">データを入力した後、**現在の深さ**の**MQStoBTS**キューが 1 つ (1)。</span><span class="sxs-lookup"><span data-stu-id="839bf-170">After you enter the data, the **Current Depth** for the **MQStoBTS** queue is one (1).</span></span> <span data-ttu-id="839bf-171">カウントがゼロ (0) に戻る、アプリケーションがメッセージを処理するとき、**現在の深さ**の**BTStoMQS**が 1 つ (1)。</span><span class="sxs-lookup"><span data-stu-id="839bf-171">When the application processes the message, the count returns to zero (0) and the **Current Depth** for **BTStoMQS** becomes one (1).</span></span> <span data-ttu-id="839bf-172">また、メッセージの内容を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="839bf-172">You can also view the content of the message.</span></span>  
  
## <a name="to-view-the-message"></a><span data-ttu-id="839bf-173">メッセージを表示するには</span><span class="sxs-lookup"><span data-stu-id="839bf-173">To view the message</span></span>  
 <span data-ttu-id="839bf-174">メッセージを表示するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="839bf-174">Follow these steps to view the message:</span></span>  
  
1.  <span data-ttu-id="839bf-175">ダブルクリックして、 **BTStoMQS**キュー。</span><span class="sxs-lookup"><span data-stu-id="839bf-175">Double-click the **BTStoMQS** queue.</span></span>  
  
2.  <span data-ttu-id="839bf-176">メッセージをダブルクリックし、、**データ**シート。</span><span class="sxs-lookup"><span data-stu-id="839bf-176">Double-click the message, and then select the **Data** sheet.</span></span> <span data-ttu-id="839bf-177">内のメッセージのテキストを表示することができます、**メッセージ データ**ボックス。</span><span class="sxs-lookup"><span data-stu-id="839bf-177">You can view the text of the message in the **Message Data** box.</span></span>  
  
3.  <span data-ttu-id="839bf-178">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="839bf-178">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="839bf-179">参照</span><span class="sxs-lookup"><span data-stu-id="839bf-179">See Also</span></span>  
 <span data-ttu-id="839bf-180">[MQSeries アダプターとは何ですか。](../core/what-is-the-mqseries-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="839bf-180">[What Is the MQSeries Adapter?](../core/what-is-the-mqseries-adapter.md) </span></span>  
 [<span data-ttu-id="839bf-181">MQSeries アダプターのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="839bf-181">MQSeries Adapter Architecture</span></span>](../core/mqseries-adapter-architecture.md)
