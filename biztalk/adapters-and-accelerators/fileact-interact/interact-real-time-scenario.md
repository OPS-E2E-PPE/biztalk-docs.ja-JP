---
title: InterAct リアルタイム シナリオ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dc73c84b-3361-41b0-b1b3-dc3c2ab31ccc
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f6d49156bebd46e50ed8b0264d67d1a3ee45cb2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366595"
---
# <a name="interact-real-time-scenario"></a><span data-ttu-id="eb60e-102">InterAct リアルタイム シナリオ</span><span class="sxs-lookup"><span data-stu-id="eb60e-102">InterAct Real-Time Scenario</span></span>
<span data-ttu-id="eb60e-103">このシナリオでは、リアルタイムでメッセージを処理する InterAct アダプターを構成します。</span><span class="sxs-lookup"><span data-stu-id="eb60e-103">In this scenario, you will configure the InterAct adapter to process messages in real time.</span></span> <span data-ttu-id="eb60e-104">現金を報告するなどの SWIFT ソリューションのシナリオで使用することができます。</span><span class="sxs-lookup"><span data-stu-id="eb60e-104">You can use in SWIFT solutions scenarios such as cash reporting.</span></span> <span data-ttu-id="eb60e-105">詳細については、SWIFT Web サイトを参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=100479](http://go.microsoft.com/fwlink/?LinkId=100479)します。</span><span class="sxs-lookup"><span data-stu-id="eb60e-105">For more information, see the SWIFT Web site at [http://go.microsoft.com/fwlink/?LinkId=100479](http://go.microsoft.com/fwlink/?LinkId=100479).</span></span>  
  
 <span data-ttu-id="eb60e-106">このセクションの手順を開始する前に、手順を完了する必要があります[チュートリアルを使用する準備](../../adapters-and-accelerators/fileact-interact/preparing-to-use-the-tutorial1.md)します。</span><span class="sxs-lookup"><span data-stu-id="eb60e-106">Before you begin the steps in this section, you must complete the steps in [Preparing to Use the Tutorial](../../adapters-and-accelerators/fileact-interact/preparing-to-use-the-tutorial1.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="eb60e-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="eb60e-107">In This Section</span></span>  
  
-   [<span data-ttu-id="eb60e-108">ステップ 1: 用に SWIFT アダプターを構成、InterAct リアルタイム シナリオ</span><span class="sxs-lookup"><span data-stu-id="eb60e-108">Step 1: Configure the SWIFT Adapter for the InterAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-real-time-scenario.md)  
  
-   [<span data-ttu-id="eb60e-109">手順 2:用に Paramfile に SWIFTNet 構成を追加、InterAct リアルタイム シナリオ</span><span class="sxs-lookup"><span data-stu-id="eb60e-109">Step 2: Add SWIFTNet Configuration to the Paramfile for the InterAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-interact-real-time-scenario.md)  
  
-   [<span data-ttu-id="eb60e-110">ステップ 3:作成する送信と受信ポートを InterAct リアルタイム シナリオ</span><span class="sxs-lookup"><span data-stu-id="eb60e-110">Step 3: Create Send and Receive Ports for the InterAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md)  
  
-   [<span data-ttu-id="eb60e-111">手順 4:テスト、InterAct リアルタイム エンド ツー エンドのシナリオ</span><span class="sxs-lookup"><span data-stu-id="eb60e-111">Step 4: Test the InterAct Real-Time End-to-End Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-real-time-end-to-end-scenario.md)