---
title: 手順 2:FileAct リアルタイム シナリオ用に Paramfile に SWIFTNet 構成を追加 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d4feec3f-4755-477e-b3d6-1dd6d075255e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0acfd70f479aec6c7557fcdf9a87c10f839502be
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366458"
---
# <a name="step-2-add-swiftnet-configuration-to-the-paramfile-for-the-fileact-real-time-scenario"></a>手順 2:FileAct リアルタイム シナリオ用に Paramfile に SWIFTNet 構成を追加します。
これらの値で初期化するために受信者を有効にする SWIFTNet に paramfile に SAG で作成したサーバー メッセージのパートナーを指定する必要があります。  
  
 この手順を開始する前に行う必要があります[手順 1。FileAct リアルタイム シナリオ用に SWIFT アダプターを構成する](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-fileact-real-time-scenario.md)します。  
  
### <a name="to-add-swiftnet-configuration-to-the-paramfile"></a>Paramfile に SWIFTNet 構成を追加するには  
  
1. Paramfile をメモ帳などのテキスト エディターで開きます。  
  
   > [!NOTE]
   >  位置に paramfile にある通常。C:\SWIFTAlliance\RA\Ra1\cfg\paramfile  
  
2. Paramfile では、サーバー メッセージのパートナー名を指定する、強調表示されている変更を行います。  
  
    username:snlowner  
  
    subsystem_name:FileactStub  
  
    \#subsystem_group:fileact  
  
    \#subsystem_dependency:Support、Swarm  
  
    subsystem_nature: 重大  
  
    subsystem_start:  
  
    **spawn"snlreceiver - SagMessagePartner \<fileact RT のサーバー MessagePartnerName \> -AdapterMode fileact"**  
  
    * 終了  
  
    subsystem_stop:  
  
    * KILL9:snlreceiver  
  
    * 終了  
  
    subsystem_status:  
  
    * NB:1:snlreceiver  
  
    * 終了  
  
    start_event:SNL001:subsystem FileactStub です。  
  
    stop_event:SNL002:subsystem FileactStub がダウン  
  
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
 [FileAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/fileact-real-time-scenario.md)   
 [ステップ 1: FileAct リアルタイム シナリオ用に SWIFT アダプターを構成します。](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-fileact-real-time-scenario.md)   
 [ステップ 3:送信ポートを作成および FileAct リアルタイム シナリオ用の受信ポート](../../adapters-and-accelerators/fileact-interact/step-3-create-the-send-ports-and-receive-ports-for-fileact-real-time-scenario.md)   
 [手順 4:FileAct リアルタイム エンド ツー エンド シナリオをテストします。](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-real-time-end-to-end-scenario.md)