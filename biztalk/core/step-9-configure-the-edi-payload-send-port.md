---
title: "手順 9: EDI ペイロードの送信ポートの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 71a8a4a7-7c3e-4e33-a9c0-a6445a3cc236
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9de1dff24af11cd03cda2550dcab921aec25d585
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-9-configure-the-edi-payload-send-port"></a><span data-ttu-id="c7991-102">手順 9: EDI ペイロードの送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="c7991-102">Step 9: Configure the EDI Payload Send Port</span></span>
<span data-ttu-id="c7991-103">![手順 11 の 9](../core/media/tut-step9-of-11.gif "Tut_Step9_of_11")</span><span class="sxs-lookup"><span data-stu-id="c7991-103">![Step 9 of 11](../core/media/tut-step9-of-11.gif "Tut_Step9_of_11")</span></span>  
  
 <span data-ttu-id="c7991-104">によって表されるバックエンド Contoso アプリケーションに、EDI ペイロードから生成された XML を送信する送信ポートを設定するこの手順で、 \\_EDIXMLToContoso フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="c7991-104">In this step, you set up a send port to send the XML generated from the EDI payload to the back-end Contoso application, represented by the \\_EDIXMLToContoso folder.</span></span> <span data-ttu-id="c7991-105">この送信ポートは、PassThruTransmit 送信パイプラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="c7991-105">This send port uses a PassThruTransmit send pipeline.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c7991-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="c7991-106">Prerequisites</span></span>  
 <span data-ttu-id="c7991-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7991-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-create-the-sendpayloadedixml-send-port"></a><span data-ttu-id="c7991-108">Send_Payload_EdiXml 送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="c7991-108">To create the Send_Payload_EdiXml send port</span></span>  
  
1.  <span data-ttu-id="c7991-109">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックして**送信ポート**、 をポイント**新規**、クリックして**静的な一方向送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="c7991-109">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-Way Send Port**.</span></span>  
  
2.  <span data-ttu-id="c7991-110">**送信ポートのプロパティ** ダイアログ ボックスで、送信ポート名**Send_Payload_EdiXml**です。</span><span class="sxs-lookup"><span data-stu-id="c7991-110">In the **Send Port Properties** dialog box, name your send port as **Send_Payload_EdiXml**.</span></span> <span data-ttu-id="c7991-111">選択**ファイル**の**型**、クリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="c7991-111">Select **FILE** for **Type**, and then click **Configure**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c7991-112">送信パイプラインではペイロード ファイルの AS2 処理を行わないため、種類には [FILE] を指定します。</span><span class="sxs-lookup"><span data-stu-id="c7991-112">The FILE type is specified because the send pipeline is not performing AS2 processing on the payload file.</span></span> <span data-ttu-id="c7991-113">送信パイプラインでは、ペイロード ファイルをローカル フォルダにルーティングして、EDI トランザクション セットが表示されるようにするだけです。</span><span class="sxs-lookup"><span data-stu-id="c7991-113">It is just routing the payload file to a local folder so you can see the EDI transaction set.</span></span>  
  
3.  <span data-ttu-id="c7991-114">**FILE トランスポートのプロパティ** ダイアログ ボックスの**コピー先フォルダー**を参照して選択[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \as2 Tutorial\\_EDIXMLToContoso です。</span><span class="sxs-lookup"><span data-stu-id="c7991-114">In the **FILE Transport Properties** dialog box, for **Destination folder**, browse to and select [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\\_EDIXMLToContoso.</span></span> <span data-ttu-id="c7991-115">ままにして**ファイル名**として**%MessageID%.xml**です。</span><span class="sxs-lookup"><span data-stu-id="c7991-115">Leave **File name** as **%MessageID%.xml**.</span></span> <span data-ttu-id="c7991-116">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7991-116">Click **OK**.</span></span>  
  
4.  <span data-ttu-id="c7991-117">既定の**PassThruTransmit**の**送信パイプライン**です。</span><span class="sxs-lookup"><span data-stu-id="c7991-117">Accept the default of **PassThruTransmit** for **Send Pipeline**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c7991-118">PassThruTransmit 送信パイプラインを使用するため、パイプラインではペイロード メッセージの EDI 処理は実行されませんが、ペイロード メッセージは AS2EdiReceive receive パイプラインで生成された XML の形式でローカル フォルダに送信されます。</span><span class="sxs-lookup"><span data-stu-id="c7991-118">Because the PassThruTransmit send pipeline is used, the pipeline will not perform any EDI processing on the payload message, but will be sent to the local folder in the XML format produced by the AS2EdiReceive receive pipeline.</span></span>  
  
5.  <span data-ttu-id="c7991-119">をクリックして**フィルター**コンソール ツリーでします。</span><span class="sxs-lookup"><span data-stu-id="c7991-119">Click **Filters** in the console tree.</span></span> <span data-ttu-id="c7991-120">**プロパティ**、入力**BTS です。MessageType**です。</span><span class="sxs-lookup"><span data-stu-id="c7991-120">For **Property**, enter **BTS.MessageType**.</span></span> <span data-ttu-id="c7991-121">**演算子**、入力 **==**です。</span><span class="sxs-lookup"><span data-stu-id="c7991-121">For **Operator**, enter **==**.</span></span> <span data-ttu-id="c7991-122">**値**、入力`http://schemas.microsoft.com/BizTalk/Edi/X12/2006#X12_00401_864`です。</span><span class="sxs-lookup"><span data-stu-id="c7991-122">For **Value**, enter `http://schemas.microsoft.com/BizTalk/Edi/X12/2006#X12_00401_864`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c7991-123">このフィルタにより、この送信ポートはメッセージ ボックスから X12 864 ペイロード メッセージのみを取得するようになります。</span><span class="sxs-lookup"><span data-stu-id="c7991-123">This filter ensures that this send port will only pick up X12 864 payload messages from the MessageBox.</span></span>  
  
6.  <span data-ttu-id="c7991-124">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7991-124">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="c7991-125">**送信ポート**のペイン、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、 **Send_Payload_EdiXml**送信ポートをクリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="c7991-125">In the **Send Ports** pane of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Send_Payload_EdiXml** send port, and then click **Start**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="c7991-126">次の手順</span><span class="sxs-lookup"><span data-stu-id="c7991-126">Next Steps</span></span>  
 <span data-ttu-id="c7991-127">AS2 および X12 を作成する間、2 つの取引アグリーメントのパートナー、」の説明に従って[手順 10: X12 および AS2 取引先アグリーメントを構成します。](../core/step-10-configure-the-x12-and-as2-trading-partner-agreement.md)</span><span class="sxs-lookup"><span data-stu-id="c7991-127">You create an AS2 and X12 agreement between the two trading partners, as described in [Step 10: Configure the X12 and AS2 Trading Partner Agreement](../core/step-10-configure-the-x12-and-as2-trading-partner-agreement.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7991-128">参照</span><span class="sxs-lookup"><span data-stu-id="c7991-128">See Also</span></span>  
 [<span data-ttu-id="c7991-129">チュートリアル 3: AS2 チュートリアル</span><span class="sxs-lookup"><span data-stu-id="c7991-129">Tutorial 3: AS2 Tutorial</span></span>](../core/tutorial-3-as2-tutorial.md)