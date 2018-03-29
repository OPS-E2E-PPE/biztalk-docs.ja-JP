---
title: '手順 8 (オンプレミス): BizTalk Server アプリケーションの構成 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 2015-12-08
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5109fb54-8453-444f-bc9c-070a65053397
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa411b7ca828a45aa0d5e58212bb48195c48180f
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="step-8-on-premises-configure-the-biztalk-server-application"></a><span data-ttu-id="4edd8-102">手順 8 (オンプレミス): BizTalk Server アプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="4edd8-102">Step 8 (On Premises): Configure the BizTalk Server Application</span></span>
<span data-ttu-id="4edd8-103">前のステップでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] オーケストレーションを作成しました。</span><span class="sxs-lookup"><span data-stu-id="4edd8-103">In the previous step you created a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration.</span></span> <span data-ttu-id="4edd8-104">このステップでは、アプリケーションをビルドし、展開し、構成します。</span><span class="sxs-lookup"><span data-stu-id="4edd8-104">In this step, you’ll build, deploy, and configure the application.</span></span>  
  
## <a name="build-and-deploy-the-application"></a><span data-ttu-id="4edd8-105">アプリのビルドと配置</span><span class="sxs-lookup"><span data-stu-id="4edd8-105">Build and deploy the application</span></span>  
  
1.  <span data-ttu-id="4edd8-106">Visual Studio で、ソリューション エクスプ ローラーでソリューション名を右クリックし、クリックして **ビルド**します。</span><span class="sxs-lookup"><span data-stu-id="4edd8-106">In Visual Studio, right-click the solution name in the Solution Explorer, and click **Build**.</span></span>  
  
2.  <span data-ttu-id="4edd8-107">展開プロセスでは、アセンブリが厳密に署名されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4edd8-107">The deployment process requires that assembly is strongly signed.</span></span>  <span data-ttu-id="4edd8-108">アセンブリに署名を行うには、厳密な名前のアセンブリ キー ファイルをプロジェクトに関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="4edd8-108">You must sign your assemblies by associating the project with a strong name assembly key file.</span></span>  
  
    1.  <span data-ttu-id="4edd8-109">ソリューション エクスプ ローラーで右クリックし、 **OrderProcessingDemo** [プロジェクト] をクリックして **プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="4edd8-109">In Solution Explorer, right-click the **OrderProcessingDemo** project, and then click **Properties**.</span></span>  
  
    2.  <span data-ttu-id="4edd8-110">クリックして、 **署名** タブをクリックし、選択、 **アセンブリに署名** チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="4edd8-110">Click the **Signing** tab, and select the **Sign the assembly** checkbox.</span></span>  
  
    3.  <span data-ttu-id="4edd8-111">ドロップダウン リストから、**厳密な名前キー ファイルを選択して**ボックスで、 **\<新規しています\>**.</span><span class="sxs-lookup"><span data-stu-id="4edd8-111">From the drop-down list in the **Choose a strong name key file** box, select **\<New…\>**.</span></span>  
  
    4.  <span data-ttu-id="4edd8-112">**厳密な名前キーの作成**  ダイアログ ボックスで、次に例をキー ファイルの名前を入力して `OrderProcessingDemo.snk`します。</span><span class="sxs-lookup"><span data-stu-id="4edd8-112">In the **Create Strong Name Key** dialog box, enter a name for the key file, for example `OrderProcessingDemo.snk`.</span></span> <span data-ttu-id="4edd8-113">パスワードを使って、キー ファイルを保護するためのチェック ボックスをオフにし、クリックして **OK**します。</span><span class="sxs-lookup"><span data-stu-id="4edd8-113">Clear the checkbox for protecting the key file with a password, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="4edd8-114">クリックして、 **展開**  タブの右側のボックスで、 **アプリケーション名**, 、型 `OrderProcessingDemo`します。</span><span class="sxs-lookup"><span data-stu-id="4edd8-114">Click the **Deployment** tab, in the box to the right of **Application Name**, type `OrderProcessingDemo`.</span></span>  
  
