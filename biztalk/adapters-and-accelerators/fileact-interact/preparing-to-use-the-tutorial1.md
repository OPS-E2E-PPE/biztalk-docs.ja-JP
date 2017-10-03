---
title: "Tutorial1 を使用する準備 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d4a792b2-8351-4ae8-9d7c-75420c00af03
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: efedfeb184b8b0105b8622b6b3f068faffd6a906
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="preparing-to-use-the-tutorial"></a>このチュートリアルを使用する準備をしています
A4SWIFT のアダプターのエンド ツー エンド チュートリアルを使用する前に、次を実行する必要があります。  
  
1.  このチュートリアルでは、次の迅速な成果物を必要となります。  
  
    -   SWIFT Alliance ゲートウェイ (SAG) 6.1  
  
    -   リモート アクセス (RA) 6.1  
  
    -   SWIFT WebStation 6.0  
  
    -   SWIFTNet リンク (SNL) 6.1  
  
2.  SAG を構成する必要があります: SAG で MessagePartners、終点、およびルーティング規則を作成し、アダプターをインストールするコンピューターで SAG 接続をテストします。 については、SAG ドキュメントを参照してください。  
  
3.  「を作成、新しいホストにする方法」Microsoft BizTalk Server ヘルプのトピックに記載の手順に従います ([http://go.microsoft.com/fwlink/?LinkId = 100422](http://go.microsoft.com/fwlink/?LinkId=100422)) という名前の InterAct アダプターの 1 つのインプロセス ホストを作成する*interacthost*、インプロセス ホスト FileAct アダプターは、という名前のいずれかと*fileacthost*です。 アダプターのハンドラーを作成するときに、これらのホストを使用します。  
  
4.  チュートリアルでは、次のフォルダーを作成します。  
  
    -   c:\SWIFTAdapterTutorial\Fileact\ClientLocation  
  
    -   c:\SWIFTAdapterTutorial\Fileact\FileRequestDropRealTime  
  
    -   c:\SWIFTAdapterTutorial\Fileact\ResponseClient  
  
    -   c:\SWIFTAdapterTutorial\Fileact\ResponseServer  
  
    -   c:\SWIFTAdapterTutorial\Fileact\ServerLocation  
  
    -   c:\SWIFTAdapterTutorial\Fileact\StatusEvents  
  
    -   c:\SWIFTAdapterTutorial\Fileact\PullRequest  
  
    -   c:\SWIFTAdapterTutorial\Fileact\PullResponse  
  
    -   c:\SWIFTAdapterTutorial\Interact\HandleRequest  
  
    -   c:\SWIFTAdapterTutorial\Interact\InputRequest_RealTime  
  
    -   c:\SWIFTAdapterTutorial\Interact\InputRequest_SnF  
  
    -   c:\SWIFTAdapterTutorial\Interact\Response  
  
    -   c:\SWIFTAdapterTutorial\Interact\PullRequest  
  
    -   c:\SWIFTAdapterTutorial\Interact\Pullresponse  
  
5.  SWIFT ITB への接続またはアダプターをテストする実際の環境が必要です。  
  
## <a name="see-also"></a>参照  
 [BizTalk FileAct と対話するアダプターのエンド ツー エンドのチュートリアル](../../adapters-and-accelerators/fileact-interact/biztalk-fileact-and-interact-adapters-end-to-end-tutorial.md)   
 [リアルタイムのシナリオを対話します。](../../adapters-and-accelerators/fileact-interact/interact-real-time-scenario.md)   
 [ストアと順方向 (プッシュ) シナリオを対話します。](../../adapters-and-accelerators/fileact-interact/interact-store-and-forward-push-scenario.md)   
 [FileAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/fileact-real-time-scenario.md)   
 [FileAct ストア アンド フォワードのシナリオ](../../adapters-and-accelerators/fileact-interact/fileact-store-and-forward-scenario.md)