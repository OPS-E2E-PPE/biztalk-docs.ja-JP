---
title: '手順 9: EDI ペイロード送信ポートの構成 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 71a8a4a7-7c3e-4e33-a9c0-a6445a3cc236
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 11f12d57a0aee016055412b9221ff2b2de442c17
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005555"
---
# <a name="step-9-configure-the-edi-payload-send-port"></a><span data-ttu-id="54ce8-102">手順 9: EDI ペイロード送信ポートの構成します。</span><span class="sxs-lookup"><span data-stu-id="54ce8-102">Step 9: Configure the EDI Payload Send Port</span></span>
<span data-ttu-id="54ce8-103">![手順 11 の 9](../core/media/tut-step9-of-11.gif "Tut_Step9_of_11")</span><span class="sxs-lookup"><span data-stu-id="54ce8-103">![Step 9 of 11](../core/media/tut-step9-of-11.gif "Tut_Step9_of_11")</span></span>  
  
 <span data-ttu-id="54ce8-104">によって表されるバックエンド Contoso アプリケーションに、EDI ペイロードから生成される XML を送信する送信ポートを設定するこの手順で、 \\_EDIXMLToContoso フォルダー。</span><span class="sxs-lookup"><span data-stu-id="54ce8-104">In this step, you set up a send port to send the XML generated from the EDI payload to the back-end Contoso application, represented by the \\_EDIXMLToContoso folder.</span></span> <span data-ttu-id="54ce8-105">この送信ポートは、PassThruTransmit 送信パイプラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="54ce8-105">This send port uses a PassThruTransmit send pipeline.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="54ce8-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="54ce8-106">Prerequisites</span></span>  
 <span data-ttu-id="54ce8-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="54ce8-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-create-the-sendpayloadedixml-send-port"></a><span data-ttu-id="54ce8-108">Send_Payload_EdiXml 送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="54ce8-108">To create the Send_Payload_EdiXml send port</span></span>  
  
1. <span data-ttu-id="54ce8-109">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリックして**送信ポート**、 をポイント**新規**、順にクリックします**静的な一方向送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="54ce8-109">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-Way Send Port**.</span></span>  
  
2. <span data-ttu-id="54ce8-110">**送信ポートのプロパティ**ダイアログ ボックスで、送信ポートに名前**Send_Payload_EdiXml**します。</span><span class="sxs-lookup"><span data-stu-id="54ce8-110">In the **Send Port Properties** dialog box, name your send port as **Send_Payload_EdiXml**.</span></span> <span data-ttu-id="54ce8-111">選択**ファイル**の**型**、 をクリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="54ce8-111">Select **FILE** for **Type**, and then click **Configure**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="54ce8-112">送信パイプラインではペイロード ファイルの AS2 処理を行わないため、種類には [FILE] を指定します。</span><span class="sxs-lookup"><span data-stu-id="54ce8-112">The FILE type is specified because the send pipeline is not performing AS2 processing on the payload file.</span></span> <span data-ttu-id="54ce8-113">送信パイプラインでは、ペイロード ファイルをローカル フォルダにルーティングして、EDI トランザクション セットが表示されるようにするだけです。</span><span class="sxs-lookup"><span data-stu-id="54ce8-113">It is just routing the payload file to a local folder so you can see the EDI transaction set.</span></span>  
  
