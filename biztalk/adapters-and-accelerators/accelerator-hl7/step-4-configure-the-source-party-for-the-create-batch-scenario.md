---
title: '手順 4: バッチの作成シナリオでは、送信元パーティの構成 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b06b6545-4c2e-4a56-9feb-bd3f9574d4d1
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dbb4e172c88c179ea53f1e48d1e08dcb63458607
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999827"
---
# <a name="step-4-configure-the-source-party-for-the-create-batch-scenario"></a><span data-ttu-id="80e78-102">手順 4: バッチの作成シナリオでは、送信元パーティを構成します。</span><span class="sxs-lookup"><span data-stu-id="80e78-102">Step 4: Configure the Source Party for the Create-Batch Scenario</span></span>
<span data-ttu-id="80e78-103">この手順では、バッチの作成シナリオでは、送信元パーティを構成します。</span><span class="sxs-lookup"><span data-stu-id="80e78-103">In this step, you configure the source party for the Create-Batch scenario.</span></span> <span data-ttu-id="80e78-104">選択することも、受信確認を BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) バッチがこのパーティ用に定義されています。</span><span class="sxs-lookup"><span data-stu-id="80e78-104">You also select the acknowledgments that BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) will batch, as defined for this party.</span></span> <span data-ttu-id="80e78-105">受信確認のバッチのスケジュールを設定するように[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]メッセージ数が 2 に到達した後にバッチを作成します。</span><span class="sxs-lookup"><span data-stu-id="80e78-105">You set the scheduling for the acknowledgment batch such that [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] will create the batch after the message count reaches 2.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="80e78-106">作成した同じ送信元パーティを使用するこのシナリオで[手順 7: を作成し、送信元パーティを構成する](../../adapters-and-accelerators/accelerator-hl7/step-7-create-and-configure-a-source-party.md)(断片化された受信バッチのシナリオ) このチュートリアルの第 1 部の。</span><span class="sxs-lookup"><span data-stu-id="80e78-106">In this scenario, you use the same source party that you created in [Step 7: Create and Configure a Source Party](../../adapters-and-accelerators/accelerator-hl7/step-7-create-and-configure-a-source-party.md) of Part 1 of this tutorial (the Fragmented Inbound Batch Scenario).</span></span>  
  
### <a name="to-configure-the-source-party-for-the-create-batch-scenario"></a><span data-ttu-id="80e78-107">バッチの作成シナリオでは、送信元パーティを構成するには</span><span class="sxs-lookup"><span data-stu-id="80e78-107">To configure the source party for the Create-Batch scenario</span></span>  
  
1. <span data-ttu-id="80e78-108">BTAHL7 構成エクスプ ローラーでの**パーティ**コンソール ツリーで、タブをクリックして**Tutorial_BatchSource**します。</span><span class="sxs-lookup"><span data-stu-id="80e78-108">In BTAHL7 Configuration Explorer, on the **Parties** tab in the console tree, click **Tutorial_BatchSource**.</span></span>  
  
2. <span data-ttu-id="80e78-109">をクリックして、**受信確認**詳細ペインでタブ。</span><span class="sxs-lookup"><span data-stu-id="80e78-109">Click the **Acknowledgment** tab in the Details pane.</span></span> <span data-ttu-id="80e78-110">いることを確認、**受信確認の種類**は**OriginalMode**します。</span><span class="sxs-lookup"><span data-stu-id="80e78-110">Verify that the **Acknowledgment type** is **OriginalMode**.</span></span>  
  
3. <span data-ttu-id="80e78-111">をクリックして、**バッチ定義**タブ。**使用可能なメッセージの Ack**、 をクリックして**BTAHL7Schemas.ADT_A03_231_GLO_DEF**、右矢印を移動 をクリックして (**>>**)にこのスキーマを追加するには**メッセージの Ack を選択した**、 をクリックし、**保存**します。</span><span class="sxs-lookup"><span data-stu-id="80e78-111">Click the **Batch Definition** tab. Under **Available Message Acks**, click **BTAHL7Schemas.ADT_A03_231_GLO_DEF**, click the Move to the right arrow (**>>**) to add this schema to **Selected Message Acks**, and then click **Save**.</span></span>  
  
4. <span data-ttu-id="80e78-112">をクリックして、**バッチ スケジュール**タブ。**後にバッチを繰り返す**セクションで、**メッセージ**、し、入力**2**で、**メッセージ**ボックス。</span><span class="sxs-lookup"><span data-stu-id="80e78-112">Click the **Batch Schedule** tab. In the **Repeat Batch After** section, select **Messages**, and then type **2** in the **Messages** box.</span></span>  
  
5. <span data-ttu-id="80e78-113">クリックして**スケジュールの開始**します。</span><span class="sxs-lookup"><span data-stu-id="80e78-113">Click **Start Schedule**.</span></span>  
  
   <span data-ttu-id="80e78-114">進みます[手順 5: メッセージ バッチの送信ポートを作成する](../../adapters-and-accelerators/accelerator-hl7/step-5-create-the-send-port-for-the-message-batch.md)します。</span><span class="sxs-lookup"><span data-stu-id="80e78-114">Proceed to [Step 5: Create the Send Port for the Message Batch](../../adapters-and-accelerators/accelerator-hl7/step-5-create-the-send-port-for-the-message-batch.md).</span></span>