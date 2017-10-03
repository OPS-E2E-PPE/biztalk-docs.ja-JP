---
title: "手順 4 C: FileAct リアルタイム シナリオのテスト インスタンスを作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 80e0cb59-8b4f-4273-a7a4-db3446008061
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04952616f1b49eb30b4eb00462e4e5295ade0cfc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-4c-create-a-test-instance-for-the-fileact-real-time-scenario"></a><span data-ttu-id="cd40f-102">手順 4 C: FileAct リアルタイム シナリオのテスト インスタンスを作成</span><span class="sxs-lookup"><span data-stu-id="cd40f-102">Step 4C: Create a Test Instance for the FileAct Real-Time Scenario</span></span>
<span data-ttu-id="cd40f-103">この手順を開始する前に行う必要があります[手順 4B: FileAct リアルタイム シナリオでは、送信ポートおよび受信ポートを開始](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-the-fileact-real-time-scenario.md)です。</span><span class="sxs-lookup"><span data-stu-id="cd40f-103">Before you begin this step, you must complete [Step 4B: Start the Send Ports and Receive Ports for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-the-fileact-real-time-scenario.md).</span></span>  
  
### <a name="to-create-a-test-instance"></a><span data-ttu-id="cd40f-104">テスト インスタンスを作成するには</span><span class="sxs-lookup"><span data-stu-id="cd40f-104">To create a test instance</span></span>  
  
1.  <span data-ttu-id="cd40f-105">メモ帳などのテキスト エディターで、新しいファイルを開くし、以下を貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="cd40f-105">Open a new file in a text editor, such as Notepad, and paste the following:</span></span>  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <Sw-ExchangeFileRequest>  
    <Sw-FileRequest>  
    <Sw-FileOpRequest>  
    <Sw-PutFileRequest>  
    <Sw-PhysicalName>%PhysicalFolderName%\sample_put.txt</Sw-PhysicalName>  
    </Sw-PutFileRequest>  
    </Sw-FileOpRequest>  
    </Sw-FileRequest>  
    </Sw-ExchangeFileRequest>  
    ```  
  
2.  <span data-ttu-id="cd40f-106">"PutReqSimple.xml"という名前のファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="cd40f-106">Save the file with the name “PutReqSimple.xml”.</span></span>  
  
3.  <span data-ttu-id="cd40f-107">ファイル (Sample_put.txt) は、クライアントの場所のフォルダーに配置されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cd40f-107">Make sure that the file (Sample_put.txt) is placed in the Client Location folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd40f-108">参照</span><span class="sxs-lookup"><span data-stu-id="cd40f-108">See Also</span></span>  
 <span data-ttu-id="cd40f-109">[手順 4: FileAct エンド ツー エンドのリアルタイムのシナリオをテストします。](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-real-time-end-to-end-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="cd40f-109">[Step 4: Test FileAct Real-Time End-to-End Scenario](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-real-time-end-to-end-scenario.md) </span></span>  
 <span data-ttu-id="cd40f-110">[手順 4 a: FileAct リアルタイム シナリオの SWIFTNet サービスの開始](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="cd40f-110">[Step 4A: Start the SWIFTNet Service for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="cd40f-111">[手順 4 b: 送信ポートを開始および FileAct リアルタイム シナリオでは、受信ポート](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-the-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="cd40f-111">[Step 4B: Start the Send Ports and Receive Ports for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-the-fileact-real-time-scenario.md) </span></span>  
 [<span data-ttu-id="cd40f-112">手順 4 D: FileAct リアルタイム シナリオでは、有効なインスタンスをテストします。</span><span class="sxs-lookup"><span data-stu-id="cd40f-112">Step 4D: Test a Valid Instance for the FileAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-the-fileact-real-time-scenario.md)