---
title: 孤立したメッセージまたは重複するメッセージを処理する送信ポートの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, duplicate messages
- messages, orphaned messages
- send ports, duplicate messages
- send ports, orphaned messages
- messages, send ports
ms.assetid: 61d51206-13e3-4d32-a184-866248db9b45
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d4a6e166a891da2a3d393d176555c2b50deed044
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65284843"
---
# <a name="creating-a-send-port-to-handle-orphan-or-duplicate-messages"></a><span data-ttu-id="b7f10-102">孤立したメッセージまたは重複するメッセージを処理する送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="b7f10-102">Creating a Send Port to Handle Orphan or Duplicate Messages</span></span>
<span data-ttu-id="b7f10-103">このトピックでは、孤立したメッセージまたは重複するメッセージを削除するために使用できる送信ポートを設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b7f10-103">This topic describes how to set up a send port that you can use to delete orphan or duplicate messages.</span></span>  
  
 <span data-ttu-id="b7f10-104">孤立したメッセージまたは重複メッセージは、場合に、問題になる可能性 Microsoft®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]パブリック プロセス オーケストレーションのメッセージの最初のコピー処理が完了した後、メッセージの追加のコピーを受信します。</span><span class="sxs-lookup"><span data-stu-id="b7f10-104">Orphan or duplicate messages can be a problem if Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] receives additional copies of a message after the public-process orchestration has completed processing the first copy of the message.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] <span data-ttu-id="b7f10-105">これらのメッセージを重複としてマークし、それらを中断します。</span><span class="sxs-lookup"><span data-stu-id="b7f10-105">marks those messages as duplicates and suspends them.</span></span> <span data-ttu-id="b7f10-106">BizTalk 管理コンソールで、これらのメッセージを表示できます。</span><span class="sxs-lookup"><span data-stu-id="b7f10-106">You can view these messages in the BizTalk Administration Console.</span></span> <span data-ttu-id="b7f10-107">BizTalk 管理コンソールの詳細については、「を使用して、BizTalk 管理コンソール」で、BizTalk Server ヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7f10-107">For more information about BizTalk Administration Console, see "Using the BizTalk Administration Console" in the BizTalk Server Help.</span></span>  
  
 <span data-ttu-id="b7f10-108">孤立したメッセージまたは重複メッセージは、確認するか、それらを削除するまでは、BizTalk 管理コンソールに残ります。</span><span class="sxs-lookup"><span data-stu-id="b7f10-108">Orphan or duplicate messages remain in the BizTalk Administration Console until you review or delete them.</span></span> <span data-ttu-id="b7f10-109">それらを削除する最も効果的な方法では、孤立したメッセージまたは重複するメッセージに設定されているフィルターと送信ポートを設定します。</span><span class="sxs-lookup"><span data-stu-id="b7f10-109">The most effective way of deleting them is to set up a send port with filters set for orphan or duplicate messages.</span></span> <span data-ttu-id="b7f10-110">BizTalk Server で使用可能な輸送手段を使用してそれらを移動することができます。</span><span class="sxs-lookup"><span data-stu-id="b7f10-110">You can move them using any transportation means available in BizTalk Server.</span></span> <span data-ttu-id="b7f10-111">たとえば、ファイル トランスポートを使用して、移動できます。</span><span class="sxs-lookup"><span data-stu-id="b7f10-111">For example, you can move them by using File transport.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] <span data-ttu-id="b7f10-112">ハード ディスク上の場所にファイルとして、孤立したメッセージまたは重複するメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="b7f10-112">sends the orphan or duplicate messages as files to a location on a hard disk.</span></span> <span data-ttu-id="b7f10-113">これにより、それらを簡単に削除します。</span><span class="sxs-lookup"><span data-stu-id="b7f10-113">This lets you to delete them easily.</span></span> <span data-ttu-id="b7f10-114">参加していると、停止状態で、中断状態としてのすべてのメッセージが送信された場合は表示その送信ポート、ポートを指定できます。</span><span class="sxs-lookup"><span data-stu-id="b7f10-114">The port can be in the enlisted and stopped state, in which case all messages sent to it will show as suspended under that send port.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b7f10-115">重複/孤立したメッセージを処理する送信ポートを作成する代わりに、これらのメッセージをメッセージ ボックス データベースから削除する特別なパイプライン コンポーネントを作成できます。</span><span class="sxs-lookup"><span data-stu-id="b7f10-115">Instead of creating a send port to handle duplicate/orphan messages, you can create a special pipeline component to delete these messages from the MessageBox database.</span></span> <span data-ttu-id="b7f10-116">内の FixMsg コンポーネントを使用することができます、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] SDK テンプレートとして。</span><span class="sxs-lookup"><span data-stu-id="b7f10-116">You can use the FixMsg component in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] SDK as a template.</span></span> <span data-ttu-id="b7f10-117">変更する必要がある、`IComponent.Execute`メソッドは null を返します。</span><span class="sxs-lookup"><span data-stu-id="b7f10-117">You have to modify the `IComponent.Execute` method to return null.</span></span> <span data-ttu-id="b7f10-118">これにより、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]コンポーネントを含むパイプラインに送信されたメッセージを破棄します。</span><span class="sxs-lookup"><span data-stu-id="b7f10-118">This causes [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] to discard any message sent to a pipeline that contains the component.</span></span> <span data-ttu-id="b7f10-119">このパイプライン コンポーネントをコンパイルし送信パイプラインに追加して、コンパイル、展開、およびシンク ポートの送信パイプラインを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7f10-119">You have to compile this pipeline component and add it to a send pipeline, and then compile, deploy, and select the send pipeline for the sink port.</span></span> <span data-ttu-id="b7f10-120">詳細については、次を参照してください。"CustomComponent ([!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]サンプル)"で BizTalk Server のヘルプ。</span><span class="sxs-lookup"><span data-stu-id="b7f10-120">For more information, see "CustomComponent ([!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Sample)" in BizTalk Server Help.</span></span>  
  
