---
title: "手順 4 D: FileAct ストア アンド フォワード (プル) シナリオの有効なインスタンスのテスト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 33c7aabe-206f-4b89-b739-ac1e63675451
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf6f53257ff2a9194cf85597d0806780f15c8e52
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-4d-test-a-valid-instance-for-the-fileact-store-and-forward-pull-scenario"></a><span data-ttu-id="a88f4-102">手順 4 D: FileAct ストア アンド フォワード (プル) シナリオの有効なインスタンスのテスト</span><span class="sxs-lookup"><span data-stu-id="a88f4-102">Step 4D: Test a Valid Instance for the FileAct Store and Forward (Pull) Scenario</span></span>
<span data-ttu-id="a88f4-103">この手順を開始する前に行う必要があります[手順 4 C: FileAct ストア アンド フォワード (プル) シナリオのテスト インスタンスを作成する](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-fileact-store-and-forward-pull-scenario.md)です。</span><span class="sxs-lookup"><span data-stu-id="a88f4-103">Before you begin this step, you must complete [Step 4C: Create a Test Instance for the FileAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-fileact-store-and-forward-pull-scenario.md).</span></span>  
  
### <a name="to-test-a-valid-instance"></a><span data-ttu-id="a88f4-104">有効なインスタンスをテストするには</span><span class="sxs-lookup"><span data-stu-id="a88f4-104">To test a valid instance</span></span>  
  
1.  <span data-ttu-id="a88f4-105">PutReqSimple.xml ファイル ドロップに**C:\SWIFTAdapterTutorial\Fileact\FileRequestDropSnF**です。</span><span class="sxs-lookup"><span data-stu-id="a88f4-105">Drop the file PutReqSimple.xml into **C:\SWIFTAdapterTutorial\Fileact\FileRequestDropSnF**.</span></span>  
  
2.  <span data-ttu-id="a88f4-106">しばらくすると、PutReqSimple.xml ファイルがフォルダーから消えますことを確認します。</span><span class="sxs-lookup"><span data-stu-id="a88f4-106">Verify that after a moment, the PutReqSimple.xml file disappears from the folder.</span></span>  
  
3.  <span data-ttu-id="a88f4-107">ドロップにファイル fileactcquirequeue.xml **C:\SWIFTAdapterTutorial\FileAct\PullRequest**です。</span><span class="sxs-lookup"><span data-stu-id="a88f4-107">Drop the file fileactcquirequeue.xml into **C:\SWIFTAdapterTutorial\FileAct\PullRequest**.</span></span>  
  
4.  <span data-ttu-id="a88f4-108">Sample_Put.txt ファイルが転送されたことを確認してください**C:\SWIFTAdapterTutorial\Fileact\ClientLocation**に**C:\SWIFTAdapterTutorial\Fileact\ServerLocation**、に応答が表示されていると。**C:\SWIFTAdapterTutorial\PullResponse**です。</span><span class="sxs-lookup"><span data-stu-id="a88f4-108">Verify that the Sample_Put.txt file is transferred from **C:\SWIFTAdapterTutorial\Fileact\ClientLocation** to **C:\SWIFTAdapterTutorial\Fileact\ServerLocation**, and that responses appear in **C:\SWIFTAdapterTutorial\PullResponse**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a88f4-109">参照</span><span class="sxs-lookup"><span data-stu-id="a88f4-109">See Also</span></span>  
 <span data-ttu-id="a88f4-110">[手順 4 a: FileAct ストア アンド フォワード (プル) シナリオの SWIFTNet サービスの開始](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-fileact-store-and-forward-pull-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="a88f4-110">[Step 4A: Start the SWIFTNet Service for the FileAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-fileact-store-and-forward-pull-scenario.md) </span></span>  
 <span data-ttu-id="a88f4-111">[手順 4 b: 送信ポートの開始し、FileAct ストア アンド フォワード (プル) シナリオの受信ポート](../../adapters-and-accelerators/fileact-interact/step-4b-start-send-and-receive-ports-for-fileact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="a88f4-111">[Step 4B: Start the Send Ports and Receive Ports for the FileAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-send-and-receive-ports-for-fileact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="a88f4-112">手順 4 C: FileAct ストア アンド フォワード (プル) シナリオのテスト インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="a88f4-112">Step 4C: Create a Test Instance for the FileAct Store and Forward (Pull) Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-fileact-store-and-forward-pull-scenario.md)