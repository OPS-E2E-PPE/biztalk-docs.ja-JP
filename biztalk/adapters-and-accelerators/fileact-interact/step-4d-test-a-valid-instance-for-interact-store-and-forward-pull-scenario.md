---
title: '手順 4 D: InterAct ストア アンド フォワード (プル) シナリオの有効なインスタンスをテスト |Microsoft ドキュメント'
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
ms.openlocfilehash: 9c9c8ea24eeb5541cf84448363ca91fcb8171f19
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223946"
---
# <a name="step-4d-test-a-valid-instance-for-the-interact-store-and-forward-pull-scenario"></a><span data-ttu-id="40b16-102">手順 4 D: InterAct ストア アンド フォワード (プル) シナリオの有効なインスタンスをテストします。</span><span class="sxs-lookup"><span data-stu-id="40b16-102">Step 4D: Test a Valid Instance for the InterAct Store and Forward (Pull) Scenario</span></span>
<span data-ttu-id="40b16-103">この手順を開始する前に行う必要があります[手順 4 C: InterAct ストア アンド フォワード (プル) シナリオのテスト インスタンスを作成する](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-interact-store-and-forward-pull-scenario.md)です。</span><span class="sxs-lookup"><span data-stu-id="40b16-103">Before you begin this step, you must complete [Step 4C: Create a Test Instance for the InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-interact-store-and-forward-pull-scenario.md).</span></span>  
  
### <a name="to-test-a-valid-instance"></a><span data-ttu-id="40b16-104">有効なインスタンスをテストするには</span><span class="sxs-lookup"><span data-stu-id="40b16-104">To test a valid instance</span></span>  
  
1.  <span data-ttu-id="40b16-105">ファイル ExchangeReqSimple.xml c:\SWIFTAdapterTutorial\Interact\InputRequest_SnF にドロップします。</span><span class="sxs-lookup"><span data-stu-id="40b16-105">Drop the file ExchangeReqSimple.xml into c:\SWIFTAdapterTutorial\Interact\InputRequest_SnF.</span></span>  
  
2.  <span data-ttu-id="40b16-106">しばらくすると、ExchangeReqSimple.xml ファイルがフォルダーから消えますことを確認します。</span><span class="sxs-lookup"><span data-stu-id="40b16-106">Verify that after a moment, the ExchangeReqSimple.xml file disappears from the folder.</span></span>  
  
3.  <span data-ttu-id="40b16-107">C:\SWIFTAdapterTutorial\Interact\PullRequest ファイル acquirequeue.xml にドロップします。</span><span class="sxs-lookup"><span data-stu-id="40b16-107">Drop the file acquirequeue.xml into c:\SWIFTAdapterTutorial\Interact\PullRequest.</span></span>  
  
4.  <span data-ttu-id="40b16-108">参照がフォルダー内に Sw:HandleRequest C:\SWIFTAdapterTutorial\Interact\PullResponse のことを確認します。</span><span class="sxs-lookup"><span data-stu-id="40b16-108">Browse to C:\SWIFTAdapterTutorial\Interact\PullResponse Verify that Sw:HandleRequest is in the folder.</span></span>  
  
5.  <span data-ttu-id="40b16-109">Sw:HandleRequest メッセージをメモ帳などのテキスト エディターで開き、payload セクションが ExchangeReqSimple.xml ファイルのものと同じであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="40b16-109">Open the Sw:HandleRequest message in a text editor, such as Notepad, and verify that the payload section is the same as in the file ExchangeReqSimple.xml.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40b16-110">参照</span><span class="sxs-lookup"><span data-stu-id="40b16-110">See Also</span></span>  
 <span data-ttu-id="40b16-111">[手順 4 a: InterAct ストア アンド フォワード (プル) シナリオの SWIFTNet サービスを開始](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-the-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="40b16-111">[Step 4A: Start the SWIFTNet Service for the InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-the-interact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="40b16-112">[手順 4 b: 送信ポートの開始し、InterAct ストア アンド フォワード (プル) シナリオの受信ポート](../../adapters-and-accelerators/fileact-interact/step-4b-start-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="40b16-112">[Step 4B: Start the Send Ports and Receive Ports for the InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="40b16-113">手順 4 C: InterAct ストア アンド フォワード (プル) シナリオのテスト インスタンスを作成</span><span class="sxs-lookup"><span data-stu-id="40b16-113">Step 4C: Create a Test Instance for the InterAct Store and Forward (Pull) Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-interact-store-and-forward-pull-scenario.md)