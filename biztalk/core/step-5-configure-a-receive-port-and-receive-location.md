---
title: 手順 5:構成を受信ポートと受信場所 |Microsoft Docs
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
ms.openlocfilehash: a4f4976c585caf858c27680b156ec3d01b09d439
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244355"
---
# <a name="step-5-configure-a-receive-port-and-receive-location"></a><span data-ttu-id="4492e-102">手順 5:構成を受信ポートと受信場所</span><span class="sxs-lookup"><span data-stu-id="4492e-102">Step 5: Configure a Receive Port and Receive Location</span></span>
<span data-ttu-id="4492e-103">![手順 5. の 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-5of9.gif "Step_5of9")</span><span class="sxs-lookup"><span data-stu-id="4492e-103">![Step 5 of 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-5of9.gif "Step_5of9")</span></span>  
  
 <span data-ttu-id="4492e-104">この手順では、受信ポートと Fabrikam パーティを設定するフォルダーに 850 メッセージを受信するための受信場所を構成します。</span><span class="sxs-lookup"><span data-stu-id="4492e-104">In this step you configure a receive port and receive location for receiving the 850 message in the folder set up for the Fabrikam party.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4492e-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="4492e-105">Prerequisites</span></span>  
 <span data-ttu-id="4492e-106">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4492e-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-configure-a-receive-port-and-receive-location-for-receiving-the-850-message"></a><span data-ttu-id="4492e-107">受信 850 メッセージを受信するための場所および受信ポートを構成するには</span><span class="sxs-lookup"><span data-stu-id="4492e-107">To configure a receive port and receive location for receiving the 850 message</span></span>  
  
1. <span data-ttu-id="4492e-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、展開**BizTalk Server 管理**、 **BizTalk グループ**、**アプリケーション**、し**BizTalkアプリケーション 1**します。</span><span class="sxs-lookup"><span data-stu-id="4492e-108">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand **BizTalk Server Administration**, **BizTalk Group**, **Applications**, and then **BizTalk Application 1**.</span></span> <span data-ttu-id="4492e-109">右クリック**受信ポート**、 をポイント**新規**、 をクリックし、**一方向の受信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="4492e-109">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
2. <span data-ttu-id="4492e-110">受信ポートのプロパティ ダイアログ ボックスでの**名前**フィールドに、入力`ReceiveEDI_fromTHEM_A`します。</span><span class="sxs-lookup"><span data-stu-id="4492e-110">In the Receive Port Properties dialog box, in the **Name** field, enter `ReceiveEDI_fromTHEM_A`.</span></span>  
  
3. <span data-ttu-id="4492e-111">をクリックして**受信場所**コンソール ツリーをクリックで**新規**右側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="4492e-111">Click **Receive Locations** in the console tree, and then click **New** in the right-hand pane.</span></span>  
  
4. <span data-ttu-id="4492e-112">**受信場所のプロパティ** ダイアログ ボックスで、**名前**フィールドに、入力`fromTHEM_4010_850`します。</span><span class="sxs-lookup"><span data-stu-id="4492e-112">In the **Receive Location Properties** dialog box, in the **Name** field, enter `fromTHEM_4010_850`.</span></span>  
  
5. <span data-ttu-id="4492e-113">**型**を選択します**ファイル**、 をクリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="4492e-113">For **Type**, select **FILE**, and then click **Configure**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="4492e-114">テスト メッセージがフォルダーに配信されるフラット ファイルであるために、受信場所のトランスポートの種類はファイルです。</span><span class="sxs-lookup"><span data-stu-id="4492e-114">The transport type of the receive location is FILE because the test message is a flat file delivered into a folder.</span></span>  
  
6. <span data-ttu-id="4492e-115">**FILE トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**参照**横に、**受信フォルダー**フィールド。</span><span class="sxs-lookup"><span data-stu-id="4492e-115">In the **FILE Transport Properties** dialog box, click the **Browse** button next to the **Receive folder** field.</span></span> <span data-ttu-id="4492e-116">**フォルダーの参照** ダイアログ ボックスに移動[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \edi Interface Developer tutorial \processedi_testlocations\scenario a \fromthem をクリック**OK**します。</span><span class="sxs-lookup"><span data-stu-id="4492e-116">In the **Browse for Folder** dialog box, move to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations\Scenario A\fromTHEM, and then click **OK**.</span></span>  
  
7. <span data-ttu-id="4492e-117">**FILE トランスポートのプロパティ** ダイアログ ボックスで、変更、**ファイル マスク**に **\*.txt**  をクリック**OK**します。</span><span class="sxs-lookup"><span data-stu-id="4492e-117">In the **FILE Transport Properties** dialog box, change the **File mask** to **\*.txt** and click **OK**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="4492e-118">入力テスト メッセージがテキスト ファイル SamplePO.txt であるために、ファイル マスクは \*.txt に設定します。</span><span class="sxs-lookup"><span data-stu-id="4492e-118">The file mask is set to \*.txt because the input test message is a text file, SamplePO.txt.</span></span>  
  
8. <span data-ttu-id="4492e-119">**受信場所のプロパティ** ダイアログ ボックスで、**受信パイプライン**フィールドで、 **EdiReceive**します。</span><span class="sxs-lookup"><span data-stu-id="4492e-119">In the **Receive Location Properties** dialog box, in the **Receive Pipeline** field, select **EdiReceive**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="4492e-120">AS2 トランスポートを経由して配信されるものを除く、EDI インターチェンジを受信するために使用する受信パイプラインは、EdiReceive パイプラインです。</span><span class="sxs-lookup"><span data-stu-id="4492e-120">The receive pipeline used to receive EDI interchanges, except for those delivered over the AS2 transport, is the EdiReceive pipeline.</span></span> <span data-ttu-id="4492e-121">(AS2EdiReceive 受信パイプラインは AS2 トランスポート経由で配信される EDI インターチェンジの受信に使用します)。</span><span class="sxs-lookup"><span data-stu-id="4492e-121">(The AS2EdiReceive receive pipeline is used to receive EDI interchanges delivered over the AS2 transport.)</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="4492e-122">EdiReceive 受信パイプラインのドロップダウン リストが表示されていない場合、アプリケーションに、BizTalk EDI アプリケーションへの参照をことはできません。</span><span class="sxs-lookup"><span data-stu-id="4492e-122">If EdiReceive is not listed in the drop-down list for receive pipeline, your application may not have a reference to the BizTalk EDI Application.</span></span> <span data-ttu-id="4492e-123">参照を追加するを参照してください。 [、BizTalk Server EDI アプリケーションへの参照を追加する方法](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)します。</span><span class="sxs-lookup"><span data-stu-id="4492e-123">To add the reference, see [How to Add a Reference to the BizTalk Server EDI Application](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782).</span></span>  
  
9. <span data-ttu-id="4492e-124">をクリックして**OK**、順にクリックします**OK**もう一度です。</span><span class="sxs-lookup"><span data-stu-id="4492e-124">Click **OK**, and then click **OK** again.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="4492e-125">BizTalk サービスに対するログオン特権を持つアカウントが、fromTHEM_4010_850 受信場所に関連付けられた受信フォルダーの完全なアクセス許可を付与するもする必要があります ([!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\processedi_testlocations\fromthem)。</span><span class="sxs-lookup"><span data-stu-id="4492e-125">The account that has log-on privileges for the BizTalk service should also be granted full access permissions for the receive folder associated with the fromTHEM_4010_850 receive location ([!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\ProcessEDI_TestLocations\fromTHEM).</span></span> <span data-ttu-id="4492e-126">それ以外の場合は、受信場所を有効にする際、エラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4492e-126">If not, you will receive an error when attempting to enable the receive location.</span></span> <span data-ttu-id="4492e-127">受信フォルダーのアクセス許可を変更するには、[セキュリティ] タブに移動、**プロパティ**Windows エクスプ ローラーでは、そのフォルダーのダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="4492e-127">To change the access permissions for the receive folder, go to the Security tab in the **Properties** dialog box for that folder in Windows Explorer.</span></span>  
  
10. <span data-ttu-id="4492e-128">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、をクリックして**受信場所**、右クリック**fromTHEM_4010_850**、順にクリックします**を有効にする**します。</span><span class="sxs-lookup"><span data-stu-id="4492e-128">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, click **Receive Locations**, right-click **fromTHEM_4010_850**, and then click **Enable**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="4492e-129">次の手順</span><span class="sxs-lookup"><span data-stu-id="4492e-129">Next Steps</span></span>  
 <span data-ttu-id="4492e-130">送信ポートを構成する (**toOrderSystem**)」の説明に従って、850 メッセージを OrderSystem に送信する[手順 6。組織にデータを送信する送信ポートを構成する](../core/step-6-configure-a-send-port-to-send-data-to-your-organization.md)します。</span><span class="sxs-lookup"><span data-stu-id="4492e-130">You configure the send port (**toOrderSystem**) to send the 850 message to OrderSystem, as described in [Step 6: Configure a Send Port to Send Data to Your Organization](../core/step-6-configure-a-send-port-to-send-data-to-your-organization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4492e-131">参照</span><span class="sxs-lookup"><span data-stu-id="4492e-131">See Also</span></span>  
 [<span data-ttu-id="4492e-132">EDI メッセージおよび受信確認を受信するポートの構成</span><span class="sxs-lookup"><span data-stu-id="4492e-132">Configuring a Port to Receive EDI Messages and Acknowledgments</span></span>](../core/configuring-a-port-to-receive-edi-messages-and-acknowledgments.md)