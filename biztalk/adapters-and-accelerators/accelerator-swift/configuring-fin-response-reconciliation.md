---
title: "FIN 対応調整の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- FIN Response Reconciliation, configuring
- configuring, FIN Response Reconciliation
ms.assetid: dc934530-76ff-4cdb-b182-46f9ea0343b7
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 384a2ea27e3d208864c8b16ec52562e6e1cfa28e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-fin-response-reconciliation"></a><span data-ttu-id="e4869-102">FIN 対応調整を構成します。</span><span class="sxs-lookup"><span data-stu-id="e4869-102">Configuring FIN Response Reconciliation</span></span>
<span data-ttu-id="e4869-103">次のセクションを構成する手順を実行する必要があります、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] FIN 対応調整 (FRR) 機能を次の図に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="e4869-103">You must perform the steps in the following sections to configure the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] FIN Response Reconciliation (FRR) feature, as shown in the following figure.</span></span>  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-frr-configuration.jpg "A4SWIFT_FRR_Configuration")  
  
 <span data-ttu-id="e4869-104">A4SWIFT のインストール ウィザードで、Message Repair および New Submission と FRR、または Message Repair and New Submission FRR、または Message Repair and New Submission せず FRR なしのインストールを選択できます。</span><span class="sxs-lookup"><span data-stu-id="e4869-104">In the A4SWIFT Installation Wizard, you can choose to install Message Repair and New Submission and FRR, or Message Repair and New Submission without FRR, or FRR without Message Repair and New Submission.</span></span> <span data-ttu-id="e4869-105">その結果、このセクションの手順に限りませんをインストールしている Message Repair and New Submission を構成します。</span><span class="sxs-lookup"><span data-stu-id="e4869-105">As a result, the instructions in this section do not assume that you are installing and configuring Message Repair and New Submission.</span></span> <span data-ttu-id="e4869-106">」の手順を実行したこと、ただし、前提、 [A4SWIFT ランタイムを構成する](../../adapters-and-accelerators/accelerator-swift/configuring-the-a4swift-runtime.md)です。</span><span class="sxs-lookup"><span data-stu-id="e4869-106">They do, however, assume that you have performed the steps in the [Configuring the A4SWIFT Runtime](../../adapters-and-accelerators/accelerator-swift/configuring-the-a4swift-runtime.md).</span></span>  
  
 <span data-ttu-id="e4869-107">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e4869-107">This section contains:</span></span>  
  
-   [<span data-ttu-id="e4869-108">バインドおよび FRR オーケストレーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="e4869-108">Binding and Starting the FRR Orchestration</span></span>](../../adapters-and-accelerators/accelerator-swift/binding-and-starting-the-frr-orchestration.md)  
  
-   [<span data-ttu-id="e4869-109">受信パイプラインの FRR の作成</span><span class="sxs-lookup"><span data-stu-id="e4869-109">Creating the FRR Receive Pipeline</span></span>](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-receive-pipeline.md)  
  
-   [<span data-ttu-id="e4869-110">バックエンド アプリケーションから受信するための受信場所の FRR を作成します。</span><span class="sxs-lookup"><span data-stu-id="e4869-110">Creating the FRR Receive Location for Receiving from the Back-End Application</span></span>](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-receive-location-for-receiving-from-the-back-end-application.md)  
  
-   [<span data-ttu-id="e4869-111">SWIFT から受信するための受信場所の FRR を作成します。</span><span class="sxs-lookup"><span data-stu-id="e4869-111">Creating the FRR Receive Location for Receiving from SWIFT</span></span>](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-receive-location-for-receiving-from-swift.md)  
  
-   [<span data-ttu-id="e4869-112">FRR 送信パイプラインを作成します。</span><span class="sxs-lookup"><span data-stu-id="e4869-112">Creating the FRR Send Pipeline</span></span>](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-pipeline.md)  
  
-   [<span data-ttu-id="e4869-113">SWIFT に送信するための FRR 送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="e4869-113">Creating the FRR Send Port for Sending to SWIFT</span></span>](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-port-for-sending-to-swift.md)  
  
-   [<span data-ttu-id="e4869-114">カスタム ハンドラーに送信するための FRR 送信ポートの作成</span><span class="sxs-lookup"><span data-stu-id="e4869-114">Creating the FRR Send Ports for Sending to the Custom Handlers</span></span>](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-ports-for-sending-to-the-custom-handlers.md)