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
# <a name="step-4d-test-a-valid-instance-for-the-fileact-store-and-forward-scenario"></a>手順 4 D:FileAct ストア アンド フォワード シナリオ用に有効なインスタンスをテストします。
この手順を開始する前に行う必要があります[手順 4 C:FileAct ストア アンド フォワード シナリオ用のテスト インスタンスを作成](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-fileact-store-and-forward-scenario.md)です。  
  
### <a name="to-test-a-valid-instance"></a>有効なインスタンスをテストするには  
  
1.  C:\SWIFTAdapterTutorial\Fileact\FileRequestDropSnF に PutReqSimple.xml ファイルを削除します。  
  
2.  しばらくすると、PutReqSimple.xml ファイルがフォルダーから消えることを確認します。  
  
3.  Sample_Put.txt ファイルが、C:\SWIFTAdapterTutorial\Fileact\ServerLocation に C:\SWIFTAdapterTurorial\Fileact\ClientLocation から転送される C:\SWIFTAdapterTutorial\ResponseServer に応答が表示されることを確認します。  
  
4.  3 つの HandleFileEventRequest メッセージの状態イベント (c:\SWIFTAdapterTutorial\Fileact\StatusEvents) フォルダーを確認します。 これらのメッセージは、次の転送状態を含める必要があります。  
  
     HandleFileEventRequest メッセージ\<Sw TransferStatus\>Accepted\</Sw-TransferStatus\>  
  
     HandleFileEventRequest メッセージ\<Sw TransferStatus\>Initiated\</Sw-TransferStatus\>  
  
     HandleFileEventRequest メッセージ\<Sw TransferStatus\>完了\</Sw-TransferStatus\>  
  
## <a name="see-also"></a>参照  
 [手順 4:テスト FileAct ストア アンド フォワード エンド ツー エンドのシナリオ](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-store-and-forward-end-to-end-scenario.md)   
 [手順 4 a:FileAct ストア アンド フォワード シナリオ用に SWIFTNet サービスを開始します。](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-store-and-forward-scenario.md)   
 [手順 4 b:送信ポートの開始し、受信 FileAct ストア アンド フォワード シナリオ用のポート](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-ports-and-receive-ports-for-fileact-store-and-forward.md)   
 [手順 4 C:FileAct ストア アンド フォワード シナリオ用のテスト インスタンスを作成します。](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-fileact-store-and-forward-scenario.md)