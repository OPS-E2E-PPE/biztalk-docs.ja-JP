---
title: '手順 6: 構成 edi-as2 の受信場所 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 167f8ba2-d38b-4088-863b-2bd90c2a12a2
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d5ec3a7c253ab37a76846962cb348cd8b203a23
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009851"
---
# <a name="step-6-configure-the-edi-as2-receive-location"></a><span data-ttu-id="23681-102">手順 6: 構成 edi-as2 の受信場所</span><span class="sxs-lookup"><span data-stu-id="23681-102">Step 6: Configure the EDI-AS2 Receive Location</span></span>
<span data-ttu-id="23681-103">![手順 11 の 6](../core/media/tut-step6-of-11.gif "Tut_Step6_of_11")</span><span class="sxs-lookup"><span data-stu-id="23681-103">![Step 6 of 11](../core/media/tut-step6-of-11.gif "Tut_Step6_of_11")</span></span>  
  
 <span data-ttu-id="23681-104">このステップでは、Fabrikam パーティからの EDI メッセージを受信する一方向の受信場所を設定します。</span><span class="sxs-lookup"><span data-stu-id="23681-104">In this step, you set up a one-way receive location that receives the EDI message from the Fabrikam party.</span></span> <span data-ttu-id="23681-105">この受信場所では、AS2EdiReceive 受信パイプラインを使用して、送信されてくる EDI および AS2 メッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="23681-105">This receive location uses the AS2EdiReceive receive pipeline to process the incoming EDI/AS2 message.</span></span> <span data-ttu-id="23681-106">このメッセージは、sender.exe アプリケーションにより、Contoso 仮想ディレクトリを通じ、BTSHTTPReceive.dll ISAPI 拡張を使用して受信場所に送信されます。</span><span class="sxs-lookup"><span data-stu-id="23681-106">The message will be sent to the receive location by the sender.exe application through the Contoso virtual directory using the BTSHTTPReceive.dll ISAPI extension.</span></span>  
  
 <span data-ttu-id="23681-107">このチュートリアルでは、MDN 応答を非同期で送信する動的送信ポートを設定します。</span><span class="sxs-lookup"><span data-stu-id="23681-107">In this tutorial, you will set up a dynamic send port to send the MDN response asynchronously.</span></span> <span data-ttu-id="23681-108">このシナリオで必要となるのは、一方向の受信ポートだけです。</span><span class="sxs-lookup"><span data-stu-id="23681-108">In this scenario, only a one-way receive port is required.</span></span> <span data-ttu-id="23681-109">しかし、同期 MDN を指定する AS2 メッセージを送信するよう Sender.exe を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="23681-109">However, you could also change Sender.exe to send an AS2 message specifying a synchronous MDN.</span></span> <span data-ttu-id="23681-110">この場合、MDN を返信するため、双方向の要求応答受信ポートを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="23681-110">You would then have to create a two-way request response receive port to return the MDN.</span></span> <span data-ttu-id="23681-111">詳細については、のソリューションのテスト"するには」セクションを参照してください。[チュートリアル (AS2): 同期 MDN による AS2 経由での EDI の受信](../core/walkthrough-as2-receiving-edi-over-as2-with-a-synchronous-mdn.md)します。</span><span class="sxs-lookup"><span data-stu-id="23681-111">For more information, see the "To test the solution" section of [Walkthrough (AS2): Receiving EDI over AS2 with a Synchronous MDN](../core/walkthrough-as2-receiving-edi-over-as2-with-a-synchronous-mdn.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="23681-112">前提条件</span><span class="sxs-lookup"><span data-stu-id="23681-112">Prerequisites</span></span>  
 <span data-ttu-id="23681-113">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="23681-113">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-create-the-biztalk-http-receive-location"></a><span data-ttu-id="23681-114">BizTalk HTTP 受信場所を作成するには</span><span class="sxs-lookup"><span data-stu-id="23681-114">To create the BizTalk HTTP receive location</span></span>  
  
1. <span data-ttu-id="23681-115">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[BizTalk アプリケーション 1] ノードを右クリックして**受信ポート**、 をポイント**新規**、 をクリックし、**一方向の受信ポート**.</span><span class="sxs-lookup"><span data-stu-id="23681-115">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, under the BizTalk Application 1 node, right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
2. <span data-ttu-id="23681-116">受信ポートに名前を付けます**Receive_AS2**します。</span><span class="sxs-lookup"><span data-stu-id="23681-116">Name the receive port as **Receive_AS2**.</span></span>  
  
