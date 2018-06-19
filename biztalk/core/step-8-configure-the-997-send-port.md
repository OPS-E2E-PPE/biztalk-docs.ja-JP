---
title: '手順 8: 997 送信ポートの構成 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4780c491-9f1a-4f13-b346-6a2e1801ec09
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec3c022ec1236d760c69250a2faecc7cacdb543c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277218"
---
# <a name="step-8-configure-the-997-send-port"></a><span data-ttu-id="b5a83-102">手順 8: 997 送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="b5a83-102">Step 8: Configure the 997 Send Port</span></span>
<span data-ttu-id="b5a83-103">![手順 11 の 8](../core/media/tut-step8-of-11.gif "Tut_Step8_of_11")</span><span class="sxs-lookup"><span data-stu-id="b5a83-103">![Step 8 of 11](../core/media/tut-step8-of-11.gif "Tut_Step8_of_11")</span></span>  
  
 <span data-ttu-id="b5a83-104">このステップでは、パートナーに 997 メッセージを送信するための送信ポートを設定します。</span><span class="sxs-lookup"><span data-stu-id="b5a83-104">In this step, you set up a send port to send the 997 message to the partner.</span></span> <span data-ttu-id="b5a83-105">この送信ポートは、AS2EdiSend 送信パイプラインを使用して、EDIINT/AS2 でエンコードされた 997 受信確認を _997ToFabrikam フォルダに送信します。</span><span class="sxs-lookup"><span data-stu-id="b5a83-105">This send port uses the AS2EdiSend send pipeline to transport an EDIINT/AS2-encoded 997 acknowledgment to the _997ToFabrikam folder.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b5a83-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="b5a83-106">Prerequisites</span></span>  
 <span data-ttu-id="b5a83-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5a83-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-create-the-sendasync997-send-port"></a><span data-ttu-id="b5a83-108">Send_Async_997 送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="b5a83-108">To create the Send_Async_997 send port</span></span>  
  
1.  <span data-ttu-id="b5a83-109">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[BizTalk アプリケーション 1] ノードを右クリックして**送信ポート**、指す**新規**、順にクリック**静的な一方向送信ポート**.</span><span class="sxs-lookup"><span data-stu-id="b5a83-109">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, under the BizTalk Application 1 node, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b5a83-110">AS2 メッセージ受信者としての Fabrikam パーティには MDN が設定されていないので、静的な一方向の送信ポートを使用します。</span><span class="sxs-lookup"><span data-stu-id="b5a83-110">You will use a static one-way send port because no MDN has been set up for the Fabrikam party as an AS2 message receiver.</span></span>  
  
2.  <span data-ttu-id="b5a83-111">**送信ポートのプロパティ** ダイアログ ボックスに、名前、送信ポートに**Send_Async_997**です。</span><span class="sxs-lookup"><span data-stu-id="b5a83-111">In the **Send Port Properties** dialog box, name your send port **Send_Async_997**.</span></span> <span data-ttu-id="b5a83-112">選択**HTTP**の**型**、クリックして**構成**です。</span><span class="sxs-lookup"><span data-stu-id="b5a83-112">Select **HTTP** for **Type**, and then click **Configure**.</span></span>  
  
3.  <span data-ttu-id="b5a83-113">**HTTP トランスポートのプロパティ** ダイアログ ボックスの**送信先 URL**、入力`http://localhost/Fabrikam/Default.aspx?Destination=_997ToFabrikam`です。</span><span class="sxs-lookup"><span data-stu-id="b5a83-113">In the **HTTP Transport Properties** dialog box, for **Destination URL**, enter `http://localhost/Fabrikam/Default.aspx?Destination=_997ToFabrikam`.</span></span> <span data-ttu-id="b5a83-114">クリア**有効チャンク エンコード** をクリックし、 **OK**です。</span><span class="sxs-lookup"><span data-stu-id="b5a83-114">Clear **Enable chunked encoding** and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b5a83-115">**送信先 URL**設定、送信ポートから Fabrikam 仮想ディレクトリに 997 メッセージを送信してされるようになります。</span><span class="sxs-lookup"><span data-stu-id="b5a83-115">The **Destination URL** setting ensures that the send port will send the 997 message to the Fabrikam virtual directory.</span></span> <span data-ttu-id="b5a83-116">この仮想ディレクトリに関連付けられている Default.aspx.cs ファイルが、.msg 拡張子を使用して 997 を構築し、送信先のフォルダに送信します。</span><span class="sxs-lookup"><span data-stu-id="b5a83-116">The Default.aspx.cs file associated with that virtual directory builds the 997 with an .msg extension, and sends it to the destination folder.</span></span>  
  
