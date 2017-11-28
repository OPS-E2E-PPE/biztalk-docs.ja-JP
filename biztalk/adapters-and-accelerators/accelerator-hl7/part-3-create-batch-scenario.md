---
title: "パート 3: 作成バッチ シナリオ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- batching, creating
- creating, batching
ms.assetid: 02247186-5b21-4738-9110-f0ca0304f0fd
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0949d45fc70ead14338e30b554e0cb4b9694b5d5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="part-3-create-batch-scenario"></a><span data-ttu-id="dada7-102">パート 3: 作成するバッチのシナリオ</span><span class="sxs-lookup"><span data-stu-id="dada7-102">Part 3: Create-Batch Scenario</span></span>
<span data-ttu-id="dada7-103">このシナリオでは、2 つの受信メッセージの受信、してバッチのメッセージに結合して先にバッチを送信します。</span><span class="sxs-lookup"><span data-stu-id="dada7-103">In this part of the scenario, you receive two incoming messages, combine them into a batched message, and send the batch to a destination.</span></span> <span data-ttu-id="dada7-104">BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) ターゲットからソースへのメッセージの生成された 2 つの受信確認を含む、受信確認のバッチを返します。</span><span class="sxs-lookup"><span data-stu-id="dada7-104">BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) returns an acknowledgment batch containing the two acknowledgments generated for the messages from the destination to the source.</span></span> <span data-ttu-id="dada7-105">次の図は、チュートリアルのこの部分のプロセス フローを示しています。</span><span class="sxs-lookup"><span data-stu-id="dada7-105">The following figure shows the process flow of this part of the tutorial.</span></span>  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-create-batch-scenario.gif "hl7_create_batch_scenario")  
  
 <span data-ttu-id="dada7-106">**バッチの作成シナリオでのメッセージのフロー**</span><span class="sxs-lookup"><span data-stu-id="dada7-106">**How messages flow in the Create-Batch scenario**</span></span>  
  
 <span data-ttu-id="dada7-107">このシナリオには、次のワークフローが含まれます。</span><span class="sxs-lookup"><span data-stu-id="dada7-107">This scenario includes the following workflow:</span></span>  
  
