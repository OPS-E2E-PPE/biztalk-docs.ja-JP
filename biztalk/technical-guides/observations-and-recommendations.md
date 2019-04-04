---
title: 所見と推奨事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 88289080-1a59-4ffc-a0b2-312ec21940c2
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf134382be6086a1a3ab96fa649fa6cbb41d9bad
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980075"
---
# <a name="observations-and-recommendations"></a>所見と推奨事項
## <a name="test-results-summary"></a>テスト結果の概要  
 メッセージングのみのシナリオの結果が発生する ~ 1 日あたり 109,382,400 メッセージ。 オーケストレーションのシナリオでは、結果は、BizTalk Server を実行している 1 台のコンピューターが 1 日あたり最大 58,752,000 のメッセージを処理できることを示します。 これらの結果は、多くの BizTalk Server ソリューションの展開されている通常のエンタープライズ クラスのハードウェアを使用してサンド ボックス環境に達成されました。 そのため、これらの結果を示すその BizTalk Server のパフォーマンスの種類は、カスタム コードなしで実現できます。 顧客向けのソリューションには、BizTalk アイテムを独自に開発した、多くの場合が含まれる多くの場合、パフォーマンスに影響を及ぼしますがな処理要件をこれが向上します。 このガイドでのアドバイスに従って、特に[BizTalk Server アプリケーションの最適化](../technical-guides/optimizing-biztalk-server-applications.md)セクションで、成果物を最小限に抑えることができます独自に開発した BizTalk Server の実装による影響します。  
  
 次の表は、このパフォーマンス評価のためのテスト結果の概要を示します。  
  
|シナリオ|メッセージング (BizTalk KPI: 1 秒あたりに処理されたドキュメント)|メッセージング (SQL KPI – SQL プロセッサ使用率)|メッセージング遅延 (秒)|オーケストレーション (BizTalk KPI: 1 秒あたりに処理されたドキュメント)|オーケストレーション (SQL KPI – SQL プロセッサ使用率)|オーケストレーションの待機時間 (秒)|  
|--------------|----------------------------------------------------------------|-------------------------------------------------------|-----------------------------------|--------------------------------------------------------------------|-----------------------------------------------------------|---------------------------------------|  
|1 つのメッセージ ボックス データベース 1 の BizTalk Server コンピューター|1 秒あたりに処理された 1266 のドキュメント|SQL の CPU 使用率が 59%|0.06|1 秒あたりに処理された 680 のドキュメント|66.5 SQL の CPU 使用率 %|0.067|  
|1 つのメッセージ ボックス データベース 2 の BizTalk Server コンピューター|1 秒あたりに処理された 1267 のドキュメント|59.8 SQL の CPU 使用率 %|0.057|1 秒あたりに処理された 686 のドキュメント|68.5 SQL の CPU 使用率 %|0.067|  
|3 つのメッセージ ボックス データベース 1 の BizTalk Server コンピューター|1 秒あたりに処理された 2102 のドキュメント|SQL の CPU 使用率が 41%|0.077|1 秒あたりに処理された 974 のドキュメント|SQL の CPU 使用率が 48%|0.11|  
|3 つのメッセージ ボックス データベース 2 の BizTalk Server コンピューター|1 秒あたりに処理された 2285 のドキュメント|58 SQL CPU 使用率|0.041|1 秒あたりに処理された 1065 のドキュメント|SQL の CPU 使用率の 65%|0..69|  
|4 つのメッセージ ボックス 1 の BizTalk Server コンピューター|1 秒あたりに処理された 2125 のドキュメント|SQL の CPU 使用率が 30%|0.078|1 秒あたりに処理された 979 のドキュメント|SQL の CPU 使用率の 37%|0.095|  
|4 つのメッセージ ボックス 2 の BizTalk Server コンピューター|1 秒あたりに処理された 2790 のドキュメント|SQL の CPU 使用率が 50%|0.052|1 秒あたりに処理された 1487 のドキュメント|SQL CPU の使用率を 63%|0.15|  
|4 つのメッセージ ボックス 3 の BizTalk Server コンピューター|1 秒あたりに処理された 2656 のドキュメント|58 SQL CPU 使用率|0.074|1 秒あたりに処理された 1388 のドキュメント|SQL の CPU 使用率の 65%|0.15|  
  
