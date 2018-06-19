---
title: Ack を受信するため、送信ポートの設定 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send ports, acknowledgements
- creating, send ports
- acknowledgements, send ports
- send ports, creating
ms.assetid: bb683e72-36e2-4a8f-acc2-8b37ed23746f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df0988a9edc2af81970237aad363315a778f821b
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
ms.locfileid: "25961608"
---
# <a name="setting-up-a-send-port-for-receiving-acks"></a><span data-ttu-id="aaad8-102">Ack を受信するための送信ポートの設定</span><span class="sxs-lookup"><span data-stu-id="aaad8-102">Setting Up a Send Port for Receiving ACKs</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="aaad8-103">BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 一方向の送信ポートで受信確認 (ACK) が表示されることができます。</span><span class="sxs-lookup"><span data-stu-id="aaad8-103"> BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) can receive acknowledgments (ACK) on a one-way send port.</span></span> <span data-ttu-id="aaad8-104">同じ接続の Ack を受信するための新しい一方向の送信ポートを設定するときは、その送信を関連付ける必要があります、一方向のポートの受信ポート。</span><span class="sxs-lookup"><span data-stu-id="aaad8-104">When you set up a new one-way send port for receiving ACKs on the same connection, you must associate that send port with a one-way receive port.</span></span>  
  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="aaad8-105">セットアップを作成、一方向受信ポート (と呼ばれる**TwoWayAckReceivePort**) と受信場所 (と呼ばれる**TwoWayAckReceiveLocation**)。</span><span class="sxs-lookup"><span data-stu-id="aaad8-105"> setup creates a one-way receive port (called **TwoWayAckReceivePort**) and receive location (called **TwoWayAckReceiveLocation**).</span></span> <span data-ttu-id="aaad8-106">受信場所、最小限の下位層プロトコル (MLLP) トランスポートの種類を使用して「127.0.0.1:65535」の URI を使用する、 **BTAHL72XReceivePipeline**です。</span><span class="sxs-lookup"><span data-stu-id="aaad8-106">The receive location uses the Minimal Lower Layer Protocol (MLLP) transport type, has a URI of "127.0.0.1:65535", and uses the **BTAHL72XReceivePipeline**.</span></span> <span data-ttu-id="aaad8-107">これらは、受信するために必要な設定とによって送信されたメッセージに対して受信 ACK の処理、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]双方向のモードで、アダプターを送信します。</span><span class="sxs-lookup"><span data-stu-id="aaad8-107">These are the settings required for receiving and processing an ACK received against a message sent out by the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] send adapter, in two-way mode.</span></span> <span data-ttu-id="aaad8-108">これは、受信場所を削除またはの他の目的で使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="aaad8-108">This receive location should not be deleted or used for any other purposes.</span></span> <span data-ttu-id="aaad8-109">データをこの受信場所に送信しないでください。</span><span class="sxs-lookup"><span data-stu-id="aaad8-109">Never send data to this receive location.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="aaad8-110">既定のこの受信場所で有効にします。</span><span class="sxs-lookup"><span data-stu-id="aaad8-110"> enables this receive location by default.</span></span>  
  
 <span data-ttu-id="aaad8-111">**TwoWayAckReceiveLocation**、どの、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]セットアップ ウィザードを作成、使用して、 **BizTalkServerApplication**受信ハンドラーとして。</span><span class="sxs-lookup"><span data-stu-id="aaad8-111">**TwoWayAckReceiveLocation**, which the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Setup Wizard creates, uses the **BizTalkServerApplication** as the receive handler.</span></span> <span data-ttu-id="aaad8-112">ただし、新しいホストを作成し、MLLP の受信ハンドラーとして使用する場合は、する必要があります、次の操作を新規作成する**TwoWayAckReceiveLocation**:</span><span class="sxs-lookup"><span data-stu-id="aaad8-112">However, if you choose to create a new host and use it as the receive handler for MLLP, then you must do the following to create a new **TwoWayAckReceiveLocation**:</span></span>  
  
1.  <span data-ttu-id="aaad8-113">作成、一方向受信ポート。</span><span class="sxs-lookup"><span data-stu-id="aaad8-113">Create a one-way receive port.</span></span>  
  
2.  <span data-ttu-id="aaad8-114">一方向作成 MLLP の受信場所。</span><span class="sxs-lookup"><span data-stu-id="aaad8-114">Create a one-way MLLP receive location.</span></span>  
  
3.  <span data-ttu-id="aaad8-115">MLLP トランスポートのプロパティの適切な値を指定します。</span><span class="sxs-lookup"><span data-stu-id="aaad8-115">Specify the appropriate values for the MLLP transport properties.</span></span>  
  
4.  <span data-ttu-id="aaad8-116">適切な受信ハンドラーを指定します。</span><span class="sxs-lookup"><span data-stu-id="aaad8-116">Specify the appropriate receive handler.</span></span>  
  
5.  <span data-ttu-id="aaad8-117">受信場所を有効化します。</span><span class="sxs-lookup"><span data-stu-id="aaad8-117">Enable the receive location.</span></span>  
  
### <a name="to-create-a-send-port-enabled-to-receive-an-ack-on-the-same-socket"></a><span data-ttu-id="aaad8-118">同じソケットで ACK の受信を有効になっている送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="aaad8-118">To create a send port enabled to receive an ACK on the same socket</span></span>  
  
