---
title: '手順 5: 構成を受信ポートと受信場所 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 43fc8d12-5fde-4ddf-a7f0-770f078ba66b
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce84560a2444d52986a25038f96fdbc835c75f9f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993371"
---
# <a name="step-5-configure-a-receive-port-and-receive-location"></a><span data-ttu-id="21f9a-102">手順 5: 構成を受信ポートと受信場所</span><span class="sxs-lookup"><span data-stu-id="21f9a-102">Step 5: Configure a Receive Port and Receive Location</span></span>
<span data-ttu-id="21f9a-103">![手順 5. の 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-5of9.gif "Step_5of9")</span><span class="sxs-lookup"><span data-stu-id="21f9a-103">![Step 5 of 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-5of9.gif "Step_5of9")</span></span>  
  
 <span data-ttu-id="21f9a-104">このステップでは、Fabrikam パーティ用に設定されたフォルダ内の 850 メッセージを受信するための受信ポートと受信場所を構成します。</span><span class="sxs-lookup"><span data-stu-id="21f9a-104">In this step you configure a receive port and receive location for receiving the 850 message in the folder set up for the Fabrikam party.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="21f9a-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="21f9a-105">Prerequisites</span></span>  
 <span data-ttu-id="21f9a-106">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="21f9a-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-configure-a-receive-port-and-receive-location-for-receiving-the-850-message"></a><span data-ttu-id="21f9a-107">850 メッセージを受信するための受信ポートと受信場所を構成するには</span><span class="sxs-lookup"><span data-stu-id="21f9a-107">To configure a receive port and receive location for receiving the 850 message</span></span>  
  
1. <span data-ttu-id="21f9a-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、展開**BizTalk Server 管理**、 **BizTalk グループ**、**アプリケーション**、し**BizTalkアプリケーション 1**します。</span><span class="sxs-lookup"><span data-stu-id="21f9a-108">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand **BizTalk Server Administration**, **BizTalk Group**, **Applications**, and then **BizTalk Application 1**.</span></span> <span data-ttu-id="21f9a-109">右クリック**受信ポート**、 をポイント**新規**、 をクリックし、**一方向の受信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="21f9a-109">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
2. <span data-ttu-id="21f9a-110">受信ポートのプロパティ ダイアログ ボックスでの**名前**フィールドに、入力`ReceiveEDI_fromTHEM_A`します。</span><span class="sxs-lookup"><span data-stu-id="21f9a-110">In the Receive Port Properties dialog box, in the **Name** field, enter `ReceiveEDI_fromTHEM_A`.</span></span>  
  
3. <span data-ttu-id="21f9a-111">をクリックして**受信場所**コンソール ツリーをクリックで**新規**右側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="21f9a-111">Click **Receive Locations** in the console tree, and then click **New** in the right-hand pane.</span></span>  
  
4. <span data-ttu-id="21f9a-112">**受信場所のプロパティ** ダイアログ ボックスで、**名前**フィールドに、入力`fromTHEM_4010_850`します。</span><span class="sxs-lookup"><span data-stu-id="21f9a-112">In the **Receive Location Properties** dialog box, in the **Name** field, enter `fromTHEM_4010_850`.</span></span>  
  
5. <span data-ttu-id="21f9a-113">**型**を選択します**ファイル**、 をクリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="21f9a-113">For **Type**, select **FILE**, and then click **Configure**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="21f9a-114">テスト メッセージはフォルダに配信されるフラット ファイルであるため、受信場所のトランスポートの種類は FILE です。</span><span class="sxs-lookup"><span data-stu-id="21f9a-114">The transport type of the receive location is FILE because the test message is a flat file delivered into a folder.</span></span>  
  
6. <span data-ttu-id="21f9a-115">**FILE トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**参照**横に、**受信フォルダー**フィールド。</span><span class="sxs-lookup"><span data-stu-id="21f9a-115">In the **FILE Transport Properties** dialog box, click the **Browse** button next to the **Receive folder** field.</span></span> <span data-ttu-id="21f9a-116">**フォルダーの参照** ダイアログ ボックスに移動[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \edi Interface Developer tutorial \processedi_testlocations\scenario a \fromthem をクリック**OK**します。</span><span class="sxs-lookup"><span data-stu-id="21f9a-116">In the **Browse for Folder** dialog box, move to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations\Scenario A\fromTHEM, and then click **OK**.</span></span>  
  
7. <span data-ttu-id="21f9a-117">**FILE トランスポートのプロパティ** ダイアログ ボックスで、変更、**ファイル マスク**に **\*.txt**  をクリック**OK**します。</span><span class="sxs-lookup"><span data-stu-id="21f9a-117">In the **FILE Transport Properties** dialog box, change the **File mask** to **\*.txt** and click **OK**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="21f9a-118">入力テスト メッセージがテキスト ファイル SamplePO.txt であるため、ファイル マスクは \*.txt に設定します。</span><span class="sxs-lookup"><span data-stu-id="21f9a-118">The file mask is set to \*.txt because the input test message is a text file, SamplePO.txt.</span></span>  
  
8. <span data-ttu-id="21f9a-119">**受信場所のプロパティ** ダイアログ ボックスで、**受信パイプライン**フィールドで、 **EdiReceive**します。</span><span class="sxs-lookup"><span data-stu-id="21f9a-119">In the **Receive Location Properties** dialog box, in the **Receive Pipeline** field, select **EdiReceive**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="21f9a-120">EDI インターチェンジ (AS2 トランスポートを経由して配信される EDI インターチェンジを除く) の受信に使用される受信パイプラインは、EdiReceive パイプラインです</span><span class="sxs-lookup"><span data-stu-id="21f9a-120">The receive pipeline used to receive EDI interchanges, except for those delivered over the AS2 transport, is the EdiReceive pipeline.</span></span> <span data-ttu-id="21f9a-121">(AS2 トランスポートを経由して配信される EDI インターチェンジの受信に使用される受信パイプラインは、AS2EdiReceive 受信パイプラインです)。</span><span class="sxs-lookup"><span data-stu-id="21f9a-121">(The AS2EdiReceive receive pipeline is used to receive EDI interchanges delivered over the AS2 transport.)</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="21f9a-122">[EdiReceive] が受信パイプラインのドロップダウン リストに表示されていなければ、アプリケーションが BizTalk EDI アプリケーションを参照していない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="21f9a-122">If EdiReceive is not listed in the drop-down list for receive pipeline, your application may not have a reference to the BizTalk EDI Application.</span></span> <span data-ttu-id="21f9a-123">参照を追加するを参照してください。 [、BizTalk Server EDI アプリケーションへの参照を追加する方法](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)します。</span><span class="sxs-lookup"><span data-stu-id="21f9a-123">To add the reference, see [How to Add a Reference to the BizTalk Server EDI Application](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782).</span></span>  
  
9. <span data-ttu-id="21f9a-124">をクリックして**OK**、順にクリックします**OK**もう一度です。</span><span class="sxs-lookup"><span data-stu-id="21f9a-124">Click **OK**, and then click **OK** again.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="21f9a-125">BizTalk サービスに対するログオン特権を持つアカウントは、fromTHEM_4010_850 受信場所に関連付けられた受信フォルダー ([!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\ProcessEDI_TestLocations\fromTHEM) に対する完全なアクセス許可も持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="21f9a-125">The account that has log-on privileges for the BizTalk service should also be granted full access permissions for the receive folder associated with the fromTHEM_4010_850 receive location ([!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\ProcessEDI_TestLocations\fromTHEM).</span></span> <span data-ttu-id="21f9a-126">持っていない場合は、受信場所を有効にしようとするとエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="21f9a-126">If not, you will receive an error when attempting to enable the receive location.</span></span> <span data-ttu-id="21f9a-127">受信フォルダーのアクセス許可を変更するには、[セキュリティ] タブに移動、**プロパティ**Windows エクスプ ローラーでは、そのフォルダーのダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="21f9a-127">To change the access permissions for the receive folder, go to the Security tab in the **Properties** dialog box for that folder in Windows Explorer.</span></span>  
  
10. <span data-ttu-id="21f9a-128">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、をクリックして**受信場所**、右クリック**fromTHEM_4010_850**、順にクリックします**を有効にする**します。</span><span class="sxs-lookup"><span data-stu-id="21f9a-128">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, click **Receive Locations**, right-click **fromTHEM_4010_850**, and then click **Enable**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="21f9a-129">次の手順</span><span class="sxs-lookup"><span data-stu-id="21f9a-129">Next Steps</span></span>  
 <span data-ttu-id="21f9a-130">送信ポートを構成する (**toOrderSystem**)」の説明に従って、850 メッセージを OrderSystem に送信する[手順 6: 組織にデータを送信する送信ポートを構成する](../core/step-6-configure-a-send-port-to-send-data-to-your-organization.md)します。</span><span class="sxs-lookup"><span data-stu-id="21f9a-130">You configure the send port (**toOrderSystem**) to send the 850 message to OrderSystem, as described in [Step 6: Configure a Send Port to Send Data to Your Organization](../core/step-6-configure-a-send-port-to-send-data-to-your-organization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21f9a-131">参照</span><span class="sxs-lookup"><span data-stu-id="21f9a-131">See Also</span></span>  
 [<span data-ttu-id="21f9a-132">EDI メッセージおよび受信確認を受信するポートの構成</span><span class="sxs-lookup"><span data-stu-id="21f9a-132">Configuring a Port to Receive EDI Messages and Acknowledgments</span></span>](../core/configuring-a-port-to-receive-edi-messages-and-acknowledgments.md)