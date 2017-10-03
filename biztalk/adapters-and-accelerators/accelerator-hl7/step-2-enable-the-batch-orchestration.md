---
title: "手順 2: バッチ オーケストレーションの有効化 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4badf807-f461-4d0a-a3b6-9f671e580d91
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f8b18e41aacf61ac4e55e1c8047e9685179656a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-enable-the-batch-orchestration"></a><span data-ttu-id="90eb8-102">手順 2: に、バッチ オーケストレーションが有効にします。</span><span class="sxs-lookup"><span data-stu-id="90eb8-102">Step 2: Enable the Batch Orchestration</span></span>
<span data-ttu-id="90eb8-103">バッチ オーケストレーションは、バッチの作成処理を制御します。</span><span class="sxs-lookup"><span data-stu-id="90eb8-103">The batch orchestration controls the create batch process.</span></span> <span data-ttu-id="90eb8-104">バッチに含まれるすべてのメッセージの参照を保持、送信バッチのトランザクションを制御、バッチ メッセージを生成、送信バッチにルーティングし、入力方向の受信確認のバッチ処理します。</span><span class="sxs-lookup"><span data-stu-id="90eb8-104">It maintains references for all messages to be included in the batch, controls the outbound batch transaction, generates the batch message, routes the outgoing batch, and processes incoming acknowledgment batches.</span></span> <span data-ttu-id="90eb8-105">作業を作成するバッチ処理のバッチ オーケストレーションを参加させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="90eb8-105">You need to enlist the batch orchestration for the create batch process to work.</span></span>  
  
### <a name="to-enable-the-batch-orchestration"></a><span data-ttu-id="90eb8-106">バッチ オーケストレーションを有効にするには</span><span class="sxs-lookup"><span data-stu-id="90eb8-106">To enable the batch orchestration</span></span>  
  
1.  <span data-ttu-id="90eb8-107">BizTalk 管理コンソールで、をクリックして**オーケストレーション**を右クリックして**BatchOrchestration.Orchestration_1**、クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="90eb8-107">In the BizTalk Administration Console, click **Orchestrations**, right-click **BatchOrchestration.Orchestration_1**, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="90eb8-108">[オーケストレーションのプロパティ] ダイアログ ボックスのコンソール ツリーで、**バインド**です。</span><span class="sxs-lookup"><span data-stu-id="90eb8-108">In the Orchestration Properties dialog box, in the console tree, click **Bindings**.</span></span>  
  
3.  <span data-ttu-id="90eb8-109">**バインド**] ウィンドウの**ホスト**[ **BizTalkServerApplication**です。</span><span class="sxs-lookup"><span data-stu-id="90eb8-109">In the **Bindings** pane, for **Host**, select **BizTalkServerApplication**.</span></span> <span data-ttu-id="90eb8-110">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="90eb8-110">Click **OK**.</span></span>  
  
4.  <span data-ttu-id="90eb8-111">BizTalk 管理コンソールで、右クリック**BatchOrchestration.Orchestration_1**、クリックして**Enlist**です。</span><span class="sxs-lookup"><span data-stu-id="90eb8-111">In the BizTalk Administration Console, right-click **BatchOrchestration.Orchestration_1**, and then click **Enlist**.</span></span>  
  
 <span data-ttu-id="90eb8-112">進みます[手順 3: を作成し、送信先パーティを構成する](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-configure-a-destination-party.md)です。</span><span class="sxs-lookup"><span data-stu-id="90eb8-112">Proceed to [Step 3: Create and Configure a Destination Party](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-configure-a-destination-party.md).</span></span>