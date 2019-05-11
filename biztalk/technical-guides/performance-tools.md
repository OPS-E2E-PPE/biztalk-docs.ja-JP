---
title: パフォーマンス ツール |Microsoft Docs
description: BizUnit、IOMeter、オーケストレーション プロファイラー、Log Parser、LoadGen、および SQL ツールを使用して BizTalk Server パフォーマンスの問題を調査します。
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6d26c17a-3eb9-41a5-b0dc-31b974bf3d9b
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36d84117f6f8f96c4d847142105012d181349c46
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291362"
---
# <a name="performance-tools"></a>パフォーマンス ツール
このトピックでは、BizTalk Server ソリューションのパフォーマンスを評価に使用できるツールについて説明します。 このトピックで説明するツールがあるさまざまな目的です。いくつかの他のユーザーには、BizTalk Server ソリューションの特定の側面のパフォーマンスを評価する集中中には、エンド ツー エンドのパフォーマンスを評価するものです。  
 
## <a name="bizunit-and-bizunit-designer"></a>BizUnit と BizUnit デザイナー  
 BizUnit は、BizTalk ソリューションの自動テストのために設計されたフレームワークです。 BizUnit は、BizTalk Server のエンド ツー エンドのシナリオをテストするための優れたツールです。 主な目的は、BizUnit で BizTalk ソリューションの自動テストを実行する、[自動テストを実装する](../technical-guides/implementing-automated-testing.md)このガイドの「します。 参照してください[BizUnit](https://github.com/BizUnit/BizUnit)します。
  
 BizUnit デザイナーは、単体テストや分散アプリケーションをテスト システムに対して使用できるための BizUnit テスト_ケースを迅速に作成できる GUI です。 このツールは、「 [BizUnit デザイナー](http://go.microsoft.com/fwlink/?LinkID=117917)します。  
  
> [!NOTE]  
>  、Microsoft では、このツールの使用はサポートされていないと、Microsoft はこのプログラムの適合性に関する保証をいたしません。 このプログラムは、ユーザー自身の責任で使用してください。  
  
## <a name="iometer"></a>IOMeter  
 IOMeter は、ディスク I/O パフォーマンスを測定するためのオープン ソース ツールです。 参照してください[ http://www.iometer.org](http://www.iometer.org/)します。
  
> [!NOTE]  
>  、Microsoft では、このツールの使用はサポートされていないと、Microsoft はこのプログラムの適合性に関する保証をいたしません。 このプログラムは、ユーザー自身の責任で使用してください。  
  
## <a name="log-parser"></a>Log Parser  
 Log parser は強力な多目的ツールなど、イベント ログ、レジストリ、ファイル システム、およびアクティブ Windows® オペレーティング システムの主要なデータ ソースに加え、ログ ファイル、XML ファイルおよび CSV ファイルなどのテキスト ベースのデータへの汎用クエリ アクセスを提供します。Directory® します。 ダウンロード[ログ パーサー](https://www.microsoft.com/download/details.aspx?id=24659)します。
  
## <a name="microsoft-biztalk-loadgen"></a>Microsoft BizTalk LoadGen  
 BizTalk LoadGen は、BizTalk Server に対してパフォーマンス テストとストレス テストを実行するために使用負荷生成ツールです。 ダウンロード[BizTalk LoadGen 2007 ツール](https://www.microsoft.com/download/details.aspx?id=14925)します。
  
## <a name="pathping"></a>pathping  
 Pathping では、ターゲット ホストする方法の 1 つまたは複数のルーター ホップでのデータの損失についてを説明します。 これを行うには、pathping は、インターネット制御メッセージ プロトコル (ICMP) パケットをパス内の各ルーターに送信します。 Pathping.exe は、Windows 2000 Server 以降すべてのバージョンの Windows で使用できます。  
  
## <a name="performance-analysis-of-logs-pal"></a>ログ (PAL) のパフォーマンス分析  
 PAL ツールは、視覚的に重要なパフォーマンス カウンターのグラフし、これらのカウンターのしきい値を超えた場合にアラートを生成する HTML ベースのレポートの生成に使用されます。 PAL は、ソリューションのパフォーマンスを最適化するときに、適切なリソースの割り当てを容易にするために、BizTalk Server ソリューションでボトルネックを特定するための優れたツールです。  
  
 パフォーマンス分析のログ (PAL) ツールの詳細については、次を参照してください。[パフォーマンス分析のログ (PAL) ツール](https://github.com/clinthuffman/PAL)します。
  
> [!NOTE]  
>  、Microsoft では、このツールの使用はサポートされていないと、Microsoft はこのプログラムの適合性に関する保証をいたしません。 このプログラムは、ユーザー自身の責任で使用してください。  
  
## <a name="performance-monitor"></a>パフォーマンス モニター  
 パフォーマンス モニターでは、視覚的に、リアルタイムまたは履歴データを確認する方法として、組み込みの Windows パフォーマンス カウンターの表示を提供します。  
  
## <a name="relog"></a>relog  
 Relog ユーティリティでは、パフォーマンス モニターで作成されたログからパフォーマンス カウンターを抽出するために使用し、タブ区切りテキスト ファイル (TSV)、コンマ区切りのテキスト ファイル (CSV)、バイナリ ファイル、および SQL データベースなどの他の形式にデータを変換します。 このデータは、し分析することができ、Log Parser などの他のツールを使用して主要業績評価指標 (Kpi) の統計情報を生成するクエリを実行します。 
  
## <a name="visual-studio---testing-the-application"></a>Visual Studio - アプリケーションのテスト  
 Microsoft Visual Studio Ultimate および Professional の両方を定義およびテスト計画を使用して、テスト作業を管理するためにテストが含まれます。 参照してください[アプリケーションのテスト](https://docs.microsoft.com/vsts/manual-test/overview)します。
  
## <a name="visual-studio-profiling-tools"></a>Visual Studio プロファイリング ツール  
 Visual Studio プロファイリング ツールを使用すると、プロファイルのカスタム .NET コンポーネント (カスタム パイプライン コンポーネント、パイプラインやオーケストレーション、カスタム functoid によって呼び出されるヘルパー コンポーネント)。 参照してください、[プロファイリング ツールを使用したアプリケーションのパフォーマンスを分析](https://docs.microsoft.com/visualstudio/profiling/performance-explorer)します。
  
## <a name="windows-performance-analysis-tools"></a>Windows パフォーマンス分析ツール  
Windows パフォーマンス ツールが遅延プロシージャ呼び出しのさまざまなアプリケーションの開始時刻、ブートの問題を含むパフォーマンスの問題の分析用にデザインされ、中断アクティビティ (Dpc および Isr) システムの応答性の問題は、アプリケーションのリソース使用状況、および割り込みの大量発生します。  
  
参照してください[Windows パフォーマンス分析](https://docs.microsoft.com/windows-hardware/test/weg/performance-tools)します。
  
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
  
## <a name="see-also"></a>参照  
 [ボトルネックの検索と解消](../technical-guides/finding-and-eliminating-bottlenecks.md)