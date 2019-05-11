---
title: 手順 4 D:InterAct ストア アンド フォワード (プル) シナリオ用の有効なインスタンスのテスト |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7c2933d0-bbe3-4486-832e-5009b2d760ac
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 100a2ba467515e5d041fcb47b03092d5c7c49cf2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364754"
---
# <a name="step-4d-test-a-valid-instance-for-the-interact-store-and-forward-pull-scenario"></a><span data-ttu-id="95328-102">手順 4 D:InterAct ストア アンド フォワード (プル) シナリオ用の有効なインスタンスをテストします。</span><span class="sxs-lookup"><span data-stu-id="95328-102">Step 4D: Test a Valid Instance for the InterAct Store and Forward (Pull) Scenario</span></span>
<span data-ttu-id="95328-103">この手順を開始する前に行う必要があります[手順 4 C:InterAct ストア アンド フォワード (プル) シナリオのテスト インスタンスを作成](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-interact-store-and-forward-pull-scenario.md)です。</span><span class="sxs-lookup"><span data-stu-id="95328-103">Before you begin this step, you must complete [Step 4C: Create a Test Instance for the InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-interact-store-and-forward-pull-scenario.md).</span></span>  
  
### <a name="to-test-a-valid-instance"></a><span data-ttu-id="95328-104">有効なインスタンスをテストするには</span><span class="sxs-lookup"><span data-stu-id="95328-104">To test a valid instance</span></span>  
  
1.  <span data-ttu-id="95328-105">ファイルの ExchangeReqSimple.xml c:\SWIFTAdapterTutorial\Interact\InputRequest_SnF にドロップします。</span><span class="sxs-lookup"><span data-stu-id="95328-105">Drop the file ExchangeReqSimple.xml into c:\SWIFTAdapterTutorial\Interact\InputRequest_SnF.</span></span>  
  
2.  <span data-ttu-id="95328-106">しばらくすると、ExchangeReqSimple.xml ファイルがフォルダーから消えることを確認します。</span><span class="sxs-lookup"><span data-stu-id="95328-106">Verify that after a moment, the ExchangeReqSimple.xml file disappears from the folder.</span></span>  
  
3.  <span data-ttu-id="95328-107">Drop the file acquirequeue.xml into c:\SWIFTAdapterTutorial\Interact\PullRequest.</span><span class="sxs-lookup"><span data-stu-id="95328-107">Drop the file acquirequeue.xml into c:\SWIFTAdapterTutorial\Interact\PullRequest.</span></span>  
  
4.  <span data-ttu-id="95328-108">C:\SWIFTAdapterTutorial\Interact\PullResponse 確認 Sw:HandleRequest は、フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="95328-108">Browse to C:\SWIFTAdapterTutorial\Interact\PullResponse Verify that Sw:HandleRequest is in the folder.</span></span>  
  
5.  <span data-ttu-id="95328-109">メモ帳などのテキスト エディターで Sw:HandleRequest メッセージを開き、payload セクションが ExchangeReqSimple.xml ファイルと同じであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="95328-109">Open the Sw:HandleRequest message in a text editor, such as Notepad, and verify that the payload section is the same as in the file ExchangeReqSimple.xml.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95328-110">参照</span><span class="sxs-lookup"><span data-stu-id="95328-110">See Also</span></span>  
 <span data-ttu-id="95328-111">[手順 4 a:InterAct ストア アンド フォワード (プル) シナリオ用に SWIFTNet サービスを開始します。](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-the-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="95328-111">[Step 4A: Start the SWIFTNet Service for the InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-the-interact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="95328-112">[手順 4 b:送信ポートの開始し、InterAct ストア アンド フォワード (プル) シナリオ用の受信ポート](../../adapters-and-accelerators/fileact-interact/step-4b-start-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="95328-112">[Step 4B: Start the Send Ports and Receive Ports for the InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="95328-113">手順 4 C:InterAct ストア アンド フォワード (プル) シナリオのテスト インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="95328-113">Step 4C: Create a Test Instance for the InterAct Store and Forward (Pull) Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-interact-store-and-forward-pull-scenario.md)