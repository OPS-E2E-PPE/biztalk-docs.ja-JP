---
title: 配置、およびアプリケーションのテスト |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e2c86d5f-1849-4b7d-8061-23f156245f5b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd6a2f7441611f6c223ac8932faaaa1b0f6f9c69
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389643"
---
# <a name="deploy-and-test-the-application"></a><span data-ttu-id="adab2-102">展開し、アプリケーションをテストします。</span><span class="sxs-lookup"><span data-stu-id="adab2-102">Deploy and test the application</span></span>
> [!NOTE]
>  <span data-ttu-id="adab2-103">このチュートリアルは、BizTalk Server にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="adab2-103">This tutorial applies to BizTalk Server only.</span></span>  
  
 <span data-ttu-id="adab2-104">このトピックでビルド、配置、構成、およびテスト、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="adab2-104">In this topic, we build, deploy, configure, and test the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application.</span></span>  
  
## <a name="build-and-deploy-the-application"></a><span data-ttu-id="adab2-105">アプリのビルドと配置</span><span class="sxs-lookup"><span data-stu-id="adab2-105">Build and deploy the application</span></span>  
  
1.  <span data-ttu-id="adab2-106">ソリューション エクスプ ローラーで BizTalk プロジェクト名を右クリックし をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="adab2-106">In the Solution Explorer, right-click the BizTalk project name, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="adab2-107">プロパティ ページで、署名 タブをクリックします記号、アセンブリのチェック ボックスを選択して、ドロップダウン リストから新しい厳密な名前キー ファイルを作成するオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="adab2-107">On the Property page, click the Signing tab, select the Sign the assembly check box, and from the drop-down choose the option to create a new strong name key file.</span></span> <span data-ttu-id="adab2-108">指示に従って、ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="adab2-108">Follow the prompts to create the file.</span></span>  
  
3.  <span data-ttu-id="adab2-109">プロジェクトへの変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="adab2-109">Save changes to the project.</span></span> <span data-ttu-id="adab2-110">ソリューション エクスプ ローラーでソリューション名を右クリックし をクリックし、**ソリューションのビルド**します。</span><span class="sxs-lookup"><span data-stu-id="adab2-110">In Solution Explorer, right-click the solution name, and then click **Build Solution**.</span></span>  
  
4.  <span data-ttu-id="adab2-111">プロジェクトが正常にビルド、ソリューション エクスプ ローラーで、ソリューション名を右クリックし、**ソリューションの配置**します。</span><span class="sxs-lookup"><span data-stu-id="adab2-111">After project builds successfully, in the Solution Explorer, right-click the solution name, and then click **Deploy Solution**.</span></span>  
  
## <a name="configure-the-application"></a><span data-ttu-id="adab2-112">アプリケーションの構成</span><span class="sxs-lookup"><span data-stu-id="adab2-112">Configure the application</span></span>  
 <span data-ttu-id="adab2-113">アプリケーションを構成する[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、作成、送信と受信ポートおよびオーケストレーションと、論理的に関連付ける送信/受信ポート、オーケストレーションの一部として作成します。</span><span class="sxs-lookup"><span data-stu-id="adab2-113">To configure the application, in [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], create the send and receive ports and then bind them to the orchestration and the logical send/receive ports created as part of the orchestration.</span></span>  
  
1. <span data-ttu-id="adab2-114">使用される JSON 注文書を受信した受信ポートを作成、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="adab2-114">Create a receive port through which a JSON purchase order is received by the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application.</span></span>  
  
   1. <span data-ttu-id="adab2-115">[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk アプリケーション 1**を右クリックして**受信ポート**、 をポイント**新規**、 をクリックし、**一方向の受信ポート**.</span><span class="sxs-lookup"><span data-stu-id="adab2-115">In [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Application 1**, right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
   2. <span data-ttu-id="adab2-116">受信ポートの名前を指定し、左側のペインからをクリックして**受信場所**します。</span><span class="sxs-lookup"><span data-stu-id="adab2-116">Provide a name for the receive port, and then from the left pan, click **Receive Locations**.</span></span> <span data-ttu-id="adab2-117">**受信場所**] タブで [**新規**します。</span><span class="sxs-lookup"><span data-stu-id="adab2-117">In the **Receive Locations** tab, click **New**.</span></span>  
  
   3. <span data-ttu-id="adab2-118">受信場所の名前を指定、として、ポートの種類を選択します。**ファイル**、 をクリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="adab2-118">Specify a name for the receive location, select the port type as **FILE**, and then click **Configure**.</span></span>  
  
   4. <span data-ttu-id="adab2-119">受信場所が着信 JSON 注文書を選択する場所のフォルダーの場所を提供します。</span><span class="sxs-lookup"><span data-stu-id="adab2-119">Provide the folder location from where the receive location will pick the incoming JSON purchase order.</span></span> <span data-ttu-id="adab2-120">指定`*.json`ファイル マスクおよびクリックとして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="adab2-120">Specify `*.json` as the file mask and then click **OK**.</span></span>  
  
   5. <span data-ttu-id="adab2-121">**受信パイプライン**ドロップダウン リストで選択**JSONToXml**します。</span><span class="sxs-lookup"><span data-stu-id="adab2-121">From the **Receive Pipeline** drop-down, select **JSONToXml**.</span></span> <span data-ttu-id="adab2-122">このカスタム受信パイプラインを作成した、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="adab2-122">You created this custom receive pipeline in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application.</span></span> <span data-ttu-id="adab2-123">省略記号ボタンを右クリックして **([...])** 、パイプラインの横にし、下のボタン**Stage 1 – Deocde コンポーネント**、次の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="adab2-123">Right-click the ellipsis **(…)** button next to the pipeline, and then under **Stage 1 – Deocde Component**, provide the following values:</span></span>  
  
      - <span data-ttu-id="adab2-124">RootNode - `ROOT`</span><span class="sxs-lookup"><span data-stu-id="adab2-124">RootNode - `ROOT`</span></span>  
  
      - <span data-ttu-id="adab2-125">RootNodeNamespace –`http://BTSJSON`します。</span><span class="sxs-lookup"><span data-stu-id="adab2-125">RootNodeNamespace –`http://BTSJSON`.</span></span>  
  
        <span data-ttu-id="adab2-126">これらの値は、ターゲットの名前空間と、JSON スキーマ ウィザードを使用して JSON 注文から生成された XML 注文書スキーマのルート ノード名を表します。</span><span class="sxs-lookup"><span data-stu-id="adab2-126">These values represent the target namespace and the root node name of the XML purchase order schema that was generated from the JSON purchase order using the JSON schema wizard.</span></span>  
  
   6. <span data-ttu-id="adab2-127">クリックして**OK**すべての開いているダイアログ ボックスを終了するまでです。</span><span class="sxs-lookup"><span data-stu-id="adab2-127">Click **OK** until you exit all open dialog boxes.</span></span>  
  
2. <span data-ttu-id="adab2-128">JSON 請求書メッセージを送信するための送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="adab2-128">Create a send port for sending out JSON invoice messages.</span></span>  
  
   1. <span data-ttu-id="adab2-129">[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk アプリケーション 1**を右クリックして**送信ポート**、 をポイント**新規**、 をクリックし、**静的の一方向送信ポート**.</span><span class="sxs-lookup"><span data-stu-id="adab2-129">In [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Application 1**, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
   2. <span data-ttu-id="adab2-130">送信ポートの名前を指定、として、ポートの種類を選択します。**ファイル**、 をクリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="adab2-130">Specify a name for the send port, select the port type as **FILE**, and then click **Configure**.</span></span>  
  
   3. <span data-ttu-id="adab2-131">送信ポートが送信 JSON 請求書をコピーするフォルダーの場所を提供します。</span><span class="sxs-lookup"><span data-stu-id="adab2-131">Provide the folder location where the send port copies the outgoing JSON invoice.</span></span> <span data-ttu-id="adab2-132">指定`%MessageID%.json`としてファイル名をクリック**OK**します。</span><span class="sxs-lookup"><span data-stu-id="adab2-132">Specify `%MessageID%.json` as the file name and then click **OK**.</span></span>  
  
   4. <span data-ttu-id="adab2-133">**送信パイプライン**ドロップダウン リストで選択**XmlToJSON**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="adab2-133">From the **Send Pipeline** drop-down, select **XmlToJSON**, and then click **OK**.</span></span>  
  
   5. <span data-ttu-id="adab2-134">クリックして**OK**すべての開いているダイアログ ボックスを終了するまでです。</span><span class="sxs-lookup"><span data-stu-id="adab2-134">Click **OK** until you exit all open dialog boxes.</span></span>  
  
3. <span data-ttu-id="adab2-135">最後に、ポートを物理オーケストレーションの一部として作成した論理ポートをバインド、アプリケーションを構成するには、今すぐ作成します。</span><span class="sxs-lookup"><span data-stu-id="adab2-135">Finally, bind the logical ports you created as part of the orchestration to the physical ports you created now to configure the application.</span></span>  
  
   1. <span data-ttu-id="adab2-136">右クリック**BizTalk アプリケーション 1**、 をクリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="adab2-136">Right-click **BizTalk Application 1**, and then click **Configure**.</span></span>  
  
   2. <span data-ttu-id="adab2-137">左側のウィンドウから次のようにクリックします。 **ProcessPO**します。</span><span class="sxs-lookup"><span data-stu-id="adab2-137">From the left pane, click **ProcessPO**.</span></span> <span data-ttu-id="adab2-138">右側のウィンドウに関連付ける、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ホストに論理ポートを物理ポートにマップしてクリックして **[ok]** します。</span><span class="sxs-lookup"><span data-stu-id="adab2-138">From the right pane, associate a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] host, map the logical ports to the physical ports, and then click **OK**.</span></span>  
  
   3. <span data-ttu-id="adab2-139">右クリック**BizTalk アプリケーション 1**、 をクリックし、**開始**します。</span><span class="sxs-lookup"><span data-stu-id="adab2-139">Right-click **BizTalk Application 1**, and then click **Start**.</span></span>  
  
## <a name="test-the-application"></a><span data-ttu-id="adab2-140">アプリケーションをテストします。</span><span class="sxs-lookup"><span data-stu-id="adab2-140">Test the application</span></span>  
  
1.  <span data-ttu-id="adab2-141">ダウンロードしたサンプルとの間を移動、 **TestMessage**フォルダーをコピー **JsonPurchaseOrder.json**、受信場所に関連付けられているフォルダーに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="adab2-141">Navigate to the sample you downloaded, and from the **TestMessage** folder, copy **JsonPurchaseOrder.json**, and paste it in the folder you associated with the receive location.</span></span> <span data-ttu-id="adab2-142">ファイルが消えるまで待ちます。</span><span class="sxs-lookup"><span data-stu-id="adab2-142">Wait till the file disappears.</span></span>  
  
2.  <span data-ttu-id="adab2-143">作成した送信ポートに関連付けられているフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="adab2-143">Navigate to the folder that you associated with the send port you created.</span></span> <span data-ttu-id="adab2-144">なお、\***\<GUID\>\*.json**フォルダーにファイルが。</span><span class="sxs-lookup"><span data-stu-id="adab2-144">Notice that a \***\<GUID\>\*.json** file is available in the folder.</span></span> <span data-ttu-id="adab2-145">ファイルを開き、請求書メッセージであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="adab2-145">Open the file and verify that it’s the invoice message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adab2-146">参照</span><span class="sxs-lookup"><span data-stu-id="adab2-146">See Also</span></span>  
 [<span data-ttu-id="adab2-147">BizTalk Server を使用して JSON メッセージの処理</span><span class="sxs-lookup"><span data-stu-id="adab2-147">Processing JSON messages using BizTalk Server</span></span>](../core/processing-json-messages-using-biztalk-server.md)