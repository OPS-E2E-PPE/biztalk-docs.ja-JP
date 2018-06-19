---
title: '手順 4 D: FileAct リアルタイム シナリオでは、有効なインスタンスをテスト |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a8975c90-462b-4c9b-8766-1272ab7ceaba
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 906a7eb08dc7542d7fa383aeb9035c0a5536cff3
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25963776"
---
# <a name="step-4d-test-a-valid-instance-for-the-fileact-real-time-scenario"></a>手順 4 D: FileAct リアルタイム シナリオでは、有効なインスタンスをテストします。
この手順を開始する前に行う必要があります[手順 4 C: FileAct リアルタイム シナリオのテスト インスタンスを作成](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-fileact-real-time-scenario.md)です。  
  
### <a name="to-test-a-valid-instance"></a>有効なインスタンスをテストするには  
  
1.  C:\SWIFTAdapterTutorial\Fileact\FileRequestDropRealTime に PutReqSimple.xml ファイルをドロップします。  
  
2.  しばらくすると、PutReqSimple.xml ファイルがフォルダーから消えますことを確認します。  
  
3.  Sample_Put.txt ファイルが転送されたことを確認してください: C:\SWIFTAdapterTutorial\Fileact\ServerLocation に C:\SWIFTAdapterTutorial\Fileact\ClientLocation と C:\SWIFTAdapterTutorial\Fileact\ResponseClient と C:\ に応答が表示されています。SWIFTAdapterTutorial\Fileact\ResponseServer です。  
  
4.  次の 3 つの HandleFileEventRequest メッセージの状態イベント (c:\SWIFTAdapterTutorial\Fileact\StatusEvents) フォルダーを確認してください。 これらのメッセージは、次の転送状態を含める必要があります。  
  
     HandleFileEventRequest メッセージ\<ソフトウェア TransferStatus\>Accepted\</Sw-TransferStatus\>  
  
     HandleFileEventRequest メッセージ\<ソフトウェア TransferStatus\>開始された\</Sw-TransferStatus\>  
  
     HandleFileEventRequest メッセージ\<ソフトウェア TransferStatus\>完了\</Sw-TransferStatus\>  
  
## <a name="see-also"></a>参照  
 [手順 4: FileAct エンド ツー エンドのリアルタイムのシナリオをテストします。](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-real-time-end-to-end-scenario.md)   
 [手順 4 a: FileAct リアルタイム シナリオの SWIFTNet サービスの開始](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-real-time-scenario.md)   
 [手順 4 b: 送信ポートを開始および FileAct リアルタイム シナリオでは、受信ポート](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-the-fileact-real-time-scenario.md)   
 [手順 4C: FileAct リアルタイム シナリオ用にテスト インスタンスを作成する](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-fileact-real-time-scenario.md)