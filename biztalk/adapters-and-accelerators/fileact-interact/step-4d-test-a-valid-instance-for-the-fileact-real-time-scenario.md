---
title: 手順 4 D:FileAct リアルタイム シナリオ用の有効なインスタンスのテスト |Microsoft Docs
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
ms.openlocfilehash: 76721d1a7870c10eb1008e3bc4f5183985816ba0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364738"
---
# <a name="step-4d-test-a-valid-instance-for-the-fileact-real-time-scenario"></a><span data-ttu-id="5476d-102">手順 4 D:FileAct リアルタイム シナリオ用の有効なインスタンスをテストします。</span><span class="sxs-lookup"><span data-stu-id="5476d-102">Step 4D: Test a Valid Instance for the FileAct Real-Time Scenario</span></span>
<span data-ttu-id="5476d-103">この手順を開始する前に行う必要があります[手順 4 C:FileAct リアルタイム シナリオ用にテスト インスタンスを作成](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-fileact-real-time-scenario.md)です。</span><span class="sxs-lookup"><span data-stu-id="5476d-103">Before you begin this step, you must complete [Step 4C: Create a Test Instance for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-fileact-real-time-scenario.md).</span></span>  
  
### <a name="to-test-a-valid-instance"></a><span data-ttu-id="5476d-104">有効なインスタンスをテストするには</span><span class="sxs-lookup"><span data-stu-id="5476d-104">To test a valid instance</span></span>  
  
1.  <span data-ttu-id="5476d-105">Drop the file PutReqSimple.xml into C:\SWIFTAdapterTutorial\Fileact\FileRequestDropRealTime.</span><span class="sxs-lookup"><span data-stu-id="5476d-105">Drop the file PutReqSimple.xml into C:\SWIFTAdapterTutorial\Fileact\FileRequestDropRealTime.</span></span>  
  
2.  <span data-ttu-id="5476d-106">しばらくすると、PutReqSimple.xml ファイルがフォルダーから消えることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5476d-106">Verify that after a moment, the PutReqSimple.xml file disappears from the folder.</span></span>  
  
3.  <span data-ttu-id="5476d-107">Sample_Put.txt ファイルが転送されることを確認します。C:\SWIFTAdapterTutorial\Fileact\ResponseClient と C:\SWIFTAdapterTutorial\Fileact\ResponseServer C:\SWIFTAdapterTutorial\Fileact\ServerLocation に C:\SWIFTAdapterTutorial\Fileact\ClientLocation とその応答が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5476d-107">Verify that the Sample_Put.txt file is transferred from: C:\SWIFTAdapterTutorial\Fileact\ClientLocation to C:\SWIFTAdapterTutorial\Fileact\ServerLocation, and that responses appear in C:\SWIFTAdapterTutorial\Fileact\ResponseClient and C:\SWIFTAdapterTutorial\Fileact\ResponseServer.</span></span>  
  
4.  <span data-ttu-id="5476d-108">3 つの HandleFileEventRequest メッセージの状態イベント (c:\SWIFTAdapterTutorial\Fileact\StatusEvents) フォルダーを確認します。</span><span class="sxs-lookup"><span data-stu-id="5476d-108">Check status event (c:\SWIFTAdapterTutorial\Fileact\StatusEvents) folder for three HandleFileEventRequest messages.</span></span> <span data-ttu-id="5476d-109">これらのメッセージは、次の転送状態を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="5476d-109">These messages should contain the following Transfer status:</span></span>  
  
     <span data-ttu-id="5476d-110">HandleFileEventRequest メッセージ\<Sw TransferStatus\>Accepted\</Sw-TransferStatus\></span><span class="sxs-lookup"><span data-stu-id="5476d-110">HandleFileEventRequest message\<Sw-TransferStatus\>Accepted\</Sw-TransferStatus\></span></span>  
  
     <span data-ttu-id="5476d-111">HandleFileEventRequest メッセージ\<Sw TransferStatus\>Initiated\</Sw-TransferStatus\></span><span class="sxs-lookup"><span data-stu-id="5476d-111">HandleFileEventRequest message \<Sw-TransferStatus\>Initiated\</Sw-TransferStatus\></span></span>  
  
     <span data-ttu-id="5476d-112">HandleFileEventRequest メッセージ\<Sw TransferStatus\>完了\</Sw-TransferStatus\></span><span class="sxs-lookup"><span data-stu-id="5476d-112">HandleFileEventRequest message \<Sw-TransferStatus\>Completed\</Sw-TransferStatus\></span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5476d-113">参照</span><span class="sxs-lookup"><span data-stu-id="5476d-113">See Also</span></span>  
 <span data-ttu-id="5476d-114">[手順 4:FileAct リアルタイム エンド ツー エンド シナリオをテストします。](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-real-time-end-to-end-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="5476d-114">[Step 4: Test FileAct Real-Time End-to-End Scenario](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-real-time-end-to-end-scenario.md) </span></span>  
 <span data-ttu-id="5476d-115">[手順 4 a:FileAct リアルタイム シナリオ用に SWIFTNet サービスを開始します。](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="5476d-115">[Step 4A: Start the SWIFTNet Service for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="5476d-116">[手順 4 b:送信ポートを開始および FileAct リアルタイム シナリオ用の受信ポート](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-the-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="5476d-116">[Step 4B: Start the Send Ports and Receive Ports for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-the-fileact-real-time-scenario.md) </span></span>  
 [<span data-ttu-id="5476d-117">手順 4 C:FileAct リアルタイム シナリオ用のテスト インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="5476d-117">Step 4C: Create a Test Instance for the FileAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-fileact-real-time-scenario.md)