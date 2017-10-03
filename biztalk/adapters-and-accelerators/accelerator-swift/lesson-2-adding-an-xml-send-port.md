---
title: "レッスン 2: XML 送信ポートの追加 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send ports, XML ports
- XML ports
ms.assetid: 03b2ee43-7874-4ef9-b716-8e16e96d8382
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 06b110b911c8cba2dbc643928e8b97e3746935a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="lesson-2-adding-an-xml-send-port"></a><span data-ttu-id="b2cb1-102">レッスン 2: XML 送信ポートの追加</span><span class="sxs-lookup"><span data-stu-id="b2cb1-102">Lesson 2: Adding an XML Send Port</span></span>
<span data-ttu-id="b2cb1-103">送信ポートを使用して、メッセージを送信する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="b2cb1-103">You use a send port to define how you want the messages sent.</span></span> <span data-ttu-id="b2cb1-104">このレッスンでは、XML メッセージを送信する方法を定義する送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="b2cb1-104">In this lesson, you create a send port to define how XML messages should be sent.</span></span>  
  
### <a name="to-add-an-xml-send-port"></a><span data-ttu-id="b2cb1-105">XML 送信ポートを追加するには</span><span class="sxs-lookup"><span data-stu-id="b2cb1-105">To add an XML send port</span></span>  
  
1.  <span data-ttu-id="b2cb1-106">BizTalk Server 管理コンソールで、右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な一方向送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="b2cb1-106">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="b2cb1-107">送信ポートのプロパティ ダイアログ ボックスで、**名前**ボックスに、入力**MT103_XML_SendPort**です。</span><span class="sxs-lookup"><span data-stu-id="b2cb1-107">In the Send Port Properties dialog box, in the **Name** box, type **MT103_XML_SendPort**.</span></span>  
  