-   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="dada7-108">メッセージ ボックス データベースにバッチの定義に準拠しているすべてのメッセージをトラップします。</span><span class="sxs-lookup"><span data-stu-id="dada7-108"> traps all messages conforming to the batch definition in the MessageBox database.</span></span> <span data-ttu-id="dada7-109">この定義でを入力する、**バッチ定義**のタブ[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー。</span><span class="sxs-lookup"><span data-stu-id="dada7-109">You enter this definition in the **Batch Definition** tab of [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer.</span></span> <span data-ttu-id="dada7-110">このチュートリアルでは[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]トラップして ADT のスキーマと Tutorial_BatchDest に送信されるすべてのメッセージをバッチ処理は ^ A03、および ADT の結果として Tutorial_BatchSource に送信されるすべての受信確認 ^ A03 メッセージ。</span><span class="sxs-lookup"><span data-stu-id="dada7-110">In this tutorial, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] will trap and batch all messages to be sent to Tutorial_BatchDest with a schema of ADT^A03, and all acknowledgments to be sent to Tutorial_BatchSource as a result of ADT^A03 messages.</span></span>  
  
-   <span data-ttu-id="dada7-111">スケジュールされたバッチの送信時の実行時に[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]送信バッチのトランザクションをトリガーするバッチ コントロール メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="dada7-111">When the scheduled batch send time occurs, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] sends a batch control message that triggers the outbound batch transaction.</span></span> <span data-ttu-id="dada7-112">上のスケジュールを定義する、**バッチ スケジュール**のタブ[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー。</span><span class="sxs-lookup"><span data-stu-id="dada7-112">You define the schedule on the **Batch Schedule** tab of [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer.</span></span> <span data-ttu-id="dada7-113">クリックして、プロセスをトリガーすることもできます。**今すぐ送信**同じタブにします。</span><span class="sxs-lookup"><span data-stu-id="dada7-113">You can also trigger the process by clicking **Send Now** on the same tab.</span></span>  
  
-   <span data-ttu-id="dada7-114">バッチ オーケストレーションは、メッセージ ボックス データベース内でトラップ メッセージからメッセージのバッチを形成します。</span><span class="sxs-lookup"><span data-stu-id="dada7-114">The batch orchestration forms the message batch out of the messages trapped in the MessageBox database.</span></span> <span data-ttu-id="dada7-115">オーケストレーションでは、ファイルのヘッダーとトレーラー、およびバッチ ヘッダーおよびトレーラーのバッチ処理もラップします。</span><span class="sxs-lookup"><span data-stu-id="dada7-115">The orchestration also wraps the batch in a file header and trailer, and a batch header and trailer.</span></span> <span data-ttu-id="dada7-116">このオーケストレーションは、ネイティブな[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]によって追加されたオーケストレーション[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]BizTalk エクスプ ローラーまたは BizTalk Server 管理コンソールで [オーケストレーション] ノードの下に記載されているため、BizTalk オーケストレーションのセットに設定します。</span><span class="sxs-lookup"><span data-stu-id="dada7-116">This orchestration is a native [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] orchestration added by [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] setup to your set of BizTalk orchestrations, so it is listed under the Orchestrations node in BizTalk Explorer or the BizTalk Server Administration Console.</span></span>  
  
-   <span data-ttu-id="dada7-117">場合 (この場合の場合と Tutorial_BatchSource)、受信確認が送信元パーティに対して定義されて、BizTalk の受信確認のバッチし (\Tutorial_BatchACKDrop フォルダー) に、バッチの形式で返します。</span><span class="sxs-lookup"><span data-stu-id="dada7-117">If acknowledgments are defined for the source party (as they are in this case for Tutorial_BatchSource), BizTalk batches the acknowledgments and returns them in a batch (to the \Tutorial_BatchACKDrop folder).</span></span> <span data-ttu-id="dada7-118">このチュートリアルでは、短い遅延後にバッチ処理された受信確認が送信されます。</span><span class="sxs-lookup"><span data-stu-id="dada7-118">In this tutorial, the batched acknowledgments are sent after a short delay.</span></span>  
  
-   <span data-ttu-id="dada7-119">オーケストレーションは、(この場合は、ハード ドライブ上の \Tutorial_BatchMsgDrop フォルダー) を変換先にバッチ メッセージを送信する送信ポート (Tutorial_BatchDest) にメッセージをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="dada7-119">The orchestration routes the message to the send port (Tutorial_BatchDest), which sends the batched message to the destination (in this case, the \Tutorial_BatchMsgDrop folder on your hard drive).</span></span> <span data-ttu-id="dada7-120">このチュートリアルでは、バッチ処理されたメッセージは 1 時間後に送信されます。</span><span class="sxs-lookup"><span data-stu-id="dada7-120">In this tutorial, the batched messages are sent after one hour.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dada7-121">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="dada7-121">In This Section</span></span>  
  
-   [<span data-ttu-id="dada7-122">手順 1: 構成して、受信ポートの有効化、BatchControlPort</span><span class="sxs-lookup"><span data-stu-id="dada7-122">Step 1: Configure and Enable the BatchControlPort Receive Port</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-1-configure-and-enable-the-batchcontrolport-receive-port.md)  
  
-   [<span data-ttu-id="dada7-123">手順 2: に、バッチ オーケストレーションが有効にします。</span><span class="sxs-lookup"><span data-stu-id="dada7-123">Step 2: Enable the Batch Orchestration</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-2-enable-the-batch-orchestration.md)  
  
-   [<span data-ttu-id="dada7-124">手順 3: を作成し、送信先パーティを構成します。</span><span class="sxs-lookup"><span data-stu-id="dada7-124">Step 3: Create and Configure a Destination Party</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-configure-a-destination-party.md)  
  
-   [<span data-ttu-id="dada7-125">手順 4: 作成バッチ シナリオでは、送信元パーティを構成します。</span><span class="sxs-lookup"><span data-stu-id="dada7-125">Step 4: Configure the Source Party for the Create-Batch Scenario</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-4-configure-the-source-party-for-the-create-batch-scenario.md)  
  
-   [<span data-ttu-id="dada7-126">手順 5: メッセージのバッチの送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="dada7-126">Step 5: Create the Send Port for the Message Batch</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-5-create-the-send-port-for-the-message-batch.md)  
  
-   [<span data-ttu-id="dada7-127">手順 6: 受信確認のバッチの送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="dada7-127">Step 6: Create the Send Port for the Acknowledgment Batch</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-6-create-the-send-port-for-the-acknowledgment-batch.md)  
  
-   [<span data-ttu-id="dada7-128">手順 7: オーケストレーションを開始し、BizTalk Server を再起動</span><span class="sxs-lookup"><span data-stu-id="dada7-128">Step 7: Start the Orchestration and Restart BizTalk Server</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-7-start-the-orchestration-and-restart-biztalk-server.md)  
  
-   [<span data-ttu-id="dada7-129">手順 8: 作成するバッチのシナリオをテストします。</span><span class="sxs-lookup"><span data-stu-id="dada7-129">Step 8: Test the Create-Batch Scenario</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-8-test-the-create-batch-scenario.md)