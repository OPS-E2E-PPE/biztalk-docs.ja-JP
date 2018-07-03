---
title: 構成する方法が表示され、BAM WCF 傍受のための場所とポートの送信 |Microsoft Docs
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
ms.openlocfilehash: 7d6fb5a58efe721f3000dddefb0354bd7834d46c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991651"
---
# <a name="how-to-configure-receive-and-send-locations-and-ports-for-bam-wcf-interception"></a><span data-ttu-id="3a819-102">BAM WCF 傍受のために受信および送信場所とポートを構成する方法</span><span class="sxs-lookup"><span data-stu-id="3a819-102">How to Configure Receive and Send Locations and Ports for BAM WCF Interception</span></span>
<span data-ttu-id="3a819-103">この手順では、重要な概念をわかりやすく示すために、コンテンツ ベースのルーティング (CBR) のシナリオで受信場所と送信場所を構成します。</span><span class="sxs-lookup"><span data-stu-id="3a819-103">In this procedure you configure the receive and send locations in a content-based routing (CBR) scenario in order to demonstrate the key concepts in a straightforward manner.</span></span> <span data-ttu-id="3a819-104">ここで示す概念は、[!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] サービスとして公開されるオーケストレーションに適用できます。</span><span class="sxs-lookup"><span data-stu-id="3a819-104">The concepts demonstrated here can be applied to an orchestration that is exposed as a [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] service.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="3a819-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="3a819-105">Prerequisites</span></span>  
 <span data-ttu-id="3a819-106">この手順では、次のことを前提としています。</span><span class="sxs-lookup"><span data-stu-id="3a819-106">This procedure assumes that you have:</span></span>  

-   <span data-ttu-id="3a819-107">ように、machince.config ファイルが変更[BAM インターセプタ動作を Machine.config ファイルに追加する方法](../core/how-to-add-the-bam-interceptor-behavior-to-the-machine-config-file.md)します。</span><span class="sxs-lookup"><span data-stu-id="3a819-107">Modified your machince.config file as shown in [How to Add the BAM Interceptor Behavior to the Machine.config File](../core/how-to-add-the-bam-interceptor-behavior-to-the-machine-config-file.md).</span></span>  

