---
title: "配置およびアプリケーションのテスト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e2c86d5f-1849-4b7d-8061-23f156245f5b
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 56b390ef87ac2ea58d91be2ff16a50f2c3748db2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="deploy-and-test-the-application"></a><span data-ttu-id="6825b-102">アプリの配置およびテスト</span><span class="sxs-lookup"><span data-stu-id="6825b-102">Deploy and test the application</span></span>
> [!NOTE]
>  <span data-ttu-id="6825b-103">このチュートリアルは、[!INCLUDE[prague](../includes/prague-md.md)] のみを対象としています。</span><span class="sxs-lookup"><span data-stu-id="6825b-103">This tutorial applies to [!INCLUDE[prague](../includes/prague-md.md)] only.</span></span>  
  
 <span data-ttu-id="6825b-104">このトピックでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリをビルド、配置、構成、テストします。</span><span class="sxs-lookup"><span data-stu-id="6825b-104">In this topic, we build, deploy, configure, and test the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application.</span></span>  
  
## <a name="build-and-deploy-the-application"></a><span data-ttu-id="6825b-105">アプリのビルドと配置</span><span class="sxs-lookup"><span data-stu-id="6825b-105">Build and deploy the application</span></span>  
  
1.  <span data-ttu-id="6825b-106">ソリューション エクスプ ローラーで BizTalk プロジェクト名を右クリックし、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="6825b-106">In the Solution Explorer, right-click the BizTalk project name, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="6825b-107">[プロパティ] ページで、[署名] タブをクリックし、[アセンブリの署名] チェック ボックスをオンにして、ドロップダウンから新しい厳密な名前のキー ファイルを作成するオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="6825b-107">On the Property page, click the Signing tab, select the Sign the assembly check box, and from the drop-down choose the option to create a new strong name key file.</span></span> <span data-ttu-id="6825b-108">表示される手順に従ってファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="6825b-108">Follow the prompts to create the file.</span></span>  
  
3.  <span data-ttu-id="6825b-109">プロジェクトへの変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="6825b-109">Save changes to the project.</span></span> <span data-ttu-id="6825b-110">ソリューション エクスプ ローラーでソリューション名を右クリックし、をクリックして**ソリューションのビルド**です。</span><span class="sxs-lookup"><span data-stu-id="6825b-110">In Solution Explorer, right-click the solution name, and then click **Build Solution**.</span></span>  
  
4.  <span data-ttu-id="6825b-111">プロジェクトが正常にビルド、ソリューション エクスプ ローラーでソリューション名を右クリックし、クリックして**ソリューションの配置**です。</span><span class="sxs-lookup"><span data-stu-id="6825b-111">After project builds successfully, in the Solution Explorer, right-click the solution name, and then click **Deploy Solution**.</span></span>  
  
## <a name="configure-the-application"></a><span data-ttu-id="6825b-112">アプリケーションの構成</span><span class="sxs-lookup"><span data-stu-id="6825b-112">Configure the application</span></span>  
 <span data-ttu-id="6825b-113">アプリを構成するには、[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] で送受信ポートを作成し、それをオーケストレーションと、オーケストレーションの一部として作成された論理送受信ポートにバインドします。</span><span class="sxs-lookup"><span data-stu-id="6825b-113">To configure the application, in [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], create the send and receive ports and then bind them to the orchestration and the logical send/receive ports created as part of the orchestration.</span></span>  
  
