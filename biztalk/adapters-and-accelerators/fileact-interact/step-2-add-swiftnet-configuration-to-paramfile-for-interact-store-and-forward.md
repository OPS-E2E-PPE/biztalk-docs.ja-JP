---
title: "手順 2: SWIFTNet の構成を追加、Paramfile InterAct ストアと転送シナリオ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2a18a43c-1dd9-4113-bf32-8bc7bf9338b0
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 78aa75762e40bfcdd033a057610cb34f38825dd8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-add-swiftnet-configuration-to-the-paramfile-for-the-interact-store-and-forward-scenario"></a>手順 2: SWIFTNet の構成を追加、Paramfile InterAct ストアと転送シナリオ
SAG で作成されたサーバー メッセージのパートナーは、これらの値で初期化するために受信者を有効にする SWIFTNet paramfile で指定する必要があります。  
  
 この手順を開始する前に行う必要があります[手順 1: SWIFT アダプター InterAct ストア アンド フォワード シナリオ用に構成](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-store-and-forward-scenario.md)です。  
  
### <a name="to-add-swiftnet-configuration-to-the-paramfile"></a>Paramfile SWIFTNet 構成を追加するには  
  
1.  メモ帳などのテキスト エディターで、paramfile を開きます。  
  
    > [!NOTE]
    >  Paramfile がある通常: C:\SWIFTAlliance\RA\Ra1\cfg\paramfile です。  
  
2.  Paramfile では、サーバー メッセージのパートナー名を指定する、強調表示された変更を行います。  
  
     username:snlowner  
  
     subsystem_name:InteractStub  
  
     \#subsystem_group:Interactsnf  
  
     \#subsystem_dependency:Support、群  
  
     subsystem_nature: 重大  
  
     subsystem_start:  
  
     **起動"snlreceiver - SagMessagePartner \<Interact SnF 用サーバー MessagePartnerName > AdapterMode Interact"**  
  
     * 終了  
  
     subsystem_stop:  
  
     * KILL9:snlreceiver  
  
     * 終了  
  
     subsystem_status:  
  
     * NB:1:snlreceiver  
  
     * 終了  
  
     start_event:SNL001:subsystem InteractStubSnF が稼働  
  
     stop_event:SNL002:subsystem InteractStubSnF がダウンしています。  
  
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
  
     #<a name="starteventsnl001subsystem-user-is-up"></a>ユーザーが稼働 start_event:SNL001:subsystem です。  
  
     #<a name="stopeventsnl002subsystem-user-is-down"></a>ユーザーがダウンして stop_event:SNL002:subsystem  
  
## <a name="see-also"></a>参照  
 [ストアと順方向 (プッシュ) シナリオを対話します。](../../adapters-and-accelerators/fileact-interact/interact-store-and-forward-push-scenario.md)   
 [手順 1: InterAct ストアと転送シナリオ SWIFT のアダプターを構成します。](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-store-and-forward-scenario.md)   
 [手順 3: 送信ポートを作成し、対話ストアと転送シナリオの受信ポート](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md)   
 [手順 4: InterAct ストアと転送のエンド ツー エンド シナリオをテストします。](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-end-to-end-scenario.md)