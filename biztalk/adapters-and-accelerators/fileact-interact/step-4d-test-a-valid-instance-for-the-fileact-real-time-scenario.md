---
title: '手順 4 D: FileAct リアルタイム シナリオでは、有効なインスタンスをテスト |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a8975c90-462b-4c9b-8766-1272ab7ceaba
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 906a7eb08dc7542d7fa383aeb9035c0a5536cff3
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25963776"
---
# <a name="step-4d-test-a-valid-instance-for-the-fileact-real-time-scenario"></a><span data-ttu-id="318f9-102">手順 4 D: FileAct リアルタイム シナリオでは、有効なインスタンスをテストします。</span><span class="sxs-lookup"><span data-stu-id="318f9-102">Step 4D: Test a Valid Instance for the FileAct Real-Time Scenario</span></span>
<span data-ttu-id="318f9-103">この手順を開始する前に行う必要があります[手順 4 C: FileAct リアルタイム シナリオのテスト インスタンスを作成](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-fileact-real-time-scenario.md)です。</span><span class="sxs-lookup"><span data-stu-id="318f9-103">Before you begin this step, you must complete [Step 4C: Create a Test Instance for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-fileact-real-time-scenario.md).</span></span>  
  
### <a name="to-test-a-valid-instance"></a><span data-ttu-id="318f9-104">有効なインスタンスをテストするには</span><span class="sxs-lookup"><span data-stu-id="318f9-104">To test a valid instance</span></span>  
  
1.  <span data-ttu-id="318f9-105">C:\SWIFTAdapterTutorial\Fileact\FileRequestDropRealTime に PutReqSimple.xml ファイルをドロップします。</span><span class="sxs-lookup"><span data-stu-id="318f9-105">Drop the file PutReqSimple.xml into C:\SWIFTAdapterTutorial\Fileact\FileRequestDropRealTime.</span></span>  
  
2.  <span data-ttu-id="318f9-106">しばらくすると、PutReqSimple.xml ファイルがフォルダーから消えますことを確認します。</span><span class="sxs-lookup"><span data-stu-id="318f9-106">Verify that after a moment, the PutReqSimple.xml file disappears from the folder.</span></span>  
  
3.  <span data-ttu-id="318f9-107">Sample_Put.txt ファイルが転送されたことを確認してください: C:\SWIFTAdapterTutorial\Fileact\ServerLocation に C:\SWIFTAdapterTutorial\Fileact\ClientLocation と C:\SWIFTAdapterTutorial\Fileact\ResponseClient と C:\ に応答が表示されています。SWIFTAdapterTutorial\Fileact\ResponseServer です。</span><span class="sxs-lookup"><span data-stu-id="318f9-107">Verify that the Sample_Put.txt file is transferred from: C:\SWIFTAdapterTutorial\Fileact\ClientLocation to C:\SWIFTAdapterTutorial\Fileact\ServerLocation, and that responses appear in C:\SWIFTAdapterTutorial\Fileact\ResponseClient and C:\SWIFTAdapterTutorial\Fileact\ResponseServer.</span></span>  
  
4.  <span data-ttu-id="318f9-108">次の 3 つの HandleFileEventRequest メッセージの状態イベント (c:\SWIFTAdapterTutorial\Fileact\StatusEvents) フォルダーを確認してください。</span><span class="sxs-lookup"><span data-stu-id="318f9-108">Check status event (c:\SWIFTAdapterTutorial\Fileact\StatusEvents) folder for three HandleFileEventRequest messages.</span></span> <span data-ttu-id="318f9-109">これらのメッセージは、次の転送状態を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="318f9-109">These messages should contain the following Transfer status:</span></span>  
  
     <span data-ttu-id="318f9-110">HandleFileEventRequest メッセージ\<ソフトウェア TransferStatus\>Accepted\</Sw-TransferStatus\></span><span class="sxs-lookup"><span data-stu-id="318f9-110">HandleFileEventRequest message\<Sw-TransferStatus\>Accepted\</Sw-TransferStatus\></span></span>  
  
     <span data-ttu-id="318f9-111">HandleFileEventRequest メッセージ\<ソフトウェア TransferStatus\>開始された\</Sw-TransferStatus\></span><span class="sxs-lookup"><span data-stu-id="318f9-111">HandleFileEventRequest message \<Sw-TransferStatus\>Initiated\</Sw-TransferStatus\></span></span>  
  
     <span data-ttu-id="318f9-112">HandleFileEventRequest メッセージ\<ソフトウェア TransferStatus\>完了\</Sw-TransferStatus\></span><span class="sxs-lookup"><span data-stu-id="318f9-112">HandleFileEventRequest message \<Sw-TransferStatus\>Completed\</Sw-TransferStatus\></span></span>  
  
## <a name="see-also"></a><span data-ttu-id="318f9-113">参照</span><span class="sxs-lookup"><span data-stu-id="318f9-113">See Also</span></span>  
 <span data-ttu-id="318f9-114">[手順 4: FileAct エンド ツー エンドのリアルタイムのシナリオをテストします。](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-real-time-end-to-end-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="318f9-114">[Step 4: Test FileAct Real-Time End-to-End Scenario](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-real-time-end-to-end-scenario.md) </span></span>  
 <span data-ttu-id="318f9-115">[手順 4 a: FileAct リアルタイム シナリオの SWIFTNet サービスの開始](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="318f9-115">[Step 4A: Start the SWIFTNet Service for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="318f9-116">[手順 4 b: 送信ポートを開始および FileAct リアルタイム シナリオでは、受信ポート](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-the-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="318f9-116">[Step 4B: Start the Send Ports and Receive Ports for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-the-fileact-real-time-scenario.md) </span></span>  
 [<span data-ttu-id="318f9-117">手順 4C: FileAct リアルタイム シナリオ用にテスト インスタンスを作成する</span><span class="sxs-lookup"><span data-stu-id="318f9-117">Step 4C: Create a Test Instance for the FileAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-fileact-real-time-scenario.md)