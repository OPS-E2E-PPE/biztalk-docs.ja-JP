---
title: 手順 4 D:FileAct ストア アンド フォワード シナリオ用に有効なインスタンスのテスト |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7f47b1fd-a4ef-4b1d-812a-8c2fa946f98c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aad1781cd33b5fad50a53df08868177d1d01bd07
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364673"
---
# <a name="step-4d-test-a-valid-instance-for-the-fileact-store-and-forward-scenario"></a><span data-ttu-id="cc7a6-102">手順 4 D:FileAct ストア アンド フォワード シナリオ用に有効なインスタンスをテストします。</span><span class="sxs-lookup"><span data-stu-id="cc7a6-102">Step 4D: Test a Valid Instance for the FileAct Store and Forward Scenario</span></span>
<span data-ttu-id="cc7a6-103">この手順を開始する前に行う必要があります[手順 4 C:FileAct ストア アンド フォワード シナリオ用のテスト インスタンスを作成](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-fileact-store-and-forward-scenario.md)です。</span><span class="sxs-lookup"><span data-stu-id="cc7a6-103">Before you begin this step, you must complete [Step 4C: Create a Test Instance for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-fileact-store-and-forward-scenario.md).</span></span>  
  
### <a name="to-test-a-valid-instance"></a><span data-ttu-id="cc7a6-104">有効なインスタンスをテストするには</span><span class="sxs-lookup"><span data-stu-id="cc7a6-104">To test a valid instance</span></span>  
  
1.  <span data-ttu-id="cc7a6-105">C:\SWIFTAdapterTutorial\Fileact\FileRequestDropSnF に PutReqSimple.xml ファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="cc7a6-105">Drop the file PutReqSimple.xml into C:\SWIFTAdapterTutorial\Fileact\FileRequestDropSnF.</span></span>  
  
2.  <span data-ttu-id="cc7a6-106">しばらくすると、PutReqSimple.xml ファイルがフォルダーから消えることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cc7a6-106">Verify that after a moment, the PutReqSimple.xml file disappears from the folder.</span></span>  
  
3.  <span data-ttu-id="cc7a6-107">Sample_Put.txt ファイルが、C:\SWIFTAdapterTutorial\Fileact\ServerLocation に C:\SWIFTAdapterTurorial\Fileact\ClientLocation から転送される C:\SWIFTAdapterTutorial\ResponseServer に応答が表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cc7a6-107">Verify that the Sample_Put.txt file is transferred from C:\SWIFTAdapterTurorial\Fileact\ClientLocation to C:\SWIFTAdapterTutorial\Fileact\ServerLocation, and that responses appear in C:\SWIFTAdapterTutorial\ResponseServer.</span></span>  
  
4.  <span data-ttu-id="cc7a6-108">3 つの HandleFileEventRequest メッセージの状態イベント (c:\SWIFTAdapterTutorial\Fileact\StatusEvents) フォルダーを確認します。</span><span class="sxs-lookup"><span data-stu-id="cc7a6-108">Check status event (c:\SWIFTAdapterTutorial\Fileact\StatusEvents) folder for three HandleFileEventRequest messages.</span></span> <span data-ttu-id="cc7a6-109">これらのメッセージは、次の転送状態を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc7a6-109">These messages should contain the following Transfer status:</span></span>  
  
     <span data-ttu-id="cc7a6-110">HandleFileEventRequest メッセージ\<Sw TransferStatus\>Accepted\</Sw-TransferStatus\></span><span class="sxs-lookup"><span data-stu-id="cc7a6-110">HandleFileEventRequest message\<Sw-TransferStatus\>Accepted\</Sw-TransferStatus\></span></span>  
  
     <span data-ttu-id="cc7a6-111">HandleFileEventRequest メッセージ\<Sw TransferStatus\>Initiated\</Sw-TransferStatus\></span><span class="sxs-lookup"><span data-stu-id="cc7a6-111">HandleFileEventRequest message \<Sw-TransferStatus\>Initiated\</Sw-TransferStatus\></span></span>  
  
     <span data-ttu-id="cc7a6-112">HandleFileEventRequest メッセージ\<Sw TransferStatus\>完了\</Sw-TransferStatus\></span><span class="sxs-lookup"><span data-stu-id="cc7a6-112">HandleFileEventRequest message \<Sw-TransferStatus\>Completed\</Sw-TransferStatus\></span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc7a6-113">参照</span><span class="sxs-lookup"><span data-stu-id="cc7a6-113">See Also</span></span>  
 <span data-ttu-id="cc7a6-114">[手順 4:テスト FileAct ストア アンド フォワード エンド ツー エンドのシナリオ](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-store-and-forward-end-to-end-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="cc7a6-114">[Step 4: Test FileAct Store and Forward End-to-End Scenario](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-store-and-forward-end-to-end-scenario.md) </span></span>  
 <span data-ttu-id="cc7a6-115">[手順 4 a:FileAct ストア アンド フォワード シナリオ用に SWIFTNet サービスを開始します。](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="cc7a6-115">[Step 4A: Start the SWIFTNet Service for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="cc7a6-116">[手順 4 b:送信ポートの開始し、受信 FileAct ストア アンド フォワード シナリオ用のポート](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-ports-and-receive-ports-for-fileact-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="cc7a6-116">[Step 4B: Start the Send Ports and Receive Ports for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-ports-and-receive-ports-for-fileact-store-and-forward.md) </span></span>  
 [<span data-ttu-id="cc7a6-117">手順 4 C:FileAct ストア アンド フォワード シナリオ用のテスト インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="cc7a6-117">Step 4C: Create a Test Instance for the FileAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-fileact-store-and-forward-scenario.md)