---
title: "パフォーマンス ツール |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6d26c17a-3eb9-41a5-b0dc-31b974bf3d9b
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c53894ca4dcf1b1541c020e14a83542a7ce56d56
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="performance-tools"></a>パフォーマンス ツール
このトピックでは、BizTalk Server ソリューションのパフォーマンスの評価に使用できるツールについて説明します。 このトピックで説明するツールがあるさまざまな目的です。他のユーザーに、BizTalk Server ソリューションの特定の側面のパフォーマンスを評価する重点中に、エンド ツー エンドのパフォーマンスを評価中に設計されています。  
  
## <a name="biztalk-server-orchestration-profiler"></a>BizTalk Server オーケストレーション プロファイラー  
 BizTalk Server オーケストレーション プロファイラーでは、オーケストレーションが一定の時間の追跡データを表示するために使用し、パフォーマンスのボトルネックをオーケストレーションに存在する場所を決定するため便利です。  
  
 BizTalk Server オーケストレーションのプロファイラーの詳細については、次を参照してください。 [BizTalk Server 2006 オーケストレーション プロファイラー](http://go.microsoft.com/fwlink/?LinkId=102209) (http://go.microsoft.com/fwlink/?LinkId=102209)。  
  
> [!NOTE]  
>  、Microsoft では、このツールの使用はサポートされていないと、Microsoft はこのプログラムの適合性に関して保証を行いません。 このプログラムは、ユーザー自身の責任で使用してください。 また、このユーティリティは BizTalk Server 2006 を使用するように設計されましたし、したがってが機能しない BizTalk Server 2010 で期待どおりに注意してください。  
  
## <a name="bizunit-30-and-bizunit-designer"></a>BizUnit 3.0 と BizUnit デザイナー  
 BizUnit は、BizTalk ソリューションの自動テスト用に設計されたフレームワークです。 BizUnit は、エンド ツー エンド BizTalk Server のシナリオをテストするための優れたツールです。 主な目的は、BizUnit による BizTalk ソリューションの自動テストを実行して、[自動テストを実装する](../technical-guides/implementing-automated-testing.md)このガイドの「します。 BizUnit 3.0 の詳細については、次を参照してください。 [BizUnit - 自動テスト分散システムのためのフレームワーク](http://go.microsoft.com/fwlink/?LinkID=85168)(http://go.microsoft.com/fwlink/?LinkID=85168)。  
  
 BizUnit デザイナーは、単体テストまたはシステム テストの分散アプリケーションのために使用するための BizUnit テスト_ケースを迅速に作成できる GUI です。 このツールはで利用可能な[BizUnit デザイナー](http://go.microsoft.com/fwlink/?LinkID=117917) (http://go.microsoft.com/fwlink/?LinkID=117917)。  
  
> [!IMPORTANT]  
>  このガイドでは、生成されたテスト_ケースの作成時点 BizUnit デザイナーによって 1.x のみと互換性のある BizUnit 2.x です。  
  
> [!NOTE]  
>  、Microsoft では、このツールの使用はサポートされていないと、Microsoft はこのプログラムの適合性に関して保証を行いません。 このプログラムは、ユーザー自身の責任で使用してください。  
  
## <a name="iometer"></a>IOMeter  
 IOMeter は、ディスク I/O パフォーマンスの測定に使用されるオープン ソース ツールです。 IOMeter の詳細については、次を参照してください。 [http://www.iometer.org](http://go.microsoft.com/fwlink/?LinkId=122412) (http://go.microsoft.com/fwlink/?LinkId=122412)。  
  
> [!NOTE]  
>  、Microsoft では、このツールの使用はサポートされていないと、Microsoft はこのプログラムの適合性に関して保証を行いません。 このプログラムは、ユーザー自身の責任で使用してください。  
  
## <a name="log-parser"></a>ログ パーサー  
 ログ パーサーは、強力な用途の広いツールなど、イベント ログ、レジストリ、ファイル システム、およびアクティブ Windows® オペレーティング システムでキーのデータ ソースに加え、ログ ファイル、XML ファイルおよび CSV ファイルなどのテキスト ベースのデータにユニバーサル クエリ アクセスを提供します。Directory® です。 ログ パーサーはダウンロード[Log Parser 2.2](http://go.microsoft.com/fwlink/?LinkID=100882) (http://go.microsoft.com/fwlink/?LinkID=100882)。  
  
## <a name="microsoft-biztalk-loadgen-2007"></a>Microsoft BizTalk LoadGen 2007  
 BizTalk LoadGen 2007 は、パフォーマンスとストレス テストの実行に使用される負荷生成ツール[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]です。  
  
 Microsoft BizTalk LoadGen 2007 ツールの詳細については、次を参照してください。 [Microsoft BizTalk LoadGen 2007 ツール](http://go.microsoft.com/fwlink/?LinkId=59841)(http://go.microsoft.com/fwlink/?LinkId=59841)。  
  
## <a name="pathping"></a>Pathping  
 Pathping は、ターゲット ホストするための方法で 1 つまたは複数のルーター ホップでデータ損失の可能性に関する情報を提供します。 これを行うには、pathping は、パス内の各ルーターをインターネット制御メッセージ プロトコル (ICMP) パケットを送信します。 Pathping.exe は、Windows 2000 Server 以来はすべてのバージョンの Windows で使用できます。  
  
## <a name="performance-analysis-of-logs-pal"></a>ログ (PAL) のパフォーマンス分析  
 PAL ツールを使用して、視覚的に重要なパフォーマンス カウンターをグラフ化し、これらのカウンターのしきい値を超えた場合にアラートを生成する HTML ベースのレポートを生成します。 PAL は、ソリューションのパフォーマンスを最適化するときに、適切なリソースの割り当てを容易にするために、BizTalk Server ソリューションのボトルネックを特定するための優れたツールです。  
  
 パフォーマンス分析のログ (PAL) ツールの詳細については、次を参照してください。[パフォーマンス分析のログ (PAL) ツール](http://go.microsoft.com/fwlink/?LinkID=98098)(http://go.microsoft.com/fwlink/?LinkID=98098)。  
  
> [!NOTE]  
>  、Microsoft では、このツールの使用はサポートされていないと、Microsoft はこのプログラムの適合性に関して保証を行いません。 このプログラムは、ユーザー自身の責任で使用してください。  
  
## <a name="performance-monitor"></a>パフォーマンス モニター  
 パフォーマンス モニターでは、リアルタイムに、または履歴データを確認する手段として、組み込みの Windows パフォーマンス カウンターを視覚的に表示できます。  
  
## <a name="relog"></a>Relog (英語の可能性あり)  
 Relog ユーティリティは、パフォーマンス カウンターをパフォーマンス モニターで作成されたログから抽出するために使用し、データ タブ区切りのテキスト ファイル (TSV)、コンマ区切りのテキスト ファイル (CSV)、バイナリ ファイル、および SQL データベースなど、他の形式に変換します。 このデータは、解析できますされ、ログ パーサーなど、他のツールを使用して主要業績評価指標 (Kpi) の統計を生成するクエリします。 Relog ユーティリティが付属して[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]およびそれ以降のバージョン。  
  
## <a name="visual-studio-2010---testing-the-application"></a>Visual Studio 2010 - アプリケーションのテスト  
 Microsoft Visual Studio 2010 Ultimate、Visual Studio テスト Professional 2010 は、Microsoft テスト マネージャーと呼ばれる新しいアプリケーションを定義およびテスト計画によるテスト作業を管理するためが追加されました。 ロード テストの操作の詳細については、次を参照してください。[アプリケーションのテスト](http://go.microsoft.com/fwlink/?LinkID=205342)(http://go.microsoft.com/fwlink/?LinkID=205342)。  
  
## <a name="visual-studio-2010-profiling-tools"></a>Visual Studio 2010 のプロファイリング ツール  
 Visual Studio プロファイリング ツールでは、カスタム .NET をプロファイルすることができます (カスタム パイプライン コンポーネント、パイプラインまたはオーケストレーション、カスタム functoid によって呼び出されるヘルパー コンポーネント) のコンポーネントです。 詳細については、Visual Studio プロファイリング ツールの「[プロファイリング ツールを使用してアプリケーションのパフォーマンスを分析する](http://go.microsoft.com/fwlink/?LinkID=210555)(http://go.microsoft.com/fwlink/?LinkID=210555).  
  
## <a name="windows-performance-analysis-tools"></a>Windows パフォーマンス分析ツール  
 Windows パフォーマンス ツールは、遅延プロシージャ呼び出しの広範なアプリケーションの開始時刻、ブートの問題を含めてパフォーマンス問題の分析用にデザインされたされ、アクティビティ (dpc の処理と Isr)、システムの応答を中断の問題は、アプリケーションのリソース使用状況、および割り込みストームが発生します。  
  
 Windows パフォーマンス分析ツールの詳細については、次を参照してください。 [Windows パフォーマンス分析](http://go.microsoft.com/fwlink/?LinkId=139763)(http://go.microsoft.com/fwlink/?LinkId=139763)。  
  
## <a name="sql-server-tools-for-performance-monitoring-and-tuning"></a>パフォーマンス監視およびチューニング用の SQL Server ツール  
 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]内のイベントを監視するためのいくつかのツールを提供[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]物理データベース デザインをチューニングします。 これらのツールに記載されて、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]オンライン ブックの「[のパフォーマンスの監視およびチューニング ツール](http://go.microsoft.com/fwlink/?LinkId=146357)(http://go.microsoft.com/fwlink/?LinkId=146357). 特定のツールの使用に関する情報[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]パフォーマンスの監視とチューニング以下に示します。  
  
### <a name="sql-profiler"></a>SQL Profiler  
 Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Profiler を使用すると、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] に送信される Transact-SQL ステートメントや、これらのステートメントで返される [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] の結果セットを取得できます。 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]と密接に連携[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]の分析、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]プロファイル トレースで発生する可能性のある問題を分析するための便利なツールを指定できます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]からの読み取りと書き込み時[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベース。 使用する方法については[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]プロファイラーを参照してください、[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]オンライン ブックの「[を使用して SQL Server Profiler](http://go.microsoft.com/fwlink/?linkid=104423) (http://go.microsoft.com/fwlink/?linkid=104423)。  
  
> [!IMPORTANT]  
>  SQL Profiler の実行に関連付けられているかなりのオーバーヘッドがあります。 したがって SQL Profiler はテストまたは開発環境での使用に最適です。 SQL Profiler を使用して、実稼働環境のトラブルシューティングを行う、関連するオーバーヘッドのコストに注意してくださいし、それに応じて SQL Profiler の使用を制限します。  
  
> [!NOTE]  
>  SQL Profiler を使用して、TRANSACT-SQL ステートメントをキャプチャする、ドライブ上にあるリモート ネットワーク共有またはその他の低速のデバイスでは、たとえば、ローカルの USB メモリ スティックではなく、ローカル ドライブに出力を生成する SQL プロファイラーを構成します。  
  
### <a name="sql-trace"></a>SQL トレース (SQL Trace)  
 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]SQL Server データベース エンジンのインスタンスでトレースを作成する TRANSACT-SQL システム ストアド プロシージャを提供します。 これらのシステム ストアド プロシージャは SQL Server Profiler を使用する代わりに、トレースを手動で作成する独自のアプリケーション内から使用できます。 これにより、企業のニーズに合わせたカスタム アプリケーションを作成できます。 SQL トレースの使用の詳細については、次を参照してください。、[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]オンライン ブックの「 [SQL トレースの概要](http://go.microsoft.com/fwlink/?LinkId=146354)(http://go.microsoft.com/fwlink/?LinkId=146354)。  
  
> [!NOTE]  
>  SQL トレースを使用して、TRANSACT-SQL ステートメントをキャプチャする、USB フラッシュ ドライブなど、リモート ネットワーク共有またはその他の低速のデバイス上にあるドライブではなく、ローカル ドライブに出力を生成する SQL トレースを構成します。  
  
### <a name="sql-activity-monitor"></a>SQL の利用状況モニター  
 [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]利用状況モニターに関する情報を提供する[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]プロセスおよびこれらのプロセスの現在のインスタンスに与える影響[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]です。 詳細については[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]の利用状況モニターを参照してください、[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]オンライン ブックの「[利用状況モニター](http://go.microsoft.com/fwlink/?LinkId=146355) (http://go.microsoft.com/fwlink/?LinkId=146355). 利用状況モニターを開く方法について[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Management Studio を参照してください、[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]オンライン ブックの「[する方法: 利用状況モニターを開く」(SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=135094) (http://go.microsoft.com/fwlink/?LinkId=135094).  
  
### <a name="sql-server-2008-r2-data-collection"></a>SQL Server 2008 R2 のデータの収集  
 [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] には、複数のソースから集めたデータを取得して保存するために使用できるデータ コレクターがあります。 データ コレクターでは、データ コレクション コンテナーを使用して、[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] を実行しているコンピューターでのデータ コレクションの範囲と頻度を決定できます。 実装の詳細については[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]データ コレクションを参照してください、[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]オンライン ブックの「[データ コレクション](http://go.microsoft.com/fwlink/?LinkId=146356)(http://go.microsoft.com/fwlink/?LinkId=146356)。  
  
### <a name="sqlio"></a>SQLIO  
 SQLIO ツールは、特定の構成の I/O 容量を評価する Microsoft によって開発されました。 SQLIO でファイル システム I/O の影響を測定するための重要なツールは、ツールの名前からわかるように、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]パフォーマンス。 ダウンロードできます SQLIO [SQLIO ディスク サブシステムのベンチマーク ツール](http://go.microsoft.com/fwlink/?LinkId=115176)(http://go.microsoft.com/fwlink/?LinkId=115176)。  
  
## <a name="see-also"></a>参照  
 [検索して、ボトルネックを解消します。](../technical-guides/finding-and-eliminating-bottlenecks.md)