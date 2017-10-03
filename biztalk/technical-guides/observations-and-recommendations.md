---
title: "監視と推奨事項 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 88289080-1a59-4ffc-a0b2-312ec21940c2
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fba4c82725239bb8e37d8bf611dd721d1ee1514b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="observations-and-recommendations"></a>監視と推奨事項
## <a name="test-results-summary"></a>テスト結果の概要  
 メッセージングのみのシナリオの結果が発生する ~ 109,382,400 日あたりのメッセージ。 オーケストレーションのシナリオでは、結果は、BizTalk Server を実行している 1 台のコンピューターが 1 日あたり最大 58,752,000 メッセージを処理できることを示します。 これらの結果は、多くの BizTalk Server ソリューションの展開されている通常のエンタープライズ クラスのハードウェアを使用して、セキュリティで保護された環境で実現しました。 したがって、これらの結果を示すないカスタム コードを使用するの BizTalk Server のパフォーマンスの種類を実現できます。 顧客のソリューションは、しばしば独自に開発された BizTalk アイテムです。多くの場合この増加処理要件がさらにパフォーマンスが低下します。 このガイドで紹介アドバイスに従って、特に[BizTalk Server アプリケーションの最適化](../technical-guides/optimizing-biztalk-server-applications.md)セクションで、カスタム開発した BizTalk Server アイテムを最小限に抑えることができますを実装することの影響。  
  
 次の表は、このパフォーマンス評価のため、テスト結果の概要を提供します。  
  
|Scenario|メッセージング (BizTalk KPI: 1 秒あたりに処理されたドキュメント)|メッセージング (SQL KPI – SQL プロセッサ使用率)|メッセージングの待機時間 (秒)|オーケストレーション (BizTalk KPI: 1 秒あたりに処理されたドキュメント)|オーケストレーション (SQL KPI – SQL プロセッサ使用率)|オーケストレーションの遅延時間 (秒)|  
|--------------|----------------------------------------------------------------|-------------------------------------------------------|-----------------------------------|--------------------------------------------------------------------|-----------------------------------------------------------|---------------------------------------|  
|1 つのメッセージ ボックス データベース 1 の BizTalk Server コンピューター|1 秒あたりに処理された 1266 のドキュメント|59 SQL CPU 使用率|0.06|1 秒あたりに処理された 680 のドキュメント|66.5 SQL CPU 使用率|0.067|  
|1 つのメッセージ ボックス データベース 2 の BizTalk Server コンピューター|1 秒あたりに処理された 1267 のドキュメント|59.8 SQL CPU 使用率|0.057|1 秒あたりに処理された 686 のドキュメント|68.5 SQL CPU 使用率|0.067|  
|3 つのメッセージ ボックス データベース 1 の BizTalk Server コンピューター|1 秒あたりに処理された 2102 のドキュメント|41 SQL CPU 使用率|0.077|1 秒あたりに処理された 974 のドキュメント|48 SQL CPU 使用率|0.11|  
|3 つのメッセージ ボックス データベース 2 の BizTalk Server コンピューター|1 秒あたりに処理された 2285 のドキュメント|58 SQL CPU 使用率|0.041|1 秒あたりに処理された 1065 のドキュメント|SQL の CPU 使用率の 65%|0..69|  
|4 つのメッセージ ボックス 1 の BizTalk Server コンピューター|1 秒あたりに処理された 2125 のドキュメント|SQL の CPU 使用率が 30%|0.078|1 秒あたりに処理された 979 のドキュメント|SQL の CPU 使用率の 37%|0.095|  
|4 つのメッセージ ボックス 2 の BizTalk Server コンピューター|1 秒あたりに処理された 2790 のドキュメント|SQL の CPU 使用率が 50%|0.052|1 秒あたりに処理された 1487 のドキュメント|SQL の CPU 使用率が 63%|0.15|  
|4 つのメッセージ ボックス 3 の BizTalk Server コンピューター|1 秒あたりに処理された 2656 のドキュメント|58 SQL CPU 使用率|0.074|1 秒あたりに処理された 1388 のドキュメント|SQL の CPU 使用率の 65%|0.15|  
  
## <a name="comparison-of-performance-statistics-with-biztalk-server-2009"></a>BizTalk Server 2009 と共にパフォーマンス統計情報の比較  
 次の表は、BizTalk Server 2009 および BizTalk Server 2010 との間のパフォーマンス統計情報の比較を示します。 この表に示す BizTalk Server 2009 のパフォーマンス統計情報は、BizTalk Server 2009 のパフォーマンスと最適化ガイドです。  
  
