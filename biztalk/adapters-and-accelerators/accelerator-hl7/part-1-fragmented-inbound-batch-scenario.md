---
title: 作業 1:受信バッチのシナリオを断片化 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching, fragmenting messages
- batching tutorial, fragmenting messages
- fragmenting messages
ms.assetid: 8adf2c17-5f66-408d-b30b-51b22d8e71fa
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d334c9cee7da4cca1a28268f0d693b5a7813839
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65290041"
---
# <a name="part-1-fragmented-inbound-batch-scenario"></a><span data-ttu-id="2647d-102">作業 1:断片化した受信バッチのシナリオ</span><span class="sxs-lookup"><span data-stu-id="2647d-102">Part 1: Fragmented Inbound Batch Scenario</span></span>
<span data-ttu-id="2647d-103">このチュートリアルには、個別のメッセージにフラグメントが、および、変換先に個々 のメッセージを送信、HL7 でエンコードされたバッチを受信します。</span><span class="sxs-lookup"><span data-stu-id="2647d-103">In this part of the tutorial, you receive an HL7-encoded batch, fragment it into individual messages, and send the individual messages to a destination.</span></span> <span data-ttu-id="2647d-104">次の図は、このプロセスの流れを示しています。</span><span class="sxs-lookup"><span data-stu-id="2647d-104">The following figure shows the flow of this process.</span></span>  
  
 <span data-ttu-id="2647d-105">![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-fragmented-inbound-batching-scenario.gif "hl7_fragmented_inbound_batching_scenario")</span><span class="sxs-lookup"><span data-stu-id="2647d-105">![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-fragmented-inbound-batching-scenario.gif "hl7_fragmented_inbound_batching_scenario")</span></span>  
  
 <span data-ttu-id="2647d-106">このシナリオには、次のワークフローが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2647d-106">This scenario includes the following workflow:</span></span>  
  
1. <span data-ttu-id="2647d-107">基幹業務アプリケーションは、Microsoft にメッセージのバッチを送信するときに、ワークフローが開始[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]統合エンジンが、最小限の下位レイヤー プロトコル (MLLP) プロトコルを使用します。</span><span class="sxs-lookup"><span data-stu-id="2647d-107">The workflow begins when a line-of-business application sends a message batch to the Microsoft [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] Integration Engine using the Minimal Lower Layer Protocol (MLLP) protocol.</span></span> <span data-ttu-id="2647d-108">バッチには ADT の 2 つのバージョンが含まれています ^ A03 メッセージ。</span><span class="sxs-lookup"><span data-stu-id="2647d-108">The batch contains two versions of an ADT^A03 message.</span></span> <span data-ttu-id="2647d-109">元のアプリケーションは、Tutorial_BatchSource パーティに属しています。</span><span class="sxs-lookup"><span data-stu-id="2647d-109">The source application belongs to the Tutorial_BatchSource party.</span></span>  
  
2. <span data-ttu-id="2647d-110">インターフェイスのエンジン、MLLP でバッチを受信する受信ポート、およびメッセージのバッチを検証します。</span><span class="sxs-lookup"><span data-stu-id="2647d-110">The Interface Engine receives the batch on an MLLP receive port, and validates the message batch.</span></span> <span data-ttu-id="2647d-111">(検証のレベルは、BTAHL7 構成エクスプ ローラーで送信元パーティの選択した設定に依存)。</span><span class="sxs-lookup"><span data-stu-id="2647d-111">(The level of validation depends on settings selected for the source party in BTAHL7 Configuration Explorer.)</span></span>  
  
3. <span data-ttu-id="2647d-112">バッチの断片化をできるようにする BTAHL7 構成エクスプ ローラーの設定に基づいて、インターフェイス エンジン バッチの解析に 2 つの個別 ADT ^ A03 メッセージ。</span><span class="sxs-lookup"><span data-stu-id="2647d-112">Based on a setting in BTAHL7 Configuration Explorer that enables batch fragmentation, the Interface Engine parses the batch into two individual ADT^A03 messages.</span></span> <span data-ttu-id="2647d-113">BTAHL7 構成エクスプ ローラーで送信元パーティの選択した設定に基づいて、個々 のメッセージを検証します。</span><span class="sxs-lookup"><span data-stu-id="2647d-113">It validates the individual messages, again based on settings selected for the source party in BTAHL7 Configuration Explorer.</span></span>  
  
4. <span data-ttu-id="2647d-114">インターフェイスのエンジンは、BTAHL7 構成エクスプ ローラーで受信確認の定義の設定に基づいて、各メッセージの受信確認を生成します。</span><span class="sxs-lookup"><span data-stu-id="2647d-114">The Interface Engine generates an acknowledgment for each message, based on the acknowledgment definition settings in BTAHL7 Configuration Explorer.</span></span> <span data-ttu-id="2647d-115">このチュートリアルでは、インターフェイス エンジンでは、メッセージごとに単一アプリケーションの同意の確認を生成、メッセージ ヘッダーと本文の両方を検証した後、元の受信確認のモードを選択します。</span><span class="sxs-lookup"><span data-stu-id="2647d-115">In this tutorial, you will select Original Acknowledgment mode, so the Interface Engine generates a single Application Accept acknowledgment for each message after validating both the message header and body.</span></span> <span data-ttu-id="2647d-116">エンジンは、ACK_024_GLO_DEF スキーマに基づいて、受信確認をビルド、受信確認の MSA2 フィールドに"AA"を入力し、MSH3、送信先パーティが入力したうえで、MSH5 で送信元パーティを入力します。</span><span class="sxs-lookup"><span data-stu-id="2647d-116">The engine builds the acknowledgment based on the ACK_024_GLO_DEF schema, enters "AA" in field MSA2 of the acknowledgment, enters the destination party in MSH3, and enters the source party in MSH5.</span></span>  
  
5. <span data-ttu-id="2647d-117">インターフェイス エンジンが MLLP の受信確認は、各ラッパーを配置し、受信確認を処理するよう MLLP 送信アダプターでパーティのソースに受信確認のルートを設定します。</span><span class="sxs-lookup"><span data-stu-id="2647d-117">The Interface Engine places MLLP wrappers around each acknowledgment, and routes the acknowledgments to the source party through an MLLP send adapter set up to process acknowledgments.</span></span>  
  
6. <span data-ttu-id="2647d-118">インターフェイスのエンジンは、MLLP ラッパーは各メッセージ、および、MLLP を個別に各メッセージの送信ポートの受信確認ではないメッセージを処理するように設定するルートを配置します。</span><span class="sxs-lookup"><span data-stu-id="2647d-118">The Interface Engine places MLLP wrappers around each message, and routes each message individually to an MLLP send port set up to process non-acknowledgment messages.</span></span>  
  
7. <span data-ttu-id="2647d-119">BTAHL7 では、その MSH5 フィールドで指定した変換先に別の MLLP 送信ポートを通じて各メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="2647d-119">BTAHL7 sends each message through another MLLP send port to the destination specified in its MSH5 field.</span></span>  
  
8. <span data-ttu-id="2647d-120">BTAHL7 送信先パーティに送信、受信した各メッセージの受信確認をアプリケーションに承認します。</span><span class="sxs-lookup"><span data-stu-id="2647d-120">The destination party sends to BTAHL7 an application-accept acknowledgment for each message that it received.</span></span>  
  
9. <span data-ttu-id="2647d-121">インターフェイスのエンジンは、各受信確認を受信します。</span><span class="sxs-lookup"><span data-stu-id="2647d-121">The Interface Engine receives each acknowledgment.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2647d-122">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="2647d-122">In This Section</span></span>  
  
-   [<span data-ttu-id="2647d-123">ステップ 1: ヘッダーと受信確認スキーマの追加</span><span class="sxs-lookup"><span data-stu-id="2647d-123">Step 1: Add Header and Acknowledgment Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-1-add-header-and-acknowledgment-schemas.md)  
  
-   [<span data-ttu-id="2647d-124">手順 2:v2.3.1 の一般的なスキーマの追加</span><span class="sxs-lookup"><span data-stu-id="2647d-124">Step 2: Add Common Schemas for v2.3.1</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-2-add-common-schemas-for-v2-3-1.md)  
  
-   [<span data-ttu-id="2647d-125">ステップ 3:トリガー イベント (メッセージ) スキーマの追加</span><span class="sxs-lookup"><span data-stu-id="2647d-125">Step 3: Add a Trigger Event (Message) Schema</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-3-add-a-trigger-event-message-schema.md)  
  
-   [<span data-ttu-id="2647d-126">手順 4:バッチ メッセージを受け入れるための受信ポートの作成</span><span class="sxs-lookup"><span data-stu-id="2647d-126">Step 4: Create a Receive Port for Accepting the Batch Message</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-4-create-a-receive-port-for-accepting-the-batch-message.md)  
  
-   [<span data-ttu-id="2647d-127">手順 5:メッセージを配信する送信ポートの作成</span><span class="sxs-lookup"><span data-stu-id="2647d-127">Step 5: Create a Send Port to Deliver Messages</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-5-create-a-send-port-to-deliver-messages.md)  
  
-   [<span data-ttu-id="2647d-128">手順 6:受信確認を配信する送信ポートの作成</span><span class="sxs-lookup"><span data-stu-id="2647d-128">Step 6: Create a Send Port to Deliver Acknowledgments</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-6-create-a-send-port-to-deliver-acknowledgments.md)  
  
-   [<span data-ttu-id="2647d-129">手順 7:ソース パーティの作成と構成</span><span class="sxs-lookup"><span data-stu-id="2647d-129">Step 7: Create and Configure a Source Party</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-7-create-and-configure-a-source-party.md)  
  
-   [<span data-ttu-id="2647d-130">手順 8:BizTalk Server の再起動</span><span class="sxs-lookup"><span data-stu-id="2647d-130">Step 8: Restart BizTalk Server</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-8-restart-biztalk-server.md)  
  
-   [<span data-ttu-id="2647d-131">手順 9:断片化した受信バッチのシナリオの確認</span><span class="sxs-lookup"><span data-stu-id="2647d-131">Step 9: Verify the Fragmented Inbound Batch Scenario</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-9-verify-the-fragmented-inbound-batch-scenario.md)