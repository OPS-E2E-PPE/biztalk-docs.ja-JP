---
title: 'レッスン 2: XML の送信ポートの追加 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send ports, XML ports
- XML ports
ms.assetid: 03b2ee43-7874-4ef9-b716-8e16e96d8382
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63d955b46ca007aea7ea74960e756520a82f43b6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005331"
---
# <a name="lesson-2-adding-an-xml-send-port"></a><span data-ttu-id="e42f6-102">レッスン 2: XML の送信ポートの追加</span><span class="sxs-lookup"><span data-stu-id="e42f6-102">Lesson 2: Adding an XML Send Port</span></span>
<span data-ttu-id="e42f6-103">送信メッセージを表示する方法を定義するのにには、送信ポートを使用します。</span><span class="sxs-lookup"><span data-stu-id="e42f6-103">You use a send port to define how you want the messages sent.</span></span> <span data-ttu-id="e42f6-104">このレッスンでは、XML メッセージを送信する方法を定義する送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="e42f6-104">In this lesson, you create a send port to define how XML messages should be sent.</span></span>  

### <a name="to-add-an-xml-send-port"></a><span data-ttu-id="e42f6-105">XML の送信ポートを追加するには</span><span class="sxs-lookup"><span data-stu-id="e42f6-105">To add an XML send port</span></span>  

1. <span data-ttu-id="e42f6-106">右クリックし、BizTalk Server 管理コンソールで**送信ポート**、 をポイント**新規**、 をクリックし、**静的な一方向送信ポート**。</span><span class="sxs-lookup"><span data-stu-id="e42f6-106">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  

2. <span data-ttu-id="e42f6-107">送信ポートのプロパティ ダイアログ ボックスでの**名前**ボックスに「 **MT103_XML_SendPort**します。</span><span class="sxs-lookup"><span data-stu-id="e42f6-107">In the Send Port Properties dialog box, in the **Name** box, type **MT103_XML_SendPort**.</span></span>  

3. <span data-ttu-id="e42f6-108">**トランスポート**セクションの**型**ボックス、ドロップダウン リストをクリックし、**ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="e42f6-108">In the **Transport** section, for the **Type** box, click the drop-down list, and then select **FILE**.</span></span>  

4. <span data-ttu-id="e42f6-109">をクリックして、**構成**型のドロップダウン リストの右側にボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e42f6-109">Click the **Configure** button to the right of the Type drop-down list.</span></span>  

5. <span data-ttu-id="e42f6-110">[FILE トランスポートのプロパティ] ダイアログ ボックスで、**参照**します。</span><span class="sxs-lookup"><span data-stu-id="e42f6-110">In the FILE Transport Properties dialog box, click **Browse**.</span></span>  

6. <span data-ttu-id="e42f6-111">フォルダーの参照 ダイアログ ボックスで、移動、 **\<ドライブ\>: \Labs\Outbound**フォルダー、およびクリック**ok**します。</span><span class="sxs-lookup"><span data-stu-id="e42f6-111">In the Browse For Folder dialog box, move to the **\<drive\>:\Labs\Outbound** folder, and then click **OK**.</span></span>  

7. <span data-ttu-id="e42f6-112">ファイル トランスポートのプロパティ ダイアログ ボックスで、ことを確認します **%MessageID%.xml**が入力されて、**ファイル名**ボックスをクリックして**OK**。</span><span class="sxs-lookup"><span data-stu-id="e42f6-112">In the FILE Transport Properties dialog box, ensure that **%MessageID%.xml** is entered in the **File Name** box, and then click **OK**.</span></span>  

8. <span data-ttu-id="e42f6-113">送信ポートのプロパティ ダイアログ ボックスで、ことを確認します**BizTalkServerApplication**が選択されている、**送信ハンドラー**ボックスで、 **PassThruTransmit**が選択されている、**送信パイプライン**ボックス。</span><span class="sxs-lookup"><span data-stu-id="e42f6-113">In the Send Port Properties dialog box, ensure that **BizTalkServerApplication** is selected for the **Send handler** box, and that **PassThruTransmit** is selected for the **Send pipeline** box.</span></span>  

9. <span data-ttu-id="e42f6-114">左側のウィンドウで次のようにクリックします。**フィルター**、し、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e42f6-114">In the left pane, click **Filters**, and then do the following:</span></span>  


   |   <span data-ttu-id="e42f6-115">プロパティ</span><span class="sxs-lookup"><span data-stu-id="e42f6-115">Use this</span></span>   |              <span data-ttu-id="e42f6-116">目的</span><span class="sxs-lookup"><span data-stu-id="e42f6-116">To do this</span></span>              |
   |--------------|--------------------------------------|
   | <span data-ttu-id="e42f6-117">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="e42f6-117">**Property**</span></span> |   <span data-ttu-id="e42f6-118">選択**BTS します。ReceivePortName**します。</span><span class="sxs-lookup"><span data-stu-id="e42f6-118">Select **BTS.ReceivePortName**.</span></span>    |
   | <span data-ttu-id="e42f6-119">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="e42f6-119">**Operator**</span></span> |            <span data-ttu-id="e42f6-120">選択 **==** します。</span><span class="sxs-lookup"><span data-stu-id="e42f6-120">Select **==**.</span></span>            |
   |  <span data-ttu-id="e42f6-121">**[値]**</span><span class="sxs-lookup"><span data-stu-id="e42f6-121">**Value**</span></span>   | <span data-ttu-id="e42f6-122">型**MT103_FlatFile_ReceivePort**します。</span><span class="sxs-lookup"><span data-stu-id="e42f6-122">Type **MT103_FlatFile_ReceivePort**.</span></span> |
   |  <span data-ttu-id="e42f6-123">**[グループ]**</span><span class="sxs-lookup"><span data-stu-id="e42f6-123">**Group**</span></span>   |           <span data-ttu-id="e42f6-124">選択**と**します。</span><span class="sxs-lookup"><span data-stu-id="e42f6-124">Select **And**.</span></span>            |


