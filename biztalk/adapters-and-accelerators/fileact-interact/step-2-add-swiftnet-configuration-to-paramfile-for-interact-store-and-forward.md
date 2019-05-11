---
title: 手順 2:InterAct ストア アンド フォワード シナリオ用に Paramfile に SWIFTNet 構成を追加 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2a18a43c-1dd9-4113-bf32-8bc7bf9338b0
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3bfa88c4a382721da5ccecc8baff2c2ebca2a50f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366193"
---
# <a name="step-2-add-swiftnet-configuration-to-the-paramfile-for-the-interact-store-and-forward-scenario"></a>手順 2:InterAct ストア アンド フォワード シナリオ用に Paramfile に SWIFTNet 構成を追加します。
これらの値で初期化するために受信者を有効にする SWIFTNet に paramfile に SAG で作成したサーバー メッセージのパートナーを指定する必要があります。  
  
 この手順を開始する前に行う必要があります[手順 1。InterAct ストア アンド フォワード シナリオ用に SWIFT アダプターを構成する](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-store-and-forward-scenario.md)します。  
  
### <a name="to-add-swiftnet-configuration-to-the-paramfile"></a>Paramfile に SWIFTNet 構成を追加するには  
  
1. Paramfile をメモ帳などのテキスト エディターで開きます。  
  
   > [!NOTE]
   >  位置に paramfile にある通常。C:\SWIFTAlliance\RA\Ra1\cfg\paramfile.  
  
2. Paramfile では、サーバー メッセージのパートナー名を指定する、強調表示されている変更を行います。  
  
    username:snlowner  
  
    subsystem_name:InteractStub  
  
    \#subsystem_group:Interactsnf  
  
    \#subsystem_dependency:Support、Swarm  
  
    subsystem_nature: 重大  
  
    subsystem_start:  
  
    **spawn"snlreceiver - SagMessagePartner \<Interact SnF 用サーバー MessagePartnerName\> AdapterMode 対話"**  
  
    * 終了  
  
    subsystem_stop:  
  
    * KILL9:snlreceiver  
  
    * 終了  
  
    subsystem_status:  
  
    * NB:1:snlreceiver  
  
    * 終了  
  
    start_event:SNL001:subsystem InteractStubSnF です。  
  
    stop_event:SNL002:subsystem InteractStubSnF がダウン  
  
    \#subsystem_name:User  
  
    \##subsystem_group:user  
  
    \##subsystem_dependency:  
  
    \#subsystem_nature: 重大  
  
    \#subsystem_start:  
  
    \#* 終了  
  
    \#subsystem_stop:  
  
    \#* 終了  
  
    \#subsystem_status:  
  
    \#* 終了  
  
    # <a name="starteventsnl001subsystem-user-is-up"></a>ユーザーが稼働 start_event:SNL001:subsystem です。  
  
    # <a name="stopeventsnl002subsystem-user-is-down"></a>ユーザーがダウンして stop_event:SNL002:subsystem  
  
## <a name="see-also"></a>参照  
 [InterAct ストア アンド フォワード (プッシュ) シナリオ](../../adapters-and-accelerators/fileact-interact/interact-store-and-forward-push-scenario.md)   
 [ステップ 1: InterAct ストア アンド フォワード シナリオ用に SWIFT アダプターを構成します。](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-store-and-forward-scenario.md)   
 [ステップ 3:送信ポートの作成し、InterAct ストア アンド フォワード シナリオ用の受信ポート](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md)   
 [手順 4:InterAct ストア アンド フォワード エンド ツー エンド シナリオをテストします。](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-end-to-end-scenario.md)