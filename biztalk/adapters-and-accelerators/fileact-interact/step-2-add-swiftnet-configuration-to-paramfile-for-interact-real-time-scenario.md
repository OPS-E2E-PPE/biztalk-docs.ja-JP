---
title: '手順 2: の Paramfile に SWIFTNet 構成を追加する、リアルタイムのシナリオを対話 |Microsoft ドキュメント'
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
ms.openlocfilehash: 3e33203279e045b28d2098ca78c55403c7070b64
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25964608"
---
# <a name="step-2-add-swiftnet-configuration-to-the-paramfile-for-the-interact-real-time-scenario"></a>手順 2: の Paramfile に SWIFTNet 構成を追加する、リアルタイムのシナリオの対話
SAG で作成されたサーバー メッセージのパートナーは、これらの値で初期化するために受信者を有効にする SWIFTNet paramfile で指定する必要があります。 手順を完了する必要があります、プロシージャを開始する前に[手順 1: 対話リアルタイム シナリオでは、SWIFT アダプターを構成](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-real-time-scenario.md)です。  
  
### <a name="to-add-swiftnet-configuration-to-the-paramfile"></a>Paramfile SWIFTNet 構成を追加するには  
  
1.  メモ帳などのテキスト エディターで、paramfile を開きます。  
  
     Paramfile がある通常: C:\SWIFTAlliance\RA\Ra1\cfg\paramfile  
  
2.  Paramfile では、サーバー メッセージのパートナー名を指定する、強調表示された変更を行います。  
  
     username:snlowner  
  
     subsystem_name:InteractStub  
  
     \#subsystem_group:InteractRT  
  
     \#subsystem_dependency:Support、群  
  
     subsystem_nature: 重大  
  
     subsystem_start:  
  
     **起動"snlreceiver - SagMessagePartner \<Interact RT 用サーバー MessagePartnerName \> AdapterMode Interact"**  
  
     * 終了  
  
     subsystem_stop:  
  
     * KILL9:snlreceiver  
  
     * 終了  
  
     subsystem_status:  
  
     * NB:1:snlreceiver  
  
     * 終了  
  
     start_event:SNL001:subsystem InteractStub が稼働  
  
     stop_event:SNL002:subsystem InteractStub がダウンしています。  
  
     \#subsystem_name:User  
  
     \## subsystem_group:user  
  
     \## subsystem_dependency:  
  
     \#subsystem_nature: 重大  
  
     \#subsystem_start:  
  
     \#* 終了  
  
     \#subsystem_stop:  
  
     \#* 終了  
  
     \#subsystem_status:  
  
     #<a name="end"></a>* 終了  
  
     #<a name="starteventsnl001subsystem-user-is-up"></a>ユーザーが稼働 start_event:SNL001:subsystem です。  
  
     #<a name="stopeventsnl002subsystem-user-is-down"></a>ユーザーがダウンして stop_event:SNL002:subsystem  
  
## <a name="see-also"></a>参照  
 [リアルタイムのシナリオを対話します。](../../adapters-and-accelerators/fileact-interact/interact-real-time-scenario.md)   
 [手順 1: 構成用のアダプターを SWIFT、リアルタイムのシナリオの対話](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-interact-real-time-scenario.md)   
 [手順 3: が送信を作成し、受信のポート、リアルタイムのシナリオの対話](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md)   
 [手順 4: InterAct リアルタイム エンド ツー エンド シナリオをテストする](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-real-time-end-to-end-scenario.md)