|Scenario|BizTalk Server 2009<br /> 最大の維持可能なスループット (MST) メッセージ/秒|BizTalk Server 2009<br />必要な BizTalk サーバーの数|BizTalk Server 2010<br />最大の維持可能なスループット (MST) メッセージ/秒|BizTalk Server 2010<br />必要な BizTalk サーバーの数|BizTalk Server 2009 から BizTalk Server 2010% の違い|  
|--------------|----------------------------------------------------------------------------|-----------------------------------------------------------|---------------------------------------------------------------------------|-----------------------------------------------------------|---------------------------------------------------------------|  
|メッセージングの 1 つのメッセージ ボックス|1291|2|1266|1|98.06%|  
|オーケストレーションの単一のメッセージ ボックス|676|2|680|1|100.59%|  
|メッセージングの 3 つのメッセージ ボックス|2103|3|2285|2 (1 BTS で 2102/秒)|108.65%|  
|メッセージングの 4 つのメッセージ ボックス|適用なし|適用なし|2790|2|適用なし|  
|オーケストレーションに 3 つのメッセージ ボックス|1005|4|1065|2 (1 BTS で 974/秒)|105.97%|  
|オーケストレーションの 4 つのメッセージ ボックス|適用なし|適用なし|1487|2|適用なし|  
  
 このラボ環境で、4 つのメッセージ ボックス データベースを使用する場合、維持可能なスループットを最大結果はとおりでした。  
  
-   メッセージング シナリオでは、1 秒あたりの 2790 ドキュメント。  
  
-   オーケストレーション シナリオでは、1 秒あたりの 1487 ドキュメント。  
  
 **メッセージの考慮事項**中に BizTalk Server にメッセージのサイズに制限はありません、BizTalk Server 2010 のテストの実行には 2 KB のメッセージのみが使用される型で使用される WCF アダプタの Wcf-nettcp アダプター。 これには、BizTalk Server 2009 のパフォーマンス最適化ガイドのテストに使用されるメッセージのサイズとアダプターの種類と一致します。  
  
 パフォーマンス向上のため、ドライバーは次のとおりです。  
  
1.  **ハードウェアの進歩により**-ラボで使用される SQL Server コンピューターが 4 CPU、クアッド コア (16 コア)、Intel Xeon E7330 2.40 GHz @ です。 2009 テストでは、CPU、4 クアッドコア (16 コア)、Intel Xeon 2.4 GHz 使用されました。  
  
     このラボで使用する BizTalk Server コンピューターは、2 個の CPU、クアッド コア (8 コア)、Nehalem ハイパー スレッド (16 個の論理コア)、Intel Xeon X 2.93 GHz @ 5570 をでした。 2009 テストでは、2 個の CPU、クアッド コア (8 コア)、Intel Xeon 2.33 GHz 使用されました。  
  
2.  **SQL Server エンジンの向上**-マイクロソフトによるテストが、基になるデータベース プラットフォームとして SQL Server 2008 R2 で実行されました。 一方、SQL Server 2008 に対して 2009 内のテストが実行されました。  
  