### <a name="to-create-a-send-port-to-handle-orphan-or-duplicate-messages"></a><span data-ttu-id="b7f10-121">孤立したメッセージまたは重複するメッセージを処理する送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="b7f10-121">To create a send port to handle orphan or duplicate messages</span></span>  
  
1. <span data-ttu-id="b7f10-122">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]の**ビュー** メニューのをクリックして**BizTalk エクスプ ローラー**です。</span><span class="sxs-lookup"><span data-stu-id="b7f10-122">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], on the **View** menu, click **BizTalk Explorer**.</span></span>  
  
2. <span data-ttu-id="b7f10-123">BizTalk エクスプ ローラーで、 **BizTalk 管理データベース**、順に展開**送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="b7f10-123">In BizTalk Explorer, expand **BizTalk Management Database**, and then expand **Send Ports**.</span></span>  
  
3. <span data-ttu-id="b7f10-124">右クリックして**送信ポート**、 をクリックし、**送信ポートの追加**します。</span><span class="sxs-lookup"><span data-stu-id="b7f10-124">Right-click **Send Ports**, and then click **Add Send Port**.</span></span>  
  
4. <span data-ttu-id="b7f10-125">新しい送信ポートを作成 ウィンドウで、次のように選択します。**静的な一方向ポート**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="b7f10-125">In the Create New Send Port window, select **Static One-Way Port**, and then click **OK**.</span></span>  
  
5. <span data-ttu-id="b7f10-126">静的な一方向送信ポートのプロパティ ウィンドウで、**名前**ボックスに、送信ポートの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="b7f10-126">In the Static One-Way Send Port Properties window, in the **Name** box, type a name for the send port.</span></span>  
  
6. <span data-ttu-id="b7f10-127">左側のウィンドウで次のようにクリックします。**トランスポート**します。</span><span class="sxs-lookup"><span data-stu-id="b7f10-127">In the left pane, click **Transport**.</span></span> <span data-ttu-id="b7f10-128">右側のウィンドウで次のようにクリックします。**トランスポートの種類**、選び**ファイル**トランスポートの種類。</span><span class="sxs-lookup"><span data-stu-id="b7f10-128">In the right pane, click **Transport Type**, and select **FILE** for the transport type.</span></span> <span data-ttu-id="b7f10-129">横にある省略記号ボタン (…) をクリックします。**アドレス (URI)**、ハード_ディスク上の場所を入力し、クリック**OK**します。</span><span class="sxs-lookup"><span data-stu-id="b7f10-129">Click the ellipsis button (...) next to **Address (URI)**, type a location on your hard disk, and then click **OK**.</span></span>  
  
7. <span data-ttu-id="b7f10-130">左側のウィンドウで次のようにクリックします。**送信**、] をクリック**送信パイプライン**、し、[ **Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**します。</span><span class="sxs-lookup"><span data-stu-id="b7f10-130">In the left pane, click **Send**, click **Send Pipeline**, and then select **Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**.</span></span>  
  
8. <span data-ttu-id="b7f10-131">左側のウィンドウで次のようにクリックします。**フィルターとマップ**、 をクリックし、**フィルター**します。</span><span class="sxs-lookup"><span data-stu-id="b7f10-131">In the left pane, click **Filters and Maps**, and then click **Filters**.</span></span>  
  
9. <span data-ttu-id="b7f10-132">右側のウィンドウで 1 行目の**プロパティ**を選択します**Microsoft.Solutions.BTARN.GlobalSchemas.IsDuplicateMessage**ままにしてドロップダウン リストから、**演算子**として**==**、入力**True**の**値**、し、**または**のドロップダウンリストから**グループ**します。</span><span class="sxs-lookup"><span data-stu-id="b7f10-132">On the first line in the right pane, for **Property**, select **Microsoft.Solutions.BTARN.GlobalSchemas.IsDuplicateMessage** from the drop-down list, leave the **Operator** as **==**, enter **True** for **Value**, and then select **Or** from the drop-down list for **Group**.</span></span>  
  
10. <span data-ttu-id="b7f10-133">右側のウィンドウで 2 行目の**プロパティ**を選択します**Microsoft.Solutions.BTARN.GlobalSchemas.IsOrphanMessage**ままにしてドロップダウン リストから、**演算子**として**==**、し、入力**True**の**値**します。</span><span class="sxs-lookup"><span data-stu-id="b7f10-133">On the second line in the right pane, for **Property**, select **Microsoft.Solutions.BTARN.GlobalSchemas.IsOrphanMessage** from the drop-down list, leave the **Operator** as **==**, and then enter **True** for **Value**.</span></span>  
  
11. <span data-ttu-id="b7f10-134">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7f10-134">Click **OK**.</span></span>  
  
12. <span data-ttu-id="b7f10-135">BizTalk エクスプ ローラーで、送信ポートの名前を右クリックして**参加**します。</span><span class="sxs-lookup"><span data-stu-id="b7f10-135">In BizTalk Explorer, right-click the name of the send port, click **Enlist**.</span></span> <span data-ttu-id="b7f10-136">送信ポートが参加して、送信ポートを右クリックし、クリックして**開始**します。</span><span class="sxs-lookup"><span data-stu-id="b7f10-136">After the send port has been enlisted, right-click the send port, and then click **Start**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7f10-137">参照</span><span class="sxs-lookup"><span data-stu-id="b7f10-137">See Also</span></span>  
 [<span data-ttu-id="b7f10-138">プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="b7f10-138">Programming Guide</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)