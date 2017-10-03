---
title: "BizTalk Server Databases2 の統合 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d7fc4fe6-3fc2-4164-9f16-90b6f473ba8c
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 56a8f594298569caaa4842a5f754ba991e9e5f51
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="consolidate-the-biztalk-server-databases2"></a>BizTalk Server データベース2 の統合
Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] のさまざまな機能で使用するデータを格納するため、Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 内に最大 13 個のデータベースを個別に作成する必要があります。 これらのデータベースを管理し保守するにはオーバーヘッドが必要になるため、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、これらのデータベースのいくつかを 1 つのデータベースに統合することができます。 ここでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースの統合を実現する方法と、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースの統合を実現するための考慮事項について説明します。  
  
> [!NOTE]
>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のインストール時に必要なすべてのデータベースの完全なリストについては、「[BizTalk Server のデータベース](../core/databases-in-biztalk-server.md)」を参照してください。  
  
## <a name="implementing-biztalk-database-consolidation"></a>BizTalk データベース統合の実施  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースの統合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] をインストールした後、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の構成中に実行します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースを統合するには、以下の手順を実行します。  
  
1.  **[スタート]** をクリックし、**[プログラム]** をポイントします。次に、[[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]] をポイントし、**[BizTalk Server 構成]** をクリックします。 構成の種類を選択するよう求めるメッセージが表示されたら、**[ユーザー構成]** をクリックします。  
  
2.  以下のデータ ストアの 1 つ以上に対し、同じ [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] の **[サーバー名]** と **[データベース名]** (たとえば、*BizTalkConsolidatedDb*) を入力します。  
  
    |機能名|データ ストア名|  
    |------------------|---------------------|  
    |エンタープライズ SSO|SSO データベース|  
    |[グループ]|BizTalk 管理データベース|  
    |[グループ]|BizTalk メッセージ ボックス データベース|  
    |[グループ]|BizTalk 追跡データベース|  
    |ビジネス ルール エンジン|ルール エンジン データベース|  
  
     以下のデータ ストアは、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] データベースを共有するように構成**しない**ようにしてください。  
  
    |機能名|データ ストア名|  
    |------------------|---------------------|  
    |BAM ツール|BAM プライマリ インポート データベース|  
    |BAM ツール|BAM アーカイブ データベース|  
  
3.  残りの構成オプションを設定し、構成を適用します。 構成ツールによって、共有 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] データベース内に、同じ [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] の **[サーバー名]** と **[データベース名]** を指定したデータ ストア用のテーブルが作成されます。  
  
## <a name="considerations-for-implementing-biztalk-database-consolidation"></a>BizTalk データベースを統合する際の考慮事項  
 BizTalk データベースを統合するときは、以下の点を考慮してください。  
  
1.  データベース統合により、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースの管理と保守に関するオーバーヘッドが減少しますが、適切な環境でのみ実施してください。 実稼働環境で [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースを統合する前に、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の持続的なパフォーマンスに対する影響をステージング環境で計測することをお勧めします。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベース統合は、以下のシナリオでデータベースの管理と保守を単純化するために検討してください。  
  
    -   小規模でデータ量の少ない [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の実稼働環境で、データベースのパフォーマンスがパフォーマンス上のボトルネックになる可能性がきわめて低い場合。  
  
    -   中規模でデータ量が中程度の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 実稼働環境において、BizTalk 追跡データベースが統合に含まれない場合。BizTalk 追跡デーベースは、統合されたデータベースとは別の物理ディスク上に作成することが理想的です。  
  
    -   大規模でデータ量の多い [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 実稼働環境において、共有された [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] データベースが、非常にパフォーマンスが高いストレージ エリア ネットワーク (SAN) デバイスに配置されており、データベースがパフォーマンス上のボトルネックになる可能性が非常に低い場合。  
  
    -   概念実証環境または開発環境で、データベースのパフォーマンスがあまり重要でない場合。  
  
2.  一般に、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 全体のパフォーマンスは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースのパフォーマンスに依存します。 そのため、データが大量であるか、将来データが大量になることが予想される [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の実稼働環境では、データベースを統合しないことをお勧めします。 例外は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースが、非常にパフォーマンスが高いストレージ エリア ネットワーク (SAN) デバイス上に配置され、データベースがパフォーマンスのボトルネックになる可能性が非常に低い場合です。 データベース ディスクがストレージ エリア ネットワーク (SAN) に格納されていない場合に統合データベースの高いパフォーマンスを実現するには、分散データベースを使用します。分散データベースを使用した場合、優れたパフォーマンスは、負荷発生時に特に顕著になります。  
  
3.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理データベースをデータベース統合に含め、統合データベースの名前が **BizTalkMgmtDb** でない場合は、その統合データベースを指すように BizTalk 管理コンソールを構成する必要があります。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] グループを管理するには、「[既存のグループに接続する方法](../core/how-to-connect-to-an-existing-group.md)」の手順に従い、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを構成して、統合データベースを指すようにしてください。  
  
4.  持続可能な [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のパフォーマンスの詳細については、「[パフォーマンス維持の計画](../core/planning-for-sustained-performance.md)」を参照してください。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースの保守に関する活動の詳細については、「[BizTalk Server1 を維持します](../core/maintaining-biztalk-server1.md)」を参照してください。