## <a name="recommendations-for-scaling-the-biztalk-server-and-sql-server-tiers"></a>BizTalk Server および SQL Server の階層を拡張するための推奨事項  
 それらの結果、BizTalk Server の製品チームでは、1 台の BizTalk Server コンピューターと 1 台の SQL Server コンピューターをサポートできること 109 件以上のメッセージ メッセージング シナリオや 58, 000 オーケストレーションで、24 時間の期間を示すことでした。 この環境で使用可能な最適な構成を BizTalk Server と SQL の層をスケールして 1 日で、128 を超えるオーケストレーション over241 百万メッセージを処理できませんでした。 結果は、多くの企業で展開されているハードウェアのクラスを使用して、セキュリティで保護された環境で実行されました。 前述のように、これらの番号は、カスタム コードがないと、最適化された環境で実現できる BizTalk Server の現実的なパフォーマンスを表します。  ハードウェアを追加したことが、さらに優れたパフォーマンスが達成できます。 多くの場合、顧客のソリューションには、追加の処理の要件、したがってリソース使用率の向上、および全体的なパフォーマンスをさらに減らすことが発生した、カスタム開発した BizTalk アイテムが含まれます。 ただしで、次の推奨事項に特に、このガイドで説明されている通知[BizTalk Server アプリケーションの最適化](../technical-guides/optimizing-biztalk-server-applications.md)、この影響を最小限に抑えることができます。  
  
 結果は、スケール アウトの BizTalk Server コンピューターの数が効果的なスケール アウト戦略メッセージ ボックス SQL Server コンピューターがボトルネックでない場合を示しています。 パフォーマンスを原因となった後、特定の BizTalk Server コンピューターを追加することになる非効率的なスケール アウト手法で、競合ポイントが、メッセージ ボックス データベース内の共有のテーブルで発生したことがわかっていますので、結果を示す、減少します。 単一のメッセージ ボックス データベースと BizTalk Server グループを得た結果を最大化するで説明する最適化を適用する必要があります[データベースのパフォーマンスの最適化](../technical-guides/optimizing-database-performance.md)です。 具体的には、SQL Server の記憶域に対して高速記憶域サブシステムを使用して、メッセージ ボックス データベース ファイルを格納する SQL Server によって使用される論理ディスクをできるだけ短時間で応答することを確認する必要があります。 許容可能な読み取り/書き込みのパフォーマンスを測定するための一般的に使用されるしきい値は 15 ミリ秒です。通常これは、によって測定は avg.ディスク読み取り秒数と平均論理ディスクのパフォーマンス オブジェクトに含まれているディスク書き込み秒数のカウンターです。 メッセージ ボックス データベースをホストする SQL Server コンピューターには、すべての利用可能な最適化が適用されたら、追加のメッセージ ボックス データベースを追加できます。 プライマリ メッセージ ボックス データベースに適用されている同じ最適化手法は、セカンダリ データベースにも適用する必要があります。 」のガイドラインに従うことをお勧め[スケール アウト SQL Server 層](http://go.microsoft.com/fwlink/?LinkID=158075)(http://go.microsoft.com/fwlink/?LinkID=158075)、BizTalk Server のドキュメントにします。  
  
 最適な結果を取得するためには、ハードウェアおよびソフトウェア スタック全体は、適切な品質のされる必要がありも正しく構成されています。 最初に、高品質のハードウェアをなどを購入する必要がありますが、ギガビット ネットワーク、高速な記憶域 (SAN または 15 K ローカル SQL ディスク) に限定されないと最新のコンピューターを複数のコア CPU ごとの複数の Cpu を持ちます。 SQL Server コンピューターを専用処理でのみ BizTalk Server にする必要があります。 1 台の SQL Server コンピューターを実行する場合は、BizTalk メッセージ ボックスを他のすべてのデータベースの 1 つ、SQL の 2 つのインスタンスを作成お勧めします。 これにより、メッセージ ボックス データベースの最適なパフォーマンス用に構成するインスタンス全体の設定です。 推奨されている、最適化[のパフォーマンスの最適化](../technical-guides/optimizing-performance.md)を適用する次の順序では、ステップ バイ ステップ:[オペレーティング システムのパフォーマンスの最適化](../technical-guides/optimizing-operating-system-performance.md)、[ネットワークの最適化パフォーマンス](../technical-guides/optimizing-network-performance.md)、[事前構成データベース Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)、[後の構成データベース Optimizations2](../technical-guides/post-configuration-database-optimizations2.md)と[BizTalk Server の一般的なOptimizations1](../technical-guides/general-biztalk-server-optimizations1.md)です。 メッセージ ボックス データベースの専用のファイル グループを作成して、」の説明に従って SAN Lun 全体で割り当てて[、Databases2 のファイル グループを最適化する](../technical-guides/optimizing-filegroups-for-the-databases2.md)、に応じてにより、パフォーマンスの向上を提供することができます、SAN の構成と LUN のレイアウトです。  
  
 BizTalk Server または SQL 層をスケールの方法を効果的に確認するのにするをお勧めのロード テスト実稼働データのおおよそのメッセージを使用して実行します。 BizTalk Server 層をスケーリングするには、前にないことを確認 SQL Server 既に、ボトルネックの推奨事項に従って[SQL Server のパフォーマンスの監視](../technical-guides/monitoring-sql-server-performance.md)です。 SQL Server がボトルネックになっている、BizTalk Server コンピューター上の CPU ヘッドルームがある場合は、ホスト インスタンスのレイアウトを変更してスループットを向上させることができます。 これが 4 または 5 つ主要業績評価指標 (Kpi)、すべてのテスト実行の大まかな比較のポイントとして使用されているを確立するために重要です。 この通知では、次の特定の変更、ソリューションの全体的なパフォーマンスが低下するかどうかをすばやく判断することができます。  
  
 層のスケール アウト、SQL Server、前に適用するすべての最適化で[データベースのパフォーマンスの最適化](../technical-guides/optimizing-database-performance.md)です。 顧客パフォーマンス ラボの中には、監視がその記憶域のディスク構成をメッセージ ボックス データベースと TempDb データベース特にが提供する以上 30% スループットの向上。 複数のメッセージ ボックス データベースに合わせたスケーリング、時に、1 つのメッセージ ボックス データベースから 2 つのメッセージ ボックス データベースをスケール アウトするほとんどのパフォーマンス上の利点があるために 3 つおよび 4 つのメッセージ ボックス データベースが使用されました。 スケール アウトは、BizTalk Server メッセージ ボックスの詳細については、次を参照してください。[スケール アウト SQL Server 層](http://go.microsoft.com/fwlink/?LinkID=158075)(http://go.microsoft.com/fwlink/?LinkID=158075)、BizTalk Server のドキュメントにします。  
  
## <a name="implemented-optimizations"></a>実装の最適化  
 このセクションでは、ラボのテストのシナリオに対して適用されたすべての最適化のチェックリストを提供します。  
  
> [!NOTE]  
>  実稼働環境でこれらを適用する前に、変更管理手順に従ってテストする必要があります。  
  
 体系的な管理された方法で最適化を適用する — 最適化の設定を適用すると、影響をテストして、: 最大パフォーマンスの利点になります。 最適化処理の影響を定期的にテストなしの最適化を適用することがあります実際には、ソリューションのパフォーマンスが低下。  
  
### <a name="checklists-of-optimizations-applied"></a>適用される最適化のチェックリスト  
 **プラットフォームとネットワークの最適化**  
  
|Optimization|リファレンス|  
|------------------|---------------|  
|BIOS: は、パフォーマンスの設定を構成します。|[オペレーティング システムのパフォーマンスを最適化します。](../technical-guides/optimizing-operating-system-performance.md)|  
|SQL Server のファイルのリアルタイム スキャンを無効にします。|[オペレーティング システムのパフォーマンスを最適化します。](../technical-guides/optimizing-operating-system-performance.md)|  
|「高パフォーマンス」を有効にするすべての BizTalk Server と SQL Server コンピューターの電源プランします。|[オペレーティング システムのパフォーマンスを向上させるための一般的なガイドライン](../technical-guides/general-guidelines-for-improving-operating-system-performance.md)|  
|すべての BizTalk Server と SQL Server のコンピューターでウイルス対策ソフトウェアを無効にします。|[オペレーティング システムのパフォーマンスを向上させるための一般的なガイドライン](../technical-guides/general-guidelines-for-improving-operating-system-performance.md)|  
  
 **SQL Server の最適化: 全般**  
  
|Optimization|リファレンス|  
|------------------|---------------|  
|NTFS ファイル アロケーション ユニットは、64 KB に設定します。|[事前構成データベース Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
|SQL Server 2008 R2 をインストールします。|[事前構成データベース Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
|SQL Server 2008 R2 のデータ コレクター/ウェアハウスを構成します。|[事前構成データベース Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
|Windows の適切な特権を SQL Server サービス アカウントに拡張されていることを確認します。|SQL Server 2008 R2:[サービス アカウントに、Windows セットアップ](http://go.microsoft.com/fwlink/?LinkID=132144)(http://go.microsoft.com/fwlink/?LinkID=132144)|  
|SQL Server の最小値と最大サーバー メモリを設定します。|[事前構成データベース Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
|SQL Server に使用されるアカウントに Windows メモリ ページのロックの特権を付与します。|[事前構成データベース Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
|複数のデータ ファイルと、適切なサイズに BizTalk Server データベースのサイズを変更済み.|[インストール後の構成データベース Optimizations2](../technical-guides/post-configuration-database-optimizations2.md)|  
|SQL Server クライアント プロトコルを構成します。|[SQL Server のトラブルシューティング](http://go.microsoft.com/fwlink/?LinkID=154250)(http://go.microsoft.com/fwlink/?LinkID=154250)|  
|Tempdb データベースを同じサイズの BizTalk Server で使用される各 SQL Server インスタンス上の複数のデータ ファイルに分割します。|[事前構成データベース Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
|SQL Server プロセスの関係を手動で設定します。|[事前構成データベース Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
|MSDTC を構成し、DTC のトレースを無効にします。|[事前構成データベース Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
|SQL Server のすべてのインスタンスの起動時のパラメーターとしてトレース フラグ-t1118 を実装を有効にします。|[事前構成データベース Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)|  
  
 **SQL Server の最適化: BizTalk データベース**  
  
|Optimization|リファレンス|  
|------------------|---------------|  
|固定値を割合値ではなく、自動拡張の BizTalk データベースを設定します。|[インストール後の構成データベース Optimizations2](../technical-guides/post-configuration-database-optimizations2.md)|  
|BizTalk データベース データとログ ファイルを別に LUN を移動して分割します。|[インストール後の構成データベース Optimizations2](../technical-guides/post-configuration-database-optimizations2.md)|  
|特定のメッセージ ボックス データベース テーブルの 'text in row' テーブル オプションの設定を検討してください。|[インストール後の構成データベース Optimizations2](../technical-guides/post-configuration-database-optimizations2.md)|  
  
 **BizTalk の最適化**  
  
|Optimization|リファレンス|  
|------------------|---------------|  
|別は、ポート、送信ポート、オーケストレーション、および追跡、別々 の専用のホスト上に表示されます。|[BizTalk Server の一般的な Optimizations1](../technical-guides/general-biztalk-server-optimizations1.md)|  
|ポーリング間隔を構成します。|[低待機時間シナリオ Optimizations2](../technical-guides/low-latency-scenario-optimizations2.md)|  
|BizTalk 構成ファイルの最大接続プロパティを調整します。|セクションの「maxconnection パラメーターの値を変更することで許可されている SOAP と HTTP の同時接続の数を増やす」[一般的な BizTalk Server Optimizations1](../technical-guides/general-biztalk-server-optimizations1.md)|  
|BizTalk Server の各ノードで、各ホスト インスタンスの CLR をホストしているパラメーターを定義します。<br /><br /> 最大 IO スレッド数: 250<br /><br /> ワーカー スレッド最大数: 100<br /><br /> 最小 IO スレッド数: 25<br /><br /> 最小ワーカー スレッド: 25|「CLR ホストの BizTalk ホスト インスタンスのスレッドの値を定義」セクション[一般的な BizTalk Server Optimizations1](../technical-guides/general-biztalk-server-optimizations1.md)|  
|10000 インプロセス メッセージと内部メッセージ キューのサイズを増やします。|[低待機時間シナリオ Optimizations2](../technical-guides/low-latency-scenario-optimizations2.md)|  
|BizTalk Server グループ レベルの追跡を無効にします。|[BizTalk Server の一般的な Optimizations1](../technical-guides/general-biztalk-server-optimizations1.md)|  
|分離受信場所、バックエンド Web サービス、および IIS 7.5、および統合モードで実行されている IIS 7.0 での WCF サービスをホストする ASP.NET 4 Web アプリケーションに対する要求を同時に実行される数を管理します。|[BizTalk Server の一般的な Optimizations1](../technical-guides/general-biztalk-server-optimizations1.md)|  
|BizTalk Server ホスト制限を無効にします。|[BizTalk Server の一般的な Optimizations1](../technical-guides/general-biztalk-server-optimizations1.md)|  
|MSDTC を構成し、DTC のトレースを無効にします。|[BizTalk Server の一般的な Optimizations1](../technical-guides/general-biztalk-server-optimizations1.md)|  
  
 **WCF 構成の最適化**  
  
|Optimization|リファレンス|  
|------------------|---------------|  
|各 WCF サービスに対して、serviceThrottling サービスの動作を適用し、設定**maxConcurrentCalls**と**maxConcurrentSessions**を 200 です。|[BizTalk Server WCF アダプターのパフォーマンスを最適化します。](../technical-guides/optimizing-biztalk-server-wcf-adapter-performance.md)|  
|バックエンド WCF サービス構成ファイルで serviceThrottling 動作の使用法を構成します。|[WCF Web サービスのパフォーマンスを最適化します。](../technical-guides/optimizing-wcf-web-service-performance.md)|  
  
## <a name="see-also"></a>参照  
 [運用環境の BizTalk Server 環境のスケーリング](../technical-guides/scaling-a-production-biztalk-server-environment.md)