---
title: "SQL Server の設定を変更しないで |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4b383bfb-c3d9-47d4-b294-f6be94302734
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2fb6e2553c005d3ba8651c860ff844e8cc74106
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="sql-server-settings-that-should-not-be-changed"></a>SQL Server の設定を変更しないでください。
設定する場合に[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]の運用の準備手順の間に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、次の設定を変更しないようにします。  
  
## <a name="sql-server-max-degree-of-parallelism"></a>SQL Server の並列処理の最大限度  
 Max Degree の並列化 (MDOP) の構成中に「1」に設定されている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]の[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]instance(s) をホストする、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージ ボックス データベースです。 これは、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンス レベルの設定。 この設定は、「1」の値からない変更する必要があります。 重大な悪影響を持つ「1」以外のものに変更することができます、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ストアド プロシージャとパフォーマンス。 インスタンスの並列処理の設定を変更する場合[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]で実行されている他のデータベース アプリケーションに悪影響を与えるには、 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 、インスタンスの別のインスタンスを作成する必要があります[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]をホストするため[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。  
  
 並列クエリでは、バッチ処理に最も適したは一般にし、意思決定支援ワークロード。 通常、これらは、並列で実行される、多くの短い、高速なクエリを持つトランザクション処理環境で必要はありません。 クエリのパフォーマンス低下につながるまたはでもでデッドロックが、クエリ プランを変更することもあります原因設定 MDOP をさらに、変更、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]クエリ。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ストアド プロシージャが適切な結合を提供および多くの作業を行うと、プランの変更から、クエリ オプティマイザーを保持しようとするために可能な限り、ヒントをロックします。 これらのストアド プロシージャは、クエリ オプティマイザーが可能な限り、画像から除外するようにクエリを構築することによって、一貫性のあるクエリの実行を提供します。  
  
 詳細については、Microsoft サポート技術情報の記事 899000 を参照してください。 ["BizTalk Server を構成するときに、SQL Server のインスタンスの並列処理の設定"](http://go.microsoft.com/fwlink/?LinkId=153432) (http://go.microsoft.com/fwlink/?LinkId=153432)。  
  
## <a name="sql-server-statistics-on-the-messagebox-database"></a>メッセージ ボックス データベースで SQL Server の統計情報  
 既定で、次のオプションがになっている、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージ ボックス データベースが作成されるとき。  
  
-   統計の自動作成します。  
  
-   統計の自動更新  
  
 メッセージ ボックス データベースにこれらのオプションを有効にしないでください。 「統計の自動作成」の有効化し、オプションの「統計の更新を自動」特に高負荷環境で不適切なクエリ実行の遅延が発生することができます。  
  
 さらに、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ストアド プロシージャは、完全結合とクエリに指定されたロック ヒントがあります。 これは、によって最適なクエリ プランが使用されるようにするため、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]でのクエリ[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。 分布と期待される結果のクエリがわかっているです。返される行の概数がわかっているとします。 統計情報は、通常必要ありません。  
  
 詳細については、次のサポート技術情報の記事を参照してください。  
  
-   **912262**—[「、自動統計更新オプション、自動統計の作成オプション、および並列処理の設定が、BizTalk Server BizTalkMsgBoxDB データベースをホストする SQL Server データベース インスタンスでになっている」](http://go.microsoft.com/fwlink/?LinkId=153430)(http://go.microsoft.com/fwlink/?LinkId=153430)。  
  
-   **917845**—[「するブロックが発生する、BizTalk Server で、BizTalkMsgBoxDb データベースに接続しようとすると、条件、またはその他の SQL Server の問題をデッドロック」](http://go.microsoft.com/fwlink/?LinkId=153429) (http://go.microsoft.com/fwlink/?LinkId=153429)。  
  
## <a name="changes-to-the-messagebox-database"></a>メッセージ ボックス データベースへの変更  
 メッセージ ボックス データベースは、Microsoft 以外のアプリケーションのソース コードのように処理されます。 必要がありますいない「に合わせて調整する」、メッセージ ボックス データベースを介してテーブル、インデックス、ストアド プロシージャ、およびほとんどの SQL Server データベースの設定を変更します。 詳細については、BizTalk のコア エンジンのブログ エントリを参照してください。 ["できる項目と、メッセージ ボックス データベース サーバーでは実行できません"](http://go.microsoft.com/fwlink/?LinkId=101577) (http://go.microsoft.com/fwlink/?LinkId=101577)。  
  
## <a name="default-settings-for-the-database-index-rebuilds-and-defragmentation"></a>データベースのインデックス再構築と最適化の既定の設定  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]最適化インデックスはサポートされません。 "DBCC INDEXDEFRAG"および"ALTER INDEX… REORGANIZE..." ページ ロック、ブロックが発生することができを使用してデッドロックを使用しているのではサポートされていません[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]("DBCC DBREINDEX"および"ALTER INDEX... の機能はサポートのデータベースのインデックスの再構築します。 REBUILD...")、メンテナンス期間中にのみ実行する必要がありますが、ときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]はデータを処理していません。 インデックスの再作成中に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]処理は、データがサポートされていません。  
  
 詳細については、Microsoft サポート技術情報の記事 917845 を参照してください["するブロックが発生する、BizTalk Server で、BizTalkMsgBoxDb データベースに接続しようとすると、条件、またはその他の SQL Server の問題をデッドロック"](http://go.microsoft.com/fwlink/?LinkId=153429) (http://go.microsoft.com/fwlink/?LinkId=153429)。  
  
 インデックスの断片化ができるだけ多くのパフォーマンスの問題の[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]DSS システムまたはインデックス スキャンを実行する OLTP システムであるようです。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]非常に選択的なクエリと更新プログラムおよび[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]またはインデックス スキャンのストアド プロシージャがテーブルに発生することはできません。  
  
 インデックスの断片化とワークロードの種類の詳細については、次を参照してください。 ["Microsoft SQL Server 2000 インデックスの最適化に関するベスト プラクティス"](http://go.microsoft.com/fwlink/?LinkId=101580) (http://go.microsoft.com/fwlink/?LinkId=101580)。 アーティクルから見積もり:  
  
 "図 1 に示すように、ほとんど間に違いは、ストアド プロシージャの前と、後パフォーマンスを最適化します。 これらのストアド プロシージャによって発行された基になるクエリは、データの一部が非常に選択的に処理をワークロードのパフォーマンスが悪影響を及ぼす受けません断片化したインデックス。"  
  
> [!NOTE]  
>  記事の内容にも適用[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]と[!INCLUDE[btsSQLServer2005](../includes/btssqlserver2005-md.md)]です。  
  
## <a name="see-also"></a>参照  
 [チェックリスト: SQL Server を構成します。](~/technical-guides/checklist-configuring-sql-server.md)