4.  <span data-ttu-id="4edd8-115">ボックスの右側にドロップ ダウン リストから **を再展開**,  **True**します。</span><span class="sxs-lookup"><span data-stu-id="4edd8-115">From the drop-down list in the box to the right of **Redeploy**, select **True**.</span></span>  
  
5.  <span data-ttu-id="4edd8-116">ソリューション エクスプ ローラーで右クリック **OrderProcessingDemo**, 、クリックして **展開**します。</span><span class="sxs-lookup"><span data-stu-id="4edd8-116">In Solution Explorer, right-click **OrderProcessingDemo**, and then click **Deploy**.</span></span>  <span data-ttu-id="4edd8-117">出力ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4edd8-117">The Output window should display:</span></span>  
  
    ```  
    ========== Build: 1 succeeded or up-to-date, 0 failed, 0 skipped ==========  
    ========== Deploy: 1 succeeded, 0 failed, 0 skipped ==========  
  
    ```  
  
## <a name="configure-the-application"></a><span data-ttu-id="4edd8-118">アプリケーションの構成</span><span class="sxs-lookup"><span data-stu-id="4edd8-118">Configure the application</span></span>  
  
1.  <span data-ttu-id="4edd8-119">をクリックして **開始**, 、 をポイント **すべてのプログラム**, 、 をポイント **[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]**, 、 をクリックし、 [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="4edd8-119">Click **Start**, point to **All Programs**, point to **[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]**, and then click [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].</span></span>  
  
2.  <span data-ttu-id="4edd8-120">左側のウィンドウのコンソール ツリーで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], を右クリックして **BizTalk グループ**, 、クリックして **更新**します。</span><span class="sxs-lookup"><span data-stu-id="4edd8-120">In the console tree on the left pane, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], right-click **BizTalk Group**, and then click **Refresh**.</span></span>  
  
3.  <span data-ttu-id="4edd8-121">展開 **BizTalk グループ**, 、展開 **アプリケーション**, 、展開 **OrderProcessingDemo**, 、 をクリックし、 **オーケストレーション**します。</span><span class="sxs-lookup"><span data-stu-id="4edd8-121">Expand **BizTalk Group**, expand **Applications**, expand **OrderProcessingDemo**, and then click **Orchestrations**.</span></span> <span data-ttu-id="4edd8-122">表示されます、 **OrderProcessingDemo.OrderProcessing** オーケストレーションが展開されています。</span><span class="sxs-lookup"><span data-stu-id="4edd8-122">You will see that the **OrderProcessingDemo.OrderProcessing** orchestration is deployed.</span></span>  
  
