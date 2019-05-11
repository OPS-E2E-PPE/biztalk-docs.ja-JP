---
title: 手順 4 D:InterAct ストア アンド フォワード シナリオ用の有効なインスタンスのテスト |Microsoft Docs
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
ms.openlocfilehash: 6a9bac2a14267b0767cd0498ecfbb8b0f96f686e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364666"
---
# <a name="step-4d-test-a-valid-instance-for-the-interact-store-and-forward-scenario"></a><span data-ttu-id="9e5e5-102">手順 4 D:InterAct ストア アンド フォワード シナリオ用の有効なインスタンスをテストします。</span><span class="sxs-lookup"><span data-stu-id="9e5e5-102">Step 4D: Test a Valid Instance for the InterAct Store and Forward Scenario</span></span>
<span data-ttu-id="9e5e5-103">この手順を開始する前に行う必要があります[手順 4 C:InterAct ストア アンド フォワード シナリオ用にテスト インスタンスを作成](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-interact-store-and-forward-scenario.md)です。</span><span class="sxs-lookup"><span data-stu-id="9e5e5-103">Before you begin this step, you must complete [Step 4C: Create a Test Instance for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-interact-store-and-forward-scenario.md).</span></span>  
  
### <a name="to-test-a-valid-instance"></a><span data-ttu-id="9e5e5-104">有効なインスタンスをテストするには</span><span class="sxs-lookup"><span data-stu-id="9e5e5-104">To test a valid instance</span></span>  
  
1.  <span data-ttu-id="9e5e5-105">Drop the file ExchangeReqSimple.xml into c:\SWIFTAdapterTutorial\Interact\InputRequest_SnF</span><span class="sxs-lookup"><span data-stu-id="9e5e5-105">Drop the file ExchangeReqSimple.xml into c:\SWIFTAdapterTutorial\Interact\InputRequest_SnF</span></span>  
  
2.  <span data-ttu-id="9e5e5-106">しばらくすると、ExchangeReqSimple.xml ファイルがフォルダーから消えることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9e5e5-106">Verify that after a moment, the ExchangeReqSimple.xml file disappears from the folder.</span></span>  
  
3.  <span data-ttu-id="9e5e5-107">C:\SWIFTAdapterTutorial\Interact\HandleRequest に移動します。</span><span class="sxs-lookup"><span data-stu-id="9e5e5-107">Browse to C:\SWIFTAdapterTutorial\Interact\HandleRequest.</span></span> <span data-ttu-id="9e5e5-108">その Sw:HandleRequest はフォルダーを確認します。</span><span class="sxs-lookup"><span data-stu-id="9e5e5-108">Verify that Sw:HandleRequest is in the folder.</span></span>  
  
4.  <span data-ttu-id="9e5e5-109">メモ帳などのテキスト エディターで Sw:HandleRequest メッセージを開き、payload セクションが ExchangeReqSimple.xml ファイルと同じであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9e5e5-109">Open the Sw:HandleRequest message in a text editor, such as Notepad, and verify that the payload section is the same as in the file ExchangeReqSimple.xml.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e5e5-110">参照</span><span class="sxs-lookup"><span data-stu-id="9e5e5-110">See Also</span></span>  
 <span data-ttu-id="9e5e5-111">[手順 4:InterAct ストア アンド フォワード エンド ツー エンド シナリオをテストします。](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-end-to-end-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="9e5e5-111">[Step 4: Test the InterAct Store and Forward End-to-End Scenario](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-end-to-end-scenario.md) </span></span>  
 <span data-ttu-id="9e5e5-112">[手順 4 a:InterAct ストア アンド フォワード シナリオ用に SWIFTNet サービスを開始します。](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="9e5e5-112">[Step 4A: Start the SWIFTNet Service for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-interact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="9e5e5-113">[手順 4 b:送信ポートの開始し、InterAct ストア アンド フォワード シナリオ用の受信ポート](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="9e5e5-113">[Step 4B: Start the Send Ports and Receive Ports for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-store-and-forward.md) </span></span>  
 [<span data-ttu-id="9e5e5-114">手順 4 C:InterAct ストア アンド フォワード シナリオ用のテスト インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="9e5e5-114">Step 4C: Create a Test Instance for the InterAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-interact-store-and-forward-scenario.md)