3. <span data-ttu-id="23681-117">をクリックして**受信場所**コンソール ツリーをクリックで**新規**します。</span><span class="sxs-lookup"><span data-stu-id="23681-117">Click **Receive Locations** in the console tree, and then click **New**.</span></span>  
  
4. <span data-ttu-id="23681-118">**受信場所のプロパティ**ダイアログ ボックスで、名前、受信場所**Receive_AS2**を選択します**HTTP**の**型**、し、クリックして**構成**します。</span><span class="sxs-lookup"><span data-stu-id="23681-118">In the **Receive Location Properties** dialog box, name your receive location **Receive_AS2**, select **HTTP** for **Type**, and then click **Configure**.</span></span>  
  
5. <span data-ttu-id="23681-119">**HTTP トランスポートのプロパティ** ダイアログ ボックスに、入力 **/Contoso/BTSHTTPReceive.dll**の**仮想ディレクトリと ISAPI 拡張**します。</span><span class="sxs-lookup"><span data-stu-id="23681-119">In the **HTTP Transport Properties** dialog box, enter **/Contoso/BTSHTTPReceive.dll** for **Virtual directory plus ISAPI extension**.</span></span> <span data-ttu-id="23681-120">クリア**成功した場合の戻り値の関連付けハンドル**選択**失敗した要求を中断**します。</span><span class="sxs-lookup"><span data-stu-id="23681-120">Clear **Return correlation handle on success** and select **Suspend failed requests**.</span></span> <span data-ttu-id="23681-121">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="23681-121">Click **OK**.</span></span>  
  
6. <span data-ttu-id="23681-122">選択**AS2EdiReceive**の**受信パイプライン**します。</span><span class="sxs-lookup"><span data-stu-id="23681-122">Select **AS2EdiReceive** for the **Receive Pipeline**.</span></span> <span data-ttu-id="23681-123">をクリックして**OK**、順にクリックします**OK**もう一度です。</span><span class="sxs-lookup"><span data-stu-id="23681-123">Click **OK**, and then click **OK** again.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="23681-124">AS2EdiReceive 受信パイプラインは、AS2 のデコードと EDI の逆アセンブルを実行します。</span><span class="sxs-lookup"><span data-stu-id="23681-124">The AS2EdiReceive receive pipeline performs AS2 decoding and EDI disassembly.</span></span>  
  
7. <span data-ttu-id="23681-125">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、をクリックして**受信場所**[BizTalk アプリケーション 1] ノードを右クリックして**Receive_AS2**、 をクリックし、**を有効にする**.</span><span class="sxs-lookup"><span data-stu-id="23681-125">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, click **Receive Locations** under the BizTalk Application 1 node, right-click **Receive_AS2**, and then click **Enable**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="23681-126">次の手順</span><span class="sxs-lookup"><span data-stu-id="23681-126">Next Steps</span></span>  
 <span data-ttu-id="23681-127">送信ポートを構成する (**Send_Asynch_MDN**)」の説明に従って、非同期 MDN を Fabrikam に送信するポートを送信[手順 7: MDN 送信ポートの構成](../core/step-7-configure-the-mdn-send-port.md)します。</span><span class="sxs-lookup"><span data-stu-id="23681-127">You configure the send port (**Send_Asynch_MDN**) send port to send the asynchronous MDN back to Fabrikam, as described in [Step 7: Configure the MDN Send Port](../core/step-7-configure-the-mdn-send-port.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23681-128">参照</span><span class="sxs-lookup"><span data-stu-id="23681-128">See Also</span></span>  
 <span data-ttu-id="23681-129">[BizTalk Server が AS2 メッセージを受信する方法](../core/how-biztalk-server-receives-as2-messages.md) </span><span class="sxs-lookup"><span data-stu-id="23681-129">[How BizTalk Server Receives AS2 Messages](../core/how-biztalk-server-receives-as2-messages.md) </span></span>  
 [<span data-ttu-id="23681-130">AS2 経由でのメッセージの受信ポートの構成</span><span class="sxs-lookup"><span data-stu-id="23681-130">Configuring a Receive Port for Messages over AS2</span></span>](../core/configuring-a-receive-port-for-messages-over-as2.md)