3.  <span data-ttu-id="b2cb1-108">**トランスポート**] セクションの**型**ボックス、ドロップダウン リストをクリックし、[**ファイル**です。</span><span class="sxs-lookup"><span data-stu-id="b2cb1-108">In the **Transport** section, for the **Type** box, click the drop-down list, and then select **FILE**.</span></span>  
  
4.  <span data-ttu-id="b2cb1-109">クリックして、**構成**型のドロップダウン リストの右側にあるボタンです。</span><span class="sxs-lookup"><span data-stu-id="b2cb1-109">Click the **Configure** button to the right of the Type drop-down list.</span></span>  
  
5.  <span data-ttu-id="b2cb1-110">[FILE トランスポートのプロパティ] ダイアログ ボックスで、**参照**です。</span><span class="sxs-lookup"><span data-stu-id="b2cb1-110">In the FILE Transport Properties dialog box, click **Browse**.</span></span>  
  
6.  <span data-ttu-id="b2cb1-111">フォルダーの参照 ダイアログ ボックスに移動、 **\<ドライブ >: \Labs\Outbound**フォルダーをクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="b2cb1-111">In the Browse For Folder dialog box, move to the **\<drive>:\Labs\Outbound** folder, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="b2cb1-112">FILE トランスポートのプロパティ ダイアログ ボックスでいることを確認**%MessageID%.xml**で入力した、**ファイル名**ボックスし、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="b2cb1-112">In the FILE Transport Properties dialog box, ensure that **%MessageID%.xml** is entered in the **File Name** box, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="b2cb1-113">送信ポートのプロパティ ダイアログ ボックスでいることを確認**BizTalkServerApplication**が選択されて、**送信ハンドラー**ボックスで、 **PassThruTransmit**が選択されて、**送信パイプライン**ボックス。</span><span class="sxs-lookup"><span data-stu-id="b2cb1-113">In the Send Port Properties dialog box, ensure that **BizTalkServerApplication** is selected for the **Send handler** box, and that **PassThruTransmit** is selected for the **Send pipeline** box.</span></span>  
  
9. <span data-ttu-id="b2cb1-114">左側のウィンドウでをクリックして**フィルター**、し、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b2cb1-114">In the left pane, click **Filters**, and then do the following:</span></span>  
  
    |<span data-ttu-id="b2cb1-115">プロパティ</span><span class="sxs-lookup"><span data-stu-id="b2cb1-115">Use this</span></span>|<span data-ttu-id="b2cb1-116">目的</span><span class="sxs-lookup"><span data-stu-id="b2cb1-116">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="b2cb1-117">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="b2cb1-117">**Property**</span></span>|<span data-ttu-id="b2cb1-118">選択**BTS です。ReceivePortName**です。</span><span class="sxs-lookup"><span data-stu-id="b2cb1-118">Select **BTS.ReceivePortName**.</span></span>|  
    |<span data-ttu-id="b2cb1-119">**演算子**</span><span class="sxs-lookup"><span data-stu-id="b2cb1-119">**Operator**</span></span>|<span data-ttu-id="b2cb1-120">選択 **==**です。</span><span class="sxs-lookup"><span data-stu-id="b2cb1-120">Select **==**.</span></span>|  
    |<span data-ttu-id="b2cb1-121">**値**</span><span class="sxs-lookup"><span data-stu-id="b2cb1-121">**Value**</span></span>|<span data-ttu-id="b2cb1-122">型**MT103_FlatFile_ReceivePort**です。</span><span class="sxs-lookup"><span data-stu-id="b2cb1-122">Type **MT103_FlatFile_ReceivePort**.</span></span>|  
    |<span data-ttu-id="b2cb1-123">**[グループ]**</span><span class="sxs-lookup"><span data-stu-id="b2cb1-123">**Group**</span></span>|<span data-ttu-id="b2cb1-124">選択**と**です。</span><span class="sxs-lookup"><span data-stu-id="b2cb1-124">Select **And**.</span></span>|  
  
10. <span data-ttu-id="b2cb1-125">プロパティの次の行の内側をクリックし、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="b2cb1-125">Click inside the next property line and do the following:</span></span>  
  
    |<span data-ttu-id="b2cb1-126">プロパティ</span><span class="sxs-lookup"><span data-stu-id="b2cb1-126">Use this</span></span>|<span data-ttu-id="b2cb1-127">目的</span><span class="sxs-lookup"><span data-stu-id="b2cb1-127">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="b2cb1-128">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="b2cb1-128">**Property**</span></span>|<span data-ttu-id="b2cb1-129">選択**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed**</span><span class="sxs-lookup"><span data-stu-id="b2cb1-129">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed**</span></span>|  
    |<span data-ttu-id="b2cb1-130">**演算子**</span><span class="sxs-lookup"><span data-stu-id="b2cb1-130">**Operator**</span></span>|<span data-ttu-id="b2cb1-131">選択 **==**です。</span><span class="sxs-lookup"><span data-stu-id="b2cb1-131">Select **==**.</span></span>|  
    |<span data-ttu-id="b2cb1-132">**値**</span><span class="sxs-lookup"><span data-stu-id="b2cb1-132">**Value**</span></span>|<span data-ttu-id="b2cb1-133">型**False**の有効なメッセージです。</span><span class="sxs-lookup"><span data-stu-id="b2cb1-133">Type **False** for valid messages.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="b2cb1-134">追加する、 **"Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed False = ="**フィルター式の句、送信ポートが送信するようにのみ正常に解析し、メッセージを検証します。</span><span class="sxs-lookup"><span data-stu-id="b2cb1-134">You add the **"Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed == False"** filter expression clause so that the send port sends only successfully parsed and validated messages.</span></span> <span data-ttu-id="b2cb1-135">ネイティブを使用して、受信パイプラインとは異なり[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、逆アセンブラー、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]逆アセンブラーは、失敗した (エラー) メッセージは中断されませんが、代わりに、メッセージ ボックスと昇格させたプロパティを使用して、失敗としてマークに公開します。</span><span class="sxs-lookup"><span data-stu-id="b2cb1-135">Unlike a receive pipeline using native [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] disassemblers, the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] disassembler will not suspend a failed (erroneous) message, but instead publishes it to the MessageBox and marks it as failed, using promoted properties.</span></span> <span data-ttu-id="b2cb1-136">A4SWIFT は、メッセージ ボックスに公開する前に、失敗したメッセージに収集されたエラーの XML 表現をアタッチします。</span><span class="sxs-lookup"><span data-stu-id="b2cb1-136">A4SWIFT attaches an XML representation of the errors that were collected to the failed message before publishing it to the MessageBox.</span></span>  
    > <span data-ttu-id="b2cb1-137">含めずに、"Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed = = False"フィルター式の句、送信ポートには、すべてのメッセージが送信されます。 成功または失敗します。</span><span class="sxs-lookup"><span data-stu-id="b2cb1-137">Without including the "Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed == False" filter expression clause, your send port will send all messages: passed or failed.</span></span> <span data-ttu-id="b2cb1-138">失敗したメッセージのサブスクリプションの詳細については、次を参照してください。[メッセージ サブスクリプションの失敗の操作](../../adapters-and-accelerators/accelerator-swift/working-with-failed-message-subscriptions.md)です。</span><span class="sxs-lookup"><span data-stu-id="b2cb1-138">For more information about failed message subscriptions, see [Working with Failed Message Subscriptions](../../adapters-and-accelerators/accelerator-swift/working-with-failed-message-subscriptions.md).</span></span>  
  
11. <span data-ttu-id="b2cb1-139">をクリックして**適用**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="b2cb1-139">Click **Apply**, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="b2cb1-140">BizTalk Server 管理コンソールで**送信ポート**を右クリックして**MT103_XML_SendPort**、クリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="b2cb1-140">In the BizTalk Server Administration Console, in **Send Ports**, right-click **MT103_XML_SendPort**, and then click **Start**.</span></span>  
  
 <span data-ttu-id="b2cb1-141">進みます[第 6 章: ビジネス ルールの展開](../../adapters-and-accelerators/accelerator-swift/module-6-deploying-the-business-rules.md)です。</span><span class="sxs-lookup"><span data-stu-id="b2cb1-141">Proceed to [Module 6: Deploying the Business Rules](../../adapters-and-accelerators/accelerator-swift/module-6-deploying-the-business-rules.md).</span></span>