10. <span data-ttu-id="e42f6-125">プロパティの次の行の内側をクリックして、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e42f6-125">Click inside the next property line and do the following:</span></span>  

    |<span data-ttu-id="e42f6-126">プロパティ</span><span class="sxs-lookup"><span data-stu-id="e42f6-126">Use this</span></span>|<span data-ttu-id="e42f6-127">目的</span><span class="sxs-lookup"><span data-stu-id="e42f6-127">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="e42f6-128">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="e42f6-128">**Property**</span></span>|<span data-ttu-id="e42f6-129">選択**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed**</span><span class="sxs-lookup"><span data-stu-id="e42f6-129">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed**</span></span>|  
    |<span data-ttu-id="e42f6-130">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="e42f6-130">**Operator**</span></span>|<span data-ttu-id="e42f6-131">選択 **==** します。</span><span class="sxs-lookup"><span data-stu-id="e42f6-131">Select **==**.</span></span>|  
    |<span data-ttu-id="e42f6-132">**[値]**</span><span class="sxs-lookup"><span data-stu-id="e42f6-132">**Value**</span></span>|<span data-ttu-id="e42f6-133">型**False**の有効なメッセージ。</span><span class="sxs-lookup"><span data-stu-id="e42f6-133">Type **False** for valid messages.</span></span>|  

    > [!NOTE]
    >  <span data-ttu-id="e42f6-134">追加する、 **"Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed False = ="** フィルター式の句、送信ポートを送信できるようのみ正常に解析し、メッセージを検証します。</span><span class="sxs-lookup"><span data-stu-id="e42f6-134">You add the **"Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed == False"** filter expression clause so that the send port sends only successfully parsed and validated messages.</span></span> <span data-ttu-id="e42f6-135">ネイティブを使用して受信パイプラインとは異なり[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、逆アセンブラー、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]逆アセンブラーによって、失敗した (誤った) メッセージが中断されないが、代わりに、メッセージ ボックスと昇格させたプロパティを使用して、失敗としてマークに発行します。</span><span class="sxs-lookup"><span data-stu-id="e42f6-135">Unlike a receive pipeline using native [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] disassemblers, the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] disassembler will not suspend a failed (erroneous) message, but instead publishes it to the MessageBox and marks it as failed, using promoted properties.</span></span> <span data-ttu-id="e42f6-136">A4SWIFT は、失敗したメッセージをメッセージ ボックスに公開する前に収集されたエラーの XML 表現をアタッチします。</span><span class="sxs-lookup"><span data-stu-id="e42f6-136">A4SWIFT attaches an XML representation of the errors that were collected to the failed message before publishing it to the MessageBox.</span></span>  
    > <span data-ttu-id="e42f6-137">を含めなくても、"Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed False = ="フィルター式の句、送信ポートには、すべてのメッセージが送信されます。 成功または失敗します。</span><span class="sxs-lookup"><span data-stu-id="e42f6-137">Without including the "Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed == False" filter expression clause, your send port will send all messages: passed or failed.</span></span> <span data-ttu-id="e42f6-138">失敗したメッセージのサブスクリプションの詳細については、次を参照してください。[メッセージ サブスクリプションの失敗の操作](../../adapters-and-accelerators/accelerator-swift/working-with-failed-message-subscriptions.md)します。</span><span class="sxs-lookup"><span data-stu-id="e42f6-138">For more information about failed message subscriptions, see [Working with Failed Message Subscriptions](../../adapters-and-accelerators/accelerator-swift/working-with-failed-message-subscriptions.md).</span></span>  

11. <span data-ttu-id="e42f6-139">クリックして**適用**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="e42f6-139">Click **Apply**, and then click **OK**.</span></span>  

12. <span data-ttu-id="e42f6-140">BizTalk Server 管理コンソールで**送信ポート**を右クリックして**MT103_XML_SendPort**、順にクリックします**開始**します。</span><span class="sxs-lookup"><span data-stu-id="e42f6-140">In the BizTalk Server Administration Console, in **Send Ports**, right-click **MT103_XML_SendPort**, and then click **Start**.</span></span>  

    <span data-ttu-id="e42f6-141">進みます[モジュール 6: ビジネス ルールの展開](../../adapters-and-accelerators/accelerator-swift/module-6-deploying-the-business-rules.md)します。</span><span class="sxs-lookup"><span data-stu-id="e42f6-141">Proceed to [Module 6: Deploying the Business Rules](../../adapters-and-accelerators/accelerator-swift/module-6-deploying-the-business-rules.md).</span></span>