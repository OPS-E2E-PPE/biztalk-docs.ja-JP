---
title: SQL Server の設定を変更しないように |Microsoft Docs
description: Max Degree of Parallelism を自動作成統計の自動更新の統計、および BizTalk Server でのインデックスの再構築
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4b383bfb-c3d9-47d4-b294-f6be94302734
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60479097dc9e56c2bc0c525d0de7d7a33afccaa5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978267"
---
# <a name="sql-server-settings-that-should-not-be-changed"></a>SQL Server の設定を変更しないでください。
設定するときに[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]の運用準備手順の間に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、次の設定を変更しないでいます。  
  
## <a name="sql-server-max-degree-of-parallelism"></a>SQL Server の並列処理の最大限度  
 最大限の並列処理 (MDOP) は、構成する際に「1」に設定されて[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]の[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスをホストする、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージ ボックス データベースです。 これは、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンス レベルの設定。 この設定は、「1」の値から変更する必要があります。 「1」以外のものに変更するの大きな悪影響を及ぼすことができます、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ストアド プロシージャとパフォーマンス。 インスタンスを並列処理の設定を変更する場合[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]で実行されている他のデータベース アプリケーションに悪影響を与えるが、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスの別のインスタンスを作成する必要があります[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]専用のホスト[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。  
  
 並列クエリでは、バッチ処理に最も適したは一般にし、意思決定支援作業します。 通常では、並列で実行されている多数の短い、高速なクエリを持つトランザクション処理環境で望ましいはありません。 クエリのパフォーマンス低下につながるまたはでもデッドロックがクエリ プランを変更することもあります原因設定 MDOP をさらに、変更、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]クエリ。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ストアド プロシージャが適切な結合を提供および多くの作業を行い、プランの変更から、クエリ オプティマイザーを維持しようとするために可能な場合にヒントをロックします。 これらのストアド プロシージャは、クエリ オプティマイザーが可能な限り、画像から実行されるように、クエリを構築することによって、一貫性のあるクエリの実行を提供します。  
  
 詳細については、[KB 899000: BizTalk Server で使用される SQL Server インスタンスの並列処理の設定](https://support.microsoft.com/help/899000/the-parallelism-setting-for-the-instance-of-sql-server-when-you-config)を参照してください。  
  
## <a name="sql-server-statistics-on-the-messagebox-database"></a>メッセージ ボックス データベースで SQL Server の統計  
 次のオプションが既定でオフ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージ ボックス データベースが作成されたとき。  
  
- 統計の自動作成します。  
  
- 統計の自動更新  
  
  メッセージ ボックス データベースにこれらのオプションを有効にしないでください。 「統計の自動作成」を有効にして、オプションの「自動 update statistics」特に負荷の高い環境で望ましくないクエリ実行の遅延が発生することができます。  
  
  さらに、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ストアド プロシージャは、正確な結合とクエリに指定されたロック ヒントがあります。 これは、によって最適なクエリ プランが使用されるようにするため、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]でクエリを[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]します。 ディストリビューションと、クエリの結果を予想が呼ばれます。返される行の概数をいいます。 通常、統計情報は必要ありません。  
  
  詳細については、次のサポート技術情報の記事を参照してください。  
  
- **912262**—[「自動更新の統計オプションの自動作成統計のオプションと、BizTalk Server BizTalkMsgBoxDB データベースをホストする SQL Server データベース インスタンスで並列処理の設定がになっている」](https://support.microsoft.com/help/912262/the-auto-update-statistics-option-the-auto-create-statistics-option-an).  
  
- **917845**—[「、発生したブロックしている BizTalk Server で、BizTalkMsgBoxDb データベースに接続しようとすると、条件、またはその他の SQL Server の問題をデッドロック」](https://support.microsoft.com/help/917845/you-experience-blocking--deadlock-conditions--or-other-sql-server-issu)します。  
  
## <a name="changes-to-the-messagebox-database"></a>メッセージ ボックス データベースへの変更  
 メッセージ ボックス データベースは、Microsoft 以外のアプリケーションのソース コードのように処理されます。 つまり、する必要がありますいない「を調整する」テーブル、インデックス、ストアド プロシージャ、およびほとんどの SQL Server データベースの設定の変更を使用してメッセージ ボックス データベースです。 詳細については、BizTalk コア エンジンのブログでは、[ことを確認し、メッセージ ボックス データベース サーバーで実行できない](http://go.microsoft.com/fwlink/p/?LinkId=101577)を参照してください。  
  
## <a name="default-settings-for-the-database-index-rebuilds-and-defragmentation"></a>データベースのインデックス再構築と最適化の既定の設定  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] インデックスの最適化をサポートしません。 "DBCC INDEXDEFRAG"および"ALTER INDEX… REORGANIZE..." ページ ロックのブロックしている可能性があるとを使用したデッドロックを使用するためにサポートされていません[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ("DBCC DBREINDEX"および"ALTER INDEX... はサポートのデータベースのインデックスの再構築します。 REBUILD...")、メンテナンス期間中にのみ実行する必要がありますが、ときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]がデータを処理していません。 インデックスを再構築中に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]処理は、データがサポートされていません。  
  
 詳細については、[KB 917845:、ブロッキングが発生した BizTalk Server で、BizTalkMsgBoxDb データベースに接続しようとすると、条件、またはその他の SQL Server の問題をデッドロック"](https://support.microsoft.com/help/917845/you-experience-blocking--deadlock-conditions--or-other-sql-server-issu)を参照してください。  
  
 インデックスの断片化がないほどのパフォーマンスの問題の[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]DSS システムまたはインデックス スキャンを実行する OLTP システムであるようです。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 非常に高いクエリと更新プログラムと[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]またはインデックス スキャンのストアド プロシージャがテーブルに発生することはできません。  
  
 
## <a name="see-also"></a>参照  
 [チェックリスト: SQL Server の構成](~/technical-guides/checklist-configuring-sql-server.md)
