---
title: 手順 4 C:テスト インスタンスを作成、InterAct リアルタイム シナリオ |Microsoft Docs
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
ms.openlocfilehash: e4539670824f23ddd4b4104da890c38ed6736fc6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364794"
---
# <a name="step-4c-create-a-test-instance-for-the-interact-real-time-scenario"></a><span data-ttu-id="ccfc5-102">手順 4 C:テスト インスタンスを作成、InterAct リアルタイム シナリオ</span><span class="sxs-lookup"><span data-stu-id="ccfc5-102">Step 4C: Create a Test Instance for the InterAct Real-Time Scenario</span></span>
<span data-ttu-id="ccfc5-103">この手順を開始する前に行う必要があります[手順 4 b:送信ポートの開始し、受信ポートを InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-real-time-scenario.md)します。</span><span class="sxs-lookup"><span data-stu-id="ccfc5-103">Before you begin this step, you must complete [Step 4B: Start the Send Ports and Receive Ports for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-real-time-scenario.md).</span></span>  
  
### <a name="to-create-a-test-instance"></a><span data-ttu-id="ccfc5-104">テスト インスタンスを作成するには</span><span class="sxs-lookup"><span data-stu-id="ccfc5-104">To create a test instance</span></span>  
  
1.  <span data-ttu-id="ccfc5-105">新しいファイルをメモ帳などのテキスト エディターで開き、次を貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="ccfc5-105">Open a new file in a text editor, such as Notepad, and paste the following:</span></span>  
  
    ```  
    <SwInt-ExchangeRequest>  
    <SwInt-Request>  
    <SwInt-RequestPayload>  
    Get Well soon  
    </SwInt-RequestPayload>  
    </SwInt-Request>  
    </SwInt-ExchangeRequest>  
    ```  
  
2.  <span data-ttu-id="ccfc5-106">名前のファイルを保存**ExchangeReqSimple.xml**します。</span><span class="sxs-lookup"><span data-stu-id="ccfc5-106">Save the file with the name **ExchangeReqSimple.xml**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccfc5-107">参照</span><span class="sxs-lookup"><span data-stu-id="ccfc5-107">See Also</span></span>  
 <span data-ttu-id="ccfc5-108">[手順 4:テスト、InterAct リアルタイム エンド ツー エンドのシナリオ](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-real-time-end-to-end-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="ccfc5-108">[Step 4: Test the InterAct Real-Time End-to-End Scenario](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-real-time-end-to-end-scenario.md) </span></span>  
 <span data-ttu-id="ccfc5-109">[手順 4 a:SWIFTNet サービスを開始します。](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service.md) </span><span class="sxs-lookup"><span data-stu-id="ccfc5-109">[Step 4A: Start the SWIFTNet Service](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service.md) </span></span>  
 <span data-ttu-id="ccfc5-110">[手順 4 b:送信ポートの開始し、受信ポートを InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="ccfc5-110">[Step 4B: Start the Send Ports and Receive Ports for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-real-time-scenario.md) </span></span>  
 [<span data-ttu-id="ccfc5-111">手順 4 D:テストの有効なインスタンス、InterAct リアルタイム シナリオ</span><span class="sxs-lookup"><span data-stu-id="ccfc5-111">Step 4D: Test a Valid Instance for the InterAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-the-interact-real-time-scenario.md)