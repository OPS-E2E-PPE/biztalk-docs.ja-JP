---
title: "FIN 対応調整 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5452dbacb8a9a20c8d2e62d62f6043aaea2d18da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="fin-response-reconciliation"></a><span data-ttu-id="1a781-102">FIN 対応調整</span><span class="sxs-lookup"><span data-stu-id="1a781-102">FIN Response Reconciliation</span></span>
<span data-ttu-id="1a781-103">機能は、FIN 対応調整 (FRR)[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]によって送信される対応する元のメッセージに FIN 応答の整合性を保ちます[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="1a781-103">The FIN Response Reconciliation (FRR) feature of [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] reconciles a FIN response with the corresponding original message sent by [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].</span></span> <span data-ttu-id="1a781-104">これは、元のメッセージの状態を確立でき、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]その状態に基づいた手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1a781-104">This establishes the status of the original message, and enables [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] to take steps based upon that status.</span></span> <span data-ttu-id="1a781-105">調整なしこのいない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1a781-105">Without reconciliation, this would not be possible.</span></span> [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="1a781-106">かわかることと、正常終了 (または失敗)、メッセージを送信元 SAA に、送信の状態を示す SAA から受け取った応答必要がありますが、2 つの間の接続を作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="1a781-106"> would know that it successfully (or unsuccessfully) sent the original message to SAA, and it would have the response that it received from SAA, indicating the status of the transmission, but it would not be able to make the connection between the two.</span></span> <span data-ttu-id="1a781-107">FRR は、その接続を確立します。</span><span class="sxs-lookup"><span data-stu-id="1a781-107">FRR establishes that connection.</span></span>  
  
 <span data-ttu-id="1a781-108">FIN 応答は受信確認 (Ack) または否定受信確認応答 (NAKs) に SAA によって送信された[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]、SAA に SWIFT ネットワークは、によって送信され、しに SAA によって転送または[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="1a781-108">FIN responses are acknowledgments (ACKs) or negative acknowledgments (NAKs) sent by SAA to [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)], or sent by the SWIFT network to SAA and then forwarded by SAA to [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].</span></span> <span data-ttu-id="1a781-109">これらの確認の有無は、メッセージのビジネスの状態を定義します。</span><span class="sxs-lookup"><span data-stu-id="1a781-109">The presence or absence of these acknowledgments defines the business status of the message.</span></span> <span data-ttu-id="1a781-110">ビジネス アクティビティ監視 (BAM) のレポートには、このステータスを監視することができます。</span><span class="sxs-lookup"><span data-stu-id="1a781-110">You can monitor this status through Business Activity Monitoring (BAM) reporting.</span></span>  
  
 <span data-ttu-id="1a781-111">FRR の周囲のカスタム アプリケーションの動作を実装することもできます。</span><span class="sxs-lookup"><span data-stu-id="1a781-111">You can also implement custom application behavior around FRR.</span></span> <span data-ttu-id="1a781-112">カスタム ハンドラーは、FIN 応答の調整のセットを処理するための独自のロジックを実装できます。</span><span class="sxs-lookup"><span data-stu-id="1a781-112">A custom handler can implement your own logic for handling reconciled sets of FIN responses.</span></span> <span data-ttu-id="1a781-113">MTS21_FIN_ACKNAK NAK メッセージと共に FRR が関連付けられたメッセージを処理するカスタム ハンドラーの例は、次を参照してください。 [FRR NAK ハンドラー サンプル](../../adapters-and-accelerators/accelerator-swift/frr-nak-handler-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="1a781-113">For an example of a custom handler that processes messages that FRR has correlated with a MTS21_FIN_ACKNAK NAK message, see [FRR NAK Handler Sample](../../adapters-and-accelerators/accelerator-swift/frr-nak-handler-sample.md).</span></span>  
  
 <span data-ttu-id="1a781-114">FRR オーケストレーションがで既定でインストールされている、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]セットアップ プログラム。</span><span class="sxs-lookup"><span data-stu-id="1a781-114">The FRR orchestration is installed by default by the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] setup program.</span></span> <span data-ttu-id="1a781-115">必要とする、受信パイプラインを作成して、FRR システムを構成する受信場所、送信ポート。</span><span class="sxs-lookup"><span data-stu-id="1a781-115">You need to configure the FRR system by creating a receive pipeline, receive locations, and send ports.</span></span> <span data-ttu-id="1a781-116">どのくらいの期間待機は遅延 NAKs、および応答の一般を指定する FRR を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a781-116">You also need to configure FRR to specify how long it should wait for delayed NAKs, and for responses in general.</span></span> <span data-ttu-id="1a781-117">FRR 構成と管理の詳細については、次を参照してください。 [FIN 対応調整を構成する](../../adapters-and-accelerators/accelerator-swift/configuring-fin-response-reconciliation.md)と[FIN 対応調整を管理する](../../adapters-and-accelerators/accelerator-swift/administering-fin-response-reconciliation.md)です。</span><span class="sxs-lookup"><span data-stu-id="1a781-117">For more information about FRR configuration and administration, see [Configuring FIN Response Reconciliation](../../adapters-and-accelerators/accelerator-swift/configuring-fin-response-reconciliation.md) and [Administering FIN Response Reconciliation](../../adapters-and-accelerators/accelerator-swift/administering-fin-response-reconciliation.md).</span></span>  
  
 <span data-ttu-id="1a781-118">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1a781-118">This section contains:</span></span>  
  
-   [<span data-ttu-id="1a781-119">FIN 応答の種類</span><span class="sxs-lookup"><span data-stu-id="1a781-119">FIN Response Types</span></span>](../../adapters-and-accelerators/accelerator-swift/fin-response-types.md)  
  
-   [<span data-ttu-id="1a781-120">FRR 処理</span><span class="sxs-lookup"><span data-stu-id="1a781-120">FRR Processing</span></span>](../../adapters-and-accelerators/accelerator-swift/frr-processing.md)  
  
-   [<span data-ttu-id="1a781-121">FRR オーケストレーション</span><span class="sxs-lookup"><span data-stu-id="1a781-121">FRR Orchestration</span></span>](../../adapters-and-accelerators/accelerator-swift/frr-orchestration.md)  
  
-   [<span data-ttu-id="1a781-122">FRR は、バックエンド アプリケーションからのメッセージの場所を受信します。</span><span class="sxs-lookup"><span data-stu-id="1a781-122">FRR Receive Location for Messages from the Back-End Application</span></span>](../../adapters-and-accelerators/accelerator-swift/frr-receive-location-for-messages-from-the-back-end-application.md)  
  
-   [<span data-ttu-id="1a781-123">SWIFT メッセージの送信ポートを FRR</span><span class="sxs-lookup"><span data-stu-id="1a781-123">FRR Send Port for Messages to SWIFT</span></span>](../../adapters-and-accelerators/accelerator-swift/frr-send-port-for-messages-to-swift.md)  
  
-   [<span data-ttu-id="1a781-124">FRR は、SWIFT からのメッセージの場所を受信します。</span><span class="sxs-lookup"><span data-stu-id="1a781-124">FRR Receive Location for Messages from SWIFT</span></span>](../../adapters-and-accelerators/accelerator-swift/frr-receive-location-for-messages-from-swift.md)  
  
-   [<span data-ttu-id="1a781-125">カスタム ハンドラーへのメッセージの送信ポートを FRR</span><span class="sxs-lookup"><span data-stu-id="1a781-125">FRR Send Ports for Messages to the Custom Handlers</span></span>](../../adapters-and-accelerators/accelerator-swift/frr-send-ports-for-messages-to-the-custom-handlers.md)  
  
-   [<span data-ttu-id="1a781-126">処理は、メッセージの設定を調整</span><span class="sxs-lookup"><span data-stu-id="1a781-126">Handling Reconciled Message Sets</span></span>](../../adapters-and-accelerators/accelerator-swift/handling-reconciled-message-sets.md)