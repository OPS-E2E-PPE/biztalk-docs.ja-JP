---
title: ビジネス シナリオのサンプル |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BTAHL7, business example
- examples, business processes
- health care organizations, business example
- business processes, example
ms.assetid: 54bfbe45-4638-4488-bbd8-c642926a35d3
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6b88bd76a1fac2ebfa5c2f75a6abbf78aab75b7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966907"
---
# <a name="sample-business-scenario"></a>サンプル ビジネス シナリオ
医療のプロセスは複雑では多くの場合、多くのシステムが含まれます。 例としては、患者が病院では、入力したときに発生するプロセスと、医師が患者のラボ テストを送信します。 この手順に関連するには 5 つのパーティを示します。  
  
- 在籍している医師  
  
- 病院の登録システム  
  
- 臨床注文入力システム  
  
- ラボ システム  
  
- 課金システム  
  
  次の手順は、このプロセスで発生する可能性があります。  
  
1.  在籍している医師は患者を登録します。  
  
    1.  ADT ^ 病院の登録システムによって O04 登録メッセージをブロードキャストします。  
  
    2.  ADT ^ O04 メッセージ Clinical、受注システムとテスト システムを含むメッセージにサブスクライブするすべての部門で受信されます。  
  
2.  医師は、実験施設から診断調査を指示します。  
  
    1.  ORM ^ O01 注文メッセージはビジネス ルールの検証後に、臨床注文入力システムから送信します。  
  
    2.  ORM ^ O01 メッセージ ラボ システムで受信されます。  
  
3.  ラボは、注文を受信し、確認メッセージを返します。  
  
    1.  ORR ^ O02 注文確認メッセージは順序を実行できることを示す、研究室のシステムで送信します。  
  
    2.  ORR ^ O02 メッセージ臨床注文入力システムによって受信されます。  
  
4.  テストの完了時に、ラボは、医師と他の部門に結果を送信します。  
  
    1.  ORU ^ テスト システムから R01 テスト結果のメッセージを送信します。  
  
    2.  ORU ^ R01 メッセージ Clinical、受注システムと課金システムで受信されます。  
  
    3.  インターフェイスのエンジンは、ワイヤレス PDA でラボの結果を受信すると、doctor を電子メール メッセージを送信します。  
  
## <a name="the-btahl7-solution"></a>BTAHL7 ソリューション  
 上記で説明したサンプル ビジネス シナリオでは、統合が必要な医療システムの例を示します。 Microsoft BizTalk Accelerator for HL7 の MicrosoftBizTalk サーバー ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) このシナリオでは、次の機能を紹介するソリューションを提供します。  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] すべてのハブとスポークの配置に関連するシステムを統合します。 各システムと直接通信する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。 これらは相互に直接通信するためにはありません。  
  
2. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] ネイティブ HL7 でエンコードされたメッセージを処理します。 独自のコーディングは必要ありません。  
  
3. ADT ^ O04 登録メッセージは、サブスクライブするすべてのシステムにブロードキャストされます。 パブリッシャーとサブスクライバーのメッセージング モデル[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を設定すると、メッセージをサブスクライブ システムのリストを保持する柔軟性を提供します。 システムを追加したり、システムの残りの部分に影響を与えずに、サブスクリプションの一覧から削除することができます。  
  
4. ビジネス ルールの ORM の検証に使用される ^ O01 注文メッセージは、システムの残りの部分に影響を与えずに動的に変更することができます。  
  
5. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] ORR を自動的に生成するように構成できる ^ O02 注文確認 (ACK) メッセージ。  
  
6. 必要に応じて、他のユーザーと、送信するためのメッセージのいずれかのバッチを処理しからの受信バッチ内でイベントを処理できます。  
  
7. に対して、エンジンですべてのメッセージを検証することができます、 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2 X スキーマが HL7 組織によって発行されました。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server がビジネス ニーズを解決するしくみ](../../adapters-and-accelerators/accelerator-hl7/how-biztalk-server-solves-the-business-need2.md)