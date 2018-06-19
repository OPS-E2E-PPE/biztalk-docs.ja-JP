---
title: '手順 4 D: InterAct ストアと転送シナリオの有効なインスタンスをテスト |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6aa49df8-ccf6-455a-99ff-38879d2b7bf9
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5d27b23195adffc5915d8cb2170dca9e975ec94
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224282"
---
# <a name="step-4d-test-a-valid-instance-for-the-interact-store-and-forward-scenario"></a><span data-ttu-id="c17b9-102">手順 4 D: InterAct ストアと転送シナリオの有効なインスタンスのテスト</span><span class="sxs-lookup"><span data-stu-id="c17b9-102">Step 4D: Test a Valid Instance for the InterAct Store and Forward Scenario</span></span>
<span data-ttu-id="c17b9-103">この手順を開始する前に行う必要があります[手順 4 C: InterAct ストア アンド フォワードのシナリオのテスト インスタンスを作成する](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-interact-store-and-forward-scenario.md)です。</span><span class="sxs-lookup"><span data-stu-id="c17b9-103">Before you begin this step, you must complete [Step 4C: Create a Test Instance for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-interact-store-and-forward-scenario.md).</span></span>  
  
### <a name="to-test-a-valid-instance"></a><span data-ttu-id="c17b9-104">有効なインスタンスをテストするには</span><span class="sxs-lookup"><span data-stu-id="c17b9-104">To test a valid instance</span></span>  
  
1.  <span data-ttu-id="c17b9-105">C:\SWIFTAdapterTutorial\Interact\InputRequest_SnF に ExchangeReqSimple.xml ファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="c17b9-105">Drop the file ExchangeReqSimple.xml into c:\SWIFTAdapterTutorial\Interact\InputRequest_SnF</span></span>  
  
2.  <span data-ttu-id="c17b9-106">しばらくすると、ExchangeReqSimple.xml ファイルがフォルダーから消えますことを確認します。</span><span class="sxs-lookup"><span data-stu-id="c17b9-106">Verify that after a moment, the ExchangeReqSimple.xml file disappears from the folder.</span></span>  
  
3.  <span data-ttu-id="c17b9-107">C:\SWIFTAdapterTutorial\Interact\HandleRequest を参照します。</span><span class="sxs-lookup"><span data-stu-id="c17b9-107">Browse to C:\SWIFTAdapterTutorial\Interact\HandleRequest.</span></span> <span data-ttu-id="c17b9-108">フォルダー内にその Sw:HandleRequest を確認します。</span><span class="sxs-lookup"><span data-stu-id="c17b9-108">Verify that Sw:HandleRequest is in the folder.</span></span>  
  
4.  <span data-ttu-id="c17b9-109">Sw:HandleRequest メッセージをメモ帳などのテキスト エディターで開き、payload セクションが ExchangeReqSimple.xml ファイルのものと同じであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c17b9-109">Open the Sw:HandleRequest message in a text editor, such as Notepad, and verify that the payload section is the same as in the file ExchangeReqSimple.xml.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c17b9-110">参照</span><span class="sxs-lookup"><span data-stu-id="c17b9-110">See Also</span></span>  
 <span data-ttu-id="c17b9-111">[手順 4: InterAct ストアと転送のエンド ツー エンド シナリオをテストします。](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-end-to-end-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="c17b9-111">[Step 4: Test the InterAct Store and Forward End-to-End Scenario](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-end-to-end-scenario.md) </span></span>  
 <span data-ttu-id="c17b9-112">[手順 4 a: サービスを開始します SWIFTNet InterAct ストアと転送シナリオ](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="c17b9-112">[Step 4A: Start the SWIFTNet Service for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-interact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="c17b9-113">[手順 4 b: 送信ポートの開始し、受信ポートを InterAct ストアと転送シナリオ](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="c17b9-113">[Step 4B: Start the Send Ports and Receive Ports for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-store-and-forward.md) </span></span>  
 [<span data-ttu-id="c17b9-114">手順 4 C: InterAct ストアと転送シナリオのテスト インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="c17b9-114">Step 4C: Create a Test Instance for the InterAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-interact-store-and-forward-scenario.md)