---
title: 手順 2:バッチ オーケストレーションを有効にする |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4badf807-f461-4d0a-a3b6-9f671e580d91
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0afe72cdf0ea747e5236f02577de16acb685061
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65288619"
---
# <a name="step-2-enable-the-batch-orchestration"></a><span data-ttu-id="1a93a-102">手順 2:バッチ オーケストレーションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="1a93a-102">Step 2: Enable the Batch Orchestration</span></span>
<span data-ttu-id="1a93a-103">バッチ オーケストレーションでは、バッチの作成処理を制御します。</span><span class="sxs-lookup"><span data-stu-id="1a93a-103">The batch orchestration controls the create batch process.</span></span> <span data-ttu-id="1a93a-104">バッチに含まれるすべてのメッセージの参照を保持、送信バッチのトランザクションを制御、バッチ メッセージを生成、送信のバッチをルーティングし、受信確認のバッチを処理します。</span><span class="sxs-lookup"><span data-stu-id="1a93a-104">It maintains references for all messages to be included in the batch, controls the outbound batch transaction, generates the batch message, routes the outgoing batch, and processes incoming acknowledgment batches.</span></span> <span data-ttu-id="1a93a-105">作業を作成するバッチ処理のバッチ オーケストレーションを参加させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a93a-105">You need to enlist the batch orchestration for the create batch process to work.</span></span>  
  
### <a name="to-enable-the-batch-orchestration"></a><span data-ttu-id="1a93a-106">バッチ オーケストレーションを有効にするには</span><span class="sxs-lookup"><span data-stu-id="1a93a-106">To enable the batch orchestration</span></span>  
  
1. <span data-ttu-id="1a93a-107">BizTalk 管理コンソールで、次のようにクリックします。**オーケストレーション**、を右クリック**BatchOrchestration.Orchestration_1**、 をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="1a93a-107">In the BizTalk Administration Console, click **Orchestrations**, right-click **BatchOrchestration.Orchestration_1**, and then click **Properties**.</span></span>  
  
2. <span data-ttu-id="1a93a-108">オーケストレーションのプロパティ] ダイアログ ボックスのコンソール ツリーで [**バインド**します。</span><span class="sxs-lookup"><span data-stu-id="1a93a-108">In the Orchestration Properties dialog box, in the console tree, click **Bindings**.</span></span>  
  
3. <span data-ttu-id="1a93a-109">**バインド**ウィンドウの**ホスト**を選択します**BizTalkServerApplication**します。</span><span class="sxs-lookup"><span data-stu-id="1a93a-109">In the **Bindings** pane, for **Host**, select **BizTalkServerApplication**.</span></span> <span data-ttu-id="1a93a-110">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a93a-110">Click **OK**.</span></span>  
  
4. <span data-ttu-id="1a93a-111">右クリックし、BizTalk 管理コンソールで**BatchOrchestration.Orchestration_1**、 をクリックし、**参加**します。</span><span class="sxs-lookup"><span data-stu-id="1a93a-111">In the BizTalk Administration Console, right-click **BatchOrchestration.Orchestration_1**, and then click **Enlist**.</span></span>  
  
   <span data-ttu-id="1a93a-112">続行する[手順 3。作成し、送信先パーティを構成する](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-configure-a-destination-party.md)します。</span><span class="sxs-lookup"><span data-stu-id="1a93a-112">Proceed to [Step 3: Create and Configure a Destination Party](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-configure-a-destination-party.md).</span></span>