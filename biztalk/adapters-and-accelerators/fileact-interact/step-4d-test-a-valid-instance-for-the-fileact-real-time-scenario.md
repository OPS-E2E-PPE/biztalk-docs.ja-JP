---
title: 手順 4 D:FileAct リアルタイム シナリオ用の有効なインスタンスのテスト |Microsoft Docs
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
ms.openlocfilehash: 76721d1a7870c10eb1008e3bc4f5183985816ba0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364738"
---
# <a name="step-4d-test-a-valid-instance-for-the-fileact-real-time-scenario"></a>手順 4 D:FileAct リアルタイム シナリオ用の有効なインスタンスをテストします。
この手順を開始する前に行う必要があります[手順 4 C:FileAct リアルタイム シナリオ用にテスト インスタンスを作成](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-fileact-real-time-scenario.md)です。  
  
### <a name="to-test-a-valid-instance"></a>有効なインスタンスをテストするには  
  
1.  Drop the file PutReqSimple.xml into C:\SWIFTAdapterTutorial\Fileact\FileRequestDropRealTime.  
  
2.  しばらくすると、PutReqSimple.xml ファイルがフォルダーから消えることを確認します。  
  
3.  Sample_Put.txt ファイルが転送されることを確認します。C:\SWIFTAdapterTutorial\Fileact\ResponseClient と C:\SWIFTAdapterTutorial\Fileact\ResponseServer C:\SWIFTAdapterTutorial\Fileact\ServerLocation に C:\SWIFTAdapterTutorial\Fileact\ClientLocation とその応答が表示されます。  
  
4.  3 つの HandleFileEventRequest メッセージの状態イベント (c:\SWIFTAdapterTutorial\Fileact\StatusEvents) フォルダーを確認します。 これらのメッセージは、次の転送状態を含める必要があります。  
  
     HandleFileEventRequest メッセージ\<Sw TransferStatus\>Accepted\</Sw-TransferStatus\>  
  
     HandleFileEventRequest メッセージ\<Sw TransferStatus\>Initiated\</Sw-TransferStatus\>  
  
     HandleFileEventRequest メッセージ\<Sw TransferStatus\>完了\</Sw-TransferStatus\>  
  
## <a name="see-also"></a>参照  
 [手順 4:FileAct リアルタイム エンド ツー エンド シナリオをテストします。](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-real-time-end-to-end-scenario.md)   
 [手順 4 a:FileAct リアルタイム シナリオ用に SWIFTNet サービスを開始します。](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-real-time-scenario.md)   
 [手順 4 b:送信ポートを開始および FileAct リアルタイム シナリオ用の受信ポート](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-the-fileact-real-time-scenario.md)   
 [手順 4 C:FileAct リアルタイム シナリオ用のテスト インスタンスを作成します。](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-fileact-real-time-scenario.md)