3. <span data-ttu-id="54ce8-114">**FILE トランスポートのプロパティ** ダイアログ ボックスの**先フォルダー**を参照して選択[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \as2 Tutorial\\_EDIXMLToContoso します。</span><span class="sxs-lookup"><span data-stu-id="54ce8-114">In the **FILE Transport Properties** dialog box, for **Destination folder**, browse to and select [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\\_EDIXMLToContoso.</span></span> <span data-ttu-id="54ce8-115">まま**ファイル名**として **%MessageID%.xml**します。</span><span class="sxs-lookup"><span data-stu-id="54ce8-115">Leave **File name** as **%MessageID%.xml**.</span></span> <span data-ttu-id="54ce8-116">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54ce8-116">Click **OK**.</span></span>  
  
4. <span data-ttu-id="54ce8-117">既定の**PassThruTransmit**の**送信パイプライン**します。</span><span class="sxs-lookup"><span data-stu-id="54ce8-117">Accept the default of **PassThruTransmit** for **Send Pipeline**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="54ce8-118">PassThruTransmit 送信パイプラインを使用するため、パイプラインではペイロード メッセージの EDI 処理は実行されませんが、ペイロード メッセージは AS2EdiReceive receive パイプラインで生成された XML の形式でローカル フォルダに送信されます。</span><span class="sxs-lookup"><span data-stu-id="54ce8-118">Because the PassThruTransmit send pipeline is used, the pipeline will not perform any EDI processing on the payload message, but will be sent to the local folder in the XML format produced by the AS2EdiReceive receive pipeline.</span></span>  
  
5. <span data-ttu-id="54ce8-119">クリックして**フィルター**コンソール ツリーでします。</span><span class="sxs-lookup"><span data-stu-id="54ce8-119">Click **Filters** in the console tree.</span></span> <span data-ttu-id="54ce8-120">**プロパティ**、入力**BTS します。MessageType**します。</span><span class="sxs-lookup"><span data-stu-id="54ce8-120">For **Property**, enter **BTS.MessageType**.</span></span> <span data-ttu-id="54ce8-121">**演算子**、入力 **==** します。</span><span class="sxs-lookup"><span data-stu-id="54ce8-121">For **Operator**, enter **==**.</span></span> <span data-ttu-id="54ce8-122">**値**、入力`http://schemas.microsoft.com/BizTalk/Edi/X12/2006#X12_00401_864`します。</span><span class="sxs-lookup"><span data-stu-id="54ce8-122">For **Value**, enter `http://schemas.microsoft.com/BizTalk/Edi/X12/2006#X12_00401_864`.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="54ce8-123">このフィルタにより、この送信ポートはメッセージ ボックスから X12 864 ペイロード メッセージのみを取得するようになります。</span><span class="sxs-lookup"><span data-stu-id="54ce8-123">This filter ensures that this send port will only pick up X12 864 payload messages from the MessageBox.</span></span>  
  
6. <span data-ttu-id="54ce8-124">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54ce8-124">Click **OK**.</span></span>  
  
7. <span data-ttu-id="54ce8-125">**送信ポート**のウィンドウ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、 **Send_Payload_EdiXml**送信ポート、およびクリックして**開始**。</span><span class="sxs-lookup"><span data-stu-id="54ce8-125">In the **Send Ports** pane of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Send_Payload_EdiXml** send port, and then click **Start**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="54ce8-126">次の手順</span><span class="sxs-lookup"><span data-stu-id="54ce8-126">Next Steps</span></span>  
 <span data-ttu-id="54ce8-127">AS2 と X12 を作成する」の説明に従って、2 つの取引先間のアグリーメントがパートナー[手順 10: X12 および AS2 取引先アグリーメントの構成](../core/step-10-configure-the-x12-and-as2-trading-partner-agreement.md)</span><span class="sxs-lookup"><span data-stu-id="54ce8-127">You create an AS2 and X12 agreement between the two trading partners, as described in [Step 10: Configure the X12 and AS2 Trading Partner Agreement](../core/step-10-configure-the-x12-and-as2-trading-partner-agreement.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54ce8-128">参照</span><span class="sxs-lookup"><span data-stu-id="54ce8-128">See Also</span></span>  
 [<span data-ttu-id="54ce8-129">チュートリアル 3: AS2 チュートリアル</span><span class="sxs-lookup"><span data-stu-id="54ce8-129">Tutorial 3: AS2 Tutorial</span></span>](../core/tutorial-3-as2-tutorial.md)