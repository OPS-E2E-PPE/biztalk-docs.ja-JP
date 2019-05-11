---
title: 手順 4 C:FileAct ストア アンド フォワード シナリオ用のテスト インスタンスを作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 477abefa-63d0-4cf2-9e4f-67467195efa8
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8bf28aaae49d670933db8315ed3dd333a28462d0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364785"
---
# <a name="step-4c-create-a-test-instance-for-the-fileact-store-and-forward-scenario"></a><span data-ttu-id="59959-102">手順 4 C:FileAct ストア アンド フォワード シナリオ用のテスト インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="59959-102">Step 4C: Create a Test Instance for the FileAct Store and Forward Scenario</span></span>
<span data-ttu-id="59959-103">この手順を開始する前に行う必要があります[手順 4 b:送信ポートと FileAct ストア アンド フォワード シナリオ用のポートを受信開始](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-ports-and-receive-ports-for-fileact-store-and-forward.md)します。</span><span class="sxs-lookup"><span data-stu-id="59959-103">Before you begin this step, you must complete [Step 4B: Start the Send Ports and Receive Ports for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-ports-and-receive-ports-for-fileact-store-and-forward.md).</span></span>  
  
### <a name="to-create-a-test-instance"></a><span data-ttu-id="59959-104">テスト インスタンスを作成するには</span><span class="sxs-lookup"><span data-stu-id="59959-104">To create a test instance</span></span>  
  
1.  <span data-ttu-id="59959-105">新しいファイルをメモ帳などのテキスト エディターで開き、次を貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="59959-105">Open a new file in a text editor, such as Notepad, and paste the following:</span></span>  
  
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
    >  <span data-ttu-id="59959-106">FILEACT で構成されている実際のフォルダー名は、%physicalfoldername を置き換える必要がありますの受信場所。</span><span class="sxs-lookup"><span data-stu-id="59959-106">You must replace %PhysicalFolderName% with the actual folder name you configured in the FILEACT receive location.</span></span>  
  
2.  <span data-ttu-id="59959-107">"PutReqSimple.xml"という名前のファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="59959-107">Save the file with the name “PutReqSimple.xml”.</span></span>  
  
3.  <span data-ttu-id="59959-108">ファイル (Sample_put.txt) が、クライアントの場所のフォルダー内に配置されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="59959-108">Make sure that the file (Sample_put.txt) is placed in the Client Location folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59959-109">参照</span><span class="sxs-lookup"><span data-stu-id="59959-109">See Also</span></span>  
 <span data-ttu-id="59959-110">[手順 4:テスト FileAct ストア アンド フォワード エンド ツー エンドのシナリオ](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-store-and-forward-end-to-end-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="59959-110">[Step 4: Test FileAct Store and Forward End-to-End Scenario](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-store-and-forward-end-to-end-scenario.md) </span></span>  
 <span data-ttu-id="59959-111">[手順 4 a:FileAct ストア アンド フォワード シナリオ用に SWIFTNet サービスを開始します。](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="59959-111">[Step 4A: Start the SWIFTNet Service for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="59959-112">[手順 4 b:送信ポートの開始し、受信 FileAct ストア アンド フォワード シナリオ用のポート](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-ports-and-receive-ports-for-fileact-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="59959-112">[Step 4B: Start the Send Ports and Receive Ports for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-ports-and-receive-ports-for-fileact-store-and-forward.md) </span></span>  
 [<span data-ttu-id="59959-113">手順 4 D:FileAct ストア アンド フォワード シナリオ用に有効なインスタンスをテストします。</span><span class="sxs-lookup"><span data-stu-id="59959-113">Step 4D: Test a Valid Instance for the FileAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-the-fileact-store-and-forward-scenario.md)