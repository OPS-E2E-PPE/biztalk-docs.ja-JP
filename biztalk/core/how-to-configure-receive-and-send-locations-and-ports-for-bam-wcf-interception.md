---
title: 構成する方法の場所と送受信ポートを BAM WCF インターセプション用 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 501194dc-427a-4910-88c9-19cf47daeaad
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aa77f39e8320c0d6598caaf5ea547592078774ba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248442"
---
# <a name="how-to-configure-receive-and-send-locations-and-ports-for-bam-wcf-interception"></a><span data-ttu-id="b2993-102">BAM WCF 傍受のために受信および送信場所とポートを構成する方法</span><span class="sxs-lookup"><span data-stu-id="b2993-102">How to Configure Receive and Send Locations and Ports for BAM WCF Interception</span></span>
<span data-ttu-id="b2993-103">この手順では、重要な概念をわかりやすく示すために、コンテンツ ベースのルーティング (CBR) のシナリオで受信場所と送信場所を構成します。</span><span class="sxs-lookup"><span data-stu-id="b2993-103">In this procedure you configure the receive and send locations in a content-based routing (CBR) scenario in order to demonstrate the key concepts in a straightforward manner.</span></span> <span data-ttu-id="b2993-104">ここで示す概念は、[!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] サービスとして公開されるオーケストレーションに適用できます。</span><span class="sxs-lookup"><span data-stu-id="b2993-104">The concepts demonstrated here can be applied to an orchestration that is exposed as a [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] service.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b2993-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="b2993-105">Prerequisites</span></span>  
 <span data-ttu-id="b2993-106">この手順では、次のことを前提としています。</span><span class="sxs-lookup"><span data-stu-id="b2993-106">This procedure assumes that you have:</span></span>  
  
-   <span data-ttu-id="b2993-107">ように、machince.config ファイルを変更[BAM インターセプタ動作を Machine.config ファイルに追加する方法](../core/how-to-add-the-bam-interceptor-behavior-to-the-machine-config-file.md)です。</span><span class="sxs-lookup"><span data-stu-id="b2993-107">Modified your machince.config file as shown in [How to Add the BAM Interceptor Behavior to the Machine.config File](../core/how-to-add-the-bam-interceptor-behavior-to-the-machine-config-file.md).</span></span>  
  
