---
title: "手順 2: FileAct ストア アンド フォワードのシナリオの Paramfile に SWIFTNet 構成を追加する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 088ab41f-8325-4330-b6f2-0164aa1911b1
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 394e570ad9bd1c0e7532923dac9c2cc702f2f567
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="step-2-add-swiftnet-configuration-to-the-paramfile-for-the-fileact-store-and-forward-scenario"></a>手順 2: FileAct ストア アンド フォワードのシナリオの Paramfile に SWIFTNet 構成を追加します。
SAG で作成されたサーバー メッセージのパートナーは、これらの値で初期化するために受信者を有効にする SWIFTNet paramfile で指定する必要があります。  
  
完全な[手順 1: SWIFT アダプター FileAct ストア アンド フォワード シナリオ用に構成](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-fileact-store-and-forward-scenario.md)この手順を開始する前にします。
  
## <a name="add-swiftnet-configuration-to-the-paramfile"></a>SWIFTNet 構成、paramfile を追加します。  
  
1.  メモ帳などのテキスト エディターで、paramfile を開きます。  
  
2.  Paramfile がある通常: C:\SWIFTAlliance\RA\Ra1\cfg\paramfile  
  
3.  Paramfile では、サーバー メッセージのパートナー名を指定する、強調表示された変更を行います。  
    
     username:snlowner  
  
     subsystem_name:FileactStub  
  
     \#subsystem_group:fileactsnf  
  
     \#subsystem_dependency:Support、群  
  
     subsystem_nature: 重大  
  
     subsystem_start:  
  
     **起動"snlreceiver - SagMessagePartner \<fileact SnF 用サーバー MessagePartnerName\> -AdapterMode fileact"**  
  
     * 終了  
  
     subsystem_stop:  
  
     * KILL9:snlreceiver  
  
     * 終了  
  
     subsystem_status:  
  
     * NB:1:snlreceiver  
  
     * 終了  
  
     start_event:SNL001:subsystem FileactStubSnF が稼働  
  
     stop_event:SNL002:subsystem FileactStubSnF がダウンしています。  
  
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
    
  
## <a name="complete-steps"></a>詳細な手順
 [FileAct ストア アンド フォワードのシナリオ](../../adapters-and-accelerators/fileact-interact/fileact-store-and-forward-scenario.md)   
 [手順 1: FileAct ストア アンド フォワードのシナリオ用 SWIFT アダプターを構成します。](../../adapters-and-accelerators/fileact-interact/step-1-configure-the-swift-adapter-for-the-fileact-store-and-forward-scenario.md)   
 [手順 3: 送信ポートを作成し、FileAct ストア アンド フォワードのシナリオの受信ポート](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md)   
 [手順 4: FileAct ストア アンド フォワード エンド ツー エンド シナリオをテストする](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-store-and-forward-end-to-end-scenario.md)