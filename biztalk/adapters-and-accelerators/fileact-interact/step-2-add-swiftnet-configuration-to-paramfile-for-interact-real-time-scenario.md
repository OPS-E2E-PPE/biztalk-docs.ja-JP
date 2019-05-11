---
title: 手順 2:用に Paramfile に SWIFTNet 構成を追加、InterAct リアルタイム シナリオ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6a900a6e-3e08-430a-8766-4a7192adba5e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ecb9f4027ddb0c8e4101d275e83ef84c7c02207b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366213"
---
# <a name="step-2-add-swiftnet-configuration-to-the-paramfile-for-the-interact-real-time-scenario"></a>手順 2:用に Paramfile に SWIFTNet 構成を追加、InterAct リアルタイム シナリオ
これらの値で初期化するために受信者を有効にする SWIFTNet に paramfile に SAG で作成したサーバー メッセージのパートナーを指定する必要があります。 手順を完了する必要があります、プロシージャを開始する前に[手順 1。用に SWIFT アダプターを構成、InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-real-time-scenario.md)します。  
  
### <a name="to-add-swiftnet-configuration-to-the-paramfile"></a>Paramfile に SWIFTNet 構成を追加するには  
  
1. Paramfile をメモ帳などのテキスト エディターで開きます。  
  
    位置に paramfile にある通常。C:\SWIFTAlliance\RA\Ra1\cfg\paramfile  
  
2. Paramfile では、サーバー メッセージのパートナー名を指定する、強調表示されている変更を行います。  
  
    username:snlowner  
  
    subsystem_name:InteractStub  
  
    \#subsystem_group:InteractRT  
  
    \#subsystem_dependency:Support、Swarm  
  
    subsystem_nature: 重大  
  
    subsystem_start:  
  
    **spawn"snlreceiver - SagMessagePartner \<Interact RT のサーバー MessagePartnerName \> AdapterMode 対話"**  
  
    * 終了  
  
    subsystem_stop:  
  
    * KILL9:snlreceiver  
  
    * 終了  
  
    subsystem_status:  
  
    * NB:1:snlreceiver  
  
    * 終了  
  
    start_event:SNL001:subsystem InteractStub です。  
  
    stop_event:SNL002:subsystem InteractStub がダウン  
  
    \#subsystem_name:User  
  
    \##subsystem_group:user  
  
    \##subsystem_dependency:  
  
    \#subsystem_nature: 重大  
  
    \#subsystem_start:  
  
    \#* 終了  
  
    \#subsystem_stop:  
  
    \#* 終了  
  
    \#subsystem_status:  
  
    # <a name="end"></a>* 終了  
  
    # <a name="starteventsnl001subsystem-user-is-up"></a>ユーザーが稼働 start_event:SNL001:subsystem です。  
  
    # <a name="stopeventsnl002subsystem-user-is-down"></a>ユーザーがダウンして stop_event:SNL002:subsystem  
  
## <a name="see-also"></a>参照  
 [InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/interact-real-time-scenario.md)   
 [ステップ 1: 用に SWIFT アダプターを構成、InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-real-time-scenario.md)   
 [ステップ 3:作成する送信と受信ポートを InterAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md)   
 [手順 4:テスト、InterAct リアルタイム エンド ツー エンドのシナリオ](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-real-time-end-to-end-scenario.md)