4.  <span data-ttu-id="b5a83-117">**送信ポートのプロパティ**ダイアログ ボックスで、 **AS2EdiSend**の**送信パイプライン**です。</span><span class="sxs-lookup"><span data-stu-id="b5a83-117">In the **Send Port Properties** dialog box, select **AS2EdiSend** for **Send Pipeline**.</span></span>  
  
5.  <span data-ttu-id="b5a83-118">をクリックして**フィルター**コンソール ツリーでします。</span><span class="sxs-lookup"><span data-stu-id="b5a83-118">Click **Filters** in the console tree.</span></span> <span data-ttu-id="b5a83-119">**プロパティ** **BTS です。MessageType**です。</span><span class="sxs-lookup"><span data-stu-id="b5a83-119">For **Property**, select **BTS.MessageType**.</span></span> <span data-ttu-id="b5a83-120">**演算子**  **==** です。</span><span class="sxs-lookup"><span data-stu-id="b5a83-120">For **Operator**, select **==**.</span></span> <span data-ttu-id="b5a83-121">**値**、入力`http://schemas.microsoft.com/Edi/X12#X12_997_Root`です。</span><span class="sxs-lookup"><span data-stu-id="b5a83-121">For **Value**, enter `http://schemas.microsoft.com/Edi/X12#X12_997_Root`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b5a83-122">このフィルタにより、送信ポートはメッセージ ボックスから 997 受信確認だけを取得するようになります。</span><span class="sxs-lookup"><span data-stu-id="b5a83-122">This filter ensures that the send port will only pick up 997 acknowledgments from the MessageBox.</span></span>  
  
6.  <span data-ttu-id="b5a83-123">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b5a83-123">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="b5a83-124">**送信ポート**のペイン、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、 **Send_Async_997**送信ポートをクリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="b5a83-124">In the **Send Ports** pane of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Send_Async_997** send port, and then click **Start**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="b5a83-125">次の手順</span><span class="sxs-lookup"><span data-stu-id="b5a83-125">Next Steps</span></span>  
 <span data-ttu-id="b5a83-126">送信ポートを構成する (**Send_Payload_EdiXml**)」の説明に従って、EDI ペイロードを Contoso に送信する[手順 9: EDI ペイロードの送信ポートを構成する](../core/step-9-configure-the-edi-payload-send-port.md)です。</span><span class="sxs-lookup"><span data-stu-id="b5a83-126">You configure the send port (**Send_Payload_EdiXml**) to send the EDI payload to Contoso, as described in [Step 9: Configure the EDI Payload Send Port](../core/step-9-configure-the-edi-payload-send-port.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5a83-127">参照</span><span class="sxs-lookup"><span data-stu-id="b5a83-127">See Also</span></span>  
 <span data-ttu-id="b5a83-128">[BizTalk Server が AS2 メッセージを送信する方法](../core/how-biztalk-server-sends-as2-messages.md) </span><span class="sxs-lookup"><span data-stu-id="b5a83-128">[How BizTalk Server Sends AS2 Messages](../core/how-biztalk-server-sends-as2-messages.md) </span></span>  
 [<span data-ttu-id="b5a83-129">AS2 経由でメッセージの静的送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="b5a83-129">Configuring a Static Send Port for Messages over AS2</span></span>](../core/configuring-a-static-send-port-for-messages-over-as2.md)