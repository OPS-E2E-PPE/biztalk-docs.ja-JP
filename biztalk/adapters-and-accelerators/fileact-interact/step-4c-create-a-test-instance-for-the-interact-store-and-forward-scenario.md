---
title: '手順 4 C: InterAct ストアと転送シナリオのテスト インスタンスを作成 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 64a69dcc-d307-47c0-87e8-b0cb2a4d655b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 44addc30191dd9541d7f5964a3de0eec244c9993
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225162"
---
# <a name="step-4c-create-a-test-instance-for-the-interact-store-and-forward-scenario"></a><span data-ttu-id="3bc49-102">手順 4 C: InterAct ストアと転送シナリオのテスト インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="3bc49-102">Step 4C: Create a Test Instance for the InterAct Store and Forward Scenario</span></span>
<span data-ttu-id="3bc49-103">この手順を開始する前に行う必要があります[手順 4B: 送信ポートと対話するストア アンド フォワード シナリオの受信ポートを開始](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-store-and-forward.md)です。</span><span class="sxs-lookup"><span data-stu-id="3bc49-103">Before you begin this step, you must complete [Step 4B: Start the Send Ports and Receive Ports for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-store-and-forward.md).</span></span>  
  
### <a name="to-create-a-test-instance"></a><span data-ttu-id="3bc49-104">テスト インスタンスを作成するには</span><span class="sxs-lookup"><span data-stu-id="3bc49-104">To create a test instance</span></span>  
  
1.  <span data-ttu-id="3bc49-105">メモ帳などのテキスト エディターで、新しいファイルを開くし、以下を貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="3bc49-105">Open a new file in a text editor, such as Notepad, and paste the following:</span></span>  
  
    ```  
    <SwInt-ExchangeRequest>  
    <SwInt-Request>  
    <SwInt-RequestPayload>  
    Get Well soon  
    </SwInt-RequestPayload>  
    </SwInt-Request>  
    </SwInt-ExchangeRequest>  
    ```  
  
2.  <span data-ttu-id="3bc49-106">ExchangeReqSimple.xml という名前のファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="3bc49-106">Save the File with the name ExchangeReqSimple.xml.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bc49-107">参照</span><span class="sxs-lookup"><span data-stu-id="3bc49-107">See Also</span></span>  
 <span data-ttu-id="3bc49-108">[手順 4: InterAct ストアと転送のエンド ツー エンド シナリオをテストします。](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-end-to-end-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="3bc49-108">[Step 4: Test the InterAct Store and Forward End-to-End Scenario](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-end-to-end-scenario.md) </span></span>  
 <span data-ttu-id="3bc49-109">[手順 4 a: サービスを開始します SWIFTNet InterAct ストアと転送シナリオ](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="3bc49-109">[Step 4A: Start the SWIFTNet Service for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-interact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="3bc49-110">[手順 4 b: 送信ポートの開始し、受信ポートを InterAct ストアと転送シナリオ](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="3bc49-110">[Step 4B: Start the Send Ports and Receive Ports for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-store-and-forward.md) </span></span>  
 [<span data-ttu-id="3bc49-111">手順 4 D: InterAct ストアと転送シナリオの有効なインスタンスのテスト</span><span class="sxs-lookup"><span data-stu-id="3bc49-111">Step 4D: Test a Valid Instance for the InterAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-the-interact-store-and-forward-scenario.md)