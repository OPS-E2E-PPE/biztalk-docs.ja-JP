---
title: 手順 4 D:FileAct ストア アンド フォワード (プル) シナリオ用の有効なインスタンスをテスト |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 33c7aabe-206f-4b89-b739-ac1e63675451
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3cf19da7b9fb0e6cbeefb3ccb9f7ff2cfbc8f86
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364776"
---
# <a name="step-4d-test-a-valid-instance-for-the-fileact-store-and-forward-pull-scenario"></a>手順 4 D:FileAct ストア アンド フォワード (プル) シナリオ用の有効なインスタンスをテストします。
この手順を開始する前に行う必要があります[手順 4 C:FileAct ストア アンド フォワード (プル) シナリオのテスト インスタンスを作成](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-fileact-store-and-forward-pull-scenario.md)です。  
  
### <a name="to-test-a-valid-instance"></a>有効なインスタンスをテストするには  
  
1.  PutReqSimple.xml ファイル ドロップに**C:\SWIFTAdapterTutorial\Fileact\FileRequestDropSnF**します。  
  
2.  しばらくすると、PutReqSimple.xml ファイルがフォルダーから消えることを確認します。  
  
3.  削除にファイル fileactcquirequeue.xml **C:\SWIFTAdapterTutorial\FileAct\PullRequest**します。  
  
4.  Sample_Put.txt ファイルが転送されることを確認します**C:\SWIFTAdapterTutorial\Fileact\ClientLocation**に**C:\SWIFTAdapterTutorial\Fileact\ServerLocation**、に応答が表示されることと。**C:\SWIFTAdapterTutorial\PullResponse**します。  
  
## <a name="see-also"></a>参照  
 [手順 4 a:FileAct ストア アンド フォワード (プル) シナリオ用に SWIFTNet サービスを開始します。](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-fileact-store-and-forward-pull-scenario.md)   
 [手順 4 b:送信ポートと FileAct ストア アンド フォワード (プル) シナリオ用のポートを受信開始](../../adapters-and-accelerators/fileact-interact/step-4b-start-send-and-receive-ports-for-fileact-store-and-forward-scenario.md)   
 [手順 4 C:FileAct ストア アンド フォワード (プル) シナリオのテスト インスタンスを作成します。](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-fileact-store-and-forward-pull-scenario.md)