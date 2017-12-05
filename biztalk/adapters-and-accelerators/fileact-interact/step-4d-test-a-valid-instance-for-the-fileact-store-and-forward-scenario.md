---
title: "手順 4 D: FileAct ストア アンド フォワードのシナリオの有効なインスタンスのテスト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7f47b1fd-a4ef-4b1d-812a-8c2fa946f98c
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b2074e5360e6dfee766546f27a560208f920688
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="step-4d-test-a-valid-instance-for-the-fileact-store-and-forward-scenario"></a>手順 4 D: FileAct ストア アンド フォワードのシナリオの有効なインスタンスのテスト
この手順を開始する前に行う必要があります[手順 4 C: FileAct ストア アンド フォワードのシナリオのテスト インスタンスを作成する](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-fileact-store-and-forward-scenario.md)です。  
  
### <a name="to-test-a-valid-instance"></a>有効なインスタンスをテストするには  
  
1.  C:\SWIFTAdapterTutorial\Fileact\FileRequestDropSnF に PutReqSimple.xml ファイルをドロップします。  
  
2.  しばらくすると、PutReqSimple.xml ファイルがフォルダーから消えますことを確認します。  
  
3.  C:\SWIFTAdapterTutorial\Fileact\ServerLocation に C:\SWIFTAdapterTurorial\Fileact\ClientLocation から Sample_Put.txt ファイルが転送されることと、C:\SWIFTAdapterTutorial\ResponseServer に応答が表示されることを確認します。  
  
4.  次の 3 つの HandleFileEventRequest メッセージの状態イベント (c:\SWIFTAdapterTutorial\Fileact\StatusEvents) フォルダーを確認してください。 これらのメッセージは、次の転送状態を含める必要があります。  
  
     HandleFileEventRequest メッセージ\<ソフトウェア TransferStatus\>Accepted\</Sw-TransferStatus\>  
  
     HandleFileEventRequest メッセージ\<ソフトウェア TransferStatus\>開始された\</Sw-TransferStatus\>  
  
     HandleFileEventRequest メッセージ\<ソフトウェア TransferStatus\>完了\</Sw-TransferStatus\>  
  
## <a name="see-also"></a>参照  
 [手順 4: FileAct ストア アンド フォワードのエンド ツー エンド シナリオをテストします。](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-store-and-forward-end-to-end-scenario.md)   
 [手順 4 a: FileAct ストア アンド フォワードのシナリオの SWIFTNet サービスの開始](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-store-and-forward-scenario.md)   
 [手順 4 b: 送信ポートの開始し、FileAct ストア アンド フォワードのシナリオの受信ポート](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-ports-and-receive-ports-for-fileact-store-and-forward.md)   
 [手順 4C: FileAct ストア アンド フォワード シナリオ用にテスト インスタンスを作成する](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-fileact-store-and-forward-scenario.md)