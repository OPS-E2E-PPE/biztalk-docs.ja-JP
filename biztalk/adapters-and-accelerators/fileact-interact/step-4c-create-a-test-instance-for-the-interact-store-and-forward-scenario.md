---
title: 手順 4 C:InterAct ストア アンド フォワード シナリオ用のテスト インスタンスの作成 |Microsoft Docs
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
ms.openlocfilehash: 0e8a15ba9273346b5038df485e26c3df3234066a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364804"
---
# <a name="step-4c-create-a-test-instance-for-the-interact-store-and-forward-scenario"></a><span data-ttu-id="82bfd-102">手順 4 C:InterAct ストア アンド フォワード シナリオ用のテスト インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="82bfd-102">Step 4C: Create a Test Instance for the InterAct Store and Forward Scenario</span></span>
<span data-ttu-id="82bfd-103">この手順を開始する前に行う必要があります[手順 4 b:送信ポートの開始し、InterAct ストア アンド フォワード シナリオ用の受信ポート](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-store-and-forward.md)します。</span><span class="sxs-lookup"><span data-stu-id="82bfd-103">Before you begin this step, you must complete [Step 4B: Start the Send Ports and Receive Ports for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-store-and-forward.md).</span></span>  
  
### <a name="to-create-a-test-instance"></a><span data-ttu-id="82bfd-104">テスト インスタンスを作成するには</span><span class="sxs-lookup"><span data-stu-id="82bfd-104">To create a test instance</span></span>  
  
1.  <span data-ttu-id="82bfd-105">新しいファイルをメモ帳などのテキスト エディターで開き、次を貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="82bfd-105">Open a new file in a text editor, such as Notepad, and paste the following:</span></span>  
  
    ```  
    <SwInt-ExchangeRequest>  
    <SwInt-Request>  
    <SwInt-RequestPayload>  
    Get Well soon  
    </SwInt-RequestPayload>  
    </SwInt-Request>  
    </SwInt-ExchangeRequest>  
    ```  
  
2.  <span data-ttu-id="82bfd-106">ExchangeReqSimple.xml という名前のファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="82bfd-106">Save the File with the name ExchangeReqSimple.xml.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82bfd-107">参照</span><span class="sxs-lookup"><span data-stu-id="82bfd-107">See Also</span></span>  
 <span data-ttu-id="82bfd-108">[手順 4:InterAct ストア アンド フォワード エンド ツー エンド シナリオをテストします。](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-end-to-end-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="82bfd-108">[Step 4: Test the InterAct Store and Forward End-to-End Scenario](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-end-to-end-scenario.md) </span></span>  
 <span data-ttu-id="82bfd-109">[手順 4 a:InterAct ストア アンド フォワード シナリオ用に SWIFTNet サービスを開始します。](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="82bfd-109">[Step 4A: Start the SWIFTNet Service for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-interact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="82bfd-110">[手順 4 b:送信ポートの開始し、InterAct ストア アンド フォワード シナリオ用の受信ポート](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="82bfd-110">[Step 4B: Start the Send Ports and Receive Ports for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-store-and-forward.md) </span></span>  
 [<span data-ttu-id="82bfd-111">手順 4 D:InterAct ストア アンド フォワード シナリオ用の有効なインスタンスをテストします。</span><span class="sxs-lookup"><span data-stu-id="82bfd-111">Step 4D: Test a Valid Instance for the InterAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-the-interact-store-and-forward-scenario.md)