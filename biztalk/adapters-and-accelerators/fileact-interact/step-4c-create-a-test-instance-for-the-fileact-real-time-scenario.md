---
title: 手順 4 C:FileAct リアルタイム シナリオ用のテスト インスタンスの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 80e0cb59-8b4f-4273-a7a4-db3446008061
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dbdc7c46b23206876e59fe7ac74fdf241787abfe
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364810"
---
# <a name="step-4c-create-a-test-instance-for-the-fileact-real-time-scenario"></a><span data-ttu-id="b5f25-102">手順 4 C:FileAct リアルタイム シナリオ用のテスト インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="b5f25-102">Step 4C: Create a Test Instance for the FileAct Real-Time Scenario</span></span>
<span data-ttu-id="b5f25-103">この手順を開始する前に行う必要があります[手順 4 b:送信ポートを開始および FileAct リアルタイム シナリオ用の受信ポート](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-the-fileact-real-time-scenario.md)します。</span><span class="sxs-lookup"><span data-stu-id="b5f25-103">Before you begin this step, you must complete [Step 4B: Start the Send Ports and Receive Ports for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-the-fileact-real-time-scenario.md).</span></span>  
  
### <a name="to-create-a-test-instance"></a><span data-ttu-id="b5f25-104">テスト インスタンスを作成するには</span><span class="sxs-lookup"><span data-stu-id="b5f25-104">To create a test instance</span></span>  
  
1.  <span data-ttu-id="b5f25-105">新しいファイルをメモ帳などのテキスト エディターで開き、次を貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="b5f25-105">Open a new file in a text editor, such as Notepad, and paste the following:</span></span>  
  
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
  
2.  <span data-ttu-id="b5f25-106">"PutReqSimple.xml"という名前のファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="b5f25-106">Save the file with the name “PutReqSimple.xml”.</span></span>  
  
3.  <span data-ttu-id="b5f25-107">ファイル (Sample_put.txt) が、クライアントの場所のフォルダー内に配置されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b5f25-107">Make sure that the file (Sample_put.txt) is placed in the Client Location folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5f25-108">参照</span><span class="sxs-lookup"><span data-stu-id="b5f25-108">See Also</span></span>  
 <span data-ttu-id="b5f25-109">[手順 4:FileAct リアルタイム エンド ツー エンド シナリオをテストします。](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-real-time-end-to-end-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="b5f25-109">[Step 4: Test FileAct Real-Time End-to-End Scenario](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-real-time-end-to-end-scenario.md) </span></span>  
 <span data-ttu-id="b5f25-110">[手順 4 a:FileAct リアルタイム シナリオ用に SWIFTNet サービスを開始します。](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="b5f25-110">[Step 4A: Start the SWIFTNet Service for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="b5f25-111">[手順 4 b:送信ポートを開始および FileAct リアルタイム シナリオ用の受信ポート](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-the-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="b5f25-111">[Step 4B: Start the Send Ports and Receive Ports for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-the-fileact-real-time-scenario.md) </span></span>  
 [<span data-ttu-id="b5f25-112">手順 4 D:FileAct リアルタイム シナリオ用の有効なインスタンスをテストします。</span><span class="sxs-lookup"><span data-stu-id="b5f25-112">Step 4D: Test a Valid Instance for the FileAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-the-fileact-real-time-scenario.md)