---
title: '手順 2: FileAct ストア アンド フォワード シナリオ用に Paramfile に SWIFTNet 構成を追加する |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 088ab41f-8325-4330-b6f2-0164aa1911b1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a287c6063ff60b08a53ec4f05d45da9225f1c30
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998243"
---
# <a name="step-2-add-swiftnet-configuration-to-the-paramfile-for-the-fileact-store-and-forward-scenario"></a>手順 2: FileAct ストア アンド フォワード シナリオ用に Paramfile に SWIFTNet 構成を追加します。
これらの値で初期化するために受信者を有効にする SWIFTNet に paramfile に SAG で作成したサーバー メッセージのパートナーを指定する必要があります。  
  
完全な[手順 1: FileAct ストア アンド フォワード シナリオ用に SWIFT アダプターを構成する](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-fileact-store-and-forward-scenario.md)この手順を開始する前にします。
  
## <a name="add-swiftnet-configuration-to-the-paramfile"></a>Paramfile に SWIFTNet 構成を追加します。  
  
1. Paramfile をメモ帳などのテキスト エディターで開きます。  
  
2. 位置に paramfile にある通常: C:\SWIFTAlliance\RA\Ra1\cfg\paramfile  
  
3. Paramfile では、サーバー メッセージのパートナー名を指定する、強調表示されている変更を行います。  
    
    username:snlowner  
  
    subsystem_name:FileactStub  
  
    \#subsystem_group:fileactsnf  
  
    \#subsystem_dependency:Support、Swarm  
  
    subsystem_nature: 重大  
  
    subsystem_start:  
  
    **spawn"snlreceiver - SagMessagePartner \<fileact SnF 用サーバー MessagePartnerName\> -AdapterMode fileact"**  
  
    * 終了  
  
    subsystem_stop:  
  
    * KILL9:snlreceiver  
  
    * 終了  
  
    subsystem_status:  
  
    * NB:1:snlreceiver  
  
    * 終了  
  
    start_event:SNL001:subsystem FileactStubSnF です。  
  
    stop_event:SNL002:subsystem FileactStubSnF がダウン  
  
    \#subsystem_name:User  
  
    \## subsystem_group:user  
  
    \## subsystem_dependency:  
  
    \#subsystem_nature: 重大  
  
    \#subsystem_start:  
  
    \#* 終了  
  
    \#subsystem_stop:  
  
    \#* 終了  
  
    \#subsystem_status:  
  
    \#* 終了  
  
    # <a name="starteventsnl001subsystem-user-is-up"></a>ユーザーが稼働 start_event:SNL001:subsystem です。  
  
    # <a name="stopeventsnl002subsystem-user-is-down"></a>ユーザーがダウンして stop_event:SNL002:subsystem  
    
  
## <a name="complete-steps"></a>手順を完了します
 [FileAct ストア アンド フォワード シナリオ](../../adapters-and-accelerators/fileact-interact/fileact-store-and-forward-scenario.md)   
 [手順 1: FileAct ストア アンド フォワード シナリオ用に SWIFT アダプターを構成します。](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-fileact-store-and-forward-scenario.md)   
 [手順 3: 送信ポートを作成し、受信 FileAct ストア アンド フォワード シナリオ用のポート](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md)   
 [手順 4: FileAct ストア アンド フォワード エンド ツー エンド シナリオをテストする](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-store-and-forward-end-to-end-scenario.md)