4.  <span data-ttu-id="4edd8-123">論理ポートを作成して、オーケストレーションで (**ReceiveSO**)、Service Bus キューからメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="4edd8-123">In the orchestration, you created a logical port (**ReceiveSO**) to receive messages from the Service Bus Queue.</span></span> <span data-ttu-id="4edd8-124">ここでは、この論理ポートにマップする物理受信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="4edd8-124">In this step, you create a physical receive port to map to the logical port.</span></span>  
  
    1.  <span data-ttu-id="4edd8-125">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで、 **OrderProcessingDemo**  ノードを右クリックして **受信ポート**, 、 をポイント **新規**, 、 をクリックし、 **一方向の受信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="4edd8-125">From the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, under the **OrderProcessingDemo** node, right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
    2.  <span data-ttu-id="4edd8-126">**[全般]** タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="4edd8-126">On the **General** tab, do the following:</span></span>  
  
        |<span data-ttu-id="4edd8-127">プロパティ</span><span class="sxs-lookup"><span data-stu-id="4edd8-127">Use this</span></span>|<span data-ttu-id="4edd8-128">目的</span><span class="sxs-lookup"><span data-stu-id="4edd8-128">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="4edd8-129">**名**</span><span class="sxs-lookup"><span data-stu-id="4edd8-129">**Name**</span></span>|<span data-ttu-id="4edd8-130">型 **ReceiveSO**します。</span><span class="sxs-lookup"><span data-stu-id="4edd8-130">Type **ReceiveSO**.</span></span>|  
        |<span data-ttu-id="4edd8-131">**失敗したメッセージのルーティングを有効にします。**</span><span class="sxs-lookup"><span data-stu-id="4edd8-131">**Enable routing for failed messages**</span></span>|<span data-ttu-id="4edd8-132">(選択解除)</span><span class="sxs-lookup"><span data-stu-id="4edd8-132">(clear)</span></span>|  
  
    3.  <span data-ttu-id="4edd8-133">クリックして **受信場所**, 、 をクリックし、 **新規**します。</span><span class="sxs-lookup"><span data-stu-id="4edd8-133">Click **Receive Locations**, and then click **New**.</span></span>  
  
    4.  <span data-ttu-id="4edd8-134">[Receive Location1 - 受信場所のプロパティ] ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="4edd8-134">From Receive Location1 – Receive Location Properties dialog box, do the following:</span></span>  
  
        |<span data-ttu-id="4edd8-135">プロパティ</span><span class="sxs-lookup"><span data-stu-id="4edd8-135">Use this</span></span>|<span data-ttu-id="4edd8-136">目的</span><span class="sxs-lookup"><span data-stu-id="4edd8-136">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="4edd8-137">**名**</span><span class="sxs-lookup"><span data-stu-id="4edd8-137">**Name**</span></span>|<span data-ttu-id="4edd8-138">型 **ReceiveOrders_SO**します。</span><span class="sxs-lookup"><span data-stu-id="4edd8-138">Type **ReceiveOrders_SO**.</span></span>|  
        |<span data-ttu-id="4edd8-139">**種類**</span><span class="sxs-lookup"><span data-stu-id="4edd8-139">**Type**</span></span>|<span data-ttu-id="4edd8-140">選択 **Sb-messaging**します。</span><span class="sxs-lookup"><span data-stu-id="4edd8-140">Select **SB-Messaging**.</span></span>|  
        |<span data-ttu-id="4edd8-141">**受信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="4edd8-141">**Receive handler**</span></span>|<span data-ttu-id="4edd8-142">**[BizTalkServerApplication]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4edd8-142">Select **BizTalkServerApplication**.</span></span>|  
        |<span data-ttu-id="4edd8-143">**受信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="4edd8-143">**Receive pipeline**</span></span>|<span data-ttu-id="4edd8-144">選択 **XMLReceive**します。</span><span class="sxs-lookup"><span data-stu-id="4edd8-144">Select **XMLReceive**.</span></span>|  
  
    5.  <span data-ttu-id="4edd8-145">クリックして **構成**します。</span><span class="sxs-lookup"><span data-stu-id="4edd8-145">Click **Configure**.</span></span>  
  
    6.  <span data-ttu-id="4edd8-146">Sb-messaging トランスポートのプロパティ ダイアログ ボックスでの **全般**  タブの **キューまたはサブスクリプション URL**, 、入力 **sb://mynamespace.servicebus.appfabriclabs.com/queueordersedi**します。</span><span class="sxs-lookup"><span data-stu-id="4edd8-146">From SB-Messaging Transport Properties dialog box, on the **General** tab, for **Queue or Subscription URL**, enter **sb://mynamespace.servicebus.appfabriclabs.com/queueordersedi**.</span></span> <span data-ttu-id="4edd8-147">ここでは、 *mynamespace*は、Service Bus 名前空間と*queueordersedi*で作成した Service Bus キューは、[手順 3 (Azure の): Service Bus キューの作成](../core/step-3-for-azure-create-a-service-bus-queue.md)です。</span><span class="sxs-lookup"><span data-stu-id="4edd8-147">Here, *mynamespace* is the Service Bus namespace and *queueordersedi* is the Service Bus Queue that you created in [Step 3 (For Azure): Create a Service Bus Queue](../core/step-3-for-azure-create-a-service-bus-queue.md).</span></span>  
  
    7.  <span data-ttu-id="4edd8-148">Sb-messaging トランスポートのプロパティ ダイアログ ボックスでの **認証**  タブで、次の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="4edd8-148">From SB-Messaging Transport Properties dialog box, on the **Authentication** tab, specify the following values:</span></span>  
  
        |<span data-ttu-id="4edd8-149">プロパティ</span><span class="sxs-lookup"><span data-stu-id="4edd8-149">Use this</span></span>|<span data-ttu-id="4edd8-150">目的</span><span class="sxs-lookup"><span data-stu-id="4edd8-150">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="4edd8-151">**アクセス制御サービス STS Uri**</span><span class="sxs-lookup"><span data-stu-id="4edd8-151">**Access Control Service STS Uri**</span></span>|<span data-ttu-id="4edd8-152">「`https://mynamespace-sb.accesscontrol.appfabriclabs.com/`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="4edd8-152">Type `https://mynamespace-sb.accesscontrol.appfabriclabs.com/`</span></span>|  
        |<span data-ttu-id="4edd8-153">**発行者名**</span><span class="sxs-lookup"><span data-stu-id="4edd8-153">**Issuer name**</span></span>|<span data-ttu-id="4edd8-154">発行者名を指定します。</span><span class="sxs-lookup"><span data-stu-id="4edd8-154">Specify the issuer name.</span></span> <span data-ttu-id="4edd8-155">通常これに設定されている `owner`します。</span><span class="sxs-lookup"><span data-stu-id="4edd8-155">Typically this is set to `owner`.</span></span>|  
        |<span data-ttu-id="4edd8-156">**発行者キー**</span><span class="sxs-lookup"><span data-stu-id="4edd8-156">**Issuer key**</span></span>|<span data-ttu-id="4edd8-157">発行者キーを指定します。</span><span class="sxs-lookup"><span data-stu-id="4edd8-157">Specify the issuer key.</span></span>|  
  
        > [!NOTE]
        >  <span data-ttu-id="4edd8-158">名前とキーから、キューの URL、ACS の URL、発行者の値を取得できます、 [Windows Azure CTP 管理ポータル](http://go.microsoft.com/fwlink/p/?LinkId=202886)します。</span><span class="sxs-lookup"><span data-stu-id="4edd8-158">You can get the values for the Queue URL, ACS URL, issuer name and key from the [Windows Azure CTP Management Portal](http://go.microsoft.com/fwlink/p/?LinkId=202886).</span></span>  
  
    8.  <span data-ttu-id="4edd8-159">クリックして **OK** すべてのダイアログ ボックスを終了するまでです。</span><span class="sxs-lookup"><span data-stu-id="4edd8-159">Click **OK** until you exit all the dialog boxes.</span></span>  
  
5.  <span data-ttu-id="4edd8-160">論理ポートを作成して、オーケストレーションで (**SendToSQL**) メッセージを送信する、 **SalesOrder** データベース テーブル。</span><span class="sxs-lookup"><span data-stu-id="4edd8-160">In the orchestration, you created a logical port (**SendToSQL**) to send messages to the **SalesOrder** database table.</span></span> <span data-ttu-id="4edd8-161">ここでは、この論理ポートにマップする物理送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="4edd8-161">In this step, you create a physical send port to map to the logical port.</span></span>  
  
    1.  <span data-ttu-id="4edd8-162">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで、 **OrderProcessingDemo**  ノードを右クリックして **送信ポート**, 、 をポイント **新規**, 、 をクリックし、 **静的な一方向送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="4edd8-162">From the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, under the **OrderProcessingDemo** node, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
    2.  <span data-ttu-id="4edd8-163">[全般] タブには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="4edd8-163">On the General tab, do the following:</span></span>  
  
        |<span data-ttu-id="4edd8-164">プロパティ</span><span class="sxs-lookup"><span data-stu-id="4edd8-164">Use this</span></span>|<span data-ttu-id="4edd8-165">目的</span><span class="sxs-lookup"><span data-stu-id="4edd8-165">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="4edd8-166">**名**</span><span class="sxs-lookup"><span data-stu-id="4edd8-166">**Name**</span></span>|<span data-ttu-id="4edd8-167">型 **SendToSQL**します。</span><span class="sxs-lookup"><span data-stu-id="4edd8-167">Type **SendToSQL**.</span></span>|  
        |<span data-ttu-id="4edd8-168">**種類**</span><span class="sxs-lookup"><span data-stu-id="4edd8-168">**Type**</span></span>|<span data-ttu-id="4edd8-169">選択 **WCF-SQL**します。</span><span class="sxs-lookup"><span data-stu-id="4edd8-169">Select **WCF-SQL**.</span></span>|  
        |<span data-ttu-id="4edd8-170">**送信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="4edd8-170">**Send handler**</span></span>|<span data-ttu-id="4edd8-171">選択 **BizTAlkServerApplication**します。</span><span class="sxs-lookup"><span data-stu-id="4edd8-171">Select **BizTAlkServerApplication**.</span></span>|  
        |<span data-ttu-id="4edd8-172">**送信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="4edd8-172">**Send pipeline**</span></span>|<span data-ttu-id="4edd8-173">選択 **PassThruTransmit**します。</span><span class="sxs-lookup"><span data-stu-id="4edd8-173">Select **PassThruTransmit**.</span></span>|  
  
    3.  <span data-ttu-id="4edd8-174">クリックして **構成**します。</span><span class="sxs-lookup"><span data-stu-id="4edd8-174">Click **Configure**.</span></span>  
  
    4.  <span data-ttu-id="4edd8-175">[WCF-SQL トランスポートのプロパティで、 **全般** ] タブで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="4edd8-175">From WCF-SQL Transport Properties, on the **General** tab, do the following:</span></span>  
  
        |<span data-ttu-id="4edd8-176">プロパティ</span><span class="sxs-lookup"><span data-stu-id="4edd8-176">Use this</span></span>|<span data-ttu-id="4edd8-177">目的</span><span class="sxs-lookup"><span data-stu-id="4edd8-177">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="4edd8-178">**アドレス (URI)**</span><span class="sxs-lookup"><span data-stu-id="4edd8-178">**Address (URI)**</span></span>|<span data-ttu-id="4edd8-179">型 **//computername/database_instance_name/databasename**します。</span><span class="sxs-lookup"><span data-stu-id="4edd8-179">Type **mssql://computername/database_instance_name/databasename**.</span></span> <span data-ttu-id="4edd8-180">たとえばに接続するため、 **DemoDB** 既定のデータベース インスタンスで実行されているローカル コンピューター上のデータベースを入力してください `mssql://.//DemoDB`</span><span class="sxs-lookup"><span data-stu-id="4edd8-180">For example, to connect to a **DemoDB** database on the local computer running under the default database instance, enter `mssql://.//DemoDB`</span></span><br /><br /> <span data-ttu-id="4edd8-181">詳細については、次を参照してください。 [SQL Server の接続 URI を作成する](../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="4edd8-181">For more information, see [Create the SQL Server connection URI](../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md).</span></span>|  
        |<span data-ttu-id="4edd8-182">**操作**</span><span class="sxs-lookup"><span data-stu-id="4edd8-182">**Action**</span></span>|<span data-ttu-id="4edd8-183">型 **TableOp、挿入、dbo/SalesOrder**します。</span><span class="sxs-lookup"><span data-stu-id="4edd8-183">Type **TableOp/Insert/dbo/SalesOrder**.</span></span>|  
  
    5.  <span data-ttu-id="4edd8-184">WCF-SQL トランスポートのプロパティで、 **資格情報**  タブで  **シングル サインオンを使用しない**, 、接続文字列で指定した SQL Server データベースに接続する (大文字小文字を区別) 資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="4edd8-184">From WCF-SQL Transport Properties, on the **Credentials** tab, select **Do not use Single Sign-On**, and specify credentials (case-sensitive) to connect to the SQL Server database you specified in the connection string.</span></span> <span data-ttu-id="4edd8-185">Windows 認証を使用して接続する場合は、資格情報を空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="4edd8-185">If you want to connect using Windows Authentication, leave the credentials blank.</span></span>  
  
    6.  <span data-ttu-id="4edd8-186">クリックして **OK** すべてのダイアログ ボックスを終了するまでです。</span><span class="sxs-lookup"><span data-stu-id="4edd8-186">Click **OK** until you exit all the dialog boxes.</span></span>  
  
6.  <span data-ttu-id="4edd8-187">論理ポートを作成して、オーケストレーションで (**SendToFile**) 共有ファイルの場所にメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="4edd8-187">In the orchestration, you created a logical port (**SendToFile**) to send messages to a shared file location.</span></span> <span data-ttu-id="4edd8-188">ここでは、この論理ポートにマップする物理送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="4edd8-188">In this step, you create a physical send port to map to the logical port.</span></span>  
  
    1.  <span data-ttu-id="4edd8-189">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで、 **OrderProcessingDemo**  ノードを右クリックして **送信ポート**, 、 をポイント **新規**, 、 をクリックし、 **静的な一方向送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="4edd8-189">From the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, under the **OrderProcessingDemo** node, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
    2.  <span data-ttu-id="4edd8-190">[全般] タブには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="4edd8-190">On the General tab, do the following:</span></span>  
  
        |<span data-ttu-id="4edd8-191">プロパティ</span><span class="sxs-lookup"><span data-stu-id="4edd8-191">Use this</span></span>|<span data-ttu-id="4edd8-192">目的</span><span class="sxs-lookup"><span data-stu-id="4edd8-192">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="4edd8-193">**名**</span><span class="sxs-lookup"><span data-stu-id="4edd8-193">**Name**</span></span>|<span data-ttu-id="4edd8-194">型 **SendToFile**します。</span><span class="sxs-lookup"><span data-stu-id="4edd8-194">Type **SendToFile**.</span></span>|  
        |<span data-ttu-id="4edd8-195">**種類**</span><span class="sxs-lookup"><span data-stu-id="4edd8-195">**Type**</span></span>|<span data-ttu-id="4edd8-196">選択 **ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="4edd8-196">Select **File**.</span></span>|  
        |<span data-ttu-id="4edd8-197">**送信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="4edd8-197">**Send handler**</span></span>|<span data-ttu-id="4edd8-198">選択 **BizTAlkServerApplication**します。</span><span class="sxs-lookup"><span data-stu-id="4edd8-198">Select **BizTAlkServerApplication**.</span></span>|  
        |<span data-ttu-id="4edd8-199">**送信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="4edd8-199">**Send pipeline**</span></span>|<span data-ttu-id="4edd8-200">選択 **XML Transmit**します。</span><span class="sxs-lookup"><span data-stu-id="4edd8-200">Select **XML Transmit**.</span></span>|  
  
    3.  <span data-ttu-id="4edd8-201">クリックして **構成**します。</span><span class="sxs-lookup"><span data-stu-id="4edd8-201">Click **Configure**.</span></span>  
  
    4.  <span data-ttu-id="4edd8-202">[FILE トランスポートのプロパティ] で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="4edd8-202">From File Transport Properties, do the following:</span></span>  
  
        |<span data-ttu-id="4edd8-203">プロパティ</span><span class="sxs-lookup"><span data-stu-id="4edd8-203">Use this</span></span>|<span data-ttu-id="4edd8-204">目的</span><span class="sxs-lookup"><span data-stu-id="4edd8-204">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="4edd8-205">**受信フォルダー**</span><span class="sxs-lookup"><span data-stu-id="4edd8-205">**Receive folder**</span></span>|<span data-ttu-id="4edd8-206">メッセージの送信先を指定します。</span><span class="sxs-lookup"><span data-stu-id="4edd8-206">Specify the location where you want to send the message.</span></span>|  
        |<span data-ttu-id="4edd8-207">**ファイル名**</span><span class="sxs-lookup"><span data-stu-id="4edd8-207">**File name**</span></span>|<span data-ttu-id="4edd8-208">保持 **%MessageID%.xml**します。</span><span class="sxs-lookup"><span data-stu-id="4edd8-208">Retain **%MessageID%.xml**.</span></span>|  
  
    5.  <span data-ttu-id="4edd8-209">クリックして **OK** すべてのダイアログ ボックスを終了するまでです。</span><span class="sxs-lookup"><span data-stu-id="4edd8-209">Click **OK** until you exit all the dialog boxes.</span></span>  
  
7.  <span data-ttu-id="4edd8-210">次に、物理ポートと論理ポートを組み合わせてアプリケーションを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4edd8-210">You must now bind the physical and logical ports together to configure the application.</span></span>  
  
    1.  <span data-ttu-id="4edd8-211">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで、右クリックし **OrderProcessingDemo**, 、 をクリックし、 **構成**します。</span><span class="sxs-lookup"><span data-stu-id="4edd8-211">From the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click **OrderProcessingDemo**, and then click **Configure**.</span></span>  
  
    2.  <span data-ttu-id="4edd8-212">アプリケーションの構成から左側のウィンドウでクリックして **OrderProcessing**します。</span><span class="sxs-lookup"><span data-stu-id="4edd8-212">From Configure Application, in the left pane, click **OrderProcessing**.</span></span>  
  
    3.  <span data-ttu-id="4edd8-213">次の表の値を使用してアプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="4edd8-213">Use the values in the following table to configure the application.</span></span>  
  
        |<span data-ttu-id="4edd8-214">プロパティ</span><span class="sxs-lookup"><span data-stu-id="4edd8-214">Use this</span></span>|<span data-ttu-id="4edd8-215">目的</span><span class="sxs-lookup"><span data-stu-id="4edd8-215">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="4edd8-216">**ホスト**</span><span class="sxs-lookup"><span data-stu-id="4edd8-216">For **Host**</span></span>|<span data-ttu-id="4edd8-217">選択 **BizTalkServerApplication**</span><span class="sxs-lookup"><span data-stu-id="4edd8-217">Select **BizTalkServerApplication**</span></span>|  
        |<span data-ttu-id="4edd8-218">論理ポート **ReceiveSO**</span><span class="sxs-lookup"><span data-stu-id="4edd8-218">For logical port **ReceiveSO**</span></span>|<span data-ttu-id="4edd8-219">物理ポートを選択して **ReceiveSO**</span><span class="sxs-lookup"><span data-stu-id="4edd8-219">Select physical port **ReceiveSO**</span></span>|  
        |<span data-ttu-id="4edd8-220">論理ポート **SendToSQL**</span><span class="sxs-lookup"><span data-stu-id="4edd8-220">For logical port **SendToSQL**</span></span>|<span data-ttu-id="4edd8-221">物理ポートを選択して **SendToSQL**</span><span class="sxs-lookup"><span data-stu-id="4edd8-221">Select physical port **SendToSQL**</span></span>|  
        |<span data-ttu-id="4edd8-222">論理ポート **SendToFile**</span><span class="sxs-lookup"><span data-stu-id="4edd8-222">For logical port **SendToFile**</span></span>|<span data-ttu-id="4edd8-223">物理ポートを選択して **SendToFile**</span><span class="sxs-lookup"><span data-stu-id="4edd8-223">Select physical port **SendToFile**</span></span>|  
  
    4.  <span data-ttu-id="4edd8-224">クリックして **OK** 構成を保存します。</span><span class="sxs-lookup"><span data-stu-id="4edd8-224">Click **OK** to save the configuration.</span></span>  
  
## <a name="start-the-application"></a><span data-ttu-id="4edd8-225">アプリケーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="4edd8-225">Start the application</span></span>  
  
1.  <span data-ttu-id="4edd8-226">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを右クリックして **OrderProcessingDemo**, 、クリックして **開始**します。</span><span class="sxs-lookup"><span data-stu-id="4edd8-226">From the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click **OrderProcessingDemo**, and then click **Start**.</span></span>  
  
2.  <span data-ttu-id="4edd8-227">ダイアログ ボックスの  **開始**します。</span><span class="sxs-lookup"><span data-stu-id="4edd8-227">From the dialog, click **Start**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4edd8-228">参照</span><span class="sxs-lookup"><span data-stu-id="4edd8-228">See Also</span></span>  
 [<span data-ttu-id="4edd8-229">チュートリアル 4: BizTalk Server 2013 を使用してハイブリッド アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="4edd8-229">Tutorial 4: Creating a Hybrid Application Using BizTalk Server 2013</span></span>](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)