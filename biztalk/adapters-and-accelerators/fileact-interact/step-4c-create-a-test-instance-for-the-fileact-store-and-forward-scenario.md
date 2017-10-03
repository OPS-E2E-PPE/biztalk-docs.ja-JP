---
title: "手順 4 C: FileAct ストア アンド フォワードのシナリオのテスト インスタンスを作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 477abefa-63d0-4cf2-9e4f-67467195efa8
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0149d93501473e039dca7f4f8c4dbe50e904098
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-4c-create-a-test-instance-for-the-fileact-store-and-forward-scenario"></a><span data-ttu-id="61c33-102">手順 4 C: FileAct ストア アンド フォワードのシナリオのテスト インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="61c33-102">Step 4C: Create a Test Instance for the FileAct Store and Forward Scenario</span></span>
<span data-ttu-id="61c33-103">この手順を開始する前に行う必要があります[手順 4B: FileAct ストア アンド フォワードのシナリオの受信ポートと送信ポートを開始](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-ports-and-receive-ports-for-fileact-store-and-forward.md)です。</span><span class="sxs-lookup"><span data-stu-id="61c33-103">Before you begin this step, you must complete [Step 4B: Start the Send Ports and Receive Ports for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-ports-and-receive-ports-for-fileact-store-and-forward.md).</span></span>  
  
### <a name="to-create-a-test-instance"></a><span data-ttu-id="61c33-104">テスト インスタンスを作成するには</span><span class="sxs-lookup"><span data-stu-id="61c33-104">To create a test instance</span></span>  
  
1.  <span data-ttu-id="61c33-105">メモ帳などのテキスト エディターで、新しいファイルを開くし、以下を貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="61c33-105">Open a new file in a text editor, such as Notepad, and paste the following:</span></span>  
  
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
  
    > [!NOTE]
    >  <span data-ttu-id="61c33-106">PhysicalFolderName % を FILEACT で構成されている実際のフォルダー名に置き換える必要がありますの受信場所。</span><span class="sxs-lookup"><span data-stu-id="61c33-106">You must replace %PhysicalFolderName% with the actual folder name you configured in the FILEACT receive location.</span></span>  
  
2.  <span data-ttu-id="61c33-107">"PutReqSimple.xml"という名前のファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="61c33-107">Save the file with the name “PutReqSimple.xml”.</span></span>  
  
3.  <span data-ttu-id="61c33-108">ファイル (Sample_put.txt) は、クライアントの場所のフォルダーに配置されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="61c33-108">Make sure that the file (Sample_put.txt) is placed in the Client Location folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61c33-109">参照</span><span class="sxs-lookup"><span data-stu-id="61c33-109">See Also</span></span>  
 <span data-ttu-id="61c33-110">[手順 4: FileAct ストア アンド フォワードのエンド ツー エンド シナリオをテストします。](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-store-and-forward-end-to-end-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="61c33-110">[Step 4: Test FileAct Store and Forward End-to-End Scenario](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-store-and-forward-end-to-end-scenario.md) </span></span>  
 <span data-ttu-id="61c33-111">[手順 4 a: FileAct ストア アンド フォワードのシナリオの SWIFTNet サービスの開始](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="61c33-111">[Step 4A: Start the SWIFTNet Service for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="61c33-112">[手順 4 b: 送信ポートの開始し、FileAct ストア アンド フォワードのシナリオの受信ポート](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-ports-and-receive-ports-for-fileact-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="61c33-112">[Step 4B: Start the Send Ports and Receive Ports for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-ports-and-receive-ports-for-fileact-store-and-forward.md) </span></span>  
 [<span data-ttu-id="61c33-113">手順 4 D: FileAct ストア アンド フォワードのシナリオの有効なインスタンスのテスト</span><span class="sxs-lookup"><span data-stu-id="61c33-113">Step 4D: Test a Valid Instance for the FileAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-the-fileact-store-and-forward-scenario.md)