## <a name="comparison-of-performance-statistics-with-biztalk-server-2009"></a>BizTalk Server 2009 と共にパフォーマンス統計情報の比較  
 次の表では、BizTalk Server 2009 および BizTalk Server 2010 との間のパフォーマンス統計情報の比較を示します。 この表に示す BizTalk Server 2009 のパフォーマンス統計情報は BizTalk Server 2009 のパフォーマンスおよび最適化ガイドです。  
  
|シナリオ|BizTalk Server 2009<br /> 最大持続可能なスループット (MST) メッセージ/秒|BizTalk Server 2009<br />必要な BizTalk サーバーの数|BizTalk Server 2010<br />最大持続可能なスループット (MST) メッセージ/秒|BizTalk Server 2010<br />必要な BizTalk サーバーの数|BizTalk Server 2009 から BizTalk Server 2010 差 (%)|  
|--------------|----------------------------------------------------------------------------|-----------------------------------------------------------|---------------------------------------------------------------------------|-----------------------------------------------------------|---------------------------------------------------------------|  
|メッセージング - 単一のメッセージ ボックス|1291|2|1266|1|98.06%|  
|オーケストレーションの単一のメッセージ ボックス|676|2|680|1|100.59%|  
|メッセージング - 3 つのメッセージ ボックス|2103|3|2285|2 (1 BTS で 2102/秒)|108.65%|  
|メッセージング - 4 のメッセージ ボックス|適用なし|適用なし|2790|2|適用なし|  
|オーケストレーションに 3 つのメッセージ ボックス|1005|4|1065|2 (1 BTS に 974/秒)|105.97%|  
|オーケストレーションの 4 つのメッセージ ボックス|適用なし|適用なし|1487|2|適用なし|  
  
 このラボ環境で、4 つのメッセージ ボックス データベースを使用する場合、最大持続可能スループットの結果は次のとおりです。  
  
- メッセージング シナリオでは、1 秒あたりの 2790 ドキュメント。  
  
- オーケストレーションでは、1 秒あたりの 1487 ドキュメント。  
  
  **メッセージの考慮事項**中に BizTalk Server にメッセージのサイズに制限はありません、2 KB のメッセージのみを使用する BizTalk Server 2010 のテストを実行および使用する WCF アダプターの種類が、Wcf-nettcp アダプター。 これには、BizTalk Server 2009 のパフォーマンス最適化ガイドのテストで使用されるメッセージ サイズとアダプターの種類と一致します。  
  
  パフォーマンス向上のため、ドライバーは次のとおりです。  
  
1.  **ハードウェアの進歩により**-ラボで使用される SQL Server コンピューターが 4 CPU、クアッド コア (16 コア)、@ 2.40 GHz Intel Xeon E7330 します。 2009 テストでは、4 CPU、クアッドコア (16 コア)、Intel Xeon 2.4 GHz 使用されました。  
  
     ラボで使用する BizTalk Server コンピューターは、2 個の CPU、クアッド コア (8 コア)、Nehalem ハイパー スレッド (16 論理コア)、Intel Xeon X @ 2.93 GHz 5570 をでした。 2009 テストでは、2 個の CPU、クアッド コア (8 コア)、Intel Xeon 2.33 GHz 使用されました。  
  
2.  **SQL Server エンジンの改善**-2009 年に、テストは、基になるデータベース プラットフォームとして SQL Server 2008 R2 で実行されたテストの結果は SQL Server 2008、に対して実行されました。  
  
