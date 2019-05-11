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
# <a name="step-4c-create-a-test-instance-for-the-fileact-real-time-scenario"></a>手順 4 C:FileAct リアルタイム シナリオ用のテスト インスタンスを作成します。
この手順を開始する前に行う必要があります[手順 4 b:送信ポートを開始および FileAct リアルタイム シナリオ用の受信ポート](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-the-fileact-real-time-scenario.md)します。  
  
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
  
2.  "PutReqSimple.xml"という名前のファイルを保存します。  
  
3.  ファイル (Sample_put.txt) が、クライアントの場所のフォルダー内に配置されることを確認します。  
  
## <a name="see-also"></a>参照  
 [手順 4:FileAct リアルタイム エンド ツー エンド シナリオをテストします。](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-real-time-end-to-end-scenario.md)   
 [手順 4 a:FileAct リアルタイム シナリオ用に SWIFTNet サービスを開始します。](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-real-time-scenario.md)   
 [手順 4 b:送信ポートを開始および FileAct リアルタイム シナリオ用の受信ポート](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-the-fileact-real-time-scenario.md)   
 [手順 4 D:FileAct リアルタイム シナリオ用の有効なインスタンスをテストします。](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-the-fileact-real-time-scenario.md)