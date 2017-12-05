---
title: "シナリオの概要 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ac14328d-c373-49da-a899-4b3ca7d6dc0a
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab36aa51d2dd28651895818caa781c49bf366f50
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="scenario-overview"></a>シナリオの概要
このトピックでは、最新エンタープライズ クラスのハードウェアで実行されているときに、BizTalk Server のスケーラビリティを評価する製品のグループ、BizTalk Server によって完了したのロード テストの概要を示します。  
  
 すべてのテストは、専用のハードウェアを使用して分離環境で行われました。 200 以上のテストの実行が実行され、すべての結果は、BizTalk Server の製品グループによって検証されました。  
  
 メッセージング シナリオと、オーケストレーション シナリオを使用してテストを実施しました両方のシナリオでは、BizTalk、Wcf-nettcp アダプターを使用します。  
  
 BizTalk Server エンジンの最大の可能なパフォーマンスを評価するには、カスタム パイプライン コンポーネントを使用していません。され、オーケストレーションのシナリオののみ、非常に単純な単一のオーケストレーションが使用されました。 パフォーマンスの最適化」に記載[のパフォーマンスの最適化](../technical-guides/optimizing-performance.md)、環境に適用されていたし、完全に記載されています[観測と推奨事項](../technical-guides/observations-and-recommendations.md)です。  
  
## <a name="test-goals"></a>テストの目的  
 ロード テスト実行の目標には、次のものが含まれています。  
  
1.  [全般] のサイズ変更と BizTalk Server のガイダンスをスケーリングを提供します。  
  
    1.  BizTalk Server グループに追加のコンピューターを追加することの影響を定量化します。 このテストのため、BizTalk Server ソリューションのパフォーマンスは、BizTalk Server グループの実行中に、BizTalk Server を実行している 2 つ、3、および 4 つのコンピューターを測定されました。  
  
    2.  BizTalk Server グループに追加の BizTalk メッセージ ボックス データベースを追加することの影響を定量化します。 このテストのため、BizTalk Server ソリューションのパフォーマンスは、1 つのメッセージ ボックス データベースまたは 4 つのメッセージ ボックス データベースを使用するグループの構成時に測定されました。  
  
        > [!NOTE]  
        >  2 つのメッセージ ボックス データベースに 1 つから拡張するときに存在する場合は、ほとんどのパフォーマンス上の利点があるために、2 つのメッセージ ボックス データベースでのテストは実行されませんでした。 実際には、2 つのメッセージ ボックス データベースに 1 つからスケーリングできますパフォーマンスが低下します。 スケール アウト メッセージ ボックスの詳細については、次を参照してください。[スケール アウト SQL Server 層](../core/scaling-up-the-sql-server-tier.md)です。
  
2.  次のシナリオのサイジングとスケールのガイダンスを提供します。  
  
    1.  WCF-NetTcp 一方向のメッセージング シナリオ  
  
    2.  WCF-NetTcp 一方向のオーケストレーション シナリオ  
  
## <a name="test-measurements-used"></a>テストの測定基準  
次の条件を使用して BizTalk Server のパフォーマンスが測定されました。  
  
