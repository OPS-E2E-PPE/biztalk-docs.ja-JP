---
title: FIN Response Reconciliation |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ACKs
- FRR
- FIN Response Reconciliation
- SAA
- NAKs
- FRR, about FRR
- acknowledgements
- FIN Response Reconciliation, about FIN Response Reconciliation
- FIN Response Reconciliation, acknowledgements
ms.assetid: 987b932b-e487-4ca8-acd0-410d71df8e6d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c2b74012c5f33967773234902a7475b8052f769
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377851"
---
# <a name="fin-response-reconciliation"></a><span data-ttu-id="9b9a0-102">FIN Response Reconciliation</span><span class="sxs-lookup"><span data-stu-id="9b9a0-102">FIN Response Reconciliation</span></span>
<span data-ttu-id="9b9a0-103">機能は、FIN 応答の調整 (FRR)[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]によって送信された対応する元のメッセージを FIN 応答の整合性を保ちます[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="9b9a0-103">The FIN Response Reconciliation (FRR) feature of [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] reconciles a FIN response with the corresponding original message sent by [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].</span></span> <span data-ttu-id="9b9a0-104">元のメッセージの状態を確立し、により、この[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]状態に基づく手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9b9a0-104">This establishes the status of the original message, and enables [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] to take steps based upon that status.</span></span> <span data-ttu-id="9b9a0-105">調整なしこのはできません。</span><span class="sxs-lookup"><span data-stu-id="9b9a0-105">Without reconciliation, this would not be possible.</span></span> [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] <span data-ttu-id="9b9a0-106">認識、ことが正常に (または失敗)、元のメッセージに送信 SAA と、転送の状態を示す SAA から受け取った応答必要がありますが、2 つの間の接続を作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="9b9a0-106">would know that it successfully (or unsuccessfully) sent the original message to SAA, and it would have the response that it received from SAA, indicating the status of the transmission, but it would not be able to make the connection between the two.</span></span> <span data-ttu-id="9b9a0-107">FRR では、その接続を確立します。</span><span class="sxs-lookup"><span data-stu-id="9b9a0-107">FRR establishes that connection.</span></span>  
  
 <span data-ttu-id="9b9a0-108">FIN 応答が受信確認 (Ack) または否定受信確認応答 (NAKs) に SAA によって送信された[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]、SAA に SWIFT ネットワークで送信され、しに SAA によって転送または[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="9b9a0-108">FIN responses are acknowledgments (ACKs) or negative acknowledgments (NAKs) sent by SAA to [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)], or sent by the SWIFT network to SAA and then forwarded by SAA to [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].</span></span> <span data-ttu-id="9b9a0-109">これらの受信確認の有無は、メッセージのビジネスの状態を定義します。</span><span class="sxs-lookup"><span data-stu-id="9b9a0-109">The presence or absence of these acknowledgments defines the business status of the message.</span></span> <span data-ttu-id="9b9a0-110">ビジネス アクティビティ監視 (BAM) のレポートには、この状態を監視することができます。</span><span class="sxs-lookup"><span data-stu-id="9b9a0-110">You can monitor this status through Business Activity Monitoring (BAM) reporting.</span></span>  
  
 <span data-ttu-id="9b9a0-111">FRR をカスタム アプリケーションの動作を実装することもできます。</span><span class="sxs-lookup"><span data-stu-id="9b9a0-111">You can also implement custom application behavior around FRR.</span></span> <span data-ttu-id="9b9a0-112">カスタム ハンドラーは、FIN 応答の調整のセットを処理するための独自のロジックを実装できます。</span><span class="sxs-lookup"><span data-stu-id="9b9a0-112">A custom handler can implement your own logic for handling reconciled sets of FIN responses.</span></span> <span data-ttu-id="9b9a0-113">MTS21_FIN_ACKNAK NAK メッセージの FRR が関連付けられたメッセージを処理するカスタム ハンドラーの例は、次を参照してください。 [FRR NAK ハンドラー サンプル](../../adapters-and-accelerators/accelerator-swift/frr-nak-handler-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="9b9a0-113">For an example of a custom handler that processes messages that FRR has correlated with a MTS21_FIN_ACKNAK NAK message, see [FRR NAK Handler Sample](../../adapters-and-accelerators/accelerator-swift/frr-nak-handler-sample.md).</span></span>  
  
 <span data-ttu-id="9b9a0-114">FRR オーケストレーションが既定でインストールされている、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]セットアップ プログラム。</span><span class="sxs-lookup"><span data-stu-id="9b9a0-114">The FRR orchestration is installed by default by the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] setup program.</span></span> <span data-ttu-id="9b9a0-115">必要があります、受信パイプラインを作成して、FRR システムを構成する受信場所、および送信ポート。</span><span class="sxs-lookup"><span data-stu-id="9b9a0-115">You need to configure the FRR system by creating a receive pipeline, receive locations, and send ports.</span></span> <span data-ttu-id="9b9a0-116">どのくらいの期間待機と、応答の遅延の NAKs の一般を指定する FRR を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b9a0-116">You also need to configure FRR to specify how long it should wait for delayed NAKs, and for responses in general.</span></span> <span data-ttu-id="9b9a0-117">FRR 構成と管理の詳細については、次を参照してください。 [FIN Response Reconciliation の構成](../../adapters-and-accelerators/accelerator-swift/configuring-fin-response-reconciliation.md)と[FIN Response Reconciliation の管理](../../adapters-and-accelerators/accelerator-swift/administering-fin-response-reconciliation.md)します。</span><span class="sxs-lookup"><span data-stu-id="9b9a0-117">For more information about FRR configuration and administration, see [Configuring FIN Response Reconciliation](../../adapters-and-accelerators/accelerator-swift/configuring-fin-response-reconciliation.md) and [Administering FIN Response Reconciliation](../../adapters-and-accelerators/accelerator-swift/administering-fin-response-reconciliation.md).</span></span>  
  
 <span data-ttu-id="9b9a0-118">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9b9a0-118">This section contains:</span></span>  
  
