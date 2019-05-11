---
title: 'パート 2: バッチ アウト シナリオでバッチ |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching, outbound batches
- batching, inbound batches
ms.assetid: 36b9d927-f5b7-4c1a-9163-9e79d17c3e9e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d950a326aae07db4763210f67118ae272785444d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65290370"
---
# <a name="part-2-batch-inbatch-out-scenario"></a><span data-ttu-id="38c7c-102">パート 2: バッチ処理/バッチ アウト シナリオ</span><span class="sxs-lookup"><span data-stu-id="38c7c-102">Part 2: Batch In/Batch Out Scenario</span></span>
<span data-ttu-id="38c7c-103">このチュートリアルでは、HL7 エンコード バッチ ファイル、渡す[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]せず、最適化、および変換先にそのままのバッチ ファイルを送信します。</span><span class="sxs-lookup"><span data-stu-id="38c7c-103">In this part of the tutorial, you receive an HL7-encoded batch file, pass it through [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] without fragmentation, and send the intact batch file to the destination.</span></span> <span data-ttu-id="38c7c-104">次の図は、このプロセスのフローと、以下のサブセクションには、ワークフローがについて説明します。</span><span class="sxs-lookup"><span data-stu-id="38c7c-104">The following figure shows the flow of this process, and the subsection below describes the workflow.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="38c7c-105">チュートリアルのこの部分を開始する前に、コマンド プロンプトを閉じることで、第 1 部で使用した MllpReceive および MllpSend ツール オフにします。</span><span class="sxs-lookup"><span data-stu-id="38c7c-105">Before starting this part of the tutorial, turn off the MllpReceive and MllpSend tools that you used in Part 1, by closing the command prompts.</span></span>  
  
 <span data-ttu-id="38c7c-106">![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-batch-in-batch-out-scenario.gif "hl7_batch_in_batch_out_scenario")</span><span class="sxs-lookup"><span data-stu-id="38c7c-106">![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-batch-in-batch-out-scenario.gif "hl7_batch_in_batch_out_scenario")</span></span>  
  
 <span data-ttu-id="38c7c-107">**バッチ内のメッセージのフローで/バッチ アウト シナリオ**</span><span class="sxs-lookup"><span data-stu-id="38c7c-107">**How messages flow in the Batch In/Batch Out scenario**</span></span>  
  
 <span data-ttu-id="38c7c-108">このシナリオには、次のワークフローが含まれます。</span><span class="sxs-lookup"><span data-stu-id="38c7c-108">This scenario includes the following workflow:</span></span>  
  
1. <span data-ttu-id="38c7c-109">基幹業務アプリケーションに、Microsoft BizTalk Accelerator for HL7 メッセージのバッチを送信するときに、ワークフローが開始されます ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) の統合エンジンが、ファイル プロトコルを使用します。</span><span class="sxs-lookup"><span data-stu-id="38c7c-109">The workflow begins when a line-of-business application sends a message batch to the Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) Integration Engine using the FILE protocol.</span></span> <span data-ttu-id="38c7c-110">バッチには ADT の 2 つのバージョンが含まれています ^ A03 メッセージ。</span><span class="sxs-lookup"><span data-stu-id="38c7c-110">The batch contains two versions of an ADT^A03 message.</span></span> <span data-ttu-id="38c7c-111">元のアプリケーションは、Tutorial_BatchSource パーティに属しています。</span><span class="sxs-lookup"><span data-stu-id="38c7c-111">The source application belongs to the Tutorial_BatchSource party.</span></span>  
  
2. <span data-ttu-id="38c7c-112">統合エンジン ファイルのバッチを受信する受信ポート、およびメッセージのバッチを検証します。</span><span class="sxs-lookup"><span data-stu-id="38c7c-112">The Integration Engine receives the batch on a FILE receive port, and validates the message batch.</span></span> <span data-ttu-id="38c7c-113">(検証のレベルでの送信元パーティ用に選択された設定によって異なります[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー。)。</span><span class="sxs-lookup"><span data-stu-id="38c7c-113">(The level of validation depends on settings selected for the source party in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer.)</span></span>  
  
3. <span data-ttu-id="38c7c-114">設定に基づいて[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]インターフェイス エンジン、パーティのバッチの断片化を無効にする構成エクスプ ローラーで個別のメッセージにバッチを解析できませんはバッチとバッチを残します。</span><span class="sxs-lookup"><span data-stu-id="38c7c-114">Based on a setting in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer that disables batch fragmentation for the party, the Interface Engine does not parse the batch into individual messages, but leaves the batch as a batch.</span></span> <span data-ttu-id="38c7c-115">送信元パーティの選択した設定に基づいて、個々 のメッセージを検証します[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー。</span><span class="sxs-lookup"><span data-stu-id="38c7c-115">It validates the individual messages, again based on settings selected for the source party in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer.</span></span>  
  
4. <span data-ttu-id="38c7c-116">インターフェイスのエンジンが受信確認の定義の設定に基づいて、バッチ メッセージの受信確認を生成、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]パーティの構成エディター。</span><span class="sxs-lookup"><span data-stu-id="38c7c-116">The Interface Engine generates an acknowledgment for the batch message, based on the acknowledgment definition settings in the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Editor for the party.</span></span> <span data-ttu-id="38c7c-117">ここでは、インターフェイス エンジン メッセージ ヘッダーと本文の両方を検証した後、メッセージ バッチの 1 つアプリケーションに同意の確認が生成されますので、元の受信確認のモードを選択します。</span><span class="sxs-lookup"><span data-stu-id="38c7c-117">In this case, you select Original Acknowledgment mode, so the Interface Engine generates a single Application Accept acknowledgment for the message batch after validating both the message header and body.</span></span> <span data-ttu-id="38c7c-118">エンジンは、ACK_024_GLO_DEF スキーマに基づいて、受信確認をビルド、受信確認の MSA2 フィールドに"AA"を入力し、MSH3、送信先パーティが入力したうえで、MSH5 で送信元パーティを入力します。</span><span class="sxs-lookup"><span data-stu-id="38c7c-118">The engine builds the acknowledgment based on the ACK_024_GLO_DEF schema, enters "AA" in field MSA2 of the acknowledgment, enters the destination party in MSH3, and enters the source party in MSH5.</span></span>  
  
5. <span data-ttu-id="38c7c-119">ファイルからソースへの受信確認のバッチがパーティ インターフェイス エンジンのルートでは、アダプターの受信確認を処理するように設定を送信します。</span><span class="sxs-lookup"><span data-stu-id="38c7c-119">The Interface Engine routes the acknowledgment batch to the source party through a FILE send adapter set up to process acknowledgments.</span></span> <span data-ttu-id="38c7c-120">この場合、 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] \Tutorial_BatchACKDrop フォルダーにバッチをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="38c7c-120">In this case, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] routes the batch to the \Tutorial_BatchACKDrop folder.</span></span>  
  
6. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="38c7c-121">先にメッセージのバッチに指定された送信先パーティでは、この場合フォルダー \Tutorial_BTAHL7Drop を送信します。</span><span class="sxs-lookup"><span data-stu-id="38c7c-121">sends the message batch to the destination specified for the destination party, in this case the folder \Tutorial_BTAHL7Drop.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="38c7c-122">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="38c7c-122">In This Section</span></span>  
  
-   [<span data-ttu-id="38c7c-123">ステップ 1: バッチ イン/バッチ アウトのパーティ情報の構成</span><span class="sxs-lookup"><span data-stu-id="38c7c-123">Step 1: Configure Party Information for Batch In/Batch Out</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-1-configure-party-information-for-batch-in-batch-out.md)  
  
-   [<span data-ttu-id="38c7c-124">手順 2:送信ポートと受信ポートの変更または作成</span><span class="sxs-lookup"><span data-stu-id="38c7c-124">Step 2: Modify or Create the Send and Receive Ports</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-2-modify-or-create-the-send-and-receive-ports.md)  
  
-   [<span data-ttu-id="38c7c-125">ステップ 3:バッチ イン/バッチ アウト シナリオのテスト</span><span class="sxs-lookup"><span data-stu-id="38c7c-125">Step 3: Test the Batch In/Batch Out Scenario</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-3-test-the-batch-in-batch-out-scenario.md)