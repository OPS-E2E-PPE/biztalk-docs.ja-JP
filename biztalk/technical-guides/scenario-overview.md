---
title: シナリオの概要 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ac14328d-c373-49da-a899-4b3ca7d6dc0a
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f5bbc23f4d6b9d1e2886059cf053a495562c1d01
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007147"
---
# <a name="scenario-overview"></a>シナリオの概要
このトピックでは、最新のエンタープライズ クラスのハードウェアで実行されているときに、BizTalk Server のスケーラビリティを評価するための製品グループのロードは、BizTalk Server で完了したテストの概要を示します。  

 すべてのテストは、専用のハードウェアを使用して、分離された環境で実行されました。 200 を超えるテストの実行が実行され、BizTalk Server の製品グループによってすべての結果が検証されました。  

 メッセージング シナリオと、オーケストレーションのシナリオでは; を使用してテストを実行しましたどちらのシナリオでは、BizTalk、Wcf-nettcp アダプターを使用します。  

 BizTalk Server エンジンの最大の可能なパフォーマンスを評価するには、カスタム パイプライン コンポーネントが使用されません。のみ、非常に単純な単一のオーケストレーションでは、オーケストレーションのシナリオが使用されました。 パフォーマンスの最適化」に記載[のパフォーマンスの最適化](../technical-guides/optimizing-performance.md)、環境に適用され、記載されて[所見と推奨事項](../technical-guides/observations-and-recommendations.md)します。  

## <a name="test-goals"></a>テストの目的  
 ロード テスト実行の目標には、次のものが含まれています。  

1.  [全般] のサイズとスケールの BizTalk Server のガイダンスを提供します。  

    1.  BizTalk Server グループに追加のコンピューターを追加することの影響を定量化します。 このテストは、BizTalk Server ソリューションのパフォーマンスが実行するときに、BizTalk Server グループが 1 つは、BizTalk Server を実行している 2 つ、3、および 4 つのコンピューターに測定されます。  

    2.  BizTalk Server グループに追加の BizTalk メッセージ ボックス データベースを追加することの影響を定量化します。 このテストのため、BizTalk Server ソリューションのパフォーマンスは、1 つのメッセージ ボックス データベースまたは 4 つのメッセージ ボックス データベースを使用して、グループの構成時に測定されました。  

        > [!NOTE]  
        >  1 から 2 つのメッセージ ボックス データベースにスケーリングするときにわずかであるか、パフォーマンス上の利点があるために、2 つのメッセージ ボックス データベースでのテストは実行されませんでした。 実際には、1 から 2 つのメッセージ ボックス データベースにスケーリングできますパフォーマンスが低下します。 スケール アウト メッセージ ボックスの詳細については、[スケール アウト SQL Server 層](../core/scaling-up-the-sql-server-tier.md)を参照してください。

2.  次のシナリオのサイズとスケールのガイダンスを提供するには。  

    1.  WCF-NetTcp 一方向メッセージング シナリオ  

    2.  WCF-NetTcp 一方向のオーケストレーション シナリオ  

## <a name="test-measurements-used"></a>テストの測定基準  
次の条件を使用して BizTalk Server のパフォーマンスが測定されました。  

1.  **全体的なスループット**– 測定された、 **BizTalk: メッセージング (*ホスト名*) \Documents Received/sec**と**BizTalk: メッセージング (*ホスト名*)\Documents 処理/秒**受信 BizTalk Server のパフォーマンス カウンターとホストを処理します。  

2.  **CPU 使用率**– で測定される、 **\Processor(_Total)\\% Processor Time** BizTalk Server のパフォーマンス カウンター] と SQL Server コンピューター。 すべてのテスト結果が確認された包括的と、パフォーマンスのボトルネックが記載されて[所見と推奨事項](../technical-guides/observations-and-recommendations.md)します。  

## <a name="scaling-out-the-processing-tier-and-the-database-tier"></a>処理レベルおよびデータベース層のスケール アウト  
BizTalk Server は、既存の BizTalk Server グループに 1 つまたは複数の BizTalk Server コンピューターを追加することで、高い処理層の機能を簡単に対応します。 BizTalk Server はメッセージ ボックス データベースの追加により増加したデータベース層の機能に対応します。  

