---
title: 可用性テストの実行 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 10b543dd-ba85-40da-8c6f-485eddb59158
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a4ec699f3daf65b245dce2f2f70cd3d4daecb00
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014715"
---
# <a name="performing-availability-testing"></a>可用性テストの実行
ディザスター リカバリー (ネットワーク カードのエラー) などの小規模な障害から実稼働サーバーの損失に至るまで、障害のさまざまなレベルから回復するには、その機能を確認するには、システムをテストする必要があります。 ディザスター リカバリーのテストと、次の手順を含める必要があります。  
  
- **個々 のハードウェア コンポーネントに障害をテストします。**  
  
   ネットワークやディスクなど、個々 のハードウェア コンポーネントの障害から回復するシステムの能力をテストする必要があります。  
  
- **1 つの BizTalk server のエラーをテストします。**  
  
   ほとんどの[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]運用環境では、ホストの処理が実行されている複数のコンピューター間で分散されている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]1 つの BizTalk グループ内。 失敗、グループ内のサーバーのいずれかのホストのイベントの処理を続行する、BizTalk グループの機能は何ですか。  
  
- **クラスター ノードのフェールオーバーをテストします。**  
  
   高可用性を実現する Windows のクラスタ リングを使用するかどうか、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースまたは BizTalk ホストをクラスター ノードのフェールオーバー機能を確認する必要があります。 Windows クラスタ リングを使用して、高い可用性を実現する方法について[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[チェックリスト: フォールト トレランスまたは負荷分散と高可用性の実現](../technical-guides/checklist-providing-high-availability-with-fault-tolerance-or-load-balancing.md)します。  
  
- **ログ配布を使用して BizTalk Server データベースの回復をテストします。**  
  
   回復を確認する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。 ログ配布を使用してバックアップおよび復元する方法の詳細情報の[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースを参照してください[内容は、BizTalk Server のログ配布しますか?](../technical-guides/what-is-biztalk-server-log-shipping.md)このガイドでまたは[ログ配布](http://go.microsoft.com/fwlink/?LinkID=153450)(<http://go.microsoft.com/fwlink/?LinkID=153450>)。  
  
   可用性を高めるために従う必要のある手順のチェックリストについては、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 、ディザスター リカバリーを使用して環境を参照してください[チェックリスト: ディザスター リカバリーによる可用性の向上](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md)します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server の可用性の向上](../technical-guides/increasing-availability-for-biztalk-server.md)