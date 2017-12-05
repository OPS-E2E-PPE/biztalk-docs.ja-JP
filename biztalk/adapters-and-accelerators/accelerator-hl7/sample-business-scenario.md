---
title: "ビジネス シナリオのサンプル |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BTAHL7, business example
- examples, business processes
- health care organizations, business example
- business processes, example
ms.assetid: 54bfbe45-4638-4488-bbd8-c642926a35d3
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 78229d903461fe2b84033b036ef02b2838832fc0
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="sample-business-scenario"></a>このサンプル ビジネス シナリオ
医療プロセスは複雑な多くの場合、れ多くのシステム。 例としては患者を病院に入ったときに発生するプロセスし医師がラボ テスト用の患者情報を送信します。 この手順に関係するには 5 つのパーティを示します。  
  
-   推進医師  
  
-   病院登録システム  
  
-   医療注文入力システム  
  
-   ラボ システム  
  
-   課金システム  
  
 次の手順は、このプロセスで発生する可能性があります。  
  
1.  推進医師は、患者を登録します。  
  
    1.  ADT ^ 病院登録システムによって O04 登録メッセージをブロードキャストします。  
  
    2.  ADT ^ 治療注文入力システムおよび実験システムなど、メッセージをサブスクライブするすべての部門が O04 メッセージを受信します。  
  
2.  医師は、ラボ機能からの診断の調査を並べ替えます。  
  
    1.  ORM ^ O01 注文メッセージはビジネス ルールの検証後に、治療の注文エントリ システムから送信します。  
  
    2.  ORM ^ 実験システム O01 メッセージを受信します。  
  
3.  ラボは、注文を受信し、確認メッセージを返します。  
  
    1.  ORR ^ O02 注文確認メッセージが送信されるラボ システムで注文を実行できることを示すです。  
  
    2.  ORR ^ 治療注文入力システムが O02 メッセージを受信します。  
  
4.  テストの完了時には、ラボは、医師およびその他の部門に結果を送信します。  
  
    1.  ORU ^ ラボ システムから R01 テスト結果のメッセージを送信します。  
  
    2.  ORU ^ 治療注文入力システムと課金システムが R01 メッセージを受信します。  
  
    3.  インターフェイスのエンジンは、ワイヤレス PDA の演習の結果を受信すると、博士に電子メール メッセージを送信します。  
  
## <a name="the-btahl7-solution"></a>BTAHL7 ソリューション  
 上記で説明したサンプル ビジネス シナリオでは、統合が必要な医療システムの例を示します。 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Server [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 次の機能を搭載したこのシナリオのソリューションを提供します。  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]すべてのハブとスポークの配置に関連するシステムを統合します。 各システムと直接通信[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。 相互に直接通信するためにはありません。  
  
2.  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]ネイティブ HL7 でエンコードされたメッセージを処理します。 カスタム コーディングは必要ありません。  
  
3.  ADT ^ O04 登録メッセージにサブスクライブできるようにするすべてのシステムに送信します。 パブリッシャーとサブスクライバーのメッセージング モデル[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]柔軟に設定および管理メッセージをサブスクライブ システムの一覧を提供します。 システムを追加したり、システムの残りの部分に影響を与えずに、サブスクリプションの一覧から削除することができます。  
  
4.  ORM の検証に使用されるビジネス ルール ^ O01 注文メッセージは、システムの残りの部分に影響を与えずに動的に変更することができます。  
  
5.  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]ORR を自動的に生成するように構成する ^ O02 注文確認 (ACK) メッセージ。  
  
6.  必要に応じて、他のユーザーと、送信するためのメッセージのバッチおよびから確認メッセージをバッチ内で上での処理できます。  
  
7.  に対して、エンジンのすべてのメッセージを検証することができます、 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2 X スキーマは、HL7 組織によって発行されました。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server がビジネス ニーズを解決するしくみ](../../adapters-and-accelerators/accelerator-hl7/how-biztalk-server-solves-the-business-need2.md)