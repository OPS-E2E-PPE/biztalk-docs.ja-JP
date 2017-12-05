---
title: "付録 d: パフォーマンスを測定するためのツールの |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 024f4a08-f3fd-4786-8549-0da5463c0bb9
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 19953e021a2416f777d9b28c14b1eb8516c70c81
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="appendix-d-tools-for-measuring-performance"></a>付録 d: ツールのパフォーマンス測定
このトピックでは、監視し、BizTalk Server 環境のパフォーマンスを評価に使用できるいくつかのツールについて説明します。  
  
## <a name="performance-analysis-of-logs-pal-tool"></a>パフォーマンス分析のログ (PAL) のツール  
 [PAL ツール](https://github.com/clinthuffman/PAL)を視覚的に重要なは、パフォーマンス モニター カウンターおよびこれらのカウンターのしきい値を超えた場合にアラートを生成をグラフ化する HTML ベースのレポートを生成するために使用します。 PAL は、ソリューションのパフォーマンスを最適化するときに、適切なリソースの割り当てを容易にするために、BizTalk Server ソリューションのボトルネックを特定するための優れたツールです。 
  
> [!NOTE]  
>  、Microsoft では、このツールの使用はサポートされていないと、Microsoft はこのプログラムの適合性に関して保証を行いません。 このプログラムは、ユーザー自身の責任で使用してください。  
  
## <a name="performance-monitor"></a>パフォーマンス モニター  
 パフォーマンス モニターでは、リアルタイムに、または履歴データを確認する手段として、組み込みの Windows パフォーマンス カウンターを視覚的に表示できます。  
  
## <a name="log-parser"></a>ログ パーサー  
 ログ パーサーは、強力な用途の広いツールなど、イベント ログ、レジストリ、ファイル システム、およびアクティブ Windows® オペレーティング システムでキーのデータ ソースに加え、ログ ファイル、XML ファイルおよび CSV ファイルなどのテキスト ベースのデータにユニバーサル クエリ アクセスを提供します。Directory® です。 ダウンロード[ログ パーサー](https://www.microsoft.com/download/details.aspx?id=24659)です。
  
## <a name="relog"></a>Relog (英語の可能性あり)  
 Relog ユーティリティは、パフォーマンス カウンターをパフォーマンス モニターで作成されたログから抽出するために使用し、データ タブ区切りのテキスト ファイル (TSV)、コンマ区切りのテキスト ファイル (CSV)、バイナリ ファイル、および SQL データベースなど、他の形式に変換します。 このデータは、解析できますされ、ログ パーサーなど、他のツールを使用して主要業績評価指標 (Kpi) の統計を生成するクエリします。 
  
## <a name="loadgen"></a>LoadGen  
 BizTalk LoadGen 2007 は、BizTalk Server に対してパフォーマンスとストレス テストを実行するために使用負荷生成ツールです。 ダウンロード[BizTalk LoadGen 2007 ツール](https://www.microsoft.com/download/details.aspx?id=14925)です。
  
## <a name="visual-studio-team-system-load-testing"></a>Visual Studio Team System のロード テスト  
 Visual Studio Team System (VSTS) は、作成して、ロード テストの実行のためのツールを提供します。 参照してください[アプリケーションのテスト](https://docs.microsoft.com/vsts/manual-test/overview)です。
  
## <a name="bizunit"></a>BizUnit  
 BizUnit は、BizTalk Server ソリューションの自動テスト用に設計されたフレームワークです。 BizUnit は、エンド ツー エンド BizTalk Server のシナリオをテストするための優れたツールです。 参照してください[BizUnit](https://github.com/BizUnit/BizUnit)です。
  
> [!NOTE]  
>  、Microsoft では、このツールの使用はサポートされていないと、Microsoft はこのプログラムの適合性に関して保証を行いません。 このプログラムは、ユーザー自身の責任で使用してください。  
  
## <a name="iometer"></a>IOMeter  
 IOMeter は、ディスク I/O パフォーマンスの測定に使用されるオープン ソース ツールです。 参照してください[http://www.iometer.org](http://www.iometer.org/)です。
  
> [!NOTE]  
>  、Microsoft では、このツールの使用はサポートされていないと、Microsoft はこのプログラムの適合性に関して保証を行いません。 このプログラムは、ユーザー自身の責任で使用してください。  
  

## <a name="pathping"></a>Pathping  
 Pathping は、ターゲット ホストするための方法で 1 つまたは複数のルーター ホップでデータ損失の可能性に関する情報を提供します。 これを行うには、pathping は、パス内の各ルーターをインターネット制御メッセージ プロトコル (ICMP) パケットを送信します。 
  
## <a name="sql-server-tools-for-performance-monitoring-and-tuning"></a>パフォーマンス監視およびチューニング用の SQL Server ツール  
SQL Server は、SQL Server のイベントを監視するためと、物理データベース デザインをチューニングするために、いくつかのツールを提供します。 参照してください[パフォーマンス監視およびチューニング ツール](https://docs.microsoft.com/en-us/sql/relational-databases/performance/performance-monitoring-and-tuning-tools)です。 
  
### <a name="sql-profiler"></a>SQL Profiler  
 SQL Server に送信される TRANSACT-SQL ステートメントをキャプチャする Microsoft SQL Server Profiler を使用することができ、これらのステートメントからの SQL Server の結果セットです。 SQL Server は SQL Server と緊密に統合されて、SQL Server プロファイル トレースを分析からの読み取りと SQL Server データベースへの書き込み時に BizTalk Server で発生する可能性がありますのある問題を分析するのに役立てることがあります。 参照してください[SQL Server Profiler を使用して](https://docs.microsoft.com/sql/tools/sql-server-profiler/sql-server-profiler-templates-and-permissions)です。
  
> [!IMPORTANT]  
>  SQL Profiler の実行に関連付けられているかなりのオーバーヘッドがあります。 したがって SQL Profiler はテストまたは開発環境での使用に最適です。 SQL Profiler を使用して、実稼働環境のトラブルシューティングを行う、関連するオーバーヘッドのコストに注意してくださいし、それに応じて SQL Profiler の使用を制限します。  
> 
>  SQL Profiler を使用して、TRANSACT-SQL ステートメントをキャプチャする、ドライブ上にあるリモート ネットワーク共有またはその他の低速のデバイスでは、たとえば、ローカルの USB メモリ スティックではなく、ローカル ドライブに出力を生成する SQL プロファイラーを構成します。  
  
### <a name="sql-trace"></a>SQL トレース (SQL Trace)  
 SQL Server では、SQL Server データベース エンジンのインスタンスでトレースを作成する TRANSACT-SQL システム ストアド プロシージャを提供します。 これらのシステム ストアド プロシージャは SQL Server Profiler を使用する代わりに、トレースを手動で作成する独自のアプリケーション内から使用できます。 これにより、企業のニーズに合わせたカスタム アプリケーションを作成できます。 参照してください[SQL トレース](https://docs.microsoft.com/sql/relational-databases/sql-trace/sql-trace)です。 
  
> [!NOTE]  
>  SQL トレースを使用して、TRANSACT-SQL ステートメントをキャプチャする、USB フラッシュ ドライブなど、リモート ネットワーク共有またはその他の低速のデバイス上にあるドライブではなく、ローカル ドライブに出力を生成する SQL トレースを構成します。  
  
### <a name="sql-activity-monitor"></a>SQL の利用状況モニター  
SQL Server の利用状況モニターは、SQL Server プロセスおよびこれらのプロセスが現在の SQL Server インスタンスに与える影響に関する情報を提供します。 参照してください[利用状況モニター](https://docs.microsoft.com/sql/relational-databases/performance-monitor/activity-monitor)、および[する方法: 利用状況モニターを開く (SQL Server Management Studio](https://docs.microsoft.com/sql/relational-databases/performance-monitor/open-activity-monitor-sql-server-management-studio)です。 
  
### <a name="sql-server-data-collection"></a>SQL Server データの収集  
SQL Server では、取得して、複数のソースから収集されるデータの保存に使用できるデータ コレクターを提供します。 データ コレクターでは、データ コレクション コンテナーは、スコープと SQL Server を実行しているコンピューター上のデータ収集の頻度を決定するために使用することができます。 参照してください[データ コレクション](https://docs.microsoft.com/sql/relational-databases/data-collection/data-collection)です。
  
### <a name="sqlio"></a>SQLIO  
 SQLIO ツールは、特定の構成の I/O 容量を評価する Microsoft によって開発されました。 ツールの名前からわかるように、SQLIO は、SQL Server のパフォーマンス上のファイル システム I/O の影響を測定するための貴重なツールです。 ダウンロード[SQLIO](https://www.microsoft.com/download/details.aspx?id=20163)です。