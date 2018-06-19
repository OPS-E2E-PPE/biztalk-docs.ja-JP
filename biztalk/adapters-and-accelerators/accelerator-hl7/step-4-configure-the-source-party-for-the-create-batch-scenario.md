---
title: '手順 4: 作成バッチ シナリオでは、送信元パーティの構成 |Microsoft ドキュメント'
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
ms.openlocfilehash: 12f7ca9eebb28bb97ae925aec4fc34cefd5a2dcd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206402"
---
# <a name="step-4-configure-the-source-party-for-the-create-batch-scenario"></a><span data-ttu-id="dd3dc-102">手順 4: 作成バッチ シナリオでは、送信元パーティを構成します。</span><span class="sxs-lookup"><span data-stu-id="dd3dc-102">Step 4: Configure the Source Party for the Create-Batch Scenario</span></span>
<span data-ttu-id="dd3dc-103">この手順では、バッチの作成シナリオでは、送信元パーティを構成します。</span><span class="sxs-lookup"><span data-stu-id="dd3dc-103">In this step, you configure the source party for the Create-Batch scenario.</span></span> <span data-ttu-id="dd3dc-104">選択することも、受信確認を BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)])、バッチ、このパーティ用に定義されています。</span><span class="sxs-lookup"><span data-stu-id="dd3dc-104">You also select the acknowledgments that BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) will batch, as defined for this party.</span></span> <span data-ttu-id="dd3dc-105">受信確認のバッチのスケジュールを設定するように[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]メッセージの数が 2 に達した後にバッチを作成します。</span><span class="sxs-lookup"><span data-stu-id="dd3dc-105">You set the scheduling for the acknowledgment batch such that [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] will create the batch after the message count reaches 2.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dd3dc-106">作成した同じ送信元パーティを使用するこのシナリオで[手順 7: を作成し、送信元パーティを構成する](../../adapters-and-accelerators/accelerator-hl7/step-7-create-and-configure-a-source-party.md)(断片化された受信バッチのシナリオ) このチュートリアルの第 1 部のです。</span><span class="sxs-lookup"><span data-stu-id="dd3dc-106">In this scenario, you use the same source party that you created in [Step 7: Create and Configure a Source Party](../../adapters-and-accelerators/accelerator-hl7/step-7-create-and-configure-a-source-party.md) of Part 1 of this tutorial (the Fragmented Inbound Batch Scenario).</span></span>  
  
### <a name="to-configure-the-source-party-for-the-create-batch-scenario"></a><span data-ttu-id="dd3dc-107">バッチの作成シナリオでは、送信元パーティを構成するには</span><span class="sxs-lookup"><span data-stu-id="dd3dc-107">To configure the source party for the Create-Batch scenario</span></span>  
  
1.  <span data-ttu-id="dd3dc-108">BTAHL7 構成エクスプ ローラーで、上、**パーティ**コンソール ツリーで、タブをクリックし**Tutorial_BatchSource**です。</span><span class="sxs-lookup"><span data-stu-id="dd3dc-108">In BTAHL7 Configuration Explorer, on the **Parties** tab in the console tree, click **Tutorial_BatchSource**.</span></span>  
  
2.  <span data-ttu-id="dd3dc-109">クリックして、**受信確認** タブで、詳細ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="dd3dc-109">Click the **Acknowledgment** tab in the Details pane.</span></span> <span data-ttu-id="dd3dc-110">いることを確認、**受信確認の種類**は**OriginalMode**です。</span><span class="sxs-lookup"><span data-stu-id="dd3dc-110">Verify that the **Acknowledgment type** is **OriginalMode**.</span></span>  
  
3.  <span data-ttu-id="dd3dc-111">クリックして、**バッチ定義**タブです。[**使用可能なメッセージの Ack**をクリックして**BTAHL7Schemas.ADT_A03_231_GLO_DEF**、右向きの矢印を移動] をクリックして (**>>**)にこのスキーマを追加するには**メッセージの Ack を選択した**、クリックして**保存**です。</span><span class="sxs-lookup"><span data-stu-id="dd3dc-111">Click the **Batch Definition** tab. Under **Available Message Acks**, click **BTAHL7Schemas.ADT_A03_231_GLO_DEF**, click the Move to the right arrow (**>>**) to add this schema to **Selected Message Acks**, and then click **Save**.</span></span>  
  
4.  <span data-ttu-id="dd3dc-112">クリックして、**バッチ スケジュール**タブです。**後にバッチを繰り返して**セクションで、**メッセージ**、し、入力**2**で、**メッセージ**ボックス。</span><span class="sxs-lookup"><span data-stu-id="dd3dc-112">Click the **Batch Schedule** tab. In the **Repeat Batch After** section, select **Messages**, and then type **2** in the **Messages** box.</span></span>  
  
5.  <span data-ttu-id="dd3dc-113">をクリックして**スケジュールの開始**です。</span><span class="sxs-lookup"><span data-stu-id="dd3dc-113">Click **Start Schedule**.</span></span>  
  
 <span data-ttu-id="dd3dc-114">進みます[手順 5: メッセージのバッチの送信ポートを作成する](../../adapters-and-accelerators/accelerator-hl7/step-5-create-the-send-port-for-the-message-batch.md)です。</span><span class="sxs-lookup"><span data-stu-id="dd3dc-114">Proceed to [Step 5: Create the Send Port for the Message Batch](../../adapters-and-accelerators/accelerator-hl7/step-5-create-the-send-port-for-the-message-batch.md).</span></span>