---
title: 手順 1:構成して有効にする BatchControlPort 受信ポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: be248a05-e740-497a-b112-8ba3a57b020b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fdc4260109769fd025b33e6b14d8fd3465d4e0e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65289119"
---
# <a name="step-1-configure-and-enable-the-batchcontrolport-receive-port"></a><span data-ttu-id="4fd05-102">手順 1:構成して有効にする BatchControlPort 受信ポート</span><span class="sxs-lookup"><span data-stu-id="4fd05-102">Step 1: Configure and Enable the BatchControlPort Receive Port</span></span>
<span data-ttu-id="4fd05-103">Microsoft BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) セットアップは、受信ポートを作成、バッチ コントロール ポートを開始するには、バッチ オーケストレーションを使用するメッセージを処理するバッチの停止、および時間。</span><span class="sxs-lookup"><span data-stu-id="4fd05-103">Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) setup creates a receive port, the batch control port, to handle the messages that the batch orchestration uses to start, stop, and time batches.</span></span> <span data-ttu-id="4fd05-104">これらのメッセージには、バッチのアクティベーションには、バッチの終了、タイマー メッセージ バッチにはが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4fd05-104">These messages include the batch activation, batch termination, and batch timer messages.</span></span> <span data-ttu-id="4fd05-105">この手順では、バッチ コントロール ポートの受信パイプラインを構成し、ポートを有効にします。</span><span class="sxs-lookup"><span data-stu-id="4fd05-105">In this step, you configure the receive pipeline for the batch control port, and enable the port.</span></span>  
  
### <a name="to-configure-and-enable-batchcontrolport"></a><span data-ttu-id="4fd05-106">構成して BatchControlPort を有効にするには</span><span class="sxs-lookup"><span data-stu-id="4fd05-106">To configure and enable BatchControlPort</span></span>  
  
1. <span data-ttu-id="4fd05-107">開始**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="4fd05-107">Start **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="4fd05-108">BizTalk Server 管理コンソールで  **BizTalk Server 管理**、 **BizTalk グループ**、**アプリケーション**、および**BizTalk アプリケーション1**します。</span><span class="sxs-lookup"><span data-stu-id="4fd05-108">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, **BizTalk Group**, **Applications**, and **BizTalk Application 1**.</span></span> <span data-ttu-id="4fd05-109">クリックして**受信場所**します。</span><span class="sxs-lookup"><span data-stu-id="4fd05-109">Click **Receive Locations**.</span></span>  
  
3. <span data-ttu-id="4fd05-110">右クリック**BatchControlLocation**、 をクリックし、**を無効にする**します。</span><span class="sxs-lookup"><span data-stu-id="4fd05-110">Right-click **BatchControlLocation**, and then click **Disable**.</span></span>  
  
4. <span data-ttu-id="4fd05-111">右クリックして**BatchControlLocation**、 をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="4fd05-111">Right-click **BatchControlLocation**, and then click **Properties**.</span></span>  
  
5. <span data-ttu-id="4fd05-112">受信場所のプロパティ ダイアログ ボックスでの**受信パイプライン**、 **BTAHL72XPipelines.BTAHL72XReceivePipeline**します。クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="4fd05-112">In the Receive Location Properties dialog box, for **Receive Pipeline**, select **BTAHL72XPipelines.BTAHL72XReceivePipeline**.Click **OK**.</span></span>  
  
6. <span data-ttu-id="4fd05-113">右クリックし、BizTalk 管理コンソールで**BatchControlLocation**、 をクリックし、**を有効にする**します。</span><span class="sxs-lookup"><span data-stu-id="4fd05-113">In the BizTalk Administration Console, right-click **BatchControlLocation**, and then click **Enable**.</span></span>  
  
   <span data-ttu-id="4fd05-114">続行する[手順 2。バッチ オーケストレーションを有効にする](../../adapters-and-accelerators/accelerator-hl7/step-2-enable-the-batch-orchestration.md)します。</span><span class="sxs-lookup"><span data-stu-id="4fd05-114">Proceed to [Step 2: Enable the Batch Orchestration](../../adapters-and-accelerators/accelerator-hl7/step-2-enable-the-batch-orchestration.md).</span></span>