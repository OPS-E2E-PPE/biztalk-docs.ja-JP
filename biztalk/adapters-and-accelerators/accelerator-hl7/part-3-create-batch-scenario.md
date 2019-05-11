---
title: 'パート 3: バッチの作成シナリオ |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching, creating
- creating, batching
ms.assetid: 02247186-5b21-4738-9110-f0ca0304f0fd
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 439e285ddc432a57add0a9a719553eb532f12bbf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65290022"
---
# <a name="part-3-create-batch-scenario"></a><span data-ttu-id="bb036-102">パート 3: バッチの作成シナリオ</span><span class="sxs-lookup"><span data-stu-id="bb036-102">Part 3: Create-Batch Scenario</span></span>
<span data-ttu-id="bb036-103">このシナリオには、バッチ メッセージに結合する、およびを先にバッチを送信する 2 つの受信メッセージの受信します。</span><span class="sxs-lookup"><span data-stu-id="bb036-103">In this part of the scenario, you receive two incoming messages, combine them into a batched message, and send the batch to a destination.</span></span> <span data-ttu-id="bb036-104">BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)])、ソース、宛先からのメッセージに対して生成された 2 つの受信確認を含む、受信確認のバッチを返します。</span><span class="sxs-lookup"><span data-stu-id="bb036-104">BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) returns an acknowledgment batch containing the two acknowledgments generated for the messages from the destination to the source.</span></span> <span data-ttu-id="bb036-105">次の図は、このチュートリアルのこの部分の処理フローを示します。</span><span class="sxs-lookup"><span data-stu-id="bb036-105">The following figure shows the process flow of this part of the tutorial.</span></span>  
  
 <span data-ttu-id="bb036-106">![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-create-batch-scenario.gif "hl7_create_batch_scenario")</span><span class="sxs-lookup"><span data-stu-id="bb036-106">![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-create-batch-scenario.gif "hl7_create_batch_scenario")</span></span>  
  
 <span data-ttu-id="bb036-107">**バッチの作成シナリオでのメッセージのフロー**</span><span class="sxs-lookup"><span data-stu-id="bb036-107">**How messages flow in the Create-Batch scenario**</span></span>  
  
 <span data-ttu-id="bb036-108">このシナリオには、次のワークフローが含まれます。</span><span class="sxs-lookup"><span data-stu-id="bb036-108">This scenario includes the following workflow:</span></span>  
  
