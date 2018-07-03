---
title: バッチ処理の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching, configuring
- configuring, batching
ms.assetid: 33c72d5e-31dd-44a8-8418-1faab3239e8e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77ea79c4b96ac54e6b2d1eed281b60a261ca5cc1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976331"
---
# <a name="configuring-batching"></a><span data-ttu-id="f44c3-102">バッチ処理の構成</span><span class="sxs-lookup"><span data-stu-id="f44c3-102">Configuring Batching</span></span>
<span data-ttu-id="f44c3-103">使用する[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]のバッチを作成する構成エクスプ ローラーでバッチ処理/バッチ送信バッチ処理の利用可能なスキーマを選択して、バッチ処理をします。</span><span class="sxs-lookup"><span data-stu-id="f44c3-103">You use [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] Configuration Explorer to create batch, batch in/batch out batching, and to select available schemas for outbound batching.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f44c3-104">メッセージのバッチ処理を構成する前に、BizTalk エクスプ ローラーを使用して取引先パートナーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f44c3-104">You must configure trading partners using BizTalk Explorer before you can configure message batching.</span></span>  
  
 <span data-ttu-id="f44c3-105">次に示します、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー**バッチ定義**タブ。</span><span class="sxs-lookup"><span data-stu-id="f44c3-105">The following figure shows the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer **Batch Definition** tab.</span></span>  
  
 <span data-ttu-id="f44c3-106">![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-ops-batchdef.gif "hl7_ops_batchdef")</span><span class="sxs-lookup"><span data-stu-id="f44c3-106">![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-ops-batchdef.gif "hl7_ops_batchdef")</span></span>  
  
 <span data-ttu-id="f44c3-107">次の手順を使用して開きます[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラーおよびバッチ処理を構成します。</span><span class="sxs-lookup"><span data-stu-id="f44c3-107">Use the following procedures to open [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer and configure batching.</span></span>  
  
### <a name="to-enable-message-batching-for-outbound-batching-create-batch"></a><span data-ttu-id="f44c3-108">メッセージの送信に (バッチの作成) をバッチ処理のバッチ処理を有効にするには</span><span class="sxs-lookup"><span data-stu-id="f44c3-108">To enable message batching for outbound batching (Create Batch)</span></span>  
  
1.  <span data-ttu-id="f44c3-109">**開始**] メニューの [open **BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="f44c3-109">In the **Start** menu, open **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="f44c3-110">管理コンソールで  **BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、順に展開**BizTalkアプリケーション 1**します。</span><span class="sxs-lookup"><span data-stu-id="f44c3-110">In the Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand **BizTalk Application 1**.</span></span>  
  
3.  <span data-ttu-id="f44c3-111">クリックして**オーケストレーション**を右クリックして**BatchOrchestration.Orchestration_1**、し、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="f44c3-111">Click **Orchestrations**, right-click **BatchOrchestration.Orchestration_1**, and then select **Properties**.</span></span>  
  
4.  <span data-ttu-id="f44c3-112">[オーケストレーションのプロパティ] ダイアログ ボックスで、**バインド**コンソール ツリーでします。</span><span class="sxs-lookup"><span data-stu-id="f44c3-112">In the Orchestration Properties dialog box, click **Bindings** in the console tree.</span></span>  
  
5.  <span data-ttu-id="f44c3-113">**バインド**ウィンドウで、適切なホストを選択**ホスト**します。</span><span class="sxs-lookup"><span data-stu-id="f44c3-113">In the **Bindings** pane, select the appropriate host for **Host**.</span></span> <span data-ttu-id="f44c3-114">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f44c3-114">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="f44c3-115">右クリックして**BatchOrchestration.Orchestration_1**、し、**参加**します。</span><span class="sxs-lookup"><span data-stu-id="f44c3-115">Right-click **BatchOrchestration.Orchestration_1**, and then select **Enlist**.</span></span>  
  
7.  <span data-ttu-id="f44c3-116">右クリックして**BatchOrchestration.Orchestration_1**、し、**開始**します。</span><span class="sxs-lookup"><span data-stu-id="f44c3-116">Right-click **BatchOrchestration.Orchestration_1**, and then select **Start**.</span></span>  
  
### <a name="to-run-btahl7-configuration-explorer"></a><span data-ttu-id="f44c3-117">BTAHL7 構成エクスプ ローラーを実行するには</span><span class="sxs-lookup"><span data-stu-id="f44c3-117">To run BTAHL7 Configuration Explorer</span></span>  
  
-   <span data-ttu-id="f44c3-118">**開始**] メニューの [open **Microsoft BizTalk Accelerator 用 HL7** 、順にクリックします**BTAHL7 構成エクスプ ローラー**します。</span><span class="sxs-lookup"><span data-stu-id="f44c3-118">In the **Start** menu, open **Microsoft BizTalk Accelerator for HL7** , and then click **BTAHL7 Configuration Explorer**.</span></span>  
  
### <a name="to-configure-batching"></a><span data-ttu-id="f44c3-119">バッチ処理を構成するには</span><span class="sxs-lookup"><span data-stu-id="f44c3-119">To configure batching</span></span>  
  
- <span data-ttu-id="f44c3-120">[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラーで、 **BTAHL7 構成エクスプ ローラー** ダイアログ ボックスで、**パーティ** タブで、構成するパーティを選択し、**バッチ定義** タブで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="f44c3-120">In [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer, in the **BTAHL7 Configuration Explorer** dialog box, on the **Parties** tab, select the party you want to configure, and then on the **Batch Definition** tab, do the following:</span></span>  
  
  |<span data-ttu-id="f44c3-121">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f44c3-121">Use this</span></span>|<span data-ttu-id="f44c3-122">目的</span><span class="sxs-lookup"><span data-stu-id="f44c3-122">To do this</span></span>|  
  |--------------|----------------|  
  |<span data-ttu-id="f44c3-123">**必要な断片化**</span><span class="sxs-lookup"><span data-stu-id="f44c3-123">**Fragmentation required**</span></span>|<span data-ttu-id="f44c3-124">以下のオプションの 1 つを選択します。</span><span class="sxs-lookup"><span data-stu-id="f44c3-124">Select one of the following options:</span></span><br /><br /> <span data-ttu-id="f44c3-125">-   **[はい]** します。</span><span class="sxs-lookup"><span data-stu-id="f44c3-125">-   **Yes**.</span></span> <span data-ttu-id="f44c3-126">断片化を有効にします。</span><span class="sxs-lookup"><span data-stu-id="f44c3-126">To enable fragmentation.</span></span><br /><span data-ttu-id="f44c3-127">-   **いいえ**します。</span><span class="sxs-lookup"><span data-stu-id="f44c3-127">-   **No**.</span></span> <span data-ttu-id="f44c3-128">断片化を無効にします。</span><span class="sxs-lookup"><span data-stu-id="f44c3-128">To disable fragmentation.</span></span> <span data-ttu-id="f44c3-129">**注:** 、新しいパーティの**断片化のために必要な**の既定値は**いいえ**します。</span><span class="sxs-lookup"><span data-stu-id="f44c3-129">**Note:**  For a new party, **Fragmentation Required** defaults to **No**.</span></span>|  
  |<span data-ttu-id="f44c3-130">**メッセージを選択します。**</span><span class="sxs-lookup"><span data-stu-id="f44c3-130">**Select Messages**</span></span>|<span data-ttu-id="f44c3-131">バッチとして送信するメッセージの種類を選択、**使用可能なメッセージ**ウィンドウで、移動、右矢印を順にクリックします (**>>**)。</span><span class="sxs-lookup"><span data-stu-id="f44c3-131">Select the message types you want to send as a batch from the **Available Messages** window, and then click the Move to the right arrow (**>>**).</span></span>|  
  |<span data-ttu-id="f44c3-132">**メッセージの受信確認を選択します。**</span><span class="sxs-lookup"><span data-stu-id="f44c3-132">**Select Message Acknowledgments**</span></span>|<span data-ttu-id="f44c3-133">バッチとして送信する受信確認を求めるメッセージの種類の選択、**使用可能なメッセージの Ack**ウィンドウで、右への移行を順にクリックします (**>>**)。</span><span class="sxs-lookup"><span data-stu-id="f44c3-133">Select the message types for which you want the acknowledgments to send as a batch from the **Available Message Acks** window, and then click the Move to the right (**>>**).</span></span>|  
  
  > [!NOTE]
  >  <span data-ttu-id="f44c3-134">追加するスキーマが表示されない場合がありますで[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]プロジェクトで[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラーが実行されています。</span><span class="sxs-lookup"><span data-stu-id="f44c3-134">You may not see schemas that you add to your In [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] project while In [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer is running.</span></span> <span data-ttu-id="f44c3-135">これらのファイルを表示するのには、再起動する必要があります[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー。</span><span class="sxs-lookup"><span data-stu-id="f44c3-135">In order to view these files, you may need to restart In [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f44c3-136">参照</span><span class="sxs-lookup"><span data-stu-id="f44c3-136">See Also</span></span>  
 [<span data-ttu-id="f44c3-137">バッチ処理のスケジュール</span><span class="sxs-lookup"><span data-stu-id="f44c3-137">Scheduling Batching</span></span>](../../adapters-and-accelerators/accelerator-hl7/scheduling-batching.md)