---
title: BizTalk Server Databases2 の統合 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d7fc4fe6-3fc2-4164-9f16-90b6f473ba8c
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f5f633383b4e57133fc3b39bec804e376e1c6542
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65266170"
---
# <a name="consolidate-the-biztalk-server-databases2"></a>BizTalk Server Databases2 を統合します。
Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インストールには、Microsoft では最大 13 個の独立したデータベースの作成が必要です[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データとして使用するためのさまざまな格納[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]機能します。 管理し、これらのデータベースを維持するために必要なオーバーヘッドが原因で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]では、1 つのデータベースにこれらのデータベースのいくつかの統合。 このセクションを実行する方法を説明します[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースを統合し、実装に関する考慮事項について説明します[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースを統合します。  

> [!NOTE]
>  すべてをインストールするときに必要なデータベースの完全な一覧については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[BizTalk Server でのデータベース](../core/databases-in-biztalk-server.md)します。  

## <a name="implementing-biztalk-database-consolidation"></a>BizTalk データベースの統合を実装します。  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] インストールした後にデータベースの統合が実行される[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、中に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]構成します。 実装する次の手順に従って[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースを統合します。  

1. クリックして**開始**、 をポイント**プログラム**、 をポイント[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、順にクリックします**BizTalk Server 構成**します。 構成の種類を選択するメッセージが表示されたら、クリックして**カスタム構成**します。  

2. 同じ入力[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]**サーバー名**と**データベース名**(たとえば*BizTalkConsolidatedDb*) の 1 つ以上の次のデータの保存します。  

   |機能名|データ ストアの名前|  
   |------------------|---------------------|  
   |Enterprise SSO|SSO データベース|  
   |グループ化|BizTalk 管理データベース|  
   |グループ化|BizTalk メッセージ ボックス データベース|  
   |グループ化|BizTalk 追跡データベース|  
   |ビジネス ルール エンジン|ルール エンジン データベース|  

    次のデータ ストアが必要がある注意**いない**を共有するように構成、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベース。  


   | 機能名 |       データ ストアの名前       |
   |--------------|-----------------------------|
   |  BAM ツール   | BAM プライマリ インポート データベース |
   |  BAM ツール   |    BAM アーカイブ データベース     |


3. 残りの構成オプションを設定し、構成を適用します。 構成ツールは、共有でテーブルを作成[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データ ストアの同じを指定したデータベース[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]**サーバー名**と**データベース名**します。  

## <a name="considerations-for-implementing-biztalk-database-consolidation"></a>BizTalk データベース統合の実装に関する考慮事項  
 BizTalk データベースを統合する場合は、次を考慮してください。  

1. データベースの統合の管理と保守に関連するオーバーヘッドの削減、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースしますが、適切な環境でのみ実装する必要があります。 実装する前に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]でデータベースを効果、運用環境で統合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ステージング環境で継続的なパフォーマンスを測定する必要があります。 実装を検討[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースをデータベースの管理と、次のシナリオでのメンテナンスを簡単に統合します。  

   - 小規模な量の少ない[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]運用環境のデータベースのパフォーマンスが非常にパフォーマンスのボトルネックになる可能性があります。  

   - 中規模、中程度のボリューム[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]統合で、BizTalk 追跡データベースが含まれていない場合、運用環境と、理想的には、統合データベースから別の物理ディスクで、BizTalk 追跡データベースが作成されたかどうか。  

   - 大規模なスケール、高ボリューム[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]実稼働環境場合、共有[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベースがパフォーマンス ボトルネックになるデータベースの可能性が非常に高パフォーマンス記憶域エリア ネットワーク (SAN) デバイス上にある物理的に非常に低いです。  

   - あまりが、データベースのパフォーマンスの概念や開発環境を実証します。  

2. 全体的な[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]パフォーマンスが通常のパフォーマンスに依存する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。 したがってデータベースの統合に実装していない[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]運用環境が発生しているか、大量に発生するのです。 1 つの例外は場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースは、データベースがパフォーマンスのボトルネックが発生する可能性が非常に低い非常に高パフォーマンス ストレージ エリア ネットワーク (SAN) デバイス上に配置します。 データベースのディスクは、高性能の SAN 上にあるありません、分散データベースは、特に負荷の下で、統合データベースに優れたパフォーマンスを提供します。  

3. 場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理データベースがデータベースの統合に含まれており、統合データベースの名前がない**BizTalkMgmtDb**、BizTalk 管理コンソールをポイントするように構成する必要があり、統合データベース。 手順に従って[既存グループへの接続方法](../core/how-to-connect-to-an-existing-group.md)を構成して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを管理するために、統合データベースを指す、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループ。  

4. 維持可能なの詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]パフォーマンスを参照してください[パフォーマンス維持の計画](../core/planning-for-sustained-performance.md)します。  

   保守に関する活動の詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースを参照してください[BizTalk Server1 を維持](../core/maintaining-biztalk-server1.md)します。