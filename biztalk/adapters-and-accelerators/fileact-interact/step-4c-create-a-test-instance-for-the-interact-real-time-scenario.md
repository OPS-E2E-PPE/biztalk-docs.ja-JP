---
title: '手順 4 C: のテスト インスタンスを作成、リアルタイムのシナリオを対話 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3557acdc-eb3f-4c70-b64a-3f523a1ba650
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21c0035074eba0eec6994aa7ab024afbcec10984
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224418"
---
# <a name="step-4c-create-a-test-instance-for-the-interact-real-time-scenario"></a><span data-ttu-id="140c0-102">手順 4 C: のテスト インスタンスを作成、リアルタイムのシナリオの対話</span><span class="sxs-lookup"><span data-stu-id="140c0-102">Step 4C: Create a Test Instance for the InterAct Real-Time Scenario</span></span>
<span data-ttu-id="140c0-103">この手順を開始する前に行う必要があります[手順 4B: 対話リアルタイム シナリオでは、送信ポートと受信ポートを開始](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-real-time-scenario.md)です。</span><span class="sxs-lookup"><span data-stu-id="140c0-103">Before you begin this step, you must complete [Step 4B: Start the Send Ports and Receive Ports for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-real-time-scenario.md).</span></span>  
  
### <a name="to-create-a-test-instance"></a><span data-ttu-id="140c0-104">テスト インスタンスを作成するには</span><span class="sxs-lookup"><span data-stu-id="140c0-104">To create a test instance</span></span>  
  
1.  <span data-ttu-id="140c0-105">メモ帳などのテキスト エディターで、新しいファイルを開くし、以下を貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="140c0-105">Open a new file in a text editor, such as Notepad, and paste the following:</span></span>  
  
    ```  
    <SwInt-ExchangeRequest>  
    <SwInt-Request>  
    <SwInt-RequestPayload>  
    Get Well soon  
    </SwInt-RequestPayload>  
    </SwInt-Request>  
    </SwInt-ExchangeRequest>  
    ```  
  
2.  <span data-ttu-id="140c0-106">名前のファイルを保存**ExchangeReqSimple.xml**です。</span><span class="sxs-lookup"><span data-stu-id="140c0-106">Save the file with the name **ExchangeReqSimple.xml**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="140c0-107">参照</span><span class="sxs-lookup"><span data-stu-id="140c0-107">See Also</span></span>  
 <span data-ttu-id="140c0-108">[手順 4: テスト、リアルタイムのエンド ツー エンド シナリオの対話](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-real-time-end-to-end-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="140c0-108">[Step 4: Test the InterAct Real-Time End-to-End Scenario](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-real-time-end-to-end-scenario.md) </span></span>  
 <span data-ttu-id="140c0-109">[手順 4 a: SWIFTNet サービスの開始](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service.md) </span><span class="sxs-lookup"><span data-stu-id="140c0-109">[Step 4A: Start the SWIFTNet Service](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service.md) </span></span>  
 <span data-ttu-id="140c0-110">[手順 4 b: 送信ポートの開始し、受信のポート、リアルタイムのシナリオの対話](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="140c0-110">[Step 4B: Start the Send Ports and Receive Ports for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-real-time-scenario.md) </span></span>  
 [<span data-ttu-id="140c0-111">手順 4 D: テストの有効なインスタンス、リアルタイムのシナリオの対話</span><span class="sxs-lookup"><span data-stu-id="140c0-111">Step 4D: Test a Valid Instance for the InterAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-the-interact-real-time-scenario.md)