BizTalk Server のスケール アウトのメトリックを提供するには、テストは、1、2、3、および fourBizTalk サーバー コンピューターで実行されました。 データベース層のスケール アウトの影響を示すためには、これらのテストは、単一およびマルチ メッセージ ボックスの両方のシステムに対して実行されました。  

## <a name="testing-scenarios"></a>テストのシナリオ  
 これらのシナリオ用の BizTalk Server 環境を経由してメッセージのフローは、以下で詳しく説明します。  

### <a name="messaging-test-scenario"></a>メッセージングのテスト シナリオ  
 ![メッセージング シナリオ](../technical-guides/media/messagingscenario.gif "MessagingScenario")  

1.  Visual Studio 2010 Ultimate edition 負荷のテストの機能は、XML メッセージを生成し、NetTcp トランスポートを使用して BizTalk Server を実行しているコンピューターに送信します。  

    > [!NOTE]  
    >  Visual Studio 2010 Ultimate edition のロード テストの詳細については、ハイパーリンクを参照してください。""[アプリケーションのテスト](http://go.microsoft.com/fwlink/?LinkID=208247)(http://go.microsoft.com/fwlink/?LinkID=208247)します。  
    >   
    >  このテスト環境で機能のテスト、Visual Studio 2010 Ultimate edition ロードを使用して方法の詳細については、[テスト自動化を容易にする Visual Studio を使用して](../technical-guides/using-visual-studio-to-facilitate-automated-testing.md)を参照してください。  

2.  BizTalk Server で XML メッセージが受信した受信場所を使用して、Wcf-nettcp 受信アダプターであること。 受信場所を構成して、メッセージの処理を行わず、PassThruReceive パイプラインを使用します。  

3.  BizTalk Server エンド ポイント マネージャー (EPM) は、BizTalk メッセージ ボックス データベースにメッセージを発行します。  

4.  Wcf-nettcp 送信アダプタを使用する BizTalk Server 送信ポートは、受信場所によって公開されたメッセージをサブスクライブし、BizTalk メッセージ ボックスからメッセージを取得します。 送信ポートは、メッセージの処理を行わず、PassThruTransmit パイプラインを使用します。  

5.  メッセージはバック エンドに WCF サービスによって配信、Wcf-nettcp 送信アダプター。  

### <a name="orchestration-test-scenario"></a>オーケストレーションのテスト シナリオ  
 ![オーケストレーション シナリオ流れ](../technical-guides/media/orchestrationscenarioflow.gif "OrchestrationScenarioFlow")  

1.  Visual Studio 2010 Ultimate edition 負荷のテストの機能は、XML メッセージを生成し、NetTcp トランスポートを使用して BizTalk Server を実行しているコンピューターに送信します。  

2.  BizTalk Server で XML メッセージが受信した受信ポートを使用して、Wcf-nettcp 受信アダプターであること。 受信ポートは、PassThruReceive を使用して、パイプラインがメッセージの処理を行わずに構成されます。  

3.  メッセージは、(手順 2 から WCF の受信ポートにバインドされた) 受信ポートおよび (手順 4 から、WCF 送信ポートにバインドされている) 送信ポートのみで構成され、簡単なオーケストレーションに配信されます。 メッセージの変数が「指定されていないか」、"System.XML.XmlDocument"の「メッセージの種類」を使用することを意味します。 オーケストレーションでは、使用して、メッセージだけが受信、受信ポートと、その送信ポートからメッセージを送信します。 メッセージの処理は実行されません。  

4.  Wcf-nettcp 送信アダプタを使用する一方向の BizTalk Server 送信ポートは、オーケストレーションによって公開されたメッセージをサブスクライブし、BizTalk メッセージ ボックスからメッセージを取得します。 送信ポートは、メッセージの処理を行わず、PassThruTransmit パイプラインを使用します。  

5.  メッセージはバック エンドに WCF サービスによって配信、Wcf-nettcp 送信アダプター。  

## <a name="hardware-configuration"></a>ハードウェアの構成  

### <a name="lab-hardware-diagram-and-specifications"></a>ラボのハードウェアのダイアグラムと仕様  
 ラボに使用されるハードウェア構成を次に示します。 スケール アウト処理とデータベース層に合わせて簡単に、次のラボのハードウェアを使用しました。  

- 2 つのエンタープライズ クラスの Hewlett Packard DL-380 コンピューターと BizTalk Server 処理層の 2 つのエンタープライズ クラス Dell R710 コンピューター。  

- データベース層の複数のメッセージ ボックス機能を提供する、4 台のエンタープライズ クラス Dell R900 コンピューター。  

  ラボで使用されるハードウェアを次の図を以下に示します。  

  ![パフォーマンス ガイド インフラストラクチャ](../technical-guides/media/performanceguideinfrastructure.gif "PerformanceGuideInfrastructure")  

  次の表は、ラボで使用されるハードウェアに関する詳細情報を提供します。  

|名前|[モデル]|CPU の種類|CPU の数|コアと CPU の数|CPU アーキテクチャ|Memory|オペレーティング システム|ソフトウェア|  
|----------|-----------|--------------|--------------------|--------------------------|----------------------|------------|----------------------|--------------|  
|R710-01|Dell PowerEdge R710|Intel Xeon X5570|2 x 2.93 GHz|4|x64|72 GB|Windows Server 2008 R2, Enterprise Edition|BizTalk Server|  
|R710-02|Dell PowerEdge R710|Intel Xeon X5570|2 x 2.93 GHz|4|x64|72 GB|Windows Server 2008 R2, Enterprise Edition|BizTalk Server|  
|DL380G7-01|Hewlett Packard DL380 G7|Intel Xeon X5670|2 x 2.93 GHz|6|x64|192 GB|Windows Server 2008 R2, Enterprise Edition|BizTalk Server|  
|DL380G7-02|Hewlett Packard DL380 G7|Intel Xeon X5670|2 x 2.93 GHz|6|x64|192 GB|Windows Server 2008 R2, Enterprise Edition|BizTalk Server|  
|DL380-01|Hewlett Packard DL380|Intel Xeon 5150|2 x 2.66 GHz|2|x64|8 GB|Windows Server 2008 R2, Enterprise Edition|SQL Server 2008 R2 のロード テスト データベース<br /><br /> Visual Studio 2010<br /><br /> バックエンド WCF サービス|  
|DL380-02|Hewlett Packard DL380|Intel Xeon E5335|2 x 2.00 GHz|4|x64|8 GB|Windows Server 2008 R2, Enterprise Edition|Visual Studio 2010 Load Test Controller|  
|DL380-03|Hewlett Packard DL380|Intel Xeon E5335|2 x 2.00 GHz|4|x64|8 GB|Windows Server 2008 R2, Enterprise Edition|Visual Studio 2010 Load Test Agent|  
|DL380-04|Hewlett Packard DL380|Intel Xeon E5335|2 x 2.00 GHz|4|x64|8 GB|Windows Server 2008 R2, Enterprise Edition|Visual Studio 2010 Load Test Agent です。<br /><br /> コマンド ライン パフォーマンス モニター|  
|R805-06|Dell PowerEdge R805|AMD クアッド コア Opteron 2354|2 x 2.2 GHz|4|x64|32 GB|Windows Server 2008 R2, Enterprise Edition|Visual Studio 2010 Load Test Agent|  
|R805-07|Dell PowerEdge R805|AMD クアッド コア Opteron 2354|2 x 2.2 GHz|4|x64|32 GB|Windows Server 2008 R2, Enterprise Edition|Visual Studio 2010 Load Test Agent|  
|R900-03|Dell PowerEdge R900|Intel Xeon E7330|4 x 2.4 GHz|4|x64|64 GB|Windows Server 2008 R2, Enterprise Edition|SQL Server 2008 R2 Cumulative Update 4|  
|R900-04|Dell PowerEdge R900|Intel Xeon E7330|4 x 2.4 GHz|4|x64|64 GB|Windows Server 2008 R2, Enterprise Edition|SQL Server 2008 R2 Cumulative Update 4|  
|R900-05|Dell PowerEdge R900|Intel Xeon E7330|4 x 2.4 GHz|4|x64|64 GB|Windows Server 2008 R2, Enterprise Edition|SQL Server 2008 R2 Cumulative Update 4|  
|R900-06|Dell PowerEdge R900|Intel Xeon E7330|4 x 2.4 GHz|4|x64|64 GB|Windows Server 2008 R2, Enterprise Edition|SQL Server 2008 R2 Cumulative Update 4|  

### <a name="storage-area-network-configuration"></a>記憶域エリア ネットワークの構成  
 次の図は、ラボ環境で使用するストレージ エリア ネットワーク (SAN) 構成を示しています。  

 ![SAN 情報](../technical-guides/media/saninformation.gif "SANinformation")  

### <a name="emc-clariion-cx4-960-san-configuration"></a>EMC CLARiiON CX4 960 SAN の構成  

|サービスのプロセッサおよびキャッシュ情報|LUN の構成|  
|---------------------------------------------|-----------------------|  
|2 つサービスのプロセッサ、それぞれに:<br /><br /> -読み取りキャッシュ サイズ: 2000 MB です。<br />-キャッシュ サイズを作成する: 8000 MB です。<br />-2 つのフロント エンド ポート ファイバ スイッチに接続されています。 ポートごとの 4 Gbps です。|-64 個のディスク (268 GB、15 k RPM、ファイバー チャネル、Seagate します。<br />-8 8 ディスクは RAID 1 + 0 64 個のディスクではこれらから分割したグループです。<br />-各 DB のサーバーには、これらの RAID グループから均等に構成されている 5 Metalun が割り当てられました。|  

 SAN の達成可能な最大スループットを確認し、運用環境での SAN に対して予想される負荷は、この値を比較する重要です。 これにより、アプリケーションをテスト/品質保証 (QA) の環境から運用環境に移行する場合は、SAN に関連するハードウェアの経費を予期しないを防ぐことは役立ちます。 たとえば、SAN の使用可能な最大のスループットは、サンド ボックス化されたテスト環境でアプリケーションの複数のための十分な可能性があります。 ただし、他のサーバー アプリケーションは、SAN を使用して、運用環境では、SAN の使用可能なスループットは十分でない可能性があり、ボトルネックになる可能性があります。  

 SAN のパフォーマンスを評価するときに、次の操作を考慮してください。  

1. **SAN の達成可能な最大のスループットとは何ですか。** – これは、サーバー、スイッチ、SAN のスループット、および SAN のコント ローラー カードの速度でホスト バス アダプター (HBA) のスループットの観点で最小公分母を使用して測定されます。  

2. **どのような他のアプリケーションは運用環境で SAN を使用しますか。** – どのような他のアプリケーションと、運用環境で、SAN の使用を検討してください。 その他のデータベースまたは Exchange Server など、それ以外の場合の I/O 集中型アプリケーションは、運用環境で、SAN を使用するが、BizTalk Server を実行しているコンピューターで使用できる SAN スループットの量が適宜減少されます。  

   ラボ環境では、専用の SAN が使用されました。 SAN に接続された 4 つの SQL Server コンピューターの各サーバーあたり 8 Gbps の潜在的な合計スループットを提供する 2 つの 4 Gbps ホスト バス アダプター (Hba) のスイッチ。 SAN が 2 つのサービス プロセッサとサービス プロセッサごとに 16 Gbps SAN とスイッチの間の潜在的な合計スループットを提供する、fiber スイッチに接続された 2 つのフロント エンド ポートが必要があります。  

   テスト環境で SQL Server を実行している 4 台のコンピューターの各 LUN の次の構成が使用されました。  

|ドライブ文字|ボリューム名|[ファイル]|LUN のサイズ (GB)|  
|------------------|-----------------|-----------|---------------------|  
|c|ローカルの C ドライブ|MASTER、MSDB、およびモデル|136|  
|H|Data_Tempdb|TempDB データ ファイル|50|  
|I|Logs_Tempdb|TempDB ログ ファイル|50|  
|J|Data_BtsMsgBox|BizTalk MsgBoxDB データ ファイル (マスター メッセージ ボックスの) + Mgmt DB、SSO DB では、DTA DB データ ファイル|120|  
|K|Logs_BtsMsgBox|BizTalk MsgBoxDB ログ ファイル (マスター メッセージ ボックスの) + Mgmt DB、SSO DB、DTA DB ログ ファイル|120|  
|O|Logs_Spare|SQL ファイルは使用されません。 DTCLog ファイルの格納に使用すると、MSDTC としてが頻繁にディスク I/O、特にマルチ メッセージ ボックス環境で。|20|  

### <a name="sqlio-test-results"></a>SQLIO テスト結果  
 SQLIO ツールを使用してベンチマークを実行およびラボ環境で使用される記憶域領域ネットワーク (SAN) の構成の入力/出力の能力を測定しました。 ツールの名前が示すように、SQLIO、SQL Server のパフォーマンス上のファイル システム I/O の影響を測定するため貴重なツールです。 

SQL Server データベース アプリケーション ストレージ エリア ネットワーク (SAN) の構成の入力/出力の能力を測定するには、[I/O 特性の分析と SQL Server データベース アプリケーションの記憶域システムのサイズ変更](https://msdn.microsoft.com/library/ee410782(SQL.100).aspx)を参照してください。  

 SQLIO、テストでは、sqlio.exe ユーティリティ問題 8 K は 8 つのスレッドからの読み取り要求と 8 の I/O キューの深さを維持します。 次のパラメーターを使用しました。  

- すべてのテストには、60 秒間実行している各 8 の処理スレッドが使用されます。  

- 8 kb のランダムなは、データ ファイルに書き込みます。  

- 8 kb のランダムなは、データ ファイルを読み取ります。  

- すべてのファイル サイズが 25 GB になります。  

- ディスク ドライブに対してベンチマークを実行するのには、h:、操作、j:、K ドライブです。  

  使用 SQLIO コマンドラインは、次のとおりです。  

- **読み取り**: sqlio 韓国-s60 frandom-o8-t8-b8 LS-FParam.txt  

- **書き込み**: sqlio -kW-s60 frandom-o8-t8-b8 LS-FParam.txt  

  Param.txt ファイルには、次のものが含まれています。  

- **ドライブの数:** : %m:、操作、j:、K  

- **テスト ファイルの物理的な場所**:  

  -   H:\testfile.dat 2 0x0 25000  

  -   I:\testfile.dat 2 0x0 25000  

  -   J:\testfile.dat 2 0x0 25000  

  -   K:\testfile.dat 2 0x0 25000  

  次の表では、テスト結果を示します。  

- 8 KB のランダムが Lun h:、操作、j:、k: (すべてのデータベース ファイルで使用される Lun) 上で同時に 25 GB のテスト ファイルから読み取ります  

  ###  

  | (IOs/秒) を 1 秒あたりの入力/出力操作 | メガバイト (Mb/秒) を 1 秒あたり | 平均待機時間 |
  |----------------------------------------------|--------------------------------|-----------------|
  |                   10662.67                   |             83.30              |      5 ミリ秒       |


- 8 KB のランダムが Lun h:、操作、j:、k: (すべてのデータベース ファイルで使用される Lun) 上で同時に 25 GB のテスト ファイルに書き込みます  

  ###  

  |(IOs/秒) を 1 秒あたりの入力/出力操作|メガバイト (Mb/秒) を 1 秒あたり|平均待機時間|  
  |------------------------------------------------------|---------------------------------------|---------------------|  
  |31527.95|246.31|1 ミリ秒|  

## <a name="see-also"></a>参照  
 [BizTalk Server の運用環境のスケーリング](../technical-guides/scaling-a-production-biztalk-server-environment.md)