1.  <span data-ttu-id="6825b-114">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリが JSON 注文書を受信する受信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="6825b-114">Create a receive port through which a JSON purchase order is received by the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application.</span></span>  
  
    1.  <span data-ttu-id="6825b-115">[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk アプリケーション 1**を右クリックして**受信ポート**、をポイント**新規**、クリックして**一方向の受信ポート**.</span><span class="sxs-lookup"><span data-stu-id="6825b-115">In [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Application 1**, right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
    2.  <span data-ttu-id="6825b-116">受信ポートの名前を指定し、左側のペイン、**受信場所**です。</span><span class="sxs-lookup"><span data-stu-id="6825b-116">Provide a name for the receive port, and then from the left pan, click **Receive Locations**.</span></span> <span data-ttu-id="6825b-117">**受信場所** タブで、をクリックして**新規**です。</span><span class="sxs-lookup"><span data-stu-id="6825b-117">In the **Receive Locations** tab, click **New**.</span></span>  
  
    3.  <span data-ttu-id="6825b-118">受信場所の名前を指定して、ポートの種類として選択**ファイル**、クリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="6825b-118">Specify a name for the receive location, select the port type as **FILE**, and then click **Configure**.</span></span>  
  
    4.  <span data-ttu-id="6825b-119">受信場所が JSON 注文書を取得するフォルダーの場所を入力します。</span><span class="sxs-lookup"><span data-stu-id="6825b-119">Provide the folder location from where the receive location will pick the incoming JSON purchase order.</span></span> <span data-ttu-id="6825b-120">指定`*.json`クリックしてファイル マスクとして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="6825b-120">Specify `*.json` as the file mask and then click **OK**.</span></span>  
  
    5.  <span data-ttu-id="6825b-121">**受信パイプライン**ドロップダウン リストで、 **JSONToXml**です。</span><span class="sxs-lookup"><span data-stu-id="6825b-121">From the **Receive Pipeline** drop-down, select **JSONToXml**.</span></span> <span data-ttu-id="6825b-122">このカスタム受信パイプラインを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリで作成しました。</span><span class="sxs-lookup"><span data-stu-id="6825b-122">You created this custom receive pipeline in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application.</span></span> <span data-ttu-id="6825b-123">省略記号ボタンを右クリックして**([...])** 、パイプラインの横にし、ボタン**Stage 1 – Deocde コンポーネント**、次の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="6825b-123">Right-click the ellipsis **(…)** button next to the pipeline, and then under **Stage 1 – Deocde Component**, provide the following values:</span></span>  
  
        -   <span data-ttu-id="6825b-124">RootNode-`ROOT`</span><span class="sxs-lookup"><span data-stu-id="6825b-124">RootNode - `ROOT`</span></span>  
  
        -   <span data-ttu-id="6825b-125">RootNodeNamespace –`http://BTSJSON`です。</span><span class="sxs-lookup"><span data-stu-id="6825b-125">RootNodeNamespace –`http://BTSJSON`.</span></span>  
  
         <span data-ttu-id="6825b-126">これらの値はターゲットの名前空間と、JSON スキーマ ウィザードを使用して JSON 注文書から再生された XML 注文書スキーマのルート ノードの名前を表します。</span><span class="sxs-lookup"><span data-stu-id="6825b-126">These values represent the target namespace and the root node name of the XML purchase order schema that was generated from the JSON purchase order using the JSON schema wizard.</span></span>  
  
    6.  <span data-ttu-id="6825b-127">をクリックして**OK**すべての開いているダイアログ ボックスを終了するまでです。</span><span class="sxs-lookup"><span data-stu-id="6825b-127">Click **OK** until you exit all open dialog boxes.</span></span>  
  
2.  <span data-ttu-id="6825b-128">JSON 請求書メッセージを送信する送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="6825b-128">Create a send port for sending out JSON invoice messages.</span></span>  
  
    1.  <span data-ttu-id="6825b-129">[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk アプリケーション 1**を右クリックして**送信ポート**、をポイント**新規**、クリックして**静的の一方向送信ポート**.</span><span class="sxs-lookup"><span data-stu-id="6825b-129">In [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Application 1**, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
    2.  <span data-ttu-id="6825b-130">送信ポートの名前を指定して、ポートの種類として選択**ファイル**、クリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="6825b-130">Specify a name for the send port, select the port type as **FILE**, and then click **Configure**.</span></span>  
  
    3.  <span data-ttu-id="6825b-131">送信ポートが送信 JSON 請求書のコピーを作成するフォルダーの場所を入力します。</span><span class="sxs-lookup"><span data-stu-id="6825b-131">Provide the folder location where the send port copies the outgoing JSON invoice.</span></span> <span data-ttu-id="6825b-132">指定`%MessageID%.json`クリックしてファイル名として**OK**です。</span><span class="sxs-lookup"><span data-stu-id="6825b-132">Specify `%MessageID%.json` as the file name and then click **OK**.</span></span>  
  
    4.  <span data-ttu-id="6825b-133">**送信パイプライン**ドロップダウン リストで、 **XmlToJSON**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="6825b-133">From the **Send Pipeline** drop-down, select **XmlToJSON**, and then click **OK**.</span></span>  
  
    5.  <span data-ttu-id="6825b-134">をクリックして**OK**すべての開いているダイアログ ボックスを終了するまでです。</span><span class="sxs-lookup"><span data-stu-id="6825b-134">Click **OK** until you exit all open dialog boxes.</span></span>  
  
3.  <span data-ttu-id="6825b-135">最後に、オーケストレーションの一部として作成した論理ポートを、作成した物理ポートにバインドしてアプリを構成します。</span><span class="sxs-lookup"><span data-stu-id="6825b-135">Finally, bind the logical ports you created as part of the orchestration to the physical ports you created now to configure the application.</span></span>  
  
    1.  <span data-ttu-id="6825b-136">右クリック**BizTalk アプリケーション 1**、クリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="6825b-136">Right-click **BizTalk Application 1**, and then click **Configure**.</span></span>  
  
    2.  <span data-ttu-id="6825b-137">左側のウィンドウからをクリックして**ProcessPO**です。</span><span class="sxs-lookup"><span data-stu-id="6825b-137">From the left pane, click **ProcessPO**.</span></span> <span data-ttu-id="6825b-138">右側のウィンドウに関連付ける、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ホストで論理ポートを物理ポートにマップをクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="6825b-138">From the right pane, associate a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] host, map the logical ports to the physical ports, and then click **OK**.</span></span>  
  
    3.  <span data-ttu-id="6825b-139">右クリック**BizTalk アプリケーション 1**、クリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="6825b-139">Right-click **BizTalk Application 1**, and then click **Start**.</span></span>  
  
## <a name="test-the-application"></a><span data-ttu-id="6825b-140">アプリのテスト</span><span class="sxs-lookup"><span data-stu-id="6825b-140">Test the application</span></span>  
  
1.  <span data-ttu-id="6825b-141">ダウンロードしたサンプルとの間を移動、 **TestMessage**フォルダーをコピー **JsonPurchaseOrder.json**、し、受信場所に関連付けられているフォルダーに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="6825b-141">Navigate to the sample you downloaded, and from the **TestMessage** folder, copy **JsonPurchaseOrder.json**, and paste it in the folder you associated with the receive location.</span></span> <span data-ttu-id="6825b-142">ファイルが消えるまで待ちます。</span><span class="sxs-lookup"><span data-stu-id="6825b-142">Wait till the file disappears.</span></span>  
  
2.  <span data-ttu-id="6825b-143">作成した送信ポートに関連付けられているフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="6825b-143">Navigate to the folder that you associated with the send port you created.</span></span> <span data-ttu-id="6825b-144">注意して、   ***\<GUID >*.json**ファイルはフォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="6825b-144">Notice that a ***\<GUID>*.json** file is available in the folder.</span></span> <span data-ttu-id="6825b-145">ファイルを開いて、それが請求書メッセージであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6825b-145">Open the file and verify that it’s the invoice message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6825b-146">参照</span><span class="sxs-lookup"><span data-stu-id="6825b-146">See Also</span></span>  
 [<span data-ttu-id="6825b-147">BizTalk Server を使用して JSON メッセージの処理</span><span class="sxs-lookup"><span data-stu-id="6825b-147">Processing JSON messages using BizTalk Server</span></span>](../core/processing-json-messages-using-biztalk-server.md)