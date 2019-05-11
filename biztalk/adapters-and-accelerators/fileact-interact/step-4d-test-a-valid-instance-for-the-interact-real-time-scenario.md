---
title: 手順 4 D:テストの有効なインスタンス、InterAct リアルタイム シナリオ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e163c3ac-a00d-40cf-b1b8-4a38f74ab0e8
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 190ba5003d24803bd8b8b3c304e671eb6ab4303c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364653"
---
# <a name="step-4d-test-a-valid-instance-for-the-interact-real-time-scenario"></a><span data-ttu-id="7ab7b-102">手順 4 D:テストの有効なインスタンス、InterAct リアルタイム シナリオ</span><span class="sxs-lookup"><span data-stu-id="7ab7b-102">Step 4D: Test a Valid Instance for the InterAct Real-Time Scenario</span></span>
<span data-ttu-id="7ab7b-103">この手順を開始する前に行う必要があります[手順 4 C:テスト インスタンスを作成、InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-interact-real-time-scenario.md)します。</span><span class="sxs-lookup"><span data-stu-id="7ab7b-103">Before you begin this step, you must complete [Step 4C: Create a Test Instance for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-interact-real-time-scenario.md).</span></span>  
  
### <a name="to-test-a-valid-instance"></a><span data-ttu-id="7ab7b-104">有効なインスタンスをテストするには</span><span class="sxs-lookup"><span data-stu-id="7ab7b-104">To test a valid instance</span></span>  
  
1.  <span data-ttu-id="7ab7b-105">Drop the file ExchangeReqSimple.xml into C:\SWIFTAdapterTutorial\Interact\InputRequest_RealTime.</span><span class="sxs-lookup"><span data-stu-id="7ab7b-105">Drop the file ExchangeReqSimple.xml into C:\SWIFTAdapterTutorial\Interact\InputRequest_RealTime.</span></span>  
  
2.  <span data-ttu-id="7ab7b-106">しばらくすると、ExchangeReqSimple.xml ファイルがフォルダーから消えることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7ab7b-106">Verify that after a moment, the ExchangeReqSimple.xml file disappears from the folder.</span></span>  
  
3.  <span data-ttu-id="7ab7b-107">C:\SWIFTAdapterTutorial\Interact\HandleRequest Sw:HandleRequest、ハンドルの要求メッセージを表示するを参照します。</span><span class="sxs-lookup"><span data-stu-id="7ab7b-107">Browse to C:\SWIFTAdapterTutorial\Interact\HandleRequest to view the handle request message, Sw:HandleRequest.</span></span>  
  
4.  <span data-ttu-id="7ab7b-108">C:\SWIFTAdapterTutorial\Interact\Response Sw:HandleResponse、ハンドルの応答メッセージを表示するを参照します。</span><span class="sxs-lookup"><span data-stu-id="7ab7b-108">Browse to C:\SWIFTAdapterTutorial\Interact\Response to view the handle response message, Sw:HandleResponse.</span></span>  
  
5.  <span data-ttu-id="7ab7b-109">メモ帳などのテキスト エディターで Sw:HandleRequest メッセージを開き、payload セクションが ExchangeReqSimple.xml ファイルと同じであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7ab7b-109">Open the Sw:HandleRequest message in a text editor, such as Notepad, and verify that the payload section is the same as in the file ExchangeReqSimple.xml.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ab7b-110">参照</span><span class="sxs-lookup"><span data-stu-id="7ab7b-110">See Also</span></span>  
 <span data-ttu-id="7ab7b-111">[手順 4:テスト、InterAct リアルタイム エンド ツー エンドのシナリオ](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-real-time-end-to-end-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="7ab7b-111">[Step 4: Test the InterAct Real-Time End-to-End Scenario](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-real-time-end-to-end-scenario.md) </span></span>  
 <span data-ttu-id="7ab7b-112">[手順 4 a:SWIFTNet サービスを開始します。](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service.md) </span><span class="sxs-lookup"><span data-stu-id="7ab7b-112">[Step 4A: Start the SWIFTNet Service](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service.md) </span></span>  
 <span data-ttu-id="7ab7b-113">[手順 4 b:送信ポートの開始し、受信ポートを InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="7ab7b-113">[Step 4B: Start the Send Ports and Receive Ports for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-real-time-scenario.md) </span></span>  
 [<span data-ttu-id="7ab7b-114">手順 4 C:テスト インスタンスを作成、InterAct リアルタイム シナリオ</span><span class="sxs-lookup"><span data-stu-id="7ab7b-114">Step 4C: Create a Test Instance for the InterAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-interact-real-time-scenario.md)