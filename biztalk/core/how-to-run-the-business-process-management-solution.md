---
title: "ビジネス プロセス管理ソリューションを実行する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- process management solution tutorial, validating
- process management solution tutorial, submitting orders
- process management solution tutorial, stopping orders
- process management solution tutorial, updating orders
ms.assetid: cb77651e-e16c-49dc-9f8a-88584cd68a8b
caps.latest.revision: "25"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3997fb18e7498ab2bc5f8c77b53740fb87ab6f93
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-run-the-business-process-management-solution"></a><span data-ttu-id="59480-102">ビジネス プロセス管理ソリューションの実行方法</span><span class="sxs-lookup"><span data-stu-id="59480-102">How to Run the Business Process Management Solution</span></span>
<span data-ttu-id="59480-103">次の手順では、単一のコンピュータでビジネス プロセス管理ソリューションを実行および検証する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="59480-103">The following steps describe how to run and validate the Business Process Management solution on a single computer.</span></span>  
  
-   [<span data-ttu-id="59480-104">ビジネス プロセス管理ソリューションを開始します。</span><span class="sxs-lookup"><span data-stu-id="59480-104">Start the Business Process Management Solution</span></span>](#step1)  
  
-   [<span data-ttu-id="59480-105">実行し、ビジネス プロセス管理ソリューションの検証</span><span class="sxs-lookup"><span data-stu-id="59480-105">Run and validate the Business Process Management Solution</span></span>](#step3)  
  
## <a name="prerequisites"></a><span data-ttu-id="59480-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="59480-106">Prerequisites</span></span>  
 <span data-ttu-id="59480-107">BPM ソリューションを実行する前に」の手順を実行する必要があります[ビジネス プロセス管理ソリューションをインストールする方法](../core/how-to-install-the-business-process-management-solution.md)です。</span><span class="sxs-lookup"><span data-stu-id="59480-107">Before running the BPM solution, you must perform the steps in [How to Install the Business Process Management Solution](../core/how-to-install-the-business-process-management-solution.md).</span></span>  
  
##  <span data-ttu-id="59480-108"><a name="step1"></a>ビジネス プロセス管理ソリューションを開始します。</span><span class="sxs-lookup"><span data-stu-id="59480-108"><a name="step1"></a> Start the Business Process Management Solution</span></span>  
  
#### <a name="to-start-the-business-process-management-solution"></a><span data-ttu-id="59480-109">ビジネス プロセス管理ソリューションを開始するには</span><span class="sxs-lookup"><span data-stu-id="59480-109">To start the Business Process Management Solution</span></span>  
  
1.  <span data-ttu-id="59480-110">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="59480-110">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="59480-111">**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**プラットフォームの設定**、展開**ホスト インスタンス**、右クリック**BizTalkServerApplication**、クリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="59480-111">In the **BizTalk Server Administration Console**, expand **BizTalk Group**, expand **Platform Settings**, expand **Host Instances**, right-click **BizTalkServerApplication**, and then click **Start**.</span></span>  
  
3.  <span data-ttu-id="59480-112">**BizTalk Server 管理コンソール**、展開**BizTalk グループ**の順に展開および**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="59480-112">In the **BizTalk Server Administration Console**, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
    1.  <span data-ttu-id="59480-113">BTSScn.BPM.MessagingApp を右クリックし、をクリックして**開始**、順にクリック**開始**上、**アプリケーションの開始** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="59480-113">Right-click BTSScn.BPM.MessagingApp, click **Start**, and then click **Start** on the **Start Application** dialog box.</span></span>  
  
    2.  <span data-ttu-id="59480-114">BTSScn.BPM.OrderBrokerApp を右クリックし、をクリックして**開始**、順にクリック**開始**上、**アプリケーションの開始** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="59480-114">Right-click BTSScn.BPM.OrderBrokerApp, click **Start**, and then click **Start** on the **Start Application** dialog box.</span></span>  
  
    3.  <span data-ttu-id="59480-115">BTSScn.BPM.CableOrderApp を右クリックし、をクリックして**開始**、順にクリック**開始**上、**アプリケーションの開始** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="59480-115">Right-click BTSScn.BPM.CableOrderApp, click **Start**, and then click **Start** on the **Start Application** dialog box.</span></span>  
  
    4.  <span data-ttu-id="59480-116">BTSScn.BPM.OrderBrokerApp.Test を右クリックし、をクリックして**停止**です。</span><span class="sxs-lookup"><span data-stu-id="59480-116">Right-click BTSScn.BPM.OrderBrokerApp.Test, and click **Stop**.</span></span> <span data-ttu-id="59480-117">**アプリケーションの停止**ダイアログ ボックスで、**完全停止 - インスタンスを終了**、クリックして**停止**です。</span><span class="sxs-lookup"><span data-stu-id="59480-117">In the **Stop Application** dialog box, select **Full Stop - Terminate instance**, and then click **Stop**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="59480-118">履歴データベースに情報を挿入します。</span><span class="sxs-lookup"><span data-stu-id="59480-118">To insert information in the history database.</span></span> <span data-ttu-id="59480-119">OrderBroker オーケストレーションは HistoryPort 送信ポートを使用して、**配信通知**プロパティが設定されて**送信**です。</span><span class="sxs-lookup"><span data-stu-id="59480-119">the OrderBroker orchestration uses the HistoryPort send port of which the **Delivery Notification** property is set **Transmitted**.</span></span> <span data-ttu-id="59480-120">送信ポートは、HistoryInsert-SP と HistoryInsert-Test-SP を含む HistoryInsert-SPG 送信グループにバインドされています。</span><span class="sxs-lookup"><span data-stu-id="59480-120">The send port is bounded to the HistoryInsert-SPG send group which includes the HistoryInsert-SP and HistoryInsert-Test-SP send ports.</span></span> <span data-ttu-id="59480-121">これら 2 つの送信ポートの場合、メッセージ エンジンは OrderBroker オーケストレーションに 2 つの受信確認メッセージを公開します。</span><span class="sxs-lookup"><span data-stu-id="59480-121">For these two send ports the message engine will publish two acknowledgment messages to the OrderBroker orchestration.</span></span> <span data-ttu-id="59480-122">使用されないメッセージにより、オーケストレーションが保留になります。</span><span class="sxs-lookup"><span data-stu-id="59480-122">It makes the orchestration suspended due to unconsumed messages.</span></span> <span data-ttu-id="59480-123">このような状況を防ぐには、どちらか一方の送信ポートの参加を解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="59480-123">To avoid this situation, you must unenlist one of the send ports.</span></span> <span data-ttu-id="59480-124">このチュートリアルでは、BTSScn.BPM.OrderBrokerApp.Test アプリケーションを完全に停止して HistoryInsert-Test-SP 送信ポートを参加解除します。</span><span class="sxs-lookup"><span data-stu-id="59480-124">In this walkthrough, unenlist HistoryInsert-Test-SP send port by fully stopping the BTSScn.BPM.OrderBrokerApp.Test application.</span></span> <span data-ttu-id="59480-125">OrderBroker オーケストレーションの詳細については、次を参照してください。 [OrderBroker オーケストレーションで処理](../core/processing-in-the-orderbroker-orchestration.md)です。</span><span class="sxs-lookup"><span data-stu-id="59480-125">For more information about the OrderBroker orchestration, see [Processing in the OrderBroker Orchestration](../core/processing-in-the-orderbroker-orchestration.md).</span></span> <span data-ttu-id="59480-126">詳細については**配信通知**プロパティを参照してください[を使用して受信確認](../core/using-acknowledgments.md)です。</span><span class="sxs-lookup"><span data-stu-id="59480-126">For more information about **Delivery Notification** property, see [Using Acknowledgments](../core/using-acknowledgments.md).</span></span>  
  
4.  <span data-ttu-id="59480-127">次に示すように、Facilities Simulator を実行します。</span><span class="sxs-lookup"><span data-stu-id="59480-127">Run the Facilities Simulator as follows:</span></span>  
  
    1.  <span data-ttu-id="59480-128">コマンド プロンプトを開き、ディレクトリを %BTSSolutionsPath%\BPM\FacilitiesSimulator\bin\debug フォルダに変更します。</span><span class="sxs-lookup"><span data-stu-id="59480-128">Open a command prompt, change the directory to the %BTSSolutionsPath%\BPM\FacilitiesSimulator\bin\debug folder.</span></span>  
  
    2.  <span data-ttu-id="59480-129">型`BTSScnBPMFacilities.exe`、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="59480-129">Type `BTSScnBPMFacilities.exe`, and then press ENTER.</span></span> <span data-ttu-id="59480-130">FacilitiesSimulator は実行した状態にしておきます。</span><span class="sxs-lookup"><span data-stu-id="59480-130">Keep the FacilitiesSimulator running.</span></span> <span data-ttu-id="59480-131">ここでは、Southridge Video のバックエンド システムを処理する場合をシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="59480-131">This application simulates the facilities processing back-end systems at Southridge Video.</span></span>  
  
    3.  <span data-ttu-id="59480-132">FacilitiesSimulator で、次の受信キューおよび送信キューを入力します。</span><span class="sxs-lookup"><span data-stu-id="59480-132">In the FacilitiesSimulator, type the following receive and transmit queues:</span></span>  
  
        |<span data-ttu-id="59480-133">名前</span><span class="sxs-lookup"><span data-stu-id="59480-133">Name</span></span>|<span data-ttu-id="59480-134">値</span><span class="sxs-lookup"><span data-stu-id="59480-134">Value</span></span>|  
        |----------|-----------|  
        |<span data-ttu-id="59480-135">**キューを受信します。**</span><span class="sxs-lookup"><span data-stu-id="59480-135">**Receive Queue**</span></span>|`.\private$\ToFacilitiesQ`|  
        |<span data-ttu-id="59480-136">**キューを送信します。**</span><span class="sxs-lookup"><span data-stu-id="59480-136">**Transmit Queue**</span></span>|`.\private$\FromFacilitiesQ`|  
  
    4.  <span data-ttu-id="59480-137">FacilitiesSimulator で、をクリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="59480-137">In the FacilitiesSimulator, Click **Start**.</span></span>  
  
5.  <span data-ttu-id="59480-138">次に示すように、Operation Server を実行します。</span><span class="sxs-lookup"><span data-stu-id="59480-138">Run the Operation Server as follows:</span></span>  
  
    1.  <span data-ttu-id="59480-139">新しいコマンド プロンプトを開き、現在のディレクトリを %BTSSolutionsPath%\BPM\OperationsServer\bin\debug フォルダに変更します。</span><span class="sxs-lookup"><span data-stu-id="59480-139">Open a new command prompt, change the current directory to the %BTSSolutionsPath%\BPM\OperationsServer\bin\debug folder.</span></span>  
  
    2.  <span data-ttu-id="59480-140">型`BTSScnBPMOperations.exe 8881`コマンド プロンプトとし、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="59480-140">Type `BTSScnBPMOperations.exe 8881` at the command prompt, and then press ENTER.</span></span> <span data-ttu-id="59480-141">Operation Server は実行した状態にしておきます。</span><span class="sxs-lookup"><span data-stu-id="59480-141">Keep the Operation Server running.</span></span> <span data-ttu-id="59480-142">Operation Server は TCP ポートの 8881 で Ops アダプタからのメッセージを受信待ちします。</span><span class="sxs-lookup"><span data-stu-id="59480-142">The Operation Server listens on the TCP port, 8881, to receive error messages from the Ops Adapter.</span></span> <span data-ttu-id="59480-143">Ops アダプタから受信したエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="59480-143">It displays the error messages received by the Ops Adapter.</span></span>  
  
6.  <span data-ttu-id="59480-144">次に示すように、ケーブル プロビジョニング システムを実行します。</span><span class="sxs-lookup"><span data-stu-id="59480-144">Run the Cable Provisioning System as follows:</span></span>  
  
    1.  <span data-ttu-id="59480-145">新しいコマンド プロンプトを開き、現在のディレクトリを %BTSSolutionsPath%\BPM\CableProvisioningSystemServer\bin\debug フォルダに変更します。</span><span class="sxs-lookup"><span data-stu-id="59480-145">Open a new command prompt, change the current directory to the %BTSSolutionsPath%\BPM\CableProvisioningSystemServer\bin\debug folder.</span></span>  
  
    2.  <span data-ttu-id="59480-146">型`BTSScnBPMProvisioning.exe 8880`、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="59480-146">Type `BTSScnBPMProvisioning.exe 8880`, and then press ENTER.</span></span> <span data-ttu-id="59480-147">ケーブル プロビジョニング システムの実行は続けます。</span><span class="sxs-lookup"><span data-stu-id="59480-147">Then, keep the Cable Provisioning System running.</span></span> <span data-ttu-id="59480-148">Cable Provisioning System は、8880 TCP ポートでリッスンします。</span><span class="sxs-lookup"><span data-stu-id="59480-148">The Cable Provisioning System listens on the TCP port, 8880.</span></span> <span data-ttu-id="59480-149">このアプリケーションは、バックエンド注文システムをシミュレートし、最終的な注文を表示します。</span><span class="sxs-lookup"><span data-stu-id="59480-149">This application simulates a back-end order system, and displays the final orders.</span></span>  
  
##  <span data-ttu-id="59480-150"><a name="step3"></a>実行し、ビジネス プロセス管理ソリューションの検証</span><span class="sxs-lookup"><span data-stu-id="59480-150"><a name="step3"></a> Run and validate the Business Process Management Solution</span></span>  
  
#### <a name="to-submit-a-new-order-and-validate-the-solution"></a><span data-ttu-id="59480-151">新しい注文の送信とソリューションの検証</span><span class="sxs-lookup"><span data-stu-id="59480-151">To submit a new order and validate the solution</span></span>  
  
1.  <span data-ttu-id="59480-152">Internet Explorer での**アドレス**ボックスには次のようにカスタマー サービス Web アプリケーションの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="59480-152">In Internet Explorer, in the **Address** box, type the URL for the Customer Service Web application as following:</span></span>  
  
    -   `http://localhost/CSRWebApp/CSRMainForm.aspx`  
  
2.  <span data-ttu-id="59480-153">**Southridge Video Customer Service Rep Order Entry Form**  ページで、次の表に、新しい注文を入力してをクリックして**注文を送信します。**</span><span class="sxs-lookup"><span data-stu-id="59480-153">On the **Southridge Video Customer Service Rep Order Entry Form** page, enter a new order in the following table, and then click **Submit Order.**</span></span>  
  
    |<span data-ttu-id="59480-154">エントリ</span><span class="sxs-lookup"><span data-stu-id="59480-154">Entry</span></span>|<span data-ttu-id="59480-155">値</span><span class="sxs-lookup"><span data-stu-id="59480-155">Value</span></span>|  
    |-----------|-----------|  
    |<span data-ttu-id="59480-156">Customer ID</span><span class="sxs-lookup"><span data-stu-id="59480-156">Customer ID</span></span>|<span data-ttu-id="59480-157">1</span><span class="sxs-lookup"><span data-stu-id="59480-157">1</span></span>|  
    |<span data-ttu-id="59480-158">Order ID</span><span class="sxs-lookup"><span data-stu-id="59480-158">Order ID</span></span>|<span data-ttu-id="59480-159">1</span><span class="sxs-lookup"><span data-stu-id="59480-159">1</span></span>|  
    |<span data-ttu-id="59480-160">Sequence Number</span><span class="sxs-lookup"><span data-stu-id="59480-160">Sequence Number</span></span>|<span data-ttu-id="59480-161">1</span><span class="sxs-lookup"><span data-stu-id="59480-161">1</span></span>|  
    |<span data-ttu-id="59480-162">Service Type Code</span><span class="sxs-lookup"><span data-stu-id="59480-162">Service Type Code</span></span>|<span data-ttu-id="59480-163">New Standard Service</span><span class="sxs-lookup"><span data-stu-id="59480-163">New Standard Service</span></span>|  
  
3.  <span data-ttu-id="59480-164">**Southridge Video Customer Service Rep Order Entry Form**  ページの結果メッセージ次のようにします。</span><span class="sxs-lookup"><span data-stu-id="59480-164">On the **Southridge Video Customer Service Rep Order Entry Form** page, the result message as follows:</span></span>  
  
     <span data-ttu-id="59480-165">**顧客 ID 1 Order ID 1 のシーケンス番号 1**</span><span class="sxs-lookup"><span data-stu-id="59480-165">**Customer ID 1 Order ID 1 Sequence Number 1**</span></span>  
  
4.  <span data-ttu-id="59480-166">Cable Provisioning System の実行中にコマンド プロンプトから入力した注文を検証します。</span><span class="sxs-lookup"><span data-stu-id="59480-166">Validate that the placed order at the command prompt running the Cable Provisioning System.</span></span> <span data-ttu-id="59480-167">送信された注文について、分析およびアクティブ化を終え、完了したことを示すメッセージがアプリケーションから表示されます。</span><span class="sxs-lookup"><span data-stu-id="59480-167">The application display the messages that the submitted order is analyzed, activated, and then completed.</span></span>  
  
5.  <span data-ttu-id="59480-168">Facilities Simulator でメッセージの合計数が 1 つ増えたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="59480-168">Validate that the number of the total messages is incremented by one on the Facilities Simulator.</span></span>  
  
#### <a name="to-submit-a-duplicate-while-the-biztalk-server-is-processing-the-original-order"></a><span data-ttu-id="59480-169">BizTalk Server が元の注文を処理している間に重複する注文を送信します。</span><span class="sxs-lookup"><span data-stu-id="59480-169">To submit a duplicate while the BizTalk Server is processing the original order</span></span>  
  
1.  <span data-ttu-id="59480-170">Internet Explorer での**アドレス**ボックスには次のようにカスタマー サービス Web アプリケーションの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="59480-170">In Internet Explorer, in the **Address** box, type the URL for the Customer Service Web application as following:</span></span>  
  
    -   `http://localhost/CSRWebApp/CSRMainForm.aspx`  
  
2.  <span data-ttu-id="59480-171">FacilitiesSimulator で、をクリックして**停止**です。</span><span class="sxs-lookup"><span data-stu-id="59480-171">In the FacilitiesSimulator, click **Stop**.</span></span> <span data-ttu-id="59480-172">これで送信された注文の処理が停止します。</span><span class="sxs-lookup"><span data-stu-id="59480-172">It prevents submitted orders from being processed further.</span></span>  
  
3.  <span data-ttu-id="59480-173">**Southridge Video Customer Service Rep Order Entry Form**  ページで、次の表に、新しい注文を入力してをクリックして**Submit Order**注文の重複をシミュレートするには、2 回クリックします。</span><span class="sxs-lookup"><span data-stu-id="59480-173">On the **Southridge Video Customer Service Rep Order Entry Form** page, enter a new order in the following table, and then click **Submit Order** twice to simulate duplicated orders.</span></span>  
  
    |<span data-ttu-id="59480-174">エントリ</span><span class="sxs-lookup"><span data-stu-id="59480-174">Entry</span></span>|<span data-ttu-id="59480-175">値</span><span class="sxs-lookup"><span data-stu-id="59480-175">Value</span></span>|  
    |-----------|-----------|  
    |<span data-ttu-id="59480-176">Customer ID</span><span class="sxs-lookup"><span data-stu-id="59480-176">Customer ID</span></span>|<span data-ttu-id="59480-177">2</span><span class="sxs-lookup"><span data-stu-id="59480-177">2</span></span>|  
    |<span data-ttu-id="59480-178">Order ID</span><span class="sxs-lookup"><span data-stu-id="59480-178">Order ID</span></span>|<span data-ttu-id="59480-179">1</span><span class="sxs-lookup"><span data-stu-id="59480-179">1</span></span>|  
    |<span data-ttu-id="59480-180">Sequence Number</span><span class="sxs-lookup"><span data-stu-id="59480-180">Sequence Number</span></span>|<span data-ttu-id="59480-181">1</span><span class="sxs-lookup"><span data-stu-id="59480-181">1</span></span>|  
    |<span data-ttu-id="59480-182">Service Type Code</span><span class="sxs-lookup"><span data-stu-id="59480-182">Service Type Code</span></span>|<span data-ttu-id="59480-183">New Standard Service</span><span class="sxs-lookup"><span data-stu-id="59480-183">New Standard Service</span></span>|  
  
4.  <span data-ttu-id="59480-184">**Southridge Video Customer Service Rep Order Entry Form**  ページの結果メッセージ次のようにします。</span><span class="sxs-lookup"><span data-stu-id="59480-184">On the **Southridge Video Customer Service Rep Order Entry Form** page, the result message as follows:</span></span>  
  
     <span data-ttu-id="59480-185">**顧客 ID 2 Order ID 1 のシーケンス番号 1**</span><span class="sxs-lookup"><span data-stu-id="59480-185">**Customer ID 2 Order ID 1 Sequence Number 1**</span></span>  
  
5.  <span data-ttu-id="59480-186">FacilitiesSimulator で、をクリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="59480-186">In the FacilitiesSimulator, click **Start**.</span></span> <span data-ttu-id="59480-187">Facilities Simulator からの応答を待っているオーケストレーションが処理を再開します。</span><span class="sxs-lookup"><span data-stu-id="59480-187">The orchestrations waiting for the responses from the Facilities Simulator will resume.</span></span> <span data-ttu-id="59480-188">1 番目の注文が処理されている間に重複する注文が送信された場合のシミュレーションになります。</span><span class="sxs-lookup"><span data-stu-id="59480-188">It simulates that a duplicate order is submitted while the first order is being processed.</span></span>  
  
6.  <span data-ttu-id="59480-189">Cable Provisioning System を実行しているコマンド プロンプトで送信した注文を確認します。</span><span class="sxs-lookup"><span data-stu-id="59480-189">Check the placed orders at the command prompt running the Cable Provisioning System.</span></span> <span data-ttu-id="59480-190">最初の注文のみについて、分析およびアクティブ化を終え、完了したことを示すメッセージがアプリケーションから表示されます。</span><span class="sxs-lookup"><span data-stu-id="59480-190">The application displays the messages that only the first order is analyzed, activated, and then completed.</span></span>  
  
7.  <span data-ttu-id="59480-191">Operation Server を実行しているコマンド プロンプトで重複注文に対するエラー メッセージを確認します。</span><span class="sxs-lookup"><span data-stu-id="59480-191">Check the error message for the duplicated orders at the command prompt running the Operation Server.</span></span>  
  
#### <a name="to-update-an-order-while-the-biztalk-server-is-processing-the-order"></a><span data-ttu-id="59480-192">BizTalk Server が処理中の注文を更新する方法</span><span class="sxs-lookup"><span data-stu-id="59480-192">To update an order while the BizTalk Server is processing the order</span></span>  
  
1.  <span data-ttu-id="59480-193">Internet Explorer での**アドレス**ボックスには次のようにカスタマー サービス Web アプリケーションの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="59480-193">In Internet Explorer, in the **Address** box, type the URL for the Customer Service Web application as following:</span></span>  
  
    -   `http://localhost/CSRWebApp/CSRMainForm.aspx`  
  
2.  <span data-ttu-id="59480-194">FacilitiesSimulator で、をクリックして**停止**です。</span><span class="sxs-lookup"><span data-stu-id="59480-194">In the FacilitiesSimulator, click **Stop**.</span></span>  
  
3.  <span data-ttu-id="59480-195">**Southridge Video Customer Service Rep Order Entry Form**  ページで、次の表に、新しい注文を入力してをクリックして**Submit Order**です。</span><span class="sxs-lookup"><span data-stu-id="59480-195">On the **Southridge Video Customer Service Rep Order Entry Form** page, enter a new order in the following table, and then click **Submit Order**.</span></span>  
  
    |<span data-ttu-id="59480-196">エントリ</span><span class="sxs-lookup"><span data-stu-id="59480-196">Entry</span></span>|<span data-ttu-id="59480-197">値</span><span class="sxs-lookup"><span data-stu-id="59480-197">Value</span></span>|  
    |-----------|-----------|  
    |<span data-ttu-id="59480-198">Customer ID</span><span class="sxs-lookup"><span data-stu-id="59480-198">Customer ID</span></span>|<span data-ttu-id="59480-199">3</span><span class="sxs-lookup"><span data-stu-id="59480-199">3</span></span>|  
    |<span data-ttu-id="59480-200">Order ID</span><span class="sxs-lookup"><span data-stu-id="59480-200">Order ID</span></span>|<span data-ttu-id="59480-201">1</span><span class="sxs-lookup"><span data-stu-id="59480-201">1</span></span>|  
    |<span data-ttu-id="59480-202">Sequence Number</span><span class="sxs-lookup"><span data-stu-id="59480-202">Sequence Number</span></span>|<span data-ttu-id="59480-203">1</span><span class="sxs-lookup"><span data-stu-id="59480-203">1</span></span>|  
    |<span data-ttu-id="59480-204">Service Type Code</span><span class="sxs-lookup"><span data-stu-id="59480-204">Service Type Code</span></span>|<span data-ttu-id="59480-205">New Standard Service</span><span class="sxs-lookup"><span data-stu-id="59480-205">New Standard Service</span></span>|  
  
4.  <span data-ttu-id="59480-206">**Southridge Video Customer Service Rep Order Entry Form**  ページの結果メッセージ次のようにします。</span><span class="sxs-lookup"><span data-stu-id="59480-206">On the **Southridge Video Customer Service Rep Order Entry Form** page, the result message as follows:</span></span>  
  
     <span data-ttu-id="59480-207">**顧客 ID 3 Order ID 1 のシーケンス番号 1**</span><span class="sxs-lookup"><span data-stu-id="59480-207">**Customer ID 3 Order ID 1 Sequence Number 1**</span></span>  
  
5.  <span data-ttu-id="59480-208">**Southridge Video Customer Service Rep Order Entry Form**  ページで、次の表に、更新された注文を入力してをクリックして**Submit Order**です。</span><span class="sxs-lookup"><span data-stu-id="59480-208">On the **Southridge Video Customer Service Rep Order Entry Form** page, enter an updated order in the following table, and then click **Submit Order**.</span></span>  
  
    |<span data-ttu-id="59480-209">エントリ</span><span class="sxs-lookup"><span data-stu-id="59480-209">Entry</span></span>|<span data-ttu-id="59480-210">値</span><span class="sxs-lookup"><span data-stu-id="59480-210">Value</span></span>|  
    |-----------|-----------|  
    |<span data-ttu-id="59480-211">Customer ID</span><span class="sxs-lookup"><span data-stu-id="59480-211">Customer ID</span></span>|<span data-ttu-id="59480-212">3</span><span class="sxs-lookup"><span data-stu-id="59480-212">3</span></span>|  
    |<span data-ttu-id="59480-213">Order ID</span><span class="sxs-lookup"><span data-stu-id="59480-213">Order ID</span></span>|<span data-ttu-id="59480-214">1</span><span class="sxs-lookup"><span data-stu-id="59480-214">1</span></span>|  
    |<span data-ttu-id="59480-215">Sequence Number</span><span class="sxs-lookup"><span data-stu-id="59480-215">Sequence Number</span></span>|<span data-ttu-id="59480-216">2</span><span class="sxs-lookup"><span data-stu-id="59480-216">2</span></span>|  
    |<span data-ttu-id="59480-217">Service Type Code</span><span class="sxs-lookup"><span data-stu-id="59480-217">Service Type Code</span></span>|<span data-ttu-id="59480-218">New Deluxe Service</span><span class="sxs-lookup"><span data-stu-id="59480-218">New Deluxe Service</span></span>|  
  
6.  <span data-ttu-id="59480-219">**Southridge Video Customer Service Rep Order Entry Form**  ページの結果メッセージ次のようにします。</span><span class="sxs-lookup"><span data-stu-id="59480-219">On the **Southridge Video Customer Service Rep Order Entry Form** page, the result message as follows:</span></span>  
  
     <span data-ttu-id="59480-220">**顧客 ID 3 Order ID 1 のシーケンス番号 2**</span><span class="sxs-lookup"><span data-stu-id="59480-220">**Customer ID 3 Order ID 1 Sequence Number 2**</span></span>  
  
7.  <span data-ttu-id="59480-221">FacilitiesSimulator で、をクリックして**開始**</span><span class="sxs-lookup"><span data-stu-id="59480-221">In the FacilitiesSimulator, click **Start**</span></span>  
  
8.  <span data-ttu-id="59480-222">結果メッセージを確認して、 **Southridge Video Customer Service Rep Order Entry Form**ページ。</span><span class="sxs-lookup"><span data-stu-id="59480-222">Check the result message on the **Southridge Video Customer Service Rep Order Entry Form** page.</span></span>  
  
9. <span data-ttu-id="59480-223">Cable Provisioning System を実行しているコマンド プロンプトで送信した注文を確認します。</span><span class="sxs-lookup"><span data-stu-id="59480-223">Check the placed orders at the command prompt running the Cable Provisioning System.</span></span> <span data-ttu-id="59480-224">2 つの注文を分析し、更新された注文のみをアクティブ化し完了したことを示すメッセージが、アプリケーションから表示されます。</span><span class="sxs-lookup"><span data-stu-id="59480-224">The application displays the messages that two orders are analyzed, but only the updated order is activated and completed.</span></span>  
  
10. <span data-ttu-id="59480-225">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、 をクリックして**イベント ビューアー**と、新しい警告を確認し、元の注文が中断されました。</span><span class="sxs-lookup"><span data-stu-id="59480-225">Click **Start**, point to **All Programs**, point to **Administrative Tools**, click **Event Viewer**, and then check a new warning that the original order was interrupted.</span></span>  
  
11. <span data-ttu-id="59480-226">Operation Server を実行しているコマンド プロンプトでルーティング エラーのエラーメッセージを確認します。</span><span class="sxs-lookup"><span data-stu-id="59480-226">Checked the routing failure error message at the command prompt running the Operation Server.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="59480-227">イベント ログと Operation Server にエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="59480-227">There will be an error in the event log and in the operations server.</span></span> <span data-ttu-id="59480-228">ビジネス プロセスのインスタンスがより高いシーケンス番号を持つ新しい注文によって中断され終了したため、Facilities System からの応答メッセージはビジネス プロセスのインスタンスへの関連付けを失っています。</span><span class="sxs-lookup"><span data-stu-id="59480-228">The response message from the Facilities System no longer correlates back to an instance of the business process as it was terminated by the interruption caused by the new order with a higher sequence number.</span></span> <span data-ttu-id="59480-229">したがって、応答メッセージは孤立し Operation Server に回送されます。</span><span class="sxs-lookup"><span data-stu-id="59480-229">Therefore response message is orphaned and will get routed to the operations server.</span></span> <span data-ttu-id="59480-230">注文の更新の詳細については、次を参照してください。[注文プロセス マネージャでのフロー](../core/order-flow-through-the-process-manager.md)です。</span><span class="sxs-lookup"><span data-stu-id="59480-230">For more information about order updates, see [Order Flow through the Process Manager](../core/order-flow-through-the-process-manager.md).</span></span>  
  
12. <span data-ttu-id="59480-231">メモ帳で %SystemDrive%:\BPMTest\HistoryUpdate-SP フォルダーで、最新のメッセージを開きます。</span><span class="sxs-lookup"><span data-stu-id="59480-231">Open the latest message in the %SystemDrive%:\BPMTest\HistoryUpdate-SP folder with Notepad.</span></span> <span data-ttu-id="59480-232">確認**CustName**、 **OrderNum**、 **OrderSeqNum**、および**ステータス**フィールドを新しい順序のメッセージが作成されているかどうかに、**ステータス**フィールドは**完了**です。</span><span class="sxs-lookup"><span data-stu-id="59480-232">Check **CustName**, **OrderNum**, **OrderSeqNum**, and **Status** fields to see if the message has been created for the new order and the **Status** field is **COMPLETED**.</span></span>  
  
#### <a name="to-terminate-an-order-while-the-biztalk-server-is-processing-the-order"></a><span data-ttu-id="59480-233">BizTalk Server が処理中の注文を終了する方法</span><span class="sxs-lookup"><span data-stu-id="59480-233">To terminate an order while the BizTalk Server is processing the order</span></span>  
  
1.  <span data-ttu-id="59480-234">Internet Explorer での**アドレス**ボックスには次のようにカスタマー サービス Web アプリケーションの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="59480-234">In Internet Explorer, in the **Address** box, type the URL for the Customer Service Web application as following:</span></span>  
  
    -   `http://localhost/CSRWebApp/CSRMainForm.aspx`  
  
2.  <span data-ttu-id="59480-235">FacilitiesSimulator で、をクリックして**停止**です。</span><span class="sxs-lookup"><span data-stu-id="59480-235">In the FacilitiesSimulator, click **Stop**.</span></span>  
  
3.  <span data-ttu-id="59480-236">**Southridge Video Customer Service Rep Order Entry Form**  ページで、次の表に、新しい注文を入力してをクリックして**Submit Order**です。</span><span class="sxs-lookup"><span data-stu-id="59480-236">On the **Southridge Video Customer Service Rep Order Entry Form** page, enter a new order in the following table, and then click **Submit Order**.</span></span>  
  
    |<span data-ttu-id="59480-237">エントリ</span><span class="sxs-lookup"><span data-stu-id="59480-237">Entry</span></span>|<span data-ttu-id="59480-238">値</span><span class="sxs-lookup"><span data-stu-id="59480-238">Value</span></span>|  
    |-----------|-----------|  
    |<span data-ttu-id="59480-239">Customer ID</span><span class="sxs-lookup"><span data-stu-id="59480-239">Customer ID</span></span>|<span data-ttu-id="59480-240">4</span><span class="sxs-lookup"><span data-stu-id="59480-240">4</span></span>|  
    |<span data-ttu-id="59480-241">Order ID</span><span class="sxs-lookup"><span data-stu-id="59480-241">Order ID</span></span>|<span data-ttu-id="59480-242">1</span><span class="sxs-lookup"><span data-stu-id="59480-242">1</span></span>|  
    |<span data-ttu-id="59480-243">Sequence Number</span><span class="sxs-lookup"><span data-stu-id="59480-243">Sequence Number</span></span>|<span data-ttu-id="59480-244">1</span><span class="sxs-lookup"><span data-stu-id="59480-244">1</span></span>|  
    |<span data-ttu-id="59480-245">Service Type Code</span><span class="sxs-lookup"><span data-stu-id="59480-245">Service Type Code</span></span>|<span data-ttu-id="59480-246">New Standard Service</span><span class="sxs-lookup"><span data-stu-id="59480-246">New Standard Service</span></span>|  
  
4.  <span data-ttu-id="59480-247">**Southridge Video Customer Service Rep Order Entry Form**  ページの結果メッセージ次のようにします。</span><span class="sxs-lookup"><span data-stu-id="59480-247">On the **Southridge Video Customer Service Rep Order Entry Form** page, the result message as follows:</span></span>  
  
     <span data-ttu-id="59480-248">**顧客 ID 4 Order ID 1 のシーケンス番号 1**</span><span class="sxs-lookup"><span data-stu-id="59480-248">**Customer ID 4 Order ID 1 Sequence Number 1**</span></span>  
  
5.  <span data-ttu-id="59480-249">**Southridge Video Customer Service Rep Order Entry Form** ] ページで [ **Terminate Order**です。</span><span class="sxs-lookup"><span data-stu-id="59480-249">On the **Southridge Video Customer Service Rep Order Entry Form** page, click **Terminate Order**.</span></span>  
  
6.  <span data-ttu-id="59480-250">**Southridge Video Customer Service Rep Order Entry Form**  ページの結果メッセージ次のようにします。</span><span class="sxs-lookup"><span data-stu-id="59480-250">On the **Southridge Video Customer Service Rep Order Entry Form** page, the result message as follows:</span></span>  
  
     <span data-ttu-id="59480-251">**顧客 ID 4 Order ID 1 のシーケンス番号 1**</span><span class="sxs-lookup"><span data-stu-id="59480-251">**Customer ID 4 Order ID 1 Sequence Number 1**</span></span>  
  
7.  <span data-ttu-id="59480-252">FacilitiesSimulator で、をクリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="59480-252">In the FacilitiesSimulator, click **Start**.</span></span>  
  
8.  <span data-ttu-id="59480-253">Cable Provisioning System を実行しているコマンド プロンプトで送信した注文を確認します。</span><span class="sxs-lookup"><span data-stu-id="59480-253">Check the placed orders at the command prompt running the Cable Provisioning System.</span></span> <span data-ttu-id="59480-254">注文の分析およびアクティブ化のみを行ったことを示すメッセージが、アプリケーションから表示されます。</span><span class="sxs-lookup"><span data-stu-id="59480-254">The application displays the messages that order is only analyzed and activated.</span></span>  
  
9. <span data-ttu-id="59480-255">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、 をクリックして**イベント ビューアー**と、新しい警告を確認し、順序は、ユーザーによって終了されました。</span><span class="sxs-lookup"><span data-stu-id="59480-255">Click **Start**, point to **All Programs**, point to **Administrative Tools**, click **Event Viewer**, and then check a new warning that the order was terminated by user.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="59480-256">注文終了の詳細については、次を参照してください。[注文プロセス マネージャでのフロー](../core/order-flow-through-the-process-manager.md)です。</span><span class="sxs-lookup"><span data-stu-id="59480-256">For more information about terminating orders, see [Order Flow through the Process Manager](../core/order-flow-through-the-process-manager.md).</span></span>  
  
10. <span data-ttu-id="59480-257">Operation Server を実行しているコマンド プロンプトでルーティング エラーのエラーメッセージを確認します。</span><span class="sxs-lookup"><span data-stu-id="59480-257">Checked the routing failure error message at the command prompt running the Operation Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59480-258">参照</span><span class="sxs-lookup"><span data-stu-id="59480-258">See Also</span></span>  
 <span data-ttu-id="59480-259">[ビジネス プロセス管理ソリューションをインストールする前に](../core/before-installing-the-business-process-management-solution.md) </span><span class="sxs-lookup"><span data-stu-id="59480-259">[Before Installing the Business Process Management Solution](../core/before-installing-the-business-process-management-solution.md) </span></span>  
 [<span data-ttu-id="59480-260">ビジネス プロセス管理ソリューションの開発者のコンピュータ設定</span><span class="sxs-lookup"><span data-stu-id="59480-260">Developer Machine Setup for the Business Process Management Solution</span></span>](../core/developer-machine-setup-for-the-business-process-management-solution.md)