1.  **全体的なスループット**– で測定、  **BizTalk: メッセージング (*hostname*) \Documents 受信/秒 * * と **BizTalk: メッセージング (*hostname*) \Documents 処理/* * 秒のパフォーマンス カウンターの BizTalk Server 受信処理の各ホストとします。  
  
2.  **CPU 使用率**– で測定された、 **\Processor(_Total)\\% Processor Time** BizTalk Server のパフォーマンス カウンター] と SQL Server コンピューター。 すべてのテスト結果をレビューした包括的と、パフォーマンス ボトルネックの記載[観測と推奨事項](../technical-guides/observations-and-recommendations.md)です。  
  
## <a name="scaling-out-the-processing-tier-and-the-database-tier"></a>処理層およびデータベース層のスケール アウト  
BizTalk Server は、既存の BizTalk Server グループに 1 つまたは複数の BizTalk Server コンピューターを追加することにより、高い処理層機能を簡単に対応します。 BizTalk Server メッセージ ボックス データベースの追加により増加したデータベース層の機能に対応します。  
  
BizTalk Server のスケール アウトのメトリックを提供するには、テストは、1、2、3、および fourBizTalk サーバー コンピューターで実行しました。 データベース層のスケール アウトの影響を示すためには、これらのテストは、単一およびマルチ メッセージ ボックスの両方のシステムに対して実行されました。  
  
## <a name="testing-scenarios"></a>テストのシナリオ  
 これらのシナリオ用の BizTalk Server 環境を経由してメッセージのフローは、以下で詳しく説明します。  
  
### <a name="messaging-test-scenario"></a>メッセージングのテスト シナリオ  
 ![メッセージング シナリオ](../technical-guides/media/messagingscenario.gif "MessagingScenario")  
  
1.  機能をテストして、Visual Studio 2010 Ultimate エディション負荷は、XML メッセージを生成し、NetTcp トランスポートを使用して BizTalk Server を実行しているコンピューターに送信します。  
  
    > [!NOTE]  
    >  Visual Studio 2010 Ultimate edition のロード テストの詳細については、ハイパーリンクを参照してください。""[アプリケーションのテスト](http://go.microsoft.com/fwlink/?LinkID=208247)(http://go.microsoft.com/fwlink/?LinkID=208247)。  
    >   
    >  このテスト環境で機能をテストして、Visual Studio 2010 Ultimate エディション ロードを使用した方法の詳細については、次を参照してください。[を使用して Visual Studio でテストを容易に自動化](../technical-guides/using-visual-studio-to-facilitate-automated-testing.md)です。  
  
2.  BizTalk Server で XML メッセージを受信場所を使用して Wcf-nettcp 受信アダプターを受信します。 受信場所がメッセージの処理を行わず、PassThruReceive パイプラインを使用するように構成します。  
  
3.  BizTalk Server エンド ポイント マネージャー (EPM) は、BizTalk メッセージ ボックス データベースにメッセージを公開します。  
  
4.  Wcf-nettcp 送信アダプターを使用する BizTalk Server 送信ポートは、受信場所で公開されたメッセージをサブスクライブし、BizTalk MessageBox からメッセージを取得します。 送信ポートでは、メッセージの処理を行わず、PassThruTransmit パイプラインを使用します。  
  
5.  メッセージが配信をバックエンドに WCF サービス、Wcf-nettcp 送信アダプターでします。  
  
### <a name="orchestration-test-scenario"></a>オーケストレーションのテストのシナリオ  
 ![オーケストレーション シナリオの流れ](../technical-guides/media/orchestrationscenarioflow.gif "OrchestrationScenarioFlow")  
  
1.  機能をテストして、Visual Studio 2010 Ultimate エディション負荷は、XML メッセージを生成し、NetTcp トランスポートを使用して BizTalk Server を実行しているコンピューターに送信します。  
  
2.  BizTalk Server で XML メッセージを受信ポートを使用して Wcf-nettcp 受信アダプターを受信します。 受信ポートは、PassThruReceive を使用して、パイプラインのメッセージの処理を実行するなしに構成されます。  
  
3.  メッセージは、(手順 2 から WCF の受信ポートにバインドされている) 受信ポートおよび (手順 4 から WCF 送信ポートにバインドされている) 送信ポートのみで構成され、簡単なオーケストレーションに配信されます。 メッセージ変数は、「指定されていないか」、つまり、"System.XML.XmlDocument"の「メッセージの種類」を使用することはできません。 オーケストレーションでメッセージを受け取るだけその受信ポートと、その送信ポートからメッセージを送信します。 メッセージの処理は実行されません。  
  
4.  Wcf-nettcp 送信アダプターを使用する一方向の BizTalk Server 送信ポートは、オーケストレーションによって公開されたメッセージをサブスクライブし、BizTalk MessageBox からメッセージを取得します。 送信ポートでは、メッセージの処理を行わず、PassThruTransmit パイプラインを使用します。  
  
5.  メッセージが配信をバックエンドに WCF サービス、Wcf-nettcp 送信アダプターでします。  
  
## <a name="hardware-configuration"></a>ハードウェアの構成  
  
### <a name="lab-hardware-diagram-and-specifications"></a>ラボ ハードウェア ダイアグラムおよび仕様  
 ラボの使用、ハードウェアの構成を次に示します。 簡単に対応するためのスケール アウト処理およびデータベース層、ラボ環境の次のハードウェアが使用されていました。  
  
-   2 つのエンタープライズ クラスの Hewlett Packard DL 380 コンピューターと、BizTalk Server 処理層の 2 つのエンタープライズ クラス Dell R710 コンピューター。  
  
-   データベースの 4 つのエンタープライズ クラス Dell R900 コンピューターは、マルチ メッセージ ボックスの機能を提供する層です。  
  
 以下に、ラボで使用されるハードウェアのダイアグラムを示します。  
  
 ![パフォーマンス ガイド インフラストラクチャ](../technical-guides/media/performanceguideinfrastructure.gif "PerformanceGuideInfrastructure")  
  
 次の表は、ラボで使用されるハードウェアに関するより具体的な情報を提供します。  
  
|名前|[モデル]|CPU の種類|CPU の数|コア/CPU の数|CPU アーキテクチャ|[メモリ]|オペレーティング システム|ソフトウェア|  
|----------|-----------|--------------|--------------------|--------------------------|----------------------|------------|----------------------|--------------|  
|R710 01|Dell PowerEdge R710|Intel Xeon X5570|2 x 2.93 GHz|4|x64|72 GB|Windows Server 2008 R2, Enterprise Edition|BizTalk Server|  
|R710 02|Dell PowerEdge R710|Intel Xeon X5570|2 x 2.93 GHz|4|x64|72 GB|Windows Server 2008 R2, Enterprise Edition|BizTalk Server|  
|DL380G7 01|Hewlett Packard DL380 G7|Intel Xeon X5670|2 x 2.93 GHz|6|x64|192 GB|Windows Server 2008 R2, Enterprise Edition|BizTalk Server|  
|DL380G7 02|Hewlett Packard DL380 G7|Intel Xeon X5670|2 x 2.93 GHz|6|x64|192 GB|Windows Server 2008 R2, Enterprise Edition|BizTalk Server|  
|DL380 01|Hewlett Packard DL380|Intel Xeon 5150|2 x 2.66 GHz|2|x64|8 GB|Windows Server 2008 R2, Enterprise Edition|SQL Server 2008 R2 のロード テスト データベース<br /><br /> Visual Studio 2010<br /><br /> WCF バックエンド サービス|  
|DL380 02|Hewlett Packard DL380|Intel Xeon E5335|2 x: 2.00 GHz|4|x64|8 GB|Windows Server 2008 R2, Enterprise Edition|Visual Studio 2010 Load Test Controller|  
|DL380 03|Hewlett Packard DL380|Intel Xeon E5335|2 x: 2.00 GHz|4|x64|8 GB|Windows Server 2008 R2, Enterprise Edition|Visual Studio 2010 Load Test Agent|  
|DL380 04|Hewlett Packard DL380|Intel Xeon E5335|2 x: 2.00 GHz|4|x64|8 GB|Windows Server 2008 R2, Enterprise Edition|Visual Studio 2010 Load Test Agent です。<br /><br /> コマンド ライン Perfmon|  
|R805 06|Dell PowerEdge R805|AMD クアッド コア Opteron 2354|2 x 2.2 GHz|4|x64|32 GB|Windows Server 2008 R2, Enterprise Edition|Visual Studio 2010 Load Test Agent|  
|R805 07|Dell PowerEdge R805|AMD クアッド コア Opteron 2354|2 x 2.2 GHz|4|x64|32 GB|Windows Server 2008 R2, Enterprise Edition|Visual Studio 2010 Load Test Agent|  
|R900 03|Dell PowerEdge R900|Intel Xeon E7330|4 x 2.4 GHz|4|x64|64 GB|Windows Server 2008 R2, Enterprise Edition|SQL Server 2008 R2 の累積更新プログラム 4|  
|R900 04|Dell PowerEdge R900|Intel Xeon E7330|4 x 2.4 GHz|4|x64|64 GB|Windows Server 2008 R2, Enterprise Edition|SQL Server 2008 R2 の累積更新プログラム 4|  
|R900 05|Dell PowerEdge R900|Intel Xeon E7330|4 x 2.4 GHz|4|x64|64 GB|Windows Server 2008 R2, Enterprise Edition|SQL Server 2008 R2 の累積更新プログラム 4|  
|R900 06|Dell PowerEdge R900|Intel Xeon E7330|4 x 2.4 GHz|4|x64|64 GB|Windows Server 2008 R2, Enterprise Edition|SQL Server 2008 R2 の累積更新プログラム 4|  
  
### <a name="storage-area-network-configuration"></a>記憶域エリア ネットワークの構成  
 次の図は、ラボ環境の使用ストレージ エリア ネットワーク (SAN) の構成を示しています。  
  
 ![SAN 情報](../technical-guides/media/saninformation.gif "SANinformation")  
  
### <a name="emc-clariion-cx4-960-san-configuration"></a>EMC CLARiiON CX4 960 SAN の構成  
  
|サービスのプロセッサおよびキャッシュ情報|LUN の構成|  
|---------------------------------------------|-----------------------|  
|2 つサービスのプロセッサ、それぞれに:<br /><br /> -読み取りキャッシュ サイズ: 2000 MB です。<br />-書き込みキャッシュのサイズ: 8000 MB です。<br />-2 つのフロント エンド ポート ファイバー スイッチに接続します。 1 ポートあたり 4 Gbps です。|-64 台のディスク (268 GB、15 k RPM、ファイバー チャネル、Seagate です。<br />-8 8 ディスクは RAID 1 + 0 グループを広げるにこれらのディスクを 64 です。<br />-各データベース サーバーには、これらの RAID グループから構成に均等に 5 Metalun が割り当てられました。|  
  
 SAN の達成可能な最大スループットを確認し、実稼働環境で SAN に対して予測される負荷にこの値を比較に重要です。 テストまたは品質保証 (QA) 環境から運用環境にアプリケーションを移動するときは、SAN に関連するハードウェアの予期しない投資を防ぐためができます。 たとえば、SAN の使用可能な最大スループットは、サンド ボックス化されたテスト環境でアプリケーションの複数のための十分なあります。 ただし、他のサーバー アプリケーションは、SAN を使用して、実稼働環境では、SAN の使用可能なスループットは十分でない可能性があり、ボトルネックになる可能性があります。  
  
 SAN のパフォーマンスを評価するときに、次を考慮してください。  
  
1.  **SAN の達成可能な最大スループットは何ですか。** – スループットは、サーバー、スイッチ SAN スループットと SAN コント ローラー カードの速度でホスト バス アダプター (HBA) の観点から、最小の共通部分を使用してこれは測定されます。  
  
2.  **どのようなその他のアプリケーションは実稼働環境で SAN を使用しますか。** -どのようなその他のアプリケーションと、実稼働環境での SAN の使用を検討してください。 その他のデータベースまたは Exchange Server など、それ以外の場合の I/O 処理を要するアプリケーションで使用する場合、SAN 実稼働環境で、BizTalk Server を実行しているコンピューターの使用可能な SAN スループットの容量が適宜減少されます。  
  
 ラボ環境では、専用の SAN が使用されました。 SAN に接続された 4 台の SQL Server コンピューターの各 8-Gbps サーバーごとの合計の潜在的なスループットを提供する 2 つの 4 Gbps ホスト バス アダプター (Hba) のスイッチ。 SAN が 2 つのサービス プロセッサにあり、各サービス プロセッサ 16-Gbps SAN とスイッチ間の合計の潜在的なスループットを提供する、ファイバー スイッチに接続された 2 つのフロント エンド ポートです。  
  
 テスト環境で SQL Server を実行する 4 台のコンピューターの各 LUN の次の構成が使用されました。  
  
|ドライブ文字|ボリューム名|[ファイル]|LUN のサイズ (GB)|  
|------------------|-----------------|-----------|---------------------|  
|C|ローカルの C ドライブ|MASTER、MSDB、およびモデル|136|  
|H|Data_Tempdb|TempDB データ ファイル|50|  
|I|Logs_Tempdb|TempDB ログ ファイル|50|  
|J|Data_BtsMsgBox|BizTalk MsgBoxDB データ ファイル (マスター メッセージ ボックスの) + Mgmt DB では、SSO DB DTA DB のデータ ファイル|120|  
|K|Logs_BtsMsgBox|BizTalk MsgBoxDB ログ ファイル (マスター メッセージ ボックスの) + Mgmt DB、SSO データベース、DTA DB ログ ファイル|120|  
|O|Logs_Spare|SQL ファイルには使用されません。 DTCLog ファイルを格納するために使用、MSDTC により発生頻繁なディスク I/O、特にマルチ メッセージ ボックス環境でします。|20|  
  
### <a name="sqlio-test-results"></a>SQLIO テスト結果  
 SQLIO ツールを使用して、ベンチマークおよびラボ環境で使用する記憶域エリア ネットワーク (SAN) 構成の入力/出力能力を測定します。 ツールの名前からわかるように、SQLIO は、SQL Server のパフォーマンス上のファイル システム I/O の影響を測定するための貴重なツールです。 

SQL Server データベース アプリケーションの記憶域エリア ネットワーク (SAN) 構成の入力/出力の能力を測定するには、次を参照してください。 [I/O の特徴の分析と SQL Server データベース アプリケーションの記憶域システムをサイズ変更](https://msdn.microsoft.com/library/ee410782(SQL.100).aspx)です。  
  
 SQLIO、テストでは、sqlio.exe ユーティリティ問題 8 K は 8 スレッドからの読み取り要求と 8 の I/O キューの深さを維持します。 次のパラメーターを使用しました。  
  
-   すべてのテストでは、60 秒間に実行している各 8 の処理スレッドを使用します。  
  
-   8 kb のランダムは、データ ファイルに書き込みます。  
  
-   8 kb のランダムは、データ ファイルを読み取ります。  
  
-   すべてのファイル サイズが 25 GB になります。  
  
-   ディスク ドライブにベンチマークするが、h:、i:、j:、および K ドライブです。  
  
 次の手順を使用 SQLIO のコマンドラインには。  
  
-   **読み取り用**: sqlio 大韓民国-s60 frandom-o8-t8-b8 %.*ls-FParam.txt  
  
-   **書き込みのため**: sqlio -kW-s60 frandom-o8-t8-b8 %.*ls-FParam.txt  
  
 Param.txt ファイルには、次のものが含まれています。  
  
-   **ドライブの数:** : %m:、i:、j:、および K  
  
-   **テスト ファイルの物理的な場所**:  
  
    -   H:\testfile.dat 2 0x0 25000  
  
    -   I:\testfile.dat 2 0x0 25000  
  
    -   J:\testfile.dat 2 0x0 25000  
  
    -   K:\testfile.dat 2 0x0 25000  
  
 次の表に、テスト結果を示します。  
  
-   8 KB のランダムが Lun h:、i: j:、k: (すべてのデータベース ファイルの使用 Lun) 上で同時に 25 GB のテスト ファイルから読み取ります  
  
    ###  
  
    |1 秒間 (1 秒あたりの Io 数) の入力/出力操作|(Mb/秒) を 1 秒あたりのメガバイト数|平均待機時間|  
    |------------------------------------------------------|---------------------------------------|---------------------|  
    |10662.67|83.30|5 ms|  
  
-   8 KB のランダムが Lun h:、i: j:、k: (すべてのデータベース ファイルの使用 Lun) 上で同時に 25 GB のテスト ファイルに書き込みます  
  
    ###  
  
    |1 秒間 (1 秒あたりの Io 数) の入力/出力操作|(Mb/秒) を 1 秒あたりのメガバイト数|平均待機時間|  
    |------------------------------------------------------|---------------------------------------|---------------------|  
    |31527.95|246.31|1 ミリ秒|  
  
## <a name="see-also"></a>参照  
 [BizTalk Server の運用環境のスケーリング](../technical-guides/scaling-a-production-biztalk-server-environment.md)