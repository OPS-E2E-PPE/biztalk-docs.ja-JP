---
title: 手順 4 C:FileAct ストア アンド フォワード (プル) シナリオのテスト インスタンスを作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 50fc72f0-ec00-46f9-b24b-fe8d5e5079ee
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c8bcd3d65e219a6720aaae0400185f59a851679
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364903"
---
# <a name="step-4c-create-a-test-instance-for-the-fileact-store-and-forward-pull-scenario"></a><span data-ttu-id="a51da-102">手順 4 C:FileAct ストア アンド フォワード (プル) シナリオのテスト インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="a51da-102">Step 4C: Create a Test Instance for the FileAct Store and Forward (Pull) Scenario</span></span>
<span data-ttu-id="a51da-103">この手順を開始する前に行う必要があります[手順 4 b:送信ポートと FileAct ストア アンド フォワード (プル) シナリオ用のポートを受信開始](../../adapters-and-accelerators/fileact-interact/step-4b-start-send-and-receive-ports-for-fileact-store-and-forward-scenario.md)します。</span><span class="sxs-lookup"><span data-stu-id="a51da-103">Before you begin this step, you must complete [Step 4B: Start the Send Ports and Receive Ports for the FileAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-send-and-receive-ports-for-fileact-store-and-forward-scenario.md).</span></span>  
  
### <a name="to-create-a-test-instance"></a><span data-ttu-id="a51da-104">テスト インスタンスを作成するには</span><span class="sxs-lookup"><span data-stu-id="a51da-104">To create a test instance</span></span>  
  
1.  <span data-ttu-id="a51da-105">新しいファイルをメモ帳などのテキスト エディターで開き、次を貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="a51da-105">Open a new file in a text editor, such as Notepad, and paste the following:</span></span>  
  
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
    >  <span data-ttu-id="a51da-106">置き換える必要があります *%physicalfoldername* FILEACT で構成する実際のフォルダーの名前を持つ受信場所。</span><span class="sxs-lookup"><span data-stu-id="a51da-106">You must replace *%PhysicalFolderName%* with the actual folder name which you configured in the FILEACT receive location.</span></span>  
  
2.  <span data-ttu-id="a51da-107">ExchangeReqSimple.xml という名前のファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="a51da-107">Save the File with the name ExchangeReqSimple.xml.</span></span>  
  
3.  <span data-ttu-id="a51da-108">新しいファイルをメモ帳などのテキスト エディターで開き、次を貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="a51da-108">Open a new file in a text editor, such as Notepad, and paste the following:</span></span>  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>  
    <Sw-ExchangeSnFRequest>  
    <Sw-SnFRequest>  
    <Sw-SnFOpRequest>  
    <Sw-AcquireSnFRequest>  
    <SwInt-Queue Type the queue name, based on your provisioning with SWIFT </SwInt-Queue>  
    <Sw-SessionMode>Pull</Sw-SessionMode>  
    <Sw-ForceAcquire>TRUE</Sw-ForceAcquire>  
    <Sw-OrderBy>InterAct</Sw-OrderBy>  
    <Sw-RecoveryMode>TRUE</Sw-RecoveryMode>  
    </Sw-AcquireSnFRequest>  
    </Sw-SnFOpRequest>  
    </Sw-SnFRequest>  
    </Sw-ExchangeSnFRequest>  
  
    ```  
  
4.  <span data-ttu-id="a51da-109">名前 acquirequeue.xml でファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="a51da-109">Save the File with the name acquirequeue.xml.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a51da-110">参照</span><span class="sxs-lookup"><span data-stu-id="a51da-110">See Also</span></span>  
 <span data-ttu-id="a51da-111">[手順 4 a:FileAct ストア アンド フォワード (プル) シナリオ用に SWIFTNet サービスを開始します。](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-fileact-store-and-forward-pull-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="a51da-111">[Step 4A: Start the SWIFTNet Service for the FileAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-fileact-store-and-forward-pull-scenario.md) </span></span>  
 <span data-ttu-id="a51da-112">[手順 4 b:送信ポートと FileAct ストア アンド フォワード (プル) シナリオ用のポートを受信開始](../../adapters-and-accelerators/fileact-interact/step-4b-start-send-and-receive-ports-for-fileact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="a51da-112">[Step 4B: Start the Send Ports and Receive Ports for the FileAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-send-and-receive-ports-for-fileact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="a51da-113">手順 4 D:FileAct ストア アンド フォワード (プル) シナリオ用の有効なインスタンスをテストします。</span><span class="sxs-lookup"><span data-stu-id="a51da-113">Step 4D: Test a Valid Instance for the FileAct Store and Forward (Pull) Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-fileact-store-and-forward-pull-scenario.md)