-   [<span data-ttu-id="9b9a0-119">FIN 応答の種類</span><span class="sxs-lookup"><span data-stu-id="9b9a0-119">FIN Response Types</span></span>](../../adapters-and-accelerators/accelerator-swift/fin-response-types.md)  
  
-   [<span data-ttu-id="9b9a0-120">FRR 処理</span><span class="sxs-lookup"><span data-stu-id="9b9a0-120">FRR Processing</span></span>](../../adapters-and-accelerators/accelerator-swift/frr-processing.md)  
  
-   [<span data-ttu-id="9b9a0-121">FRR オーケストレーション</span><span class="sxs-lookup"><span data-stu-id="9b9a0-121">FRR Orchestration</span></span>](../../adapters-and-accelerators/accelerator-swift/frr-orchestration.md)  
  
-   [<span data-ttu-id="9b9a0-122">バックエンド アプリケーションからのメッセージの FRR 受信場所</span><span class="sxs-lookup"><span data-stu-id="9b9a0-122">FRR Receive Location for Messages from the Back-End Application</span></span>](../../adapters-and-accelerators/accelerator-swift/frr-receive-location-for-messages-from-the-back-end-application.md)  
  
-   [<span data-ttu-id="9b9a0-123">SWIFT へのメッセージのための FRR 送信ポート</span><span class="sxs-lookup"><span data-stu-id="9b9a0-123">FRR Send Port for Messages to SWIFT</span></span>](../../adapters-and-accelerators/accelerator-swift/frr-send-port-for-messages-to-swift.md)  
  
-   [<span data-ttu-id="9b9a0-124">SWIFT からのメッセージのための FRR 受信場所</span><span class="sxs-lookup"><span data-stu-id="9b9a0-124">FRR Receive Location for Messages from SWIFT</span></span>](../../adapters-and-accelerators/accelerator-swift/frr-receive-location-for-messages-from-swift.md)  
  
-   [<span data-ttu-id="9b9a0-125">カスタム ハンドラーへのメッセージのための FRR 送信ポート</span><span class="sxs-lookup"><span data-stu-id="9b9a0-125">FRR Send Ports for Messages to the Custom Handlers</span></span>](../../adapters-and-accelerators/accelerator-swift/frr-send-ports-for-messages-to-the-custom-handlers.md)  
  
-   [<span data-ttu-id="9b9a0-126">調整されたメッセージ セットの処理</span><span class="sxs-lookup"><span data-stu-id="9b9a0-126">Handling Reconciled Message Sets</span></span>](../../adapters-and-accelerators/accelerator-swift/handling-reconciled-message-sets.md)