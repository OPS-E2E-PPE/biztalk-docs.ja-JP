---
title: 可用性テストを実行して |Microsoft ドキュメント
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
ms.openlocfilehash: e6f0d9b1cb7b38ab8a1173ee227a8202812048f0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298306"
---
# <a name="performing-availability-testing"></a>可用性テストを実行します。
災害復旧をさまざまなレベルのネットワーク カードのエラー) などの小規模な障害から実稼働サーバーの消失までの範囲の障害から復旧できることを確認するには、システムをテストする必要があります。 災害復旧のテストと、次の手順を含める必要があります。  
  
-   **個々 のハードウェア コンポーネントに障害をテストします。**  
  
     ネットワークまたはディスクなど、個々 のハードウェア コンポーネントの障害から復旧するシステムの機能をテストする必要があります。  
  
-   **1 つの BizTalk server のエラーをテストします。**  
  
     ほとんどの[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]実稼働環境、ホストの処理が実行されている複数のコンピューター間で分散されている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]1 つの BizTalk グループにします。 ホストのイベントの処理を続行する、BizTalk グループの機能は、グループ内のサーバーのいずれかが失敗する場合  
  
-   **クラスター ノードのフェールオーバーをテストします。**  
  
     高可用性を実現する、Windows クラスタ リングが使用されるかどうか、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースまたは BizTalk ホスト、クラスター ノードのフェールオーバー機能を確認してください。 Windows クラスタ リングを使用して、高い可用性を実現する方法の詳細について[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[チェックリスト: フォールト トレランスと負荷分散と高可用性の実現](../technical-guides/checklist-providing-high-availability-with-fault-tolerance-or-load-balancing.md)です。  
  
-   **ログ配布を使用して BizTalk Server データベースの復旧をテストします。**  
  
     回復をことを確認する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。 バックアップおよび復元するログ配布の使用の詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースを参照してください[新機能は、BizTalk Server ログ配布しますか?](../technical-guides/what-is-biztalk-server-log-shipping.md)このガイドでまたは[ログ配布](http://go.microsoft.com/fwlink/?LinkID=153450)(http://go.microsoft.com/fwlink/?LinkID=153450)。  
  
     可用性を高めるために従う必要のある手順のチェックリストについては、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 、災害復旧を使用して環境を参照してください[チェックリスト: 可用性と災害復旧を増やす](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md)です。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server の可用性の向上](../technical-guides/increasing-availability-for-biztalk-server.md)