- [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="bb036-109">メッセージ ボックス データベースにバッチ定義に準拠しているすべてのメッセージをトラップします。</span><span class="sxs-lookup"><span data-stu-id="bb036-109">traps all messages conforming to the batch definition in the MessageBox database.</span></span> <span data-ttu-id="bb036-110">この定義での入力、**バッチ定義**のタブ[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー。</span><span class="sxs-lookup"><span data-stu-id="bb036-110">You enter this definition in the **Batch Definition** tab of [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer.</span></span> <span data-ttu-id="bb036-111">このチュートリアルで[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]トラップして ADT のスキーマと Tutorial_BatchDest に送信されるすべてのメッセージ バッチは ^ A03、および ADT の結果として Tutorial_BatchSource に送信されるすべての受信確認 ^ A03 メッセージ。</span><span class="sxs-lookup"><span data-stu-id="bb036-111">In this tutorial, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] will trap and batch all messages to be sent to Tutorial_BatchDest with a schema of ADT^A03, and all acknowledgments to be sent to Tutorial_BatchSource as a result of ADT^A03 messages.</span></span>  
  
- <span data-ttu-id="bb036-112">スケジュールされたバッチの送信時間が発生したときに[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]送信バッチのトランザクションをトリガーするバッチ コントロール メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="bb036-112">When the scheduled batch send time occurs, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] sends a batch control message that triggers the outbound batch transaction.</span></span> <span data-ttu-id="bb036-113">上のスケジュールを定義、**バッチ スケジュール**タブ[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー。</span><span class="sxs-lookup"><span data-stu-id="bb036-113">You define the schedule on the **Batch Schedule** tab of [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer.</span></span> <span data-ttu-id="bb036-114">クリックして、プロセスをトリガーすることもできます。**今すぐ送信**同じタブ。</span><span class="sxs-lookup"><span data-stu-id="bb036-114">You can also trigger the process by clicking **Send Now** on the same tab.</span></span>  
  
- <span data-ttu-id="bb036-115">バッチ オーケストレーションでは、メッセージ ボックス データベース内のトラップ メッセージからメッセージのバッチを形成します。</span><span class="sxs-lookup"><span data-stu-id="bb036-115">The batch orchestration forms the message batch out of the messages trapped in the MessageBox database.</span></span> <span data-ttu-id="bb036-116">オーケストレーションには、ファイルのヘッダーとトレーラー、およびバッチ ヘッダーおよびトレーラーのバッチ処理もラップします。</span><span class="sxs-lookup"><span data-stu-id="bb036-116">The orchestration also wraps the batch in a file header and trailer, and a batch header and trailer.</span></span> <span data-ttu-id="bb036-117">このオーケストレーションは、ネイティブ[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]によって追加されたオーケストレーション[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]を BizTalk エクスプ ローラーまたは BizTalk Server 管理コンソールでオーケストレーション ノードの下に記載されているため、BizTalk オーケストレーションのセットに設定します。</span><span class="sxs-lookup"><span data-stu-id="bb036-117">This orchestration is a native [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] orchestration added by [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] setup to your set of BizTalk orchestrations, so it is listed under the Orchestrations node in BizTalk Explorer or the BizTalk Server Administration Console.</span></span>  
  
- <span data-ttu-id="bb036-118">場合 (Tutorial_BatchSource をここでは) として、送信元パーティの受信確認が定義されて、BizTalk の受信確認をバッチ処理しバッチで (\Tutorial_BatchACKDrop フォルダー) に返します。</span><span class="sxs-lookup"><span data-stu-id="bb036-118">If acknowledgments are defined for the source party (as they are in this case for Tutorial_BatchSource), BizTalk batches the acknowledgments and returns them in a batch (to the \Tutorial_BatchACKDrop folder).</span></span> <span data-ttu-id="bb036-119">このチュートリアルでは、短い遅延の後、バッチ処理された受信確認が送信されます。</span><span class="sxs-lookup"><span data-stu-id="bb036-119">In this tutorial, the batched acknowledgments are sent after a short delay.</span></span>  
  
- <span data-ttu-id="bb036-120">オーケストレーションは、(この場合は、ハード ドライブ上の \Tutorial_BatchMsgDrop フォルダー) を先にバッチ処理されたメッセージを送信する送信ポート (Tutorial_BatchDest) にメッセージをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="bb036-120">The orchestration routes the message to the send port (Tutorial_BatchDest), which sends the batched message to the destination (in this case, the \Tutorial_BatchMsgDrop folder on your hard drive).</span></span> <span data-ttu-id="bb036-121">このチュートリアルでは、バッチ処理されたメッセージは 1 時間後に送信されます。</span><span class="sxs-lookup"><span data-stu-id="bb036-121">In this tutorial, the batched messages are sent after one hour.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bb036-122">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="bb036-122">In This Section</span></span>  
  
-   [<span data-ttu-id="bb036-123">ステップ 1: BatchControlPort 受信ポートの構成と有効化</span><span class="sxs-lookup"><span data-stu-id="bb036-123">Step 1: Configure and Enable the BatchControlPort Receive Port</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-1-configure-and-enable-the-batchcontrolport-receive-port.md)  
  
-   [<span data-ttu-id="bb036-124">手順 2:バッチ オーケストレーションの有効化</span><span class="sxs-lookup"><span data-stu-id="bb036-124">Step 2: Enable the Batch Orchestration</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-2-enable-the-batch-orchestration.md)  
  
-   [<span data-ttu-id="bb036-125">ステップ 3:送信先パーティの作成と構成</span><span class="sxs-lookup"><span data-stu-id="bb036-125">Step 3: Create and Configure a Destination Party</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-configure-a-destination-party.md)  
  
-   [<span data-ttu-id="bb036-126">手順 4:バッチの作成シナリオのソース パーティの構成</span><span class="sxs-lookup"><span data-stu-id="bb036-126">Step 4: Configure the Source Party for the Create-Batch Scenario</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-4-configure-the-source-party-for-the-create-batch-scenario.md)  
  
-   [<span data-ttu-id="bb036-127">手順 5:メッセージ バッチの送信ポートの作成</span><span class="sxs-lookup"><span data-stu-id="bb036-127">Step 5: Create the Send Port for the Message Batch</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-5-create-the-send-port-for-the-message-batch.md)  
  
-   [<span data-ttu-id="bb036-128">手順 6:受信確認バッチの送信ポートの作成</span><span class="sxs-lookup"><span data-stu-id="bb036-128">Step 6: Create the Send Port for the Acknowledgment Batch</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-6-create-the-send-port-for-the-acknowledgment-batch.md)  
  
-   [<span data-ttu-id="bb036-129">手順 7:オーケストレーションの開始と BizTalk Server の再起動</span><span class="sxs-lookup"><span data-stu-id="bb036-129">Step 7: Start the Orchestration and Restart BizTalk Server</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-7-start-the-orchestration-and-restart-biztalk-server.md)  
  
-   [<span data-ttu-id="bb036-130">手順 8:バッチの作成シナリオのテスト</span><span class="sxs-lookup"><span data-stu-id="bb036-130">Step 8: Test the Create-Batch Scenario</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-8-test-the-create-batch-scenario.md)