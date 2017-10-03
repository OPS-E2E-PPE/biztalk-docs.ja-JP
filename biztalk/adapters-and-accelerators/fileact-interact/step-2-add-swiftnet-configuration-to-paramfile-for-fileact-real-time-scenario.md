---
title: "手順 2: SWIFTNet の構成を追加、Paramfile FileAct リアルタイム シナリオ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d4feec3f-4755-477e-b3d6-1dd6d075255e
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 793378e25c3ba92170e1da36b0c8276ab13357ae
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-add-swiftnet-configuration-to-the-paramfile-for-the-fileact-real-time-scenario"></a>手順 2: SWIFTNet の構成を追加、Paramfile FileAct リアルタイム シナリオ
SAG で作成されたサーバー メッセージのパートナーは、これらの値で初期化するために受信者を有効にする SWIFTNet paramfile で指定する必要があります。  
  
 この手順を開始する前に行う必要があります[手順 1: FileAct リアルタイム シナリオでは、SWIFT アダプターを構成する](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-fileact-real-time-scenario.md)です。  
  
### <a name="to-add-swiftnet-configuration-to-the-paramfile"></a>Paramfile SWIFTNet 構成を追加するには  
  
1.  メモ帳などのテキスト エディターで、paramfile を開きます。  
  
    > [!NOTE]
    >  Paramfile がある通常: C:\SWIFTAlliance\RA\Ra1\cfg\paramfile  
  
2.  Paramfile では、サーバー メッセージのパートナー名を指定する、強調表示された変更を行います。  
  
     username:snlowner  
  
     subsystem_name:FileactStub  
  
     \#subsystem_group:fileact  
  
     \#subsystem_dependency:Support、群  
  
     subsystem_nature: 重大  
  
     subsystem_start:  
  
     **起動"snlreceiver - SagMessagePartner \<fileact RT 用サーバー MessagePartnerName > - AdapterMode fileact"**  
  
     * 終了  
  
     subsystem_stop:  
  
     * KILL9:snlreceiver  
  
     * 終了  
  
     subsystem_status:  
  
     * NB:1:snlreceiver  
  
     * 終了  
  
     start_event:SNL001:subsystem FileactStub が稼働  
  
     stop_event:SNL002:subsystem FileactStub がダウンしています。  
  
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
 [FileAct リアルタイム シナリオ](../../adapters-and-accelerators/fileact-interact/fileact-real-time-scenario.md)   
 [手順 1: FileAct リアルタイム シナリオでは、SWIFT のアダプターを構成します。](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-fileact-real-time-scenario.md)   
 [手順 3: 送信ポートを作成し、FileAct リアルタイムのシナリオの受信ポート](../../adapters-and-accelerators/fileact-interact/step-3-create-the-send-ports-and-receive-ports-for-fileact-real-time-scenario.md)   
 [手順 4: FileAct エンド ツー エンドのリアルタイムのシナリオをテストします。](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-real-time-end-to-end-scenario.md)