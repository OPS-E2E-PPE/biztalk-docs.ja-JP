---
title: "パート 2: バッチのバッチにシナリオを |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- batching, outbound batches
- batching, inbound batches
ms.assetid: 36b9d927-f5b7-4c1a-9163-9e79d17c3e9e
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 56ffac38676fe6b163a39ff06be5fe0538800d2c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="part-2-batch-inbatch-out-scenario"></a><span data-ttu-id="11c27-102">パート 2: バッチのシナリオをバッチ処理/</span><span class="sxs-lookup"><span data-stu-id="11c27-102">Part 2: Batch In/Batch Out Scenario</span></span>
<span data-ttu-id="11c27-103">このチュートリアルでは、HL7 エンコード バッチ ファイルを受け取る、渡す[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]せず、断片化を解消し、変換先にそのままバッチ ファイルを送信します。</span><span class="sxs-lookup"><span data-stu-id="11c27-103">In this part of the tutorial, you receive an HL7-encoded batch file, pass it through [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] without fragmentation, and send the intact batch file to the destination.</span></span> <span data-ttu-id="11c27-104">次の図は、このプロセスのフローと下記のサブセクションで、ワークフローを記述します。</span><span class="sxs-lookup"><span data-stu-id="11c27-104">The following figure shows the flow of this process, and the subsection below describes the workflow.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="11c27-105">このチュートリアルのこの部分を開始する前に、コマンド プロンプトを閉じて、第 1 部で使用した MllpReceive および MllpSend ツールは、オフにします。</span><span class="sxs-lookup"><span data-stu-id="11c27-105">Before starting this part of the tutorial, turn off the MllpReceive and MllpSend tools that you used in Part 1, by closing the command prompts.</span></span>  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-batch-in-batch-out-scenario.gif "hl7_batch_in_batch_out_scenario")  
  
 <span data-ttu-id="11c27-106">**バッチ内のメッセージのフローのシナリオをバッチ処理/**</span><span class="sxs-lookup"><span data-stu-id="11c27-106">**How messages flow in the Batch In/Batch Out scenario**</span></span>  
  
 <span data-ttu-id="11c27-107">このシナリオには、次のワークフローが含まれます。</span><span class="sxs-lookup"><span data-stu-id="11c27-107">This scenario includes the following workflow:</span></span>  
  
1.  <span data-ttu-id="11c27-108">基幹業務アプリケーションにメッセージ バッチを送信するときに、ワークフローが開始され、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) の統合エンジン ファイル プロトコルを使用します。</span><span class="sxs-lookup"><span data-stu-id="11c27-108">The workflow begins when a line-of-business application sends a message batch to the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) Integration Engine using the FILE protocol.</span></span> <span data-ttu-id="11c27-109">バッチが、ADT の 2 つのバージョンを含む ^ A03 メッセージ。</span><span class="sxs-lookup"><span data-stu-id="11c27-109">The batch contains two versions of an ADT^A03 message.</span></span> <span data-ttu-id="11c27-110">送信元アプリケーションは、Tutorial_BatchSource パーティに属しています。</span><span class="sxs-lookup"><span data-stu-id="11c27-110">The source application belongs to the Tutorial_BatchSource party.</span></span>  
  
2.  <span data-ttu-id="11c27-111">統合エンジンは、受信ファイルのバッチの受信ポート、およびメッセージのバッチを検証します。</span><span class="sxs-lookup"><span data-stu-id="11c27-111">The Integration Engine receives the batch on a FILE receive port, and validates the message batch.</span></span> <span data-ttu-id="11c27-112">(検証のレベルでの送信元パーティ用に選択された設定によって異なります[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー。)。</span><span class="sxs-lookup"><span data-stu-id="11c27-112">(The level of validation depends on settings selected for the source party in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer.)</span></span>  
  
3.  <span data-ttu-id="11c27-113">設定に基づいて[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]インターフェイス エンジンは、このパーティのバッチの断片化を無効にする構成エクスプ ローラーは、個別のメッセージにバッチを解析できませんが、バッチとバッチのままにします。</span><span class="sxs-lookup"><span data-stu-id="11c27-113">Based on a setting in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer that disables batch fragmentation for the party, the Interface Engine does not parse the batch into individual messages, but leaves the batch as a batch.</span></span> <span data-ttu-id="11c27-114">ソース パーティ用に選択された設定に基づいて、個々 のメッセージを検証して[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー。</span><span class="sxs-lookup"><span data-stu-id="11c27-114">It validates the individual messages, again based on settings selected for the source party in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer.</span></span>  
  
4.  <span data-ttu-id="11c27-115">インターフェイスのエンジンが、受信確認の定義の設定に基づいて、バッチ メッセージの受信確認を生成、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]パーティの構成エディター。</span><span class="sxs-lookup"><span data-stu-id="11c27-115">The Interface Engine generates an acknowledgment for the batch message, based on the acknowledgment definition settings in the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Editor for the party.</span></span> <span data-ttu-id="11c27-116">ここでは、インターフェイス エンジンでは、メッセージ ヘッダーと本文の両方を検証した後、単一アプリケーションの同意の受信確認メッセージ バッチが生成されるため、元の受信確認モードを選択します。</span><span class="sxs-lookup"><span data-stu-id="11c27-116">In this case, you select Original Acknowledgment mode, so the Interface Engine generates a single Application Accept acknowledgment for the message batch after validating both the message header and body.</span></span> <span data-ttu-id="11c27-117">エンジンは、ACK_024_GLO_DEF スキーマに基づいて、受信確認をビルド、受信確認の MSA2 フィールドに"AA"を入力し、MSH3、送信先パーティを入力したうえで、MSH5 で送信元パーティを入力します。</span><span class="sxs-lookup"><span data-stu-id="11c27-117">The engine builds the acknowledgment based on the ACK_024_GLO_DEF schema, enters "AA" in field MSA2 of the acknowledgment, enters the destination party in MSH3, and enters the source party in MSH5.</span></span>  
  
5.  <span data-ttu-id="11c27-118">ファイルをパーティの受信確認のバッチにソース インターフェイス エンジンのルートは、アダプターの受信確認を処理する設定を送信します。</span><span class="sxs-lookup"><span data-stu-id="11c27-118">The Interface Engine routes the acknowledgment batch to the source party through a FILE send adapter set up to process acknowledgments.</span></span> <span data-ttu-id="11c27-119">この場合、 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] \Tutorial_BatchACKDrop フォルダーをバッチにルーティングします。</span><span class="sxs-lookup"><span data-stu-id="11c27-119">In this case, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] routes the batch to the \Tutorial_BatchACKDrop folder.</span></span>  
  
6.  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="11c27-120">メッセージのバッチ、変換先に指定された送信先パーティのここではフォルダー \Tutorial_BTAHL7Drop を送信します。</span><span class="sxs-lookup"><span data-stu-id="11c27-120"> sends the message batch to the destination specified for the destination party, in this case the folder \Tutorial_BTAHL7Drop.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="11c27-121">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="11c27-121">In This Section</span></span>  
  
-   [<span data-ttu-id="11c27-122">手順 1: 構成内のバッチの情報をパーティ/アウト バッチ</span><span class="sxs-lookup"><span data-stu-id="11c27-122">Step 1: Configure Party Information for Batch In/Batch Out</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-1-configure-party-information-for-batch-in-batch-out.md)  
  
-   [<span data-ttu-id="11c27-123">手順 2: 変更または作成、送信および受信ポート</span><span class="sxs-lookup"><span data-stu-id="11c27-123">Step 2: Modify or Create the Send and Receive Ports</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-2-modify-or-create-the-send-and-receive-ports.md)  
  
-   [<span data-ttu-id="11c27-124">手順 3: テストのバッチ処理/シナリオをバッチ処理</span><span class="sxs-lookup"><span data-stu-id="11c27-124">Step 3: Test the Batch In/Batch Out Scenario</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-3-test-the-batch-in-batch-out-scenario.md)