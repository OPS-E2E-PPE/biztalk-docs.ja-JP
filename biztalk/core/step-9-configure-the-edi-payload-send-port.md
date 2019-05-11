---
title: 手順 9:EDI ペイロード送信ポートの構成 |Microsoft Docs
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
ms.openlocfilehash: 77a43ec4402cf2abf86d77e1d6d10512ff9d3694
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244218"
---
# <a name="step-9-configure-the-edi-payload-send-port"></a><span data-ttu-id="240ca-102">手順 9:EDI ペイロード送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="240ca-102">Step 9: Configure the EDI Payload Send Port</span></span>
<span data-ttu-id="240ca-103">![手順 11 の 9](../core/media/tut-step9-of-11.gif "Tut_Step9_of_11")</span><span class="sxs-lookup"><span data-stu-id="240ca-103">![Step 9 of 11](../core/media/tut-step9-of-11.gif "Tut_Step9_of_11")</span></span>  
  
 <span data-ttu-id="240ca-104">によって表されるバックエンド Contoso アプリケーションに、EDI ペイロードから生成される XML を送信する送信ポートを設定するこの手順で、 \\_EDIXMLToContoso フォルダー。</span><span class="sxs-lookup"><span data-stu-id="240ca-104">In this step, you set up a send port to send the XML generated from the EDI payload to the back-end Contoso application, represented by the \\_EDIXMLToContoso folder.</span></span> <span data-ttu-id="240ca-105">この送信ポートは、PassThruTransmit 送信パイプラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="240ca-105">This send port uses a PassThruTransmit send pipeline.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="240ca-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="240ca-106">Prerequisites</span></span>  
 <span data-ttu-id="240ca-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="240ca-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-create-the-sendpayloadedixml-send-port"></a><span data-ttu-id="240ca-108">Send_Payload_EdiXml 送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="240ca-108">To create the Send_Payload_EdiXml send port</span></span>  
  
1. <span data-ttu-id="240ca-109">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリックして**送信ポート**、 をポイント**新規**、順にクリックします**静的な一方向送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="240ca-109">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-Way Send Port**.</span></span>  
  
2. <span data-ttu-id="240ca-110">**送信ポートのプロパティ**ダイアログ ボックスで、送信ポートに名前**Send_Payload_EdiXml**します。</span><span class="sxs-lookup"><span data-stu-id="240ca-110">In the **Send Port Properties** dialog box, name your send port as **Send_Payload_EdiXml**.</span></span> <span data-ttu-id="240ca-111">選択**ファイル**の**型**、 をクリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="240ca-111">Select **FILE** for **Type**, and then click **Configure**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="240ca-112">ファイルの種類は、送信パイプラインがペイロード ファイルに AS2 処理が実行していないために指定されます。</span><span class="sxs-lookup"><span data-stu-id="240ca-112">The FILE type is specified because the send pipeline is not performing AS2 processing on the payload file.</span></span> <span data-ttu-id="240ca-113">EDI トランザクション セットを表示できるようにローカル フォルダーにペイロード ファイルのルーティングにはだけです。</span><span class="sxs-lookup"><span data-stu-id="240ca-113">It is just routing the payload file to a local folder so you can see the EDI transaction set.</span></span>  
  
3. <span data-ttu-id="240ca-114">**FILE トランスポートのプロパティ** ダイアログ ボックスの**先フォルダー**を参照して選択[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \as2 Tutorial\\_EDIXMLToContoso します。</span><span class="sxs-lookup"><span data-stu-id="240ca-114">In the **FILE Transport Properties** dialog box, for **Destination folder**, browse to and select [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\\_EDIXMLToContoso.</span></span> <span data-ttu-id="240ca-115">まま**ファイル名**として **%MessageID%.xml**します。</span><span class="sxs-lookup"><span data-stu-id="240ca-115">Leave **File name** as **%MessageID%.xml**.</span></span> <span data-ttu-id="240ca-116">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="240ca-116">Click **OK**.</span></span>  
  
4. <span data-ttu-id="240ca-117">既定の**PassThruTransmit**の**送信パイプライン**します。</span><span class="sxs-lookup"><span data-stu-id="240ca-117">Accept the default of **PassThruTransmit** for **Send Pipeline**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="240ca-118">PassThruTransmit 送信パイプラインを使用しているため、パイプラインは EDI ペイロード メッセージの処理は実行されませんが、AS2EdiReceive によって生成された XML 形式でローカル フォルダーに送信されます受信パイプライン。</span><span class="sxs-lookup"><span data-stu-id="240ca-118">Because the PassThruTransmit send pipeline is used, the pipeline will not perform any EDI processing on the payload message, but will be sent to the local folder in the XML format produced by the AS2EdiReceive receive pipeline.</span></span>  
  
5. <span data-ttu-id="240ca-119">クリックして**フィルター**コンソール ツリーでします。</span><span class="sxs-lookup"><span data-stu-id="240ca-119">Click **Filters** in the console tree.</span></span> <span data-ttu-id="240ca-120">**プロパティ**、入力**BTS します。MessageType**します。</span><span class="sxs-lookup"><span data-stu-id="240ca-120">For **Property**, enter **BTS.MessageType**.</span></span> <span data-ttu-id="240ca-121">**演算子**、入力 **==** します。</span><span class="sxs-lookup"><span data-stu-id="240ca-121">For **Operator**, enter **==**.</span></span> <span data-ttu-id="240ca-122">**値**、入力`http://schemas.microsoft.com/BizTalk/Edi/X12/2006#X12_00401_864`します。</span><span class="sxs-lookup"><span data-stu-id="240ca-122">For **Value**, enter `http://schemas.microsoft.com/BizTalk/Edi/X12/2006#X12_00401_864`.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="240ca-123">このフィルターにより、この送信ポートはのみ X12 864 ペイロード メッセージ、メッセージ ボックスから。</span><span class="sxs-lookup"><span data-stu-id="240ca-123">This filter ensures that this send port will only pick up X12 864 payload messages from the MessageBox.</span></span>  
  
6. <span data-ttu-id="240ca-124">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="240ca-124">Click **OK**.</span></span>  
  
7. <span data-ttu-id="240ca-125">**送信ポート**のウィンドウ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、 **Send_Payload_EdiXml**送信ポート、およびクリックして**開始**。</span><span class="sxs-lookup"><span data-stu-id="240ca-125">In the **Send Ports** pane of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Send_Payload_EdiXml** send port, and then click **Start**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="240ca-126">次の手順</span><span class="sxs-lookup"><span data-stu-id="240ca-126">Next Steps</span></span>  
 <span data-ttu-id="240ca-127">AS2 と X12 を作成する」の説明に従って、2 つの取引先アグリーメントがパートナー[手順 10。X12 および AS2 取引先アグリーメントを構成します。](../core/step-10-configure-the-x12-and-as2-trading-partner-agreement.md)</span><span class="sxs-lookup"><span data-stu-id="240ca-127">You create an AS2 and X12 agreement between the two trading partners, as described in [Step 10: Configure the X12 and AS2 Trading Partner Agreement](../core/step-10-configure-the-x12-and-as2-trading-partner-agreement.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="240ca-128">参照</span><span class="sxs-lookup"><span data-stu-id="240ca-128">See Also</span></span>  
 [<span data-ttu-id="240ca-129">チュートリアル 3: AS2 チュートリアル</span><span class="sxs-lookup"><span data-stu-id="240ca-129">Tutorial 3: AS2 Tutorial</span></span>](../core/tutorial-3-as2-tutorial.md)