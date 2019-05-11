---
title: Tutorial1 を使用する準備 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d4a792b2-8351-4ae8-9d7c-75420c00af03
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8bc4614d82471f6573134c6da47966bf8ca57330
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366574"
---
# <a name="preparing-to-use-the-tutorial"></a>チュートリアルを使用する準備をしています
A4SWIFT アダプターのエンド ツー エンド チュートリアルを使用する前に、次を行う必要があります。  
  
1.  このチュートリアルでは、次の SWIFT 成果物を必要となります。  
  
    -   SWIFT Alliance ゲートウェイ (SAG) 6.1  
  
    -   リモート アクセス (RA) 6.1  
  
    -   SWIFT WebStation 6.0  
  
    -   SWIFTNet リンク (SNL) 6.1  
  
2.  SAG を構成する必要があります: SAG で MessagePartners、終点、およびルーティング規則を作成し、アダプターをインストールするコンピューターで SAG 接続をテストします。 については、SAG ドキュメントを参照してください。  
  
3.  「を作成、新しいホストにする方法」Microsoft BizTalk Server ヘルプのトピックに記載の指示に従います ([http://go.microsoft.com/fwlink/?LinkId=100422](http://go.microsoft.com/fwlink/?LinkId=100422)) という、InterAct アダプターの 1 つのインプロセス ホストを作成する*interacthost*、インプロセス ホストという名前の FileAct アダプターの 1 つ*fileacthost*します。 アダプターのハンドラーを作成するときに、これらのホストを使用します。  
  
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
 [BizTalk FileAct および InterAct アダプターのエンド ツー エンド チュートリアル](../../adapters-and-accelerators/fileact-interact/biztalk-fileact-and-interact-adapters-end-to-end-tutorial.md)   
 [InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/interact-real-time-scenario.md)   
 [InterAct ストア アンド フォワード (プッシュ) シナリオ](../../adapters-and-accelerators/fileact-interact/interact-store-and-forward-push-scenario.md)   
 [FileAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/fileact-real-time-scenario.md)   
 [FileAct ストア アンド フォワード シナリオ](../../adapters-and-accelerators/fileact-interact/fileact-store-and-forward-scenario.md)