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
# <a name="step-4c-create-a-test-instance-for-the-fileact-store-and-forward-pull-scenario"></a>手順 4 C:FileAct ストア アンド フォワード (プル) シナリオのテスト インスタンスを作成します。
この手順を開始する前に行う必要があります[手順 4 b:送信ポートと FileAct ストア アンド フォワード (プル) シナリオ用のポートを受信開始](../../adapters-and-accelerators/fileact-interact/step-4b-start-send-and-receive-ports-for-fileact-store-and-forward-scenario.md)します。  
  
### <a name="to-create-a-test-instance"></a>テスト インスタンスを作成するには  
  
1.  新しいファイルをメモ帳などのテキスト エディターで開き、次を貼り付けます。  
  
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
    >  置き換える必要があります *%physicalfoldername* FILEACT で構成する実際のフォルダーの名前を持つ受信場所。  
  
2.  ExchangeReqSimple.xml という名前のファイルを保存します。  
  
3.  新しいファイルをメモ帳などのテキスト エディターで開き、次を貼り付けます。  
  
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
  
4.  名前 acquirequeue.xml でファイルを保存します。  
  
## <a name="see-also"></a>参照  
 [手順 4 a:FileAct ストア アンド フォワード (プル) シナリオ用に SWIFTNet サービスを開始します。](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-fileact-store-and-forward-pull-scenario.md)   
 [手順 4 b:送信ポートと FileAct ストア アンド フォワード (プル) シナリオ用のポートを受信開始](../../adapters-and-accelerators/fileact-interact/step-4b-start-send-and-receive-ports-for-fileact-store-and-forward-scenario.md)   
 [手順 4 D:FileAct ストア アンド フォワード (プル) シナリオ用の有効なインスタンスをテストします。](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-fileact-store-and-forward-pull-scenario.md)