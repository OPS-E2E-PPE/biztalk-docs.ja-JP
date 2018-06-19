---
title: '手順 1: 構成して、受信ポートの有効化、BatchControlPort |Microsoft ドキュメント'
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
ms.openlocfilehash: d50289924062268db078844f2b3d2eaaccda23a2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206146"
---
# <a name="step-1-configure-and-enable-the-batchcontrolport-receive-port"></a><span data-ttu-id="2e43f-102">手順 1: 構成して、受信ポートの有効化、BatchControlPort</span><span class="sxs-lookup"><span data-stu-id="2e43f-102">Step 1: Configure and Enable the BatchControlPort Receive Port</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="2e43f-103">BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) セットアップは、受信ポートを作成、バッチ コントロール ポート、開始するには、バッチ オーケストレーションを使用するメッセージを処理するバッチの終了、および時間。</span><span class="sxs-lookup"><span data-stu-id="2e43f-103"> BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) setup creates a receive port, the batch control port, to handle the messages that the batch orchestration uses to start, stop, and time batches.</span></span> <span data-ttu-id="2e43f-104">これらのメッセージには、バッチのアクティベーションには、バッチの終了、タイマー メッセージをバッチ処理が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2e43f-104">These messages include the batch activation, batch termination, and batch timer messages.</span></span> <span data-ttu-id="2e43f-105">このステップでは、バッチ コントロール ポートの受信パイプラインを構成し、ポートを有効にします。</span><span class="sxs-lookup"><span data-stu-id="2e43f-105">In this step, you configure the receive pipeline for the batch control port, and enable the port.</span></span>  
  
### <a name="to-configure-and-enable-batchcontrolport"></a><span data-ttu-id="2e43f-106">構成して BatchControlPort を有効にするには</span><span class="sxs-lookup"><span data-stu-id="2e43f-106">To configure and enable BatchControlPort</span></span>  
  
1.  <span data-ttu-id="2e43f-107">開始**BizTalk Server 管理**です。</span><span class="sxs-lookup"><span data-stu-id="2e43f-107">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="2e43f-108">BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、 **BizTalk グループ**、**アプリケーション**、および**BizTalk アプリケーション1**です。</span><span class="sxs-lookup"><span data-stu-id="2e43f-108">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, **BizTalk Group**, **Applications**, and **BizTalk Application 1**.</span></span> <span data-ttu-id="2e43f-109">をクリックして**受信場所**です。</span><span class="sxs-lookup"><span data-stu-id="2e43f-109">Click **Receive Locations**.</span></span>  
  
3.  <span data-ttu-id="2e43f-110">右クリック**BatchControlLocation**、クリックして**を無効にする**です。</span><span class="sxs-lookup"><span data-stu-id="2e43f-110">Right-click **BatchControlLocation**, and then click **Disable**.</span></span>  
  
4.  <span data-ttu-id="2e43f-111">右クリック**BatchControlLocation**、クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="2e43f-111">Right-click **BatchControlLocation**, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="2e43f-112">受信場所のプロパティ] ダイアログ ボックスの**受信パイプライン**[ **BTAHL72XPipelines.BTAHL72XReceivePipeline**です。をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="2e43f-112">In the Receive Location Properties dialog box, for **Receive Pipeline**, select **BTAHL72XPipelines.BTAHL72XReceivePipeline**.Click **OK**.</span></span>  
  
6.  <span data-ttu-id="2e43f-113">BizTalk 管理コンソールで、右クリック**BatchControlLocation**、クリックして**を有効にする**です。</span><span class="sxs-lookup"><span data-stu-id="2e43f-113">In the BizTalk Administration Console, right-click **BatchControlLocation**, and then click **Enable**.</span></span>  
  
 <span data-ttu-id="2e43f-114">進みます[手順 2: バッチ オーケストレーションを有効にする](../../adapters-and-accelerators/accelerator-hl7/step-2-enable-the-batch-orchestration.md)です。</span><span class="sxs-lookup"><span data-stu-id="2e43f-114">Proceed to [Step 2: Enable the Batch Orchestration](../../adapters-and-accelerators/accelerator-hl7/step-2-enable-the-batch-orchestration.md).</span></span>