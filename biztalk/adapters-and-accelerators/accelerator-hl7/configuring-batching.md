---
title: "バッチ処理の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- batching, configuring
- configuring, batching
ms.assetid: 33c72d5e-31dd-44a8-8418-1faab3239e8e
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b9ab9ead01273e54826db670e7e6d6a2e9af6200
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-batching"></a><span data-ttu-id="c54a6-102">バッチ処理の構成</span><span class="sxs-lookup"><span data-stu-id="c54a6-102">Configuring Batching</span></span>
<span data-ttu-id="c54a6-103">使用する[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]バッチを作成する構成エクスプ ローラーでバッチ/バッチ送信バッチ処理の利用可能なスキーマを選択して、バッチ処理をします。</span><span class="sxs-lookup"><span data-stu-id="c54a6-103">You use [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] Configuration Explorer to create batch, batch in/batch out batching, and to select available schemas for outbound batching.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c54a6-104">メッセージのバッチ処理を構成する前に、BizTalk エクスプ ローラーを使用して取引先を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c54a6-104">You must configure trading partners using BizTalk Explorer before you can configure message batching.</span></span>  
  
 <span data-ttu-id="c54a6-105">次の図に示しています、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー**バッチ定義**タブです。</span><span class="sxs-lookup"><span data-stu-id="c54a6-105">The following figure shows the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer **Batch Definition** tab.</span></span>  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-ops-batchdef.gif "hl7_ops_batchdef")  
  
 <span data-ttu-id="c54a6-106">開くには、次の手順を使用して[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラーとバッチ処理を構成します。</span><span class="sxs-lookup"><span data-stu-id="c54a6-106">Use the following procedures to open [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer and configure batching.</span></span>  
  
### <a name="to-enable-message-batching-for-outbound-batching-create-batch"></a><span data-ttu-id="c54a6-107">メッセージの送信に (バッチの作成) をバッチ処理のバッチ処理を有効にするには</span><span class="sxs-lookup"><span data-stu-id="c54a6-107">To enable message batching for outbound batching (Create Batch)</span></span>  
  
1.  <span data-ttu-id="c54a6-108">**開始** メニューの 開いている**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="c54a6-108">In the **Start** menu, open **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="c54a6-109">管理コンソールで  **BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、順に展開**BizTalkアプリケーション 1**です。</span><span class="sxs-lookup"><span data-stu-id="c54a6-109">In the Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand **BizTalk Application 1**.</span></span>  
  
3.  <span data-ttu-id="c54a6-110">をクリックして**オーケストレーション**を右クリックして**BatchOrchestration.Orchestration_1**、し、**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="c54a6-110">Click **Orchestrations**, right-click **BatchOrchestration.Orchestration_1**, and then select **Properties**.</span></span>  
  
4.  <span data-ttu-id="c54a6-111">[オーケストレーションのプロパティ] ダイアログ ボックスで、**バインド**コンソール ツリーでします。</span><span class="sxs-lookup"><span data-stu-id="c54a6-111">In the Orchestration Properties dialog box, click **Bindings** in the console tree.</span></span>  
  
5.  <span data-ttu-id="c54a6-112">**バインド** ウィンドウで、適切なホストを選択して**ホスト**です。</span><span class="sxs-lookup"><span data-stu-id="c54a6-112">In the **Bindings** pane, select the appropriate host for **Host**.</span></span> <span data-ttu-id="c54a6-113">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c54a6-113">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="c54a6-114">右クリック**BatchOrchestration.Orchestration_1**、し、 **Enlist**です。</span><span class="sxs-lookup"><span data-stu-id="c54a6-114">Right-click **BatchOrchestration.Orchestration_1**, and then select **Enlist**.</span></span>  
  
7.  <span data-ttu-id="c54a6-115">右クリック**BatchOrchestration.Orchestration_1**、し、**開始**です。</span><span class="sxs-lookup"><span data-stu-id="c54a6-115">Right-click **BatchOrchestration.Orchestration_1**, and then select **Start**.</span></span>  
  
### <a name="to-run-btahl7-configuration-explorer"></a><span data-ttu-id="c54a6-116">BTAHL7 構成エクスプ ローラーを実行するには</span><span class="sxs-lookup"><span data-stu-id="c54a6-116">To run BTAHL7 Configuration Explorer</span></span>  
  
-   <span data-ttu-id="c54a6-117">**開始**メニューの 開く**Microsoft BizTalk Accelerator 用 HL7** 、クリックして**BTAHL7 構成エクスプ ローラー**です。</span><span class="sxs-lookup"><span data-stu-id="c54a6-117">In the **Start** menu, open **Microsoft BizTalk Accelerator for HL7** , and then click **BTAHL7 Configuration Explorer**.</span></span>  
  
### <a name="to-configure-batching"></a><span data-ttu-id="c54a6-118">バッチ処理を構成するには</span><span class="sxs-lookup"><span data-stu-id="c54a6-118">To configure batching</span></span>  
  
-   <span data-ttu-id="c54a6-119">[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラーで、 **BTAHL7 構成エクスプ ローラー** ダイアログ ボックスで、**パーティ** タブで、構成するパーティを選択し、**バッチ定義** タブで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="c54a6-119">In [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer, in the **BTAHL7 Configuration Explorer** dialog box, on the **Parties** tab, select the party you want to configure, and then on the **Batch Definition** tab, do the following:</span></span>  
  
    |<span data-ttu-id="c54a6-120">プロパティ</span><span class="sxs-lookup"><span data-stu-id="c54a6-120">Use this</span></span>|<span data-ttu-id="c54a6-121">目的</span><span class="sxs-lookup"><span data-stu-id="c54a6-121">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="c54a6-122">**断片化が必要**</span><span class="sxs-lookup"><span data-stu-id="c54a6-122">**Fragmentation required**</span></span>|<span data-ttu-id="c54a6-123">以下のオプションの 1 つを選択します。</span><span class="sxs-lookup"><span data-stu-id="c54a6-123">Select one of the following options:</span></span><br /><br /> <span data-ttu-id="c54a6-124">-   **[はい]**です。</span><span class="sxs-lookup"><span data-stu-id="c54a6-124">-   **Yes**.</span></span> <span data-ttu-id="c54a6-125">断片化を有効にします。</span><span class="sxs-lookup"><span data-stu-id="c54a6-125">To enable fragmentation.</span></span><br /><span data-ttu-id="c54a6-126">-   **いいえ**です。</span><span class="sxs-lookup"><span data-stu-id="c54a6-126">-   **No**.</span></span> <span data-ttu-id="c54a6-127">断片化を無効にします。</span><span class="sxs-lookup"><span data-stu-id="c54a6-127">To disable fragmentation.</span></span> <span data-ttu-id="c54a6-128">**注:** 、新しいパーティの**断片化のために必要な**の既定値は**いいえ**です。</span><span class="sxs-lookup"><span data-stu-id="c54a6-128">**Note:**  For a new party, **Fragmentation Required** defaults to **No**.</span></span>|  
    |<span data-ttu-id="c54a6-129">**メッセージを選択します。**</span><span class="sxs-lookup"><span data-stu-id="c54a6-129">**Select Messages**</span></span>|<span data-ttu-id="c54a6-130">バッチとして送信するメッセージの種類を選択して、**使用可能なメッセージ** ウィンドウで、移動、右矢印をクリックして (**>>**)。</span><span class="sxs-lookup"><span data-stu-id="c54a6-130">Select the message types you want to send as a batch from the **Available Messages** window, and then click the Move to the right arrow (**>>**).</span></span>|  
    |<span data-ttu-id="c54a6-131">**メッセージの受信確認を選択します。**</span><span class="sxs-lookup"><span data-stu-id="c54a6-131">**Select Message Acknowledgments**</span></span>|<span data-ttu-id="c54a6-132">バッチとして送信する受信確認を求めるメッセージの種類を選択して、**使用可能なメッセージの Ack**ウィンドウで、右へ移動をクリックし、(**>>**)。</span><span class="sxs-lookup"><span data-stu-id="c54a6-132">Select the message types for which you want the acknowledgments to send as a batch from the **Available Message Acks** window, and then click the Move to the right (**>>**).</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="c54a6-133">追加するスキーマが表示されない場合がありますで[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]プロジェクト内で[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラーが実行されています。</span><span class="sxs-lookup"><span data-stu-id="c54a6-133">You may not see schemas that you add to your In [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] project while In [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer is running.</span></span> <span data-ttu-id="c54a6-134">これらのファイルを表示するのを再起動する必要があります[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー。</span><span class="sxs-lookup"><span data-stu-id="c54a6-134">In order to view these files, you may need to restart In [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c54a6-135">参照</span><span class="sxs-lookup"><span data-stu-id="c54a6-135">See Also</span></span>  
 [<span data-ttu-id="c54a6-136">バッチ処理のスケジュール設定</span><span class="sxs-lookup"><span data-stu-id="c54a6-136">Scheduling Batching</span></span>](../../adapters-and-accelerators/accelerator-hl7/scheduling-batching.md)