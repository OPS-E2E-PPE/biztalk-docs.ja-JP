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
# <a name="step-4c-create-a-test-instance-for-the-fileact-store-and-forward-scenario"></a>手順 4 C:FileAct ストア アンド フォワード シナリオ用のテスト インスタンスを作成します。
この手順を開始する前に行う必要があります[手順 4 b:送信ポートと FileAct ストア アンド フォワード シナリオ用のポートを受信開始](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-ports-and-receive-ports-for-fileact-store-and-forward.md)します。  
  
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
    >  FILEACT で構成されている実際のフォルダー名は、%physicalfoldername を置き換える必要がありますの受信場所。  
  
2.  "PutReqSimple.xml"という名前のファイルを保存します。  
  
3.  ファイル (Sample_put.txt) が、クライアントの場所のフォルダー内に配置されることを確認します。  
  
## <a name="see-also"></a>参照  
 [手順 4:テスト FileAct ストア アンド フォワード エンド ツー エンドのシナリオ](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-store-and-forward-end-to-end-scenario.md)   
 [手順 4 a:FileAct ストア アンド フォワード シナリオ用に SWIFTNet サービスを開始します。](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-store-and-forward-scenario.md)   
 [手順 4 b:送信ポートの開始し、受信 FileAct ストア アンド フォワード シナリオ用のポート](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-ports-and-receive-ports-for-fileact-store-and-forward.md)   
 [手順 4 D:FileAct ストア アンド フォワード シナリオ用に有効なインスタンスをテストします。](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-the-fileact-store-and-forward-scenario.md)