1.  <span data-ttu-id="aaad8-119">BizTalk 管理コンソールを開き、展開**BizTalk Server 管理コンソール**、 **BizTalk グループ**、**アプリケーション**、および**BizTalkアプリケーション 1**です。</span><span class="sxs-lookup"><span data-stu-id="aaad8-119">Open the BizTalk Administration Console, and then expand **BizTalk Server Administration**, **BizTalk Group**, **Applications**, and **BizTalk Application 1**.</span></span> <span data-ttu-id="aaad8-120">右クリック**送信ポート**、新規作成 をポイントし、クリックして**静的な一方向送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="aaad8-120">Right-click **Send Ports**, point to New, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="aaad8-121">**名前**ボックスに、送信ポートの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="aaad8-121">In the **Name** box, type the name of the send port.</span></span>  
  
3.  <span data-ttu-id="aaad8-122">**トランスポート**] セクションの**型**[ **MLLP**です。</span><span class="sxs-lookup"><span data-stu-id="aaad8-122">In the **Transport** section, for **Type**, select **MLLP**.</span></span>  
  
4.  <span data-ttu-id="aaad8-123">クリックして **構成**します。</span><span class="sxs-lookup"><span data-stu-id="aaad8-123">Click **Configure**.</span></span>  
  
5.  <span data-ttu-id="aaad8-124">MLLP トランスポートのプロパティ ダイアログ ボックスで、ホストと接続の名前を入力します (たとえば、 **localhost**)。</span><span class="sxs-lookup"><span data-stu-id="aaad8-124">In the MLLP Transport Properties dialog box, type a connection name and host (for instance, **localhost**).</span></span>  
  
6.  <span data-ttu-id="aaad8-125">**送信請求-応答を有効に****はい**です。</span><span class="sxs-lookup"><span data-stu-id="aaad8-125">For **Solicit Response Enabled**, select **Yes**.</span></span> <span data-ttu-id="aaad8-126">ままにして**送信受信場所 (URI) を確認**空、クリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="aaad8-126">Leave **Submit Receive Location (URI) for ACK** blank, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="aaad8-127">ままにした場合**受信場所の送信**空白、BTAHL7 URI の入力、デフォルト**TwoWayAckReceiveLocation**です。</span><span class="sxs-lookup"><span data-stu-id="aaad8-127">When you leave **Submit Receive Location** blank, BTAHL7 enters the URI for the default **TwoWayAckReceiveLocation**.</span></span> <span data-ttu-id="aaad8-128">その後のクリックを確認する **[ok]** の手順 6 でをクリックして**構成**もう一度です。</span><span class="sxs-lookup"><span data-stu-id="aaad8-128">You can verify that after clicking **OK** in step 6, by clicking **Configuration** again.</span></span> <span data-ttu-id="aaad8-129">URI **TwoWayAckReceiveLocation**に入力されます (127.0.0.1:65535)**送信受信場所 (URI) を ACK**です。</span><span class="sxs-lookup"><span data-stu-id="aaad8-129">The URI for **TwoWayAckReceiveLocation** (127.0.0.1:65535) will be entered in **Submit Receive Location (URI) for ACK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="aaad8-130">受信確認をサブスクライブする送信ポートを作成する必要がありますか、ACK は、サブスクリプションが見つからなかったため、一時停止状態で表示されます。</span><span class="sxs-lookup"><span data-stu-id="aaad8-130">You must create a send port to subscribe to the ACK received, or the ACK will be seen in a suspended state, because no subscriptions were found.</span></span> <span data-ttu-id="aaad8-131">送信ポートで受信確認をサブスクライブする場合は、たとえば、フィルターを使用して**BTS です。MessageType = = \< *MessageType* \>** と**BTS です。ReceivePortName = = \< *ReceivePort*\>** です。</span><span class="sxs-lookup"><span data-stu-id="aaad8-131">To subscribe to the ACK received by the send port, use filters, for example, **BTS.MessageType == \<*MessageType*\>** and **BTS.ReceivePortName == \<*ReceivePort*\>**.</span></span> <span data-ttu-id="aaad8-132">メッセージの種類は、静的な確認の場合、 **StaticAck**です。</span><span class="sxs-lookup"><span data-stu-id="aaad8-132">For static ACKs, the message type is **StaticAck**.</span></span>  
  
7.  <span data-ttu-id="aaad8-133">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aaad8-133">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aaad8-134">参照</span><span class="sxs-lookup"><span data-stu-id="aaad8-134">See Also</span></span>  
 <span data-ttu-id="aaad8-135">[作成して、受信確認の処理](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span><span class="sxs-lookup"><span data-stu-id="aaad8-135">[Creating and Processing Acknowledgments](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span></span>  
 <span data-ttu-id="aaad8-136">[ACK メッセージ スキーマの種類](../../adapters-and-accelerators/accelerator-hl7/ack-message-schema-types.md) </span><span class="sxs-lookup"><span data-stu-id="aaad8-136">[ACK Message Schema Types](../../adapters-and-accelerators/accelerator-hl7/ack-message-schema-types.md) </span></span>  
 <span data-ttu-id="aaad8-137">[メッセージ受信確認セグメント](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md) </span><span class="sxs-lookup"><span data-stu-id="aaad8-137">[Message Acknowledgment Segment](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md) </span></span>  
 [<span data-ttu-id="aaad8-138">受信確認エラーの条件</span><span class="sxs-lookup"><span data-stu-id="aaad8-138">Acknowledgment Error Conditions</span></span>](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-error-conditions.md)