## <a name="recommendations-for-scaling-the-biztalk-server-and-sql-server-tiers"></a>BizTalk Server と SQL Server 層のスケーリングの推奨事項  
 これらの結果に、BizTalk Server 製品チームでは、1 台の BizTalk Server コンピューターと 1 つの SQL Server コンピューターをサポートできること 109 通を超えるメッセージ メッセージング シナリオおよび 58 件のオーケストレーションで、24 時間の期間を示すことでした。 この環境で使用可能な最適な構成を BizTalk Server と SQL の層をスケールすることによって 1 日で、128 を超えるオーケストレーション over241, 000, 000 のメッセージを処理できませんでした。 結果は、多くの企業で展開されているハードウェアのクラスを使用して、サンド ボックス環境で実行されました。 前述のように、これらの数値は、カスタム コードはありませんし、最適化された環境で実現可能な BizTalk Server の現実的なパフォーマンスを表します。  ハードウェアを追加したことができます、さらに優れたパフォーマンスが達成されています。 多くの場合、顧客のソリューションには、追加の処理の要件、そのリソースの使用率の増加と全体的なパフォーマンスをさらに減らすことが発生した、独自に開発した BizTalk アイテムが含まれます。 ただしでの推奨事項では特に、このガイドで説明されているアドバイス[BizTalk Server アプリケーションの最適化](../technical-guides/optimizing-biztalk-server-applications.md)、この影響を最小限に抑えることができます。  
  
 結果は、ことは、メッセージ ボックス SQL Server コンピューターがボトルネックでない場合に、効果的なスケール アウト戦略にはスケール アウトの BizTalk Server コンピューターの数を示します。 パフォーマンスの原因となった、結果を示す BizTalk Server コンピューターを追加するになる非効率的なスケール アウト手法で、メッセージ ボックス データベース内の共有テーブルでの競合ポイントが発生したことを観察しましたので、特定時点より後減少します。 BizTalk サーバー グループが 1 つのメッセージ ボックス データベースから取得できる結果を最大化するで説明されている最適化を実行する必要があります[データベースのパフォーマンスの最適化](../technical-guides/optimizing-database-performance.md)します。 具体的には、SQL Server の記憶域に対して高速記憶域サブシステムを使用して、メッセージ ボックス データベースのファイルを格納する SQL Server で使用する論理ディスクをできるだけ短時間で応答することを確認する必要があります。 許容可能な読み取り/書き込みのパフォーマンスを測定するための一般的に使用されるしきい値は 15 ミリ秒です。通常これは、平均で測定されます。ディスク読み取り秒数と平均論理ディスクのパフォーマンス オブジェクトの下にあるディスク書き込み秒数のカウンターです。 メッセージ ボックス データベースをホストする SQL Server コンピューターには、すべての利用可能な最適化が適用されたら、追加のメッセージ ボックス データベースを追加できます。 プライマリ メッセージ ボックス データベースに適用されている同じ最適化手法は、セカンダリ データベースにも適用する必要があります。 ガイドラインに従うことをお勧めします。[スケール アウト SQL Server 層](http://go.microsoft.com/fwlink/?LinkID=158075)(http://go.microsoft.com/fwlink/?LinkID=158075) 、BizTalk Server のドキュメントにします。  
  
 最適な結果を得るためには、全体のハードウェアおよびソフトウェア スタックは適切な品質である必要があるし、も正しく構成されています。 最初に、適切な高品質なハードウェアを購入を含む、する必要がありますが、ギガビット ネットワーク、高速ストレージ (SAN または 15 K ローカル SQL ディスク) に限定されませんし、最新のコンピューターを複数のコア CPU ごとの複数の Cpu を持ちます。 SQL Server コンピューターは、BizTalk Server のみ処理を専用必要があります。 1 台の SQL Server コンピューターを実行するときに、BizTalk メッセージ ボックスのいずれかとその他のすべてのデータベースのいずれか、SQL の 2 つのインスタンスを作成をお勧めします。 これにより、メッセージ ボックス データベースのパフォーマンスを最適化用に構成するインスタンス全体の設定ができます。 推奨されている最適化[のパフォーマンスの最適化](../technical-guides/optimizing-performance.md)を適用する次の順序では、ステップ バイ ステップ:[オペレーティング システムのパフォーマンスの最適化](../technical-guides/optimizing-operating-system-performance.md)、[ネットワークの最適化パフォーマンス](../technical-guides/optimizing-network-performance.md)、[事前構成データベース Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)、[構成後のデータベース Optimizations2](../technical-guides/post-configuration-database-optimizations2.md)と[一般的な BizTalk ServerOptimizations1](../technical-guides/general-biztalk-server-optimizations1.md)します。 メッセージ ボックス データベースの専用のファイル グループを作成して、SAN Lun にわたってこれらの割り当て」の説明に従って[、Databases2 のファイル グループを最適化する](../technical-guides/optimizing-filegroups-for-the-databases2.md)、に応じて大幅なパフォーマンスの向上を提供することができます、SAN の構成と LUN のレイアウト。  
  
 BizTalk Server または SQL の層をスケールする方法を効率的に特定するには、お勧めするロード テストの実際の運用データを近似するメッセージを使用して実行します。 BizTalk Server 層をスケールする前に SQL Server がしないように既にボトルネックで推奨している[SQL Server のパフォーマンスの監視](../technical-guides/monitoring-sql-server-performance.md)します。 SQL Server で、ボトルネックになっている、BizTalk Server コンピューター上の CPU ヘッドルームがある場合は、ホスト インスタンスのレイアウトを変更することによってスループットを向上させることができます。 4 または 5 つ主要業績評価指標 (Kpi)、すべてのテスト実行の大まかな比較のポイントとして使用されるを確立するために重要です。 このアドバイスは、次の特定の変更は、ソリューションの全体的なパフォーマンスを低下するかどうかをすばやく計測することができます。  
  
 SQL Server 層を拡大する前に適用での最適化のすべて[データベースのパフォーマンスの最適化](../technical-guides/optimizing-database-performance.md)します。 気付きましたが、メッセージ ボックス データベースのディスク記憶域構成を顧客パフォーマンス ラボの中で、でき、TempDb の各データベースで特に以上 30% スループットの向上。 複数のメッセージ ボックス データベースをスケーリングして、3 つおよび 4 つのメッセージ ボックス データベースは、1 つのメッセージ ボックス データベースから 2 つのメッセージ ボックス データベースをスケール アウトするほとんどのパフォーマンス上の利点があるため、使用されました。 スケール アウトは、BizTalk Server メッセージ ボックスの詳細については、[スケール アウト SQL Server 層](http://go.microsoft.com/fwlink/?LinkID=158075)(http://go.microsoft.com/fwlink/?LinkID=158075) 、BizTalk Server のドキュメントにを参照してください。  
  
## <a name="implemented-optimizations"></a>実装の最適化  
 このセクションでは、ラボ テストのシナリオに適用されたすべての最適化のチェックリストを提供します。  
  
> [!NOTE]  
>  実稼働環境内でこれらを適用する前に、変更管理手順に従ってテストする必要があります。  
  
 体系的な管理された方法で最適化を適用する: 一連の最適化を適用すると、影響をテストし-最大のパフォーマンス上のメリットになります。 最適化を適用する最適化処理の影響を定期的にテストせず実際に可能性があります、ソリューションのパフォーマンスが低下します。  
  
### <a name="checklists-of-optimizations-applied"></a>適用される最適化のチェックリスト  
 **プラットフォームとネットワークの最適化**  
  
|Optimization|リファレンス|  
|------------------|---------------|  
|BIOS: は、パフォーマンスの設定を構成します。|[オペレーティング システムのパフォーマンスの最適化](../technical-guides/optimizing-operating-system-performance.md)|  
|SQL Server のファイルのリアルタイム スキャンを無効にします。|[オペレーティング システムのパフォーマンスの最適化](../technical-guides/optimizing-operating-system-performance.md)|  
|「高パフォーマンス」を有効にするすべての BizTalk Server と SQL Server コンピューターの電源プランします。|[オペレーティング システムのパフォーマンスを向上するための一般的なガイドライン](../technical-guides/general-guidelines-for-improving-operating-system-performance.md)|  
|すべての BizTalk Server と SQL Server のコンピューターでウイルス対策ソフトウェアを無効にします。|[オペレーティング システムのパフォーマンスを向上するための一般的なガイドライン](../technical-guides/general-guidelines-for-improving-operating-system-performance.md)|  
  
 **SQL Server の最適化: 全般**  
  
|Optimization|リファレンス|  
|------------------|---------------|  
|NTFS ファイル アロケーション ユニットは、64 KB に設定します。|[データベースの事前構成 Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
|SQL Server 2008 R2 をインストールします。|[データベースの事前構成 Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
|SQL Server 2008 R2 のデータ コレクター/ウェアハウスを構成します。|[データベースの事前構成 Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
|SQL Server サービス アカウントに適切な Windows 権限が拡張されていることを確認します。|SQL Server 2008 R2:[サービス アカウントに、Windows セットアップ](http://go.microsoft.com/fwlink/?LinkID=132144)(http://go.microsoft.com/fwlink/?LinkID=132144)|  
|SQL Server の最小値と最大サーバー メモリを設定します。|[データベースの事前構成 Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
|SQL Server に使用されるアカウントに Windows Lock Pages の In Memory 特権を付与します。|[データベースの事前構成 Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
|複数のデータ ファイルのサイズを適切なサイズに BizTalk Server データベースを事前.|[構成後のデータベース Optimizations2](../technical-guides/post-configuration-database-optimizations2.md)|  
|SQL Server クライアント プロトコルを構成します。|[SQL Server のトラブルシューティング](http://go.microsoft.com/fwlink/?LinkID=154250)(http://go.microsoft.com/fwlink/?LinkID=154250)|  
|Tempdb データベースを BizTalk Server で使用される各 SQL Server インスタンスに等しいサイズの複数のデータ ファイルに分割します。|[データベースの事前構成 Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
|SQL Server プロセスの関係を手動で設定します。|[データベースの事前構成 Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
|MSDTC を構成し、DTC のトレースを無効にします。|[データベースの事前構成 Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
|SQL Server のすべてのインスタンスの起動時のパラメーターとしてトレース フラグ-t1118 を実装を有効にします。|[データベースの事前構成 Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
  
 **BizTalk データベースの SQL Server の最適化:**  
  
|Optimization|リファレンス|  
|------------------|---------------|  
|固定値をパーセント値ではなく、自動拡張の BizTalk データベースを設定します。|[構成後のデータベース Optimizations2](../technical-guides/post-configuration-database-optimizations2.md)|  
|LUN を分離する BizTalk データベース データとログ ファイルを移動/分割します。|[構成後のデータベース Optimizations2](../technical-guides/post-configuration-database-optimizations2.md)|  
|特定のメッセージ ボックス データベース テーブルの 'text in row' テーブル オプションを設定してみてください。|[構成後のデータベース Optimizations2](../technical-guides/post-configuration-database-optimizations2.md)|  
  
 **BizTalk の最適化**  
  
|Optimization|リファレンス|  
|------------------|---------------|  
|個別は、ポート、送信ポート、オーケストレーション、および追跡専用のホスト上に表示されます。|[BizTalk Server の一般的な Optimizations1](../technical-guides/general-biztalk-server-optimizations1.md)|  
|ポーリング間隔を構成します。|[低待機時間シナリオ Optimizations2](../technical-guides/low-latency-scenario-optimizations2.md)|  
|BizTalk 構成ファイルの最大接続プロパティを調整します。|セクションの「maxconnection パラメーターの値を変更することで許可される SOAP と HTTP の同時接続の数を増やす」[一般的な BizTalk Server Optimizations1](../technical-guides/general-biztalk-server-optimizations1.md)|  
|BizTalk Server の各ノードで、各ホスト インスタンスの CLR をホストしているパラメーターを定義します。<br /><br /> 最大 IO スレッドの数: 250<br /><br /> ワーカー スレッド最大数: 100<br /><br /> 最小 IO スレッドの数: 25<br /><br /> 最小ワーカー スレッド: 25|「CLR ホストの BizTalk ホスト インスタンスのスレッドの値を定義する」のセクションの[一般的な BizTalk Server Optimizations1](../technical-guides/general-biztalk-server-optimizations1.md)|  
|10000 インプロセス メッセージと内部メッセージ キューのサイズを増やします。|[低待機時間シナリオ Optimizations2](../technical-guides/low-latency-scenario-optimizations2.md)|  
|BizTalk Server グループ レベルの追跡を無効にします。|[BizTalk Server の一般的な Optimizations1](../technical-guides/general-biztalk-server-optimizations1.md)|  
|同時に実行される分離受信場所、バックエンド Web サービス、および IIS 7.5 統合モードで実行されている IIS 7.0 での WCF サービスをホストできる ASP.NET 4 Web アプリケーションの要求数を管理します。|[BizTalk Server の一般的な Optimizations1](../technical-guides/general-biztalk-server-optimizations1.md)|  
|BizTalk Server ホストの制限を無効にします。|[BizTalk Server の一般的な Optimizations1](../technical-guides/general-biztalk-server-optimizations1.md)|  
|MSDTC を構成し、DTC のトレースを無効にします。|[BizTalk Server の一般的な Optimizations1](../technical-guides/general-biztalk-server-optimizations1.md)|  
  
 **WCF 構成の最適化**  
  
|Optimization|リファレンス|  
|------------------|---------------|  
|各 WCF サービスの serviceThrottling サービスの動作を適用し、設定**maxConcurrentCalls**と**maxConcurrentSessions** 200 にします。|[BizTalk Server WCF Adapter パフォーマンスの最適化](../technical-guides/optimizing-biztalk-server-wcf-adapter-performance.md)|  
|バックエンド WCF サービス構成ファイルで serviceThrottling 動作の使用率を構成します。|[WCF Web Service パフォーマンスの最適化](../technical-guides/optimizing-wcf-web-service-performance.md)|  
  
## <a name="see-also"></a>参照  
 [BizTalk Server の運用環境のスケーリング](../technical-guides/scaling-a-production-biztalk-server-environment.md)