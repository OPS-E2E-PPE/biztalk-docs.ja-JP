---
title: "手順 4 D: テストの有効なインスタンス、リアルタイムのシナリオを対話 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e163c3ac-a00d-40cf-b1b8-4a38f74ab0e8
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94bdb2acd8147ec5041df7d6a1c4324ca833d9e4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-4d-test-a-valid-instance-for-the-interact-real-time-scenario"></a><span data-ttu-id="f4998-102">手順 4 D: テストの有効なインスタンス、リアルタイムのシナリオの対話</span><span class="sxs-lookup"><span data-stu-id="f4998-102">Step 4D: Test a Valid Instance for the InterAct Real-Time Scenario</span></span>
<span data-ttu-id="f4998-103">この手順を開始する前に行う必要があります[手順 4 C: 対話リアルタイム シナリオのテスト インスタンスを作成](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-interact-real-time-scenario.md)です。</span><span class="sxs-lookup"><span data-stu-id="f4998-103">Before you begin this step, you must complete [Step 4C: Create a Test Instance for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-interact-real-time-scenario.md).</span></span>  
  
### <a name="to-test-a-valid-instance"></a><span data-ttu-id="f4998-104">有効なインスタンスをテストするには</span><span class="sxs-lookup"><span data-stu-id="f4998-104">To test a valid instance</span></span>  
  
1.  <span data-ttu-id="f4998-105">C:\SWIFTAdapterTutorial\Interact\InputRequest_RealTime に ExchangeReqSimple.xml ファイルをドロップします。</span><span class="sxs-lookup"><span data-stu-id="f4998-105">Drop the file ExchangeReqSimple.xml into C:\SWIFTAdapterTutorial\Interact\InputRequest_RealTime.</span></span>  
  
2.  <span data-ttu-id="f4998-106">しばらくすると、ExchangeReqSimple.xml ファイルがフォルダーから消えますことを確認します。</span><span class="sxs-lookup"><span data-stu-id="f4998-106">Verify that after a moment, the ExchangeReqSimple.xml file disappears from the folder.</span></span>  
  
3.  <span data-ttu-id="f4998-107">C:\SWIFTAdapterTutorial\Interact\HandleRequest Sw:HandleRequest ハンドル要求メッセージを表示するを参照します。</span><span class="sxs-lookup"><span data-stu-id="f4998-107">Browse to C:\SWIFTAdapterTutorial\Interact\HandleRequest to view the handle request message, Sw:HandleRequest.</span></span>  
  
4.  <span data-ttu-id="f4998-108">C:\SWIFTAdapterTutorial\Interact\Response Sw:HandleResponse ハンドル応答メッセージを表示するを参照します。</span><span class="sxs-lookup"><span data-stu-id="f4998-108">Browse to C:\SWIFTAdapterTutorial\Interact\Response to view the handle response message, Sw:HandleResponse.</span></span>  
  
5.  <span data-ttu-id="f4998-109">Sw:HandleRequest メッセージをメモ帳などのテキスト エディターで開き、payload セクションが ExchangeReqSimple.xml ファイルのものと同じであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f4998-109">Open the Sw:HandleRequest message in a text editor, such as Notepad, and verify that the payload section is the same as in the file ExchangeReqSimple.xml.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4998-110">参照</span><span class="sxs-lookup"><span data-stu-id="f4998-110">See Also</span></span>  
 <span data-ttu-id="f4998-111">[手順 4: テスト、リアルタイムのエンド ツー エンド シナリオの対話](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-real-time-end-to-end-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="f4998-111">[Step 4: Test the InterAct Real-Time End-to-End Scenario](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-real-time-end-to-end-scenario.md) </span></span>  
 <span data-ttu-id="f4998-112">[手順 4 a: SWIFTNet サービスの開始](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service.md) </span><span class="sxs-lookup"><span data-stu-id="f4998-112">[Step 4A: Start the SWIFTNet Service](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service.md) </span></span>  
 <span data-ttu-id="f4998-113">[手順 4 b: 送信ポートの開始し、受信のポート、リアルタイムのシナリオの対話](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="f4998-113">[Step 4B: Start the Send Ports and Receive Ports for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-real-time-scenario.md) </span></span>  
 [<span data-ttu-id="f4998-114">手順 4 C: のテスト インスタンスを作成、リアルタイムのシナリオの対話</span><span class="sxs-lookup"><span data-stu-id="f4998-114">Step 4C: Create a Test Instance for the InterAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-interact-real-time-scenario.md)