-   <span data-ttu-id="b2993-108">WCF アダプターを BizTalk server でスライド ショーとして作成[BizTalk Server の WCF アダプターを作成する方法](../core/how-to-create-a-wcf-adapter-for-biztalk-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="b2993-108">Created a WCF adapter for BizTalk Server as show in [How to Create a WCF Adapter for BizTalk Server](../core/how-to-create-a-wcf-adapter-for-biztalk-server.md).</span></span>  
  
### <a name="to-configure-the-receive-and-send-locations"></a><span data-ttu-id="b2993-109">受信場所と送信場所を構成するには</span><span class="sxs-lookup"><span data-stu-id="b2993-109">To configure the receive and send locations</span></span>  
  
1.  <span data-ttu-id="b2993-110">BizTalk 管理コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="b2993-110">Open the BizTalk Administration Console.</span></span> <span data-ttu-id="b2993-111">これを行うには、をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、クリックして**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="b2993-111">To do this, click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="b2993-112">コンソール ツリーを展開し、BizTalk アプリケーションの [受信場所] ノードを探します。</span><span class="sxs-lookup"><span data-stu-id="b2993-112">Expand the console tree to locate the Receive Locations node for your BizTalk application.</span></span> <span data-ttu-id="b2993-113">をクリックして[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、 をクリックして**アプリケーション**で選択したアプリケーションをクリックして、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]クリックしてサービスの種類 ダイアログ ボックス、**受信場所**です。</span><span class="sxs-lookup"><span data-stu-id="b2993-113">Click [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], click **Applications**, click the application you selected in the [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] Service Type dialog box, and then click **Receive Locations**.</span></span> <span data-ttu-id="b2993-114">作成した受信場所に対応する、新しい受信場所が作成されます。</span><span class="sxs-lookup"><span data-stu-id="b2993-114">There will be a new receive location corresponding to the one you created.</span></span> <span data-ttu-id="b2993-115">新しい受信場所は、無効な状態になります。</span><span class="sxs-lookup"><span data-stu-id="b2993-115">It will be in disabled status.</span></span>  
  
3.  <span data-ttu-id="b2993-116">開くには、受信場所をダブルクリックして、**受信場所のプロパティ** ダイアログ ボックス、および WCF カスタム トランスポートの種類としてを選択します。</span><span class="sxs-lookup"><span data-stu-id="b2993-116">Double-click the receive location to open the **Receive Location Properties** dialog box, and then choose WCF-Custom as the transport type.</span></span>  
  
4.  <span data-ttu-id="b2993-117">クリックして、**構成**を開く ボタン、 **Wcf-custom トランスポートのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="b2993-117">Click the **Configure** button to open the **WCF-Custom Transport Properties** dialog box.</span></span>  
  
5.  <span data-ttu-id="b2993-118">クリックして、**バインディング**タブし、使用するバインディングを選択します。</span><span class="sxs-lookup"><span data-stu-id="b2993-118">Click the **Binding** tab and select the binding you want to use.</span></span>  
  
6.  <span data-ttu-id="b2993-119">クリックして、**動作** タブで、右クリックし、 **endpointbehavior**ノードをクリックして**拡張機能の追加**です。</span><span class="sxs-lookup"><span data-stu-id="b2993-119">Click the **Behavior** tab, right-click the **EndpointBehavior** node, and then select **Add Extension**.</span></span>  
  
7.  <span data-ttu-id="b2993-120">BAMEndPointExtension (machine.config ファイルに追加した拡張機能) を選択し、クリックして**Ok**です。</span><span class="sxs-lookup"><span data-stu-id="b2993-120">Select the BAMEndPointExtension (this is the extension you added to the machine.config file), and then click **Ok**.</span></span>  
  
     <span data-ttu-id="b2993-121">![動作拡張機能の選択画面](../core/media/fe830d29-504e-465a-9316-b3f0db2dbc24.gif "fe830d29-504e-465a-9316-b3f0db2dbc24")</span><span class="sxs-lookup"><span data-stu-id="b2993-121">![Select Behavior Extension screen](../core/media/fe830d29-504e-465a-9316-b3f0db2dbc24.gif "fe830d29-504e-465a-9316-b3f0db2dbc24")</span></span>  
  
8.  <span data-ttu-id="b2993-122">作成した拡張機能を選択、次の値を入力し、クリックして**OK**:</span><span class="sxs-lookup"><span data-stu-id="b2993-122">Select the extension you just created, enter the following values, and then click **OK**:</span></span>  
  
    |<span data-ttu-id="b2993-123">プロパティ</span><span class="sxs-lookup"><span data-stu-id="b2993-123">Property</span></span>|<span data-ttu-id="b2993-124">値</span><span class="sxs-lookup"><span data-stu-id="b2993-124">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="b2993-125">PollingIntervalSec</span><span class="sxs-lookup"><span data-stu-id="b2993-125">PollingIntervalSec</span></span>|<span data-ttu-id="b2993-126">10</span><span class="sxs-lookup"><span data-stu-id="b2993-126">10</span></span>|  
    |<span data-ttu-id="b2993-127">ConnectionString</span><span class="sxs-lookup"><span data-stu-id="b2993-127">ConnectionString</span></span>|<span data-ttu-id="b2993-128">ConnectionString: 統合セキュリティを = SSPI;Persist Security Info = False; Initial Catalog = BAMPrimaryImport; データ ソース =</span><span class="sxs-lookup"><span data-stu-id="b2993-128">ConnectionString: Integrated Security=SSPI;Persist Security Info=False;Initial Catalog=BAMPrimaryImport;Data Source=</span></span>|  
  
9. <span data-ttu-id="b2993-129">**受信場所のプロパティ**ダイアログ ボックスで、 **PassThruReceive**から、**受信パイプライン**クリックしてドロップダウン リスト、 **OK**.</span><span class="sxs-lookup"><span data-stu-id="b2993-129">In the **Receive Location Properties** dialog box, select **PassThruReceive** from the **Receive pipeline** drop-down list, and then click **OK**.</span></span>  
  
10. <span data-ttu-id="b2993-130">受信場所を有効にし、管理コンソールを更新します。</span><span class="sxs-lookup"><span data-stu-id="b2993-130">Enable the receive location and refresh the Administration console.</span></span> <span data-ttu-id="b2993-131">開始状態は、設定が正常に行われたことを示します。</span><span class="sxs-lookup"><span data-stu-id="b2993-131">A started status indicates that the setup is successful.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2993-132">参照</span><span class="sxs-lookup"><span data-stu-id="b2993-132">See Also</span></span>  
 [<span data-ttu-id="b2993-133">BAM データを受信する WCF アダプタの構成</span><span class="sxs-lookup"><span data-stu-id="b2993-133">Configuring the WCF Adapter to Intercept BAM Data</span></span>](../core/configuring-the-wcf-adapter-to-intercept-bam-data.md)