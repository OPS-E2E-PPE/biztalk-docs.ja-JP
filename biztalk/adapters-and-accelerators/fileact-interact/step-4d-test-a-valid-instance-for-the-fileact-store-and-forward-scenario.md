---
title: "手順 4 D: FileAct ストア アンド フォワードのシナリオの有効なインスタンスのテスト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7f47b1fd-a4ef-4b1d-812a-8c2fa946f98c
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b2074e5360e6dfee766546f27a560208f920688
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="step-4d-test-a-valid-instance-for-the-fileact-store-and-forward-scenario"></a><span data-ttu-id="e657d-102">手順 4 D: FileAct ストア アンド フォワードのシナリオの有効なインスタンスのテスト</span><span class="sxs-lookup"><span data-stu-id="e657d-102">Step 4D: Test a Valid Instance for the FileAct Store and Forward Scenario</span></span>
<span data-ttu-id="e657d-103">この手順を開始する前に行う必要があります[手順 4 C: FileAct ストア アンド フォワードのシナリオのテスト インスタンスを作成する](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-fileact-store-and-forward-scenario.md)です。</span><span class="sxs-lookup"><span data-stu-id="e657d-103">Before you begin this step, you must complete [Step 4C: Create a Test Instance for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-fileact-store-and-forward-scenario.md).</span></span>  
  
### <a name="to-test-a-valid-instance"></a><span data-ttu-id="e657d-104">有効なインスタンスをテストするには</span><span class="sxs-lookup"><span data-stu-id="e657d-104">To test a valid instance</span></span>  
  
1.  <span data-ttu-id="e657d-105">C:\SWIFTAdapterTutorial\Fileact\FileRequestDropSnF に PutReqSimple.xml ファイルをドロップします。</span><span class="sxs-lookup"><span data-stu-id="e657d-105">Drop the file PutReqSimple.xml into C:\SWIFTAdapterTutorial\Fileact\FileRequestDropSnF.</span></span>  
  
2.  <span data-ttu-id="e657d-106">しばらくすると、PutReqSimple.xml ファイルがフォルダーから消えますことを確認します。</span><span class="sxs-lookup"><span data-stu-id="e657d-106">Verify that after a moment, the PutReqSimple.xml file disappears from the folder.</span></span>  
  
3.  <span data-ttu-id="e657d-107">C:\SWIFTAdapterTutorial\Fileact\ServerLocation に C:\SWIFTAdapterTurorial\Fileact\ClientLocation から Sample_Put.txt ファイルが転送されることと、C:\SWIFTAdapterTutorial\ResponseServer に応答が表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e657d-107">Verify that the Sample_Put.txt file is transferred from C:\SWIFTAdapterTurorial\Fileact\ClientLocation to C:\SWIFTAdapterTutorial\Fileact\ServerLocation, and that responses appear in C:\SWIFTAdapterTutorial\ResponseServer.</span></span>  
  
4.  <span data-ttu-id="e657d-108">次の 3 つの HandleFileEventRequest メッセージの状態イベント (c:\SWIFTAdapterTutorial\Fileact\StatusEvents) フォルダーを確認してください。</span><span class="sxs-lookup"><span data-stu-id="e657d-108">Check status event (c:\SWIFTAdapterTutorial\Fileact\StatusEvents) folder for three HandleFileEventRequest messages.</span></span> <span data-ttu-id="e657d-109">これらのメッセージは、次の転送状態を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="e657d-109">These messages should contain the following Transfer status:</span></span>  
  
     <span data-ttu-id="e657d-110">HandleFileEventRequest メッセージ\<ソフトウェア TransferStatus\>Accepted\</Sw-TransferStatus\></span><span class="sxs-lookup"><span data-stu-id="e657d-110">HandleFileEventRequest message\<Sw-TransferStatus\>Accepted\</Sw-TransferStatus\></span></span>  
  
     <span data-ttu-id="e657d-111">HandleFileEventRequest メッセージ\<ソフトウェア TransferStatus\>開始された\</Sw-TransferStatus\></span><span class="sxs-lookup"><span data-stu-id="e657d-111">HandleFileEventRequest message \<Sw-TransferStatus\>Initiated\</Sw-TransferStatus\></span></span>  
  
     <span data-ttu-id="e657d-112">HandleFileEventRequest メッセージ\<ソフトウェア TransferStatus\>完了\</Sw-TransferStatus\></span><span class="sxs-lookup"><span data-stu-id="e657d-112">HandleFileEventRequest message \<Sw-TransferStatus\>Completed\</Sw-TransferStatus\></span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e657d-113">参照</span><span class="sxs-lookup"><span data-stu-id="e657d-113">See Also</span></span>  
 <span data-ttu-id="e657d-114">[手順 4: FileAct ストア アンド フォワードのエンド ツー エンド シナリオをテストします。](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-store-and-forward-end-to-end-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="e657d-114">[Step 4: Test FileAct Store and Forward End-to-End Scenario](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-store-and-forward-end-to-end-scenario.md) </span></span>  
 <span data-ttu-id="e657d-115">[手順 4 a: FileAct ストア アンド フォワードのシナリオの SWIFTNet サービスの開始](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="e657d-115">[Step 4A: Start the SWIFTNet Service for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="e657d-116">[手順 4 b: 送信ポートの開始し、FileAct ストア アンド フォワードのシナリオの受信ポート](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-ports-and-receive-ports-for-fileact-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="e657d-116">[Step 4B: Start the Send Ports and Receive Ports for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-ports-and-receive-ports-for-fileact-store-and-forward.md) </span></span>  
 [<span data-ttu-id="e657d-117">手順 4C: FileAct ストア アンド フォワード シナリオ用にテスト インスタンスを作成する</span><span class="sxs-lookup"><span data-stu-id="e657d-117">Step 4C: Create a Test Instance for the FileAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-fileact-store-and-forward-scenario.md)