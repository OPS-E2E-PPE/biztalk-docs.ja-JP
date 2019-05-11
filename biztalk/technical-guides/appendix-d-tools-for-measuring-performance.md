---
title: 付録 D:パフォーマンスを測定するためのツール |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 024f4a08-f3fd-4786-8549-0da5463c0bb9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 55e4eb3132bd953ff5cf2d525442f61b4c635582
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401393"
---
# <a name="appendix-d-tools-for-measuring-performance"></a>付録 D:パフォーマンスを測定するためのツール
このトピックでは、監視し、BizTalk Server 環境のパフォーマンスを評価に使用できるいくつかのツールについて説明します。  
  
## <a name="performance-analysis-of-logs-pal-tool"></a>パフォーマンスの分析ログ (PAL) ツール  
 [PAL ツール](https://github.com/clinthuffman/PAL)グラフ視覚的に、重要なは、パフォーマンス モニター カウンターおよびこれらのカウンターのしきい値を超えた場合にアラートを生成する HTML ベースのレポートを生成するために使用します。 PAL は、ソリューションのパフォーマンスを最適化するときに、適切なリソースの割り当てを容易にするために、BizTalk Server ソリューションでボトルネックを特定するための優れたツールです。 
  
> [!NOTE]  
>  、Microsoft では、このツールの使用はサポートされていないと、Microsoft はこのプログラムの適合性に関する保証をいたしません。 このプログラムは、ユーザー自身の責任で使用してください。  
  
## <a name="performance-monitor"></a>パフォーマンス モニター  
 パフォーマンス モニターでは、視覚的に、リアルタイムまたは履歴データを確認する方法として、組み込みの Windows パフォーマンス カウンターの表示を提供します。  
  
## <a name="log-parser"></a>Log Parser  
 Log parser は強力な多目的ツールなど、イベント ログ、レジストリ、ファイル システム、およびアクティブ Windows® オペレーティング システムの主要なデータ ソースに加え、ログ ファイル、XML ファイルおよび CSV ファイルなどのテキスト ベースのデータへの汎用クエリ アクセスを提供します。Directory® します。 ダウンロード[ログ パーサー](https://www.microsoft.com/download/details.aspx?id=24659)します。
  
## <a name="relog"></a>relog  
 Relog ユーティリティでは、パフォーマンス モニターで作成されたログからパフォーマンス カウンターを抽出するために使用し、タブ区切りテキスト ファイル (TSV)、コンマ区切りのテキスト ファイル (CSV)、バイナリ ファイル、および SQL データベースなどの他の形式にデータを変換します。 このデータは、し分析することができ、Log Parser などの他のツールを使用して主要業績評価指標 (Kpi) の統計情報を生成するクエリを実行します。 
  
## <a name="loadgen"></a>LoadGen  
 BizTalk LoadGen 2007 は、BizTalk Server に対してパフォーマンス テストとストレス テストを実行するために使用負荷生成ツールです。 ダウンロード[BizTalk LoadGen 2007 ツール](https://www.microsoft.com/download/details.aspx?id=14925)します。
  
## <a name="visual-studio-team-system-load-testing"></a>Visual Studio Team System ロード テスト  
 Visual Studio Team System (VSTS) を作成して、ロード テストを実行するためのツールを提供します。 参照してください[アプリケーションのテスト](https://docs.microsoft.com/vsts/manual-test/overview)します。
  
## <a name="bizunit"></a>BizUnit  
 BizUnit は、BizTalk Server ソリューションの自動テストのために設計されたフレームワークです。 BizUnit は、BizTalk Server のエンド ツー エンドのシナリオをテストするための優れたツールです。 参照してください[BizUnit](https://github.com/BizUnit/BizUnit)します。
  
> [!NOTE]  
>  、Microsoft では、このツールの使用はサポートされていないと、Microsoft はこのプログラムの適合性に関する保証をいたしません。 このプログラムは、ユーザー自身の責任で使用してください。  
  
## <a name="iometer"></a>IOMeter  
 IOMeter は、ディスク I/O パフォーマンスを測定するためのオープン ソース ツールです。 参照してください[ http://www.iometer.org](http://www.iometer.org/)します。
  
> [!NOTE]  
>  、Microsoft では、このツールの使用はサポートされていないと、Microsoft はこのプログラムの適合性に関する保証をいたしません。 このプログラムは、ユーザー自身の責任で使用してください。  
  

## <a name="pathping"></a>pathping  
 Pathping では、ターゲット ホストする方法の 1 つまたは複数のルーター ホップでのデータの損失についてを説明します。 これを行うには、pathping は、インターネット制御メッセージ プロトコル (ICMP) パケットをパス内の各ルーターに送信します。 
  
## <a name="sql-server-tools-for-performance-monitoring-and-tuning"></a>パフォーマンスの監視とチューニングの SQL Server ツール  
SQL Server は、SQL Server のイベントの監視と物理データベース デザインをチューニングするためのいくつかのツールを提供します。 参照してください[パフォーマンス監視およびチューニング ツール](https://docs.microsoft.com/sql/relational-databases/performance/performance-monitoring-and-tuning-tools)します。 
  
### <a name="sql-profiler"></a>SQL Profiler  
 Microsoft SQL Server Profiler は、SQL Server に送信される TRANSACT-SQL ステートメントをキャプチャするために使用でき、これらのステートメントから SQL Server の結果を設定します。 SQL Server は SQL Server で密接に統合されているので、SQL Server プロファイル トレースの分析から読み取って SQL Server データベースへの書き込み時に BizTalk Server で発生する可能性のある問題を分析するための便利なツールを使用できます。 参照してください[SQL Server Profiler を使用して](https://docs.microsoft.com/sql/tools/sql-server-profiler/sql-server-profiler-templates-and-permissions)します。
  
> [!IMPORTANT]  
>  SQL Profiler の実行に関連付けられているかなりのオーバーヘッドがあります。 そのため SQL Profiler は、テストまたは開発環境で使用するために最適です。 SQL Profiler を使用して、運用環境のトラブルシューティングを行う場合、関連するオーバーヘッド コストを認識しそれに応じて SQL Profiler の使用を制限します。  
> 
>  SQL Profiler を使用して、TRANSACT-SQL ステートメントをキャプチャする、ドライブ上にあるリモート ネットワーク共有またはその他の低速のデバイスでは、たとえば、ローカルの USB メモリ スティックではなく、ローカル ドライブへの出力を生成する SQL Profiler を構成します。  
  
### <a name="sql-trace"></a>SQL トレース (SQL Trace)  
 SQL Server では、トレース、SQL Server データベース エンジンのインスタンスを作成する TRANSACT-SQL システム ストアド プロシージャを提供します。 これらのシステム ストアド プロシージャは SQL Server Profiler を使用する代わりに、トレースを手動で作成するユーザー独自のアプリケーションから使用できます。 これにより、企業のニーズに合わせたカスタム アプリケーションを作成できます。 参照してください[SQL トレース](https://docs.microsoft.com/sql/relational-databases/sql-trace/sql-trace)します。 
  
> [!NOTE]  
>  SQL トレースを使用して、TRANSACT-SQL ステートメントをキャプチャする、USB フラッシュ ドライブなど、リモート ネットワーク共有またはその他の低速のデバイスに配置されているドライブではなく、ローカル ドライブへの出力を生成する SQL トレースを構成します。  
  
### <a name="sql-activity-monitor"></a>SQL の利用状況モニター  
SQL Server の利用状況モニターは、SQL Server のプロセスおよびこれらのプロセスが現在の SQL Server インスタンスに与える影響についての情報を提供します。 参照してください[の利用状況モニター](https://docs.microsoft.com/sql/relational-databases/performance-monitor/activity-monitor)、および[方法。利用状況モニターを開く (SQL Server Management Studio](https://docs.microsoft.com/sql/relational-databases/performance-monitor/open-activity-monitor-sql-server-management-studio)します。 
  
### <a name="sql-server-data-collection"></a>SQL Server データの収集  
SQL Server を取得し、複数のソースから収集されるデータの保存に使用できるデータ コレクターを提供します。 データ コレクターでは、範囲と SQL Server を実行しているコンピューター上のデータ収集の頻度を決定するためのデータのコレクション コンテナーを使用することができます。 参照してください[データ コレクション](https://docs.microsoft.com/sql/relational-databases/data-collection/data-collection)します。
  
### <a name="sqlio"></a>SQLIO  
 SQLIO ツールは、特定の構成の I/O 容量を評価する Microsoft によって開発されました。 ツールの名前が示すように、SQLIO、SQL Server のパフォーマンス上のファイル システム I/O の影響を測定するため貴重なツールです。 ダウンロード[SQLIO](https://www.microsoft.com/download/details.aspx?id=20163)します。