-   <span data-ttu-id="3a819-108">WCF アダプターが BizTalk server に示すよう作成[BizTalk Server の WCF アダプターを作成する方法](../core/how-to-create-a-wcf-adapter-for-biztalk-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="3a819-108">Created a WCF adapter for BizTalk Server as show in [How to Create a WCF Adapter for BizTalk Server](../core/how-to-create-a-wcf-adapter-for-biztalk-server.md).</span></span>  

### <a name="to-configure-the-receive-and-send-locations"></a><span data-ttu-id="3a819-109">受信場所と送信場所を構成するには</span><span class="sxs-lookup"><span data-stu-id="3a819-109">To configure the receive and send locations</span></span>  

1. <span data-ttu-id="3a819-110">BizTalk 管理コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="3a819-110">Open the BizTalk Administration Console.</span></span> <span data-ttu-id="3a819-111">これを行うには、次のようにクリックします。**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリックし、 **BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="3a819-111">To do this, click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="3a819-112">コンソール ツリーを展開し、BizTalk アプリケーションの [受信場所] ノードを探します。</span><span class="sxs-lookup"><span data-stu-id="3a819-112">Expand the console tree to locate the Receive Locations node for your BizTalk application.</span></span> <span data-ttu-id="3a819-113">クリックして[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、 をクリックして**アプリケーション**で選択したアプリケーションをクリックして、[!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)]サービスの種類 ダイアログ ボックスをクリック**受信場所**します。</span><span class="sxs-lookup"><span data-stu-id="3a819-113">Click [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], click **Applications**, click the application you selected in the [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] Service Type dialog box, and then click **Receive Locations**.</span></span> <span data-ttu-id="3a819-114">作成した受信場所に対応する、新しい受信場所が作成されます。</span><span class="sxs-lookup"><span data-stu-id="3a819-114">There will be a new receive location corresponding to the one you created.</span></span> <span data-ttu-id="3a819-115">新しい受信場所は、無効な状態になります。</span><span class="sxs-lookup"><span data-stu-id="3a819-115">It will be in disabled status.</span></span>  

3. <span data-ttu-id="3a819-116">開く受信場所をダブルクリックして、**受信場所のプロパティ**] ダイアログ ボックスし、[Wcf-custom トランスポートの種類としてを選択します。</span><span class="sxs-lookup"><span data-stu-id="3a819-116">Double-click the receive location to open the **Receive Location Properties** dialog box, and then choose WCF-Custom as the transport type.</span></span>  

4. <span data-ttu-id="3a819-117">をクリックして、**構成**ボタンをクリックする、 **Wcf-custom トランスポートのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="3a819-117">Click the **Configure** button to open the **WCF-Custom Transport Properties** dialog box.</span></span>  

5. <span data-ttu-id="3a819-118">をクリックして、**バインド**タブし、使用するバインディングを選択します。</span><span class="sxs-lookup"><span data-stu-id="3a819-118">Click the **Binding** tab and select the binding you want to use.</span></span>  

6. <span data-ttu-id="3a819-119">をクリックして、**動作** タブで、右クリックし、 **endpointbehavior**ノードをクリックして**拡張機能の追加**します。</span><span class="sxs-lookup"><span data-stu-id="3a819-119">Click the **Behavior** tab, right-click the **EndpointBehavior** node, and then select **Add Extension**.</span></span>  

7. <span data-ttu-id="3a819-120">BAMEndPointExtension (machine.config ファイルに追加した拡張機能) を選択し、クリックして**Ok**します。</span><span class="sxs-lookup"><span data-stu-id="3a819-120">Select the BAMEndPointExtension (this is the extension you added to the machine.config file), and then click **Ok**.</span></span>  

    <span data-ttu-id="3a819-121">![動作拡張機能の選択画面](../core/media/fe830d29-504e-465a-9316-b3f0db2dbc24.gif "fe830d29-504e-465a-9316-b3f0db2dbc24")</span><span class="sxs-lookup"><span data-stu-id="3a819-121">![Select Behavior Extension screen](../core/media/fe830d29-504e-465a-9316-b3f0db2dbc24.gif "fe830d29-504e-465a-9316-b3f0db2dbc24")</span></span>  

8. <span data-ttu-id="3a819-122">作成した拡張機能を選択、次の値を入力し、クリックして**OK**:</span><span class="sxs-lookup"><span data-stu-id="3a819-122">Select the extension you just created, enter the following values, and then click **OK**:</span></span>  


   |      <span data-ttu-id="3a819-123">プロパティ</span><span class="sxs-lookup"><span data-stu-id="3a819-123">Property</span></span>      |                                                        <span data-ttu-id="3a819-124">値</span><span class="sxs-lookup"><span data-stu-id="3a819-124">Value</span></span>                                                         |
   |--------------------|----------------------------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="3a819-125">PollingIntervalSec</span><span class="sxs-lookup"><span data-stu-id="3a819-125">PollingIntervalSec</span></span> |                                                          <span data-ttu-id="3a819-126">10</span><span class="sxs-lookup"><span data-stu-id="3a819-126">10</span></span>                                                          |
   |  <span data-ttu-id="3a819-127">ConnectionString</span><span class="sxs-lookup"><span data-stu-id="3a819-127">ConnectionString</span></span>  | <span data-ttu-id="3a819-128">ConnectionString: Integrated Security = SSPI;Persist Security Info = False; Initial Catalog = BAMPrimaryImport; データ ソース =</span><span class="sxs-lookup"><span data-stu-id="3a819-128">ConnectionString: Integrated Security=SSPI;Persist Security Info=False;Initial Catalog=BAMPrimaryImport;Data Source=</span></span> |


9. <span data-ttu-id="3a819-129">**受信場所のプロパティ**ダイアログ ボックスで、 **PassThruReceive**から、**受信パイプライン**ドロップダウン リスト、およびクリック **[ok]**.</span><span class="sxs-lookup"><span data-stu-id="3a819-129">In the **Receive Location Properties** dialog box, select **PassThruReceive** from the **Receive pipeline** drop-down list, and then click **OK**.</span></span>  

10. <span data-ttu-id="3a819-130">受信場所を有効にし、管理コンソールを更新します。</span><span class="sxs-lookup"><span data-stu-id="3a819-130">Enable the receive location and refresh the Administration console.</span></span> <span data-ttu-id="3a819-131">開始状態は、設定が正常に行われたことを示します。</span><span class="sxs-lookup"><span data-stu-id="3a819-131">A started status indicates that the setup is successful.</span></span>  

## <a name="see-also"></a><span data-ttu-id="3a819-132">参照</span><span class="sxs-lookup"><span data-stu-id="3a819-132">See Also</span></span>  
 [<span data-ttu-id="3a819-133">BAM データを受信するための WCF アダプターの構成</span><span class="sxs-lookup"><span data-stu-id="3a819-133">Configuring the WCF Adapter to Intercept BAM Data</span></span>](../core/configuring-the-wcf-adapter-to-intercept-bam-data.md)