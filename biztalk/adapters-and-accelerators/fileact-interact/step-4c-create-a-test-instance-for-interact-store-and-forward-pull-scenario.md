---
title: "手順 4 C: InterAct ストア アンド フォワード (プル) シナリオのテスト インスタンスを作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3c937edd-9524-4f8f-9bd1-68e24f2eebdc
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf5d0908593110b04f6e5cd0f5912b66264dc7a2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-4c-create-a-test-instance-for-the-interact-store-and-forward-pull-scenario"></a><span data-ttu-id="78fa2-102">手順 4 C: InterAct ストア アンド フォワード (プル) シナリオのテスト インスタンスを作成</span><span class="sxs-lookup"><span data-stu-id="78fa2-102">Step 4C: Create a Test Instance for the InterAct Store and Forward (Pull) Scenario</span></span>
<span data-ttu-id="78fa2-103">この手順を開始する前に行う必要があります[手順 3 b: InterAct ストアと転送 (するプル) シナリオ用の動的送信ポートにオーケストレーションをバインド](../../adapters-and-accelerators/fileact-interact/step-3b-bind-orchestration-with-dynamic-send-port-for-interact-scenario.md)です。</span><span class="sxs-lookup"><span data-stu-id="78fa2-103">Before you begin this step, you must complete [Step 3B: Bind the orchestration with dynamic send port for InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-bind-orchestration-with-dynamic-send-port-for-interact-scenario.md).</span></span>  
  
### <a name="to-create-a-test-instance"></a><span data-ttu-id="78fa2-104">テスト インスタンスを作成するには</span><span class="sxs-lookup"><span data-stu-id="78fa2-104">To create a test instance</span></span>  
  
1.  <span data-ttu-id="78fa2-105">メモ帳などのテキスト エディターで、新しいファイルを開くし、以下を貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="78fa2-105">Open a new file in a text editor, such as Notepad, and paste the following:</span></span>  
  
    ```  
    SwInt-ExchangeRequest>  
    <SwInt-Request>  
    <SwInt-RequestPayload>  
    Get Well soon  
    </SwInt-RequestPayload>  
    </SwInt-Request>  
    </SwInt-ExchangeRequest>  
  
    ```  
  
2.  <span data-ttu-id="78fa2-106">ExchangeReqSimple.xml という名前のファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="78fa2-106">Save the File with the name ExchangeReqSimple.xml.</span></span>  
  
3.  <span data-ttu-id="78fa2-107">メモ帳などのテキスト エディターで、新しいファイルを開くし、以下を貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="78fa2-107">Open a new file in a text editor, such as Notepad, and paste the following:</span></span>  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>  
    <Sw-ExchangeSnFRequest>  
    <Sw-SnFRequest>  
    <Sw-SnFOpRequest>  
    <Sw-AcquireSnFRequest>  
    <SwInt-Queue>ptsguspp_genericfa!x</SwInt-Queue>  
    <Sw-SessionMode>Pull</Sw-SessionMode>  
    <Sw-ForceAcquire>TRUE</Sw-ForceAcquire>  
    <Sw-OrderBy>FileAct</Sw-OrderBy>  
    <Sw-RecoveryMode>TRUE</Sw-RecoveryMode>  
    </Sw-AcquireSnFRequest>  
    </Sw-SnFOpRequest>  
    </Sw-SnFRequest>  
    </Sw-ExchangeSnFRequest>  
  
    ```  
  
4.  <span data-ttu-id="78fa2-108">名前 acquirequeue.xml でファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="78fa2-108">Save the File with the name acquirequeue.xml.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78fa2-109">参照</span><span class="sxs-lookup"><span data-stu-id="78fa2-109">See Also</span></span>  
 <span data-ttu-id="78fa2-110">[手順 4 a: InterAct ストア アンド フォワード (プル) シナリオの SWIFTNet サービスを開始](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-the-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="78fa2-110">[Step 4A: Start the SWIFTNet Service for the InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-the-interact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="78fa2-111">[手順 4 b: 送信ポートの開始し、InterAct ストア アンド フォワード (プル) シナリオの受信ポート](../../adapters-and-accelerators/fileact-interact/step-4b-start-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="78fa2-111">[Step 4B: Start the Send Ports and Receive Ports for the InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="78fa2-112">手順 4 D: InterAct ストア アンド フォワード (プル) シナリオの有効なインスタンスをテストします。</span><span class="sxs-lookup"><span data-stu-id="78fa2-112">Step 4D: Test a Valid Instance for the InterAct Store and Forward (Pull) Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-interact-store-and-forward-pull-scenario.md)