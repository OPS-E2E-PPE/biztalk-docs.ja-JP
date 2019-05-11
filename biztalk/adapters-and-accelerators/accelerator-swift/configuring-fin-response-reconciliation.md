---
title: FIN Response Reconciliation の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FIN Response Reconciliation, configuring
- configuring, FIN Response Reconciliation
ms.assetid: dc934530-76ff-4cdb-b182-46f9ea0343b7
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6fa404335d4136c2c51f990d8c81b753bfcc020c
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65527524"
---
# <a name="configuring-fin-response-reconciliation"></a><span data-ttu-id="57472-102">FIN Response Reconciliation の構成</span><span class="sxs-lookup"><span data-stu-id="57472-102">Configuring FIN Response Reconciliation</span></span>
<span data-ttu-id="57472-103">Microsoft を構成するのには、次のセクションで手順を実行する必要があります[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]FIN 応答の調整 (FRR) 機能を次の図に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="57472-103">You must perform the steps in the following sections to configure the Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] FIN Response Reconciliation (FRR) feature, as shown in the following figure.</span></span>  
  
 <span data-ttu-id="57472-104">![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-frr-configuration.jpg "A4SWIFT_FRR_Configuration")</span><span class="sxs-lookup"><span data-stu-id="57472-104">![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-frr-configuration.jpg "A4SWIFT_FRR_Configuration")</span></span>  
  
 <span data-ttu-id="57472-105">A4SWIFT のインストール ウィザードでは、Message Repair および New Submission と FRR、または Message Repair and New Submission FRR、または Message Repair and New Submission せず FRR せずにインストールできます。</span><span class="sxs-lookup"><span data-stu-id="57472-105">In the A4SWIFT Installation Wizard, you can choose to install Message Repair and New Submission and FRR, or Message Repair and New Submission without FRR, or FRR without Message Repair and New Submission.</span></span> <span data-ttu-id="57472-106">その結果、このセクションの手順をインストールおよび Message Repair and New Submission の構成が想定しないでください。</span><span class="sxs-lookup"><span data-stu-id="57472-106">As a result, the instructions in this section do not assume that you are installing and configuring Message Repair and New Submission.</span></span> <span data-ttu-id="57472-107">ただし、前提としている手順を実行したこと、 [A4SWIFT ランタイムの構成](../../adapters-and-accelerators/accelerator-swift/configuring-the-a4swift-runtime.md)します。</span><span class="sxs-lookup"><span data-stu-id="57472-107">They do, however, assume that you have performed the steps in the [Configuring the A4SWIFT Runtime](../../adapters-and-accelerators/accelerator-swift/configuring-the-a4swift-runtime.md).</span></span>  
  
 <span data-ttu-id="57472-108">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="57472-108">This section contains:</span></span>  
  
-   [<span data-ttu-id="57472-109">FRR オーケストレーションのバインドと開始</span><span class="sxs-lookup"><span data-stu-id="57472-109">Binding and Starting the FRR Orchestration</span></span>](../../adapters-and-accelerators/accelerator-swift/binding-and-starting-the-frr-orchestration.md)  
  
-   [<span data-ttu-id="57472-110">FRR 受信パイプラインの作成</span><span class="sxs-lookup"><span data-stu-id="57472-110">Creating the FRR Receive Pipeline</span></span>](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-receive-pipeline.md)  
  
-   [<span data-ttu-id="57472-111">バックエンド アプリケーションからの受信用として FRR 受信場所を作成する</span><span class="sxs-lookup"><span data-stu-id="57472-111">Creating the FRR Receive Location for Receiving from the Back-End Application</span></span>](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-receive-location-for-receiving-from-the-back-end-application.md)  
  
-   [<span data-ttu-id="57472-112">SWIFT からの受信用として FRR 受信場所を作成する</span><span class="sxs-lookup"><span data-stu-id="57472-112">Creating the FRR Receive Location for Receiving from SWIFT</span></span>](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-receive-location-for-receiving-from-swift.md)  
  
-   [<span data-ttu-id="57472-113">FRR 送信パイプラインの作成</span><span class="sxs-lookup"><span data-stu-id="57472-113">Creating the FRR Send Pipeline</span></span>](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-pipeline.md)  
  
-   [<span data-ttu-id="57472-114">SWIFT への送信用として FRR 送信ポートを作成する</span><span class="sxs-lookup"><span data-stu-id="57472-114">Creating the FRR Send Port for Sending to SWIFT</span></span>](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-port-for-sending-to-swift.md)  
  
-   [<span data-ttu-id="57472-115">カスタム ハンドラーへの送信用として FRR 送信ポートを作成する</span><span class="sxs-lookup"><span data-stu-id="57472-115">Creating the FRR Send Ports for Sending to the Custom Handlers</span></span>](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-ports-for-sending-to-the-custom-handlers.md)