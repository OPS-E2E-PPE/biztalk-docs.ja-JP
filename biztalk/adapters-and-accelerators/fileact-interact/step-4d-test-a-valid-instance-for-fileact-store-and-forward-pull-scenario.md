---
title: '手順 4 D: FileAct ストア アンド フォワード (プル) シナリオの有効なインスタンスのテスト |Microsoft ドキュメント'
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
ms.openlocfilehash: cf6f53257ff2a9194cf85597d0806780f15c8e52
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223698"
---
# <a name="step-4d-test-a-valid-instance-for-the-fileact-store-and-forward-pull-scenario"></a>手順 4 D: FileAct ストア アンド フォワード (プル) シナリオの有効なインスタンスのテスト
この手順を開始する前に行う必要があります[手順 4 C: FileAct ストア アンド フォワード (プル) シナリオのテスト インスタンスを作成する](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-fileact-store-and-forward-pull-scenario.md)です。  
  
### <a name="to-test-a-valid-instance"></a>有効なインスタンスをテストするには  
  
1.  PutReqSimple.xml ファイル ドロップに**C:\SWIFTAdapterTutorial\Fileact\FileRequestDropSnF**です。  
  
2.  しばらくすると、PutReqSimple.xml ファイルがフォルダーから消えますことを確認します。  
  
3.  ドロップにファイル fileactcquirequeue.xml **C:\SWIFTAdapterTutorial\FileAct\PullRequest**です。  
  
4.  Sample_Put.txt ファイルが転送されたことを確認してください**C:\SWIFTAdapterTutorial\Fileact\ClientLocation**に**C:\SWIFTAdapterTutorial\Fileact\ServerLocation**、に応答が表示されていると。**C:\SWIFTAdapterTutorial\PullResponse**です。  
  
## <a name="see-also"></a>参照  
 [手順 4 a: FileAct ストア アンド フォワード (プル) シナリオの SWIFTNet サービスの開始](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-fileact-store-and-forward-pull-scenario.md)   
 [手順 4 b: 送信ポートの開始し、FileAct ストア アンド フォワード (プル) シナリオの受信ポート](../../adapters-and-accelerators/fileact-interact/step-4b-start-send-and-receive-ports-for-fileact-store-and-forward-scenario.md)   
 [手順 4 C: FileAct ストア アンド フォワード (プル) シナリオのテスト インスタンスを作成します。](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-fileact-store-and-forward-pull-scenario.md)