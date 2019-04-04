---
title: '手順 7: MDN 送信ポートの構成 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 983033ac-9d32-47c8-9bb8-b4161bcdf183
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3e65ac8f264e1d8784c97645383b055391397da1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987747"
---
# <a name="step-7-configure-the-mdn-send-port"></a><span data-ttu-id="99539-102">手順 7: MDN 送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="99539-102">Step 7: Configure the MDN Send Port</span></span>
<span data-ttu-id="99539-103">![手順 11 の 7](../core/media/tut-step7-of-11.gif "Tut_Step7_of_11")</span><span class="sxs-lookup"><span data-stu-id="99539-103">![Step 7 of 11](../core/media/tut-step7-of-11.gif "Tut_Step7_of_11")</span></span>  
  
 <span data-ttu-id="99539-104">この手順で設定する動的送信ポートに非同期 MDN を送信する、 \\_MDNToFabrikam フォルダー。</span><span class="sxs-lookup"><span data-stu-id="99539-104">In this step, you set up a dynamic send port to send an asynchronous MDN to the \\_MDNToFabrikam folder.</span></span> <span data-ttu-id="99539-105">この送信ポートは、AS2Send 送信パイプラインを使用して送信 MDN 応答を生成します。</span><span class="sxs-lookup"><span data-stu-id="99539-105">This send port uses the AS2Send send pipeline to generate the outgoing MDN response.</span></span> <span data-ttu-id="99539-106">これは、動的送信ポートであるためにはアドレスを使用、メッセージのヘッダーの Receipt-delivery-option 行にするメッセージをルーティングする、 \\_MDNToFabrikam フォルダー。</span><span class="sxs-lookup"><span data-stu-id="99539-106">Since this is a dynamic send port, it will use the address in the Receipt-Delivery-Option line in the header of the message to route the message to the \\_MDNToFabrikam folder.</span></span> <span data-ttu-id="99539-107">そのアドレスは Fabrikam 仮想ディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="99539-107">That address is the Fabrikam virtual directory.</span></span> <span data-ttu-id="99539-108">その仮想ディレクトリに関連付けられている Default.aspx.cs ファィルは、.msg 拡張子を使用して MDN を構築し、このファイルを送信先のフォルダに送信します。送信先のフォルダも Receipt-Delivery-Option に指定されています。</span><span class="sxs-lookup"><span data-stu-id="99539-108">The Default.aspx.cs file associated with that virtual directory builds the MDN with an .msg extension, and sends the file to the destination folder (which is also specified in Receipt-Delivery-Option).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="99539-109">また、メッセージ設定をアグリーメント設定でオーバーライドすることで、別のアドレスに MDN を送信するようアグリーメントを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="99539-109">You can also configure the agreement to send the MDN to another address, by overriding the message settings with the agreement settings.</span></span> <span data-ttu-id="99539-110">詳細については、「</span><span class="sxs-lookup"><span data-stu-id="99539-110">For more information, see</span></span>  
  
 <span data-ttu-id="99539-111">この例で、MDN は動的送信ポートを使用して送信されます。しかし、静的送信ポートを使用して MDN を静的アドレスに送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="99539-111">In this example the MDN is sent using a dynamic send port; however you can also use a static send port to send the MDN to a static address.</span></span> <span data-ttu-id="99539-112">詳細については、[AS2 経由での非同期 Mdn の静的送信ポートを構成する](../core/configuring-a-static-send-port-for-asynchronous-mdns-over-as2.md)と[AS2 経由での非同期 Mdn の動的送信ポートを構成する](../core/configuring-a-dynamic-send-port-for-asynchronous-mdns-over-as2.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99539-112">For more information, see [Configuring a Static Send Port for Asynchronous MDNs over AS2](../core/configuring-a-static-send-port-for-asynchronous-mdns-over-as2.md) and [Configuring a Dynamic Send Port for Asynchronous MDNs over AS2](../core/configuring-a-dynamic-send-port-for-asynchronous-mdns-over-as2.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="99539-113">前提条件</span><span class="sxs-lookup"><span data-stu-id="99539-113">Prerequisites</span></span>  
 <span data-ttu-id="99539-114">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="99539-114">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-create-the-sendasyncmdn-send-port"></a><span data-ttu-id="99539-115">Send_Async_MDN 送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="99539-115">To create the Send_Async_MDN send port</span></span>  
  
1. <span data-ttu-id="99539-116">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[BizTalk アプリケーション 1] ノードを右クリックして**送信ポート**、 をポイント**新規**、 をクリックし、**動的の一方向送信ポート**.</span><span class="sxs-lookup"><span data-stu-id="99539-116">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, under the BizTalk Application 1 node, right-click **Send Ports**, point to **New**, and then click **Dynamic One-way Send Port**.</span></span>  
  
2. <span data-ttu-id="99539-117">**送信ポートのプロパティ**ダイアログ ボックスで、送信ポートの名前として**Send_Async_MDN**します。</span><span class="sxs-lookup"><span data-stu-id="99539-117">In the **Send Port Properties** dialog box, name the send port as **Send_Async_MDN**.</span></span>  
  
3. <span data-ttu-id="99539-118">選択**AS2Send**の**送信パイプライン**します。</span><span class="sxs-lookup"><span data-stu-id="99539-118">Select **AS2Send** for **Send pipeline**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="99539-119">MDN には EDI 処理が不要であるため、AS2Send パイプラインが使用されます。</span><span class="sxs-lookup"><span data-stu-id="99539-119">The AS2Send pipeline is used because no EDI processing is required for the MDN.</span></span>  
  
4. <span data-ttu-id="99539-120">クリックして**フィルター**コンソール ツリーでします。</span><span class="sxs-lookup"><span data-stu-id="99539-120">Click **Filters** in the console tree.</span></span> <span data-ttu-id="99539-121">フィルター ペインで選択**EdiIntAS.IsAS2AsynchronousMdn**の**プロパティ**、 **==** の**演算子**、しを入力します**True**の**値**します。</span><span class="sxs-lookup"><span data-stu-id="99539-121">In the Filters pane, select **EdiIntAS.IsAS2AsynchronousMdn** for **Property**, **==** for **Operator**, and enter **True** for **Value**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="99539-122">このフィルタにより、動的送信ポートは MessageBox から非同期の MDN のみを抽出するようになります。</span><span class="sxs-lookup"><span data-stu-id="99539-122">This filter ensures that the dynamic send port only picks up asynchronous MDNs from the MessageBox.</span></span>  
  
5. <span data-ttu-id="99539-123">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="99539-123">Click **OK**.</span></span>  
  
6. <span data-ttu-id="99539-124">**送信ポート**のウィンドウ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリック**Send_Async_MDN**、順にクリックします**開始**します。</span><span class="sxs-lookup"><span data-stu-id="99539-124">In the **Send Ports** pane of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click **Send_Async_MDN**, and then click **Start**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="99539-125">次の手順</span><span class="sxs-lookup"><span data-stu-id="99539-125">Next Steps</span></span>  
 <span data-ttu-id="99539-126">送信ポートを構成する (**Send_Async_997**) を 997 受信確認を Fabrikam に返信」の説明に従って[手順 8: 997 送信ポート構成](../core/step-8-configure-the-997-send-port.md)します。</span><span class="sxs-lookup"><span data-stu-id="99539-126">You configure the send port (**Send_Async_997**) to send the 997 acknowledgement back to Fabrikam, as described in [Step 8: Configure the 997 Send Port](../core/step-8-configure-the-997-send-port.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99539-127">参照</span><span class="sxs-lookup"><span data-stu-id="99539-127">See Also</span></span>  
 <span data-ttu-id="99539-128">[BizTalk Server が AS2 メッセージを送信する方法](../core/how-biztalk-server-sends-as2-messages.md) </span><span class="sxs-lookup"><span data-stu-id="99539-128">[How BizTalk Server Sends AS2 Messages](../core/how-biztalk-server-sends-as2-messages.md) </span></span>  
 <span data-ttu-id="99539-129">[AS2 経由での非同期 Mdn の静的送信ポートを構成します。](../core/configuring-a-static-send-port-for-asynchronous-mdns-over-as2.md) </span><span class="sxs-lookup"><span data-stu-id="99539-129">[Configuring a Static Send Port for Asynchronous MDNs over AS2](../core/configuring-a-static-send-port-for-asynchronous-mdns-over-as2.md) </span></span>  
 [<span data-ttu-id="99539-130">AS2 経由でのメッセージの動的送信ポートの構成</span><span class="sxs-lookup"><span data-stu-id="99539-130">Configuring a Dynamic Send Port for Messages over AS2</span></span>](../core/configuring-a-dynamic-send-port-for-messages-over-as2.md)