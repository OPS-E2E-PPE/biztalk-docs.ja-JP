---
title: 'パート 1: 断片化した受信バッチ シナリオ |Microsoft ドキュメント'
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
ms.openlocfilehash: d8891bd09c803c77e1878b304f5db5b71a26ab9d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206218"
---
# <a name="part-1-fragmented-inbound-batch-scenario"></a><span data-ttu-id="341d8-102">パート 1: 断片化した受信バッチのシナリオ</span><span class="sxs-lookup"><span data-stu-id="341d8-102">Part 1: Fragmented Inbound Batch Scenario</span></span>
<span data-ttu-id="341d8-103">このチュートリアルには、個別のメッセージにフラグメント、および、先に個々 のメッセージを送信、HL7 でエンコードされたバッチを受信します。</span><span class="sxs-lookup"><span data-stu-id="341d8-103">In this part of the tutorial, you receive an HL7-encoded batch, fragment it into individual messages, and send the individual messages to a destination.</span></span> <span data-ttu-id="341d8-104">次の図は、このプロセスの流れを示しています。</span><span class="sxs-lookup"><span data-stu-id="341d8-104">The following figure shows the flow of this process.</span></span>  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-fragmented-inbound-batching-scenario.gif "hl7_fragmented_inbound_batching_scenario")  
  
 <span data-ttu-id="341d8-105">このシナリオには、次のワークフローが含まれます。</span><span class="sxs-lookup"><span data-stu-id="341d8-105">This scenario includes the following workflow:</span></span>  
  
1.  <span data-ttu-id="341d8-106">基幹業務アプリケーションにメッセージ バッチを送信するときに、ワークフローが開始され、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]最小限下位層プロトコル (MLLP) プロトコルを使用して統合エンジンです。</span><span class="sxs-lookup"><span data-stu-id="341d8-106">The workflow begins when a line-of-business application sends a message batch to the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] Integration Engine using the Minimal Lower Layer Protocol (MLLP) protocol.</span></span> <span data-ttu-id="341d8-107">バッチが、ADT の 2 つのバージョンを含む ^ A03 メッセージ。</span><span class="sxs-lookup"><span data-stu-id="341d8-107">The batch contains two versions of an ADT^A03 message.</span></span> <span data-ttu-id="341d8-108">送信元アプリケーションは、Tutorial_BatchSource パーティに属しています。</span><span class="sxs-lookup"><span data-stu-id="341d8-108">The source application belongs to the Tutorial_BatchSource party.</span></span>  
  
2.  <span data-ttu-id="341d8-109">インターフェイス エンジン、MLLP にバッチを受信する受信ポート、およびメッセージのバッチを検証します。</span><span class="sxs-lookup"><span data-stu-id="341d8-109">The Interface Engine receives the batch on an MLLP receive port, and validates the message batch.</span></span> <span data-ttu-id="341d8-110">(検証のレベル設定によって異なります BTAHL7 構成エクスプ ローラーで送信元パーティ用に選択します。)</span><span class="sxs-lookup"><span data-stu-id="341d8-110">(The level of validation depends on settings selected for the source party in BTAHL7 Configuration Explorer.)</span></span>  
  
3.  <span data-ttu-id="341d8-111">BTAHL7 構成エクスプ ローラーでバッチの断片化をできるようにする設定に基づき、インターフェイス エンジンを解析してバッチに 2 つの個別 ADT ^ A03 メッセージ。</span><span class="sxs-lookup"><span data-stu-id="341d8-111">Based on a setting in BTAHL7 Configuration Explorer that enables batch fragmentation, the Interface Engine parses the batch into two individual ADT^A03 messages.</span></span> <span data-ttu-id="341d8-112">BTAHL7 構成エクスプ ローラーで送信元パーティ用に選択された設定に基づいて、個々 のメッセージを検証します。</span><span class="sxs-lookup"><span data-stu-id="341d8-112">It validates the individual messages, again based on settings selected for the source party in BTAHL7 Configuration Explorer.</span></span>  
  
4.  <span data-ttu-id="341d8-113">インターフェイスのエンジンは、BTAHL7 構成エクスプ ローラーで受信確認の定義の設定に基づいて、各メッセージの受信確認を生成します。</span><span class="sxs-lookup"><span data-stu-id="341d8-113">The Interface Engine generates an acknowledgment for each message, based on the acknowledgment definition settings in BTAHL7 Configuration Explorer.</span></span> <span data-ttu-id="341d8-114">このチュートリアルでは、ため、インターフェイス エンジンは、メッセージ ヘッダーと本文の両方を検証した後のメッセージごとに 1 つ、アプリケーションは、受け入れ確認の生成元の受信確認モードを選択します。</span><span class="sxs-lookup"><span data-stu-id="341d8-114">In this tutorial, you will select Original Acknowledgment mode, so the Interface Engine generates a single Application Accept acknowledgment for each message after validating both the message header and body.</span></span> <span data-ttu-id="341d8-115">エンジンは、ACK_024_GLO_DEF スキーマに基づいて、受信確認をビルド、受信確認の MSA2 フィールドに"AA"を入力し、MSH3、送信先パーティを入力したうえで、MSH5 で送信元パーティを入力します。</span><span class="sxs-lookup"><span data-stu-id="341d8-115">The engine builds the acknowledgment based on the ACK_024_GLO_DEF schema, enters "AA" in field MSA2 of the acknowledgment, enters the destination party in MSH3, and enters the source party in MSH5.</span></span>  
  
5.  <span data-ttu-id="341d8-116">インターフェイスのエンジンは、各受信確認の MLLP ラッパーし、ルート ソースに受信確認が MLLP 送信アダプターを使ってパーティが受信確認を処理する設定。</span><span class="sxs-lookup"><span data-stu-id="341d8-116">The Interface Engine places MLLP wrappers around each acknowledgment, and routes the acknowledgments to the source party through an MLLP send adapter set up to process acknowledgments.</span></span>  
  
6.  <span data-ttu-id="341d8-117">インターフェイス エンジンは、各メッセージ、および各メッセージに MLLP を個別に送信ポートの非受信確認メッセージを処理するを設定するルート ラッパー MLLP を配置します。</span><span class="sxs-lookup"><span data-stu-id="341d8-117">The Interface Engine places MLLP wrappers around each message, and routes each message individually to an MLLP send port set up to process non-acknowledgment messages.</span></span>  
  
7.  <span data-ttu-id="341d8-118">BTAHL7 では、その MSH5 フィールドで指定した宛先に別の MLLP 送信ポートを通じて各メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="341d8-118">BTAHL7 sends each message through another MLLP send port to the destination specified in its MSH5 field.</span></span>  
  
8.  <span data-ttu-id="341d8-119">BTAHL7 送信先パーティに送信するアプリケーションに受け入れられるように、受信した各メッセージの受信確認します。</span><span class="sxs-lookup"><span data-stu-id="341d8-119">The destination party sends to BTAHL7 an application-accept acknowledgment for each message that it received.</span></span>  
  
9. <span data-ttu-id="341d8-120">インターフェイス エンジンでは、各受信確認を受信します。</span><span class="sxs-lookup"><span data-stu-id="341d8-120">The Interface Engine receives each acknowledgment.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="341d8-121">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="341d8-121">In This Section</span></span>  
  
-   [<span data-ttu-id="341d8-122">手順 1: ヘッダーと受信確認スキーマを追加します。</span><span class="sxs-lookup"><span data-stu-id="341d8-122">Step 1: Add Header and Acknowledgment Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-1-add-header-and-acknowledgment-schemas.md)  
  
-   [<span data-ttu-id="341d8-123">手順 2: v2.3.1 の一般的なスキーマを追加します。</span><span class="sxs-lookup"><span data-stu-id="341d8-123">Step 2: Add Common Schemas for v2.3.1</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-2-add-common-schemas-for-v2-3-1.md)  
  
-   [<span data-ttu-id="341d8-124">手順 3: トリガー イベント (メッセージ) のスキーマを追加します。</span><span class="sxs-lookup"><span data-stu-id="341d8-124">Step 3: Add a Trigger Event (Message) Schema</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-3-add-a-trigger-event-message-schema.md)  
  
-   [<span data-ttu-id="341d8-125">手順 4: 作成、バッチ メッセージを受け入れるための受信ポート</span><span class="sxs-lookup"><span data-stu-id="341d8-125">Step 4: Create a Receive Port for Accepting the Batch Message</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-4-create-a-receive-port-for-accepting-the-batch-message.md)  
  
-   [<span data-ttu-id="341d8-126">手順 5: メッセージを配信する送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="341d8-126">Step 5: Create a Send Port to Deliver Messages</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-5-create-a-send-port-to-deliver-messages.md)  
  
-   [<span data-ttu-id="341d8-127">手順 6: 受信確認を配信する送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="341d8-127">Step 6: Create a Send Port to Deliver Acknowledgments</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-6-create-a-send-port-to-deliver-acknowledgments.md)  
  
-   [<span data-ttu-id="341d8-128">手順 7: を作成し、送信元パーティを構成します。</span><span class="sxs-lookup"><span data-stu-id="341d8-128">Step 7: Create and Configure a Source Party</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-7-create-and-configure-a-source-party.md)  
  
-   [<span data-ttu-id="341d8-129">手順 8: BizTalk Server を再起動します。</span><span class="sxs-lookup"><span data-stu-id="341d8-129">Step 8: Restart BizTalk Server</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-8-restart-biztalk-server.md)  
  
-   [<span data-ttu-id="341d8-130">手順 9: 断片化した受信バッチのシナリオを確認してください。</span><span class="sxs-lookup"><span data-stu-id="341d8-130">Step 9: Verify the Fragmented Inbound Batch Scenario</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-9-verify-the-fragmented-inbound-batch-scenario.md)