---
title: パフォーマンスと安定性テストを自動化するための BizUnit および LoadGen を使用して |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 73c2a97a-6256-4010-8374-433017cb15d4
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e84fcd29af6b698713623fbca556d988e037d8c1
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25976280"
---
# <a name="using-bizunit-and-loadgen-to-automate-performance-and-stability-testing"></a>パフォーマンスと安定性テストを自動化するための BizUnit および LoadGen を使用します。
このトピックでは、パフォーマンスと安定性は、BizTalk Server ソリューションのテストを自動化するための BizUnit で Microsoft BizTalk LoadGen 2007 ツールを使用する方法に関する情報を提供します。  
  
## <a name="biztalk-server-performance-testing-step-by-step"></a>BizTalk Server のパフォーマンス テスト、詳細な手順  
 BizTalk Server のパフォーマンス テストを自動化する方法を調査する前にどのような手順は、パフォーマンス テストで通常実行されるかを理解すると便利です。 次の手順には、プロセスのテスト「標準」BizTalk Server のパフォーマンスの代表者がいます。  
  
1.  結果とデータを収集、たとえば、イベント ログ、トレース ログ、パフォーマンス モニターのデータを格納するテストの結果ディレクトリを作成します。  
  
2.  テスト環境内のすべてのサーバー上のイベント ログをオフにします。  
  
3.  すべての BizTalk ホスト インスタンスを停止します。  
  
4.  SOAP および HTTP 受信アダプター ハンドラーなど、BizTalk 分離ホストを実行しているすべての IIS インスタンスを停止します。  
  
5.  BizTalk Server を実行しているコンピューターで使用される SQL Server のすべてのインスタンスを再起動します。  
  
6.  以前のテスト実行から残されたデータがないことを確認するメッセージ ボックス データベースをクリーンアップします。 これは、機能は、残されたデータは、テスト結果をゆがめる可能性がありますので重要です。  
  
7.  BizTalk ホスト インスタンスを起動します。  
  
8.  テスト環境のすべてのサーバーでは、関連するパフォーマンス モニター カウンターを開始します。  
  
9. システム キャッシュを初期化するためにシステムで「準備」のメッセージを送信します。  
  
10. 準備メッセージが処理された後は、SQL Server のテスト結果のデータベースにテストの開始時刻を追跡します。  
  
11. すべての LoadGen のテスト エージェントを起動して、パフォーマンス テストを開始します。  
  
12. テストが完了するまで待機 – 多くの場合、これ行う体系的にホスト キューの長さなどのパフォーマンス モニター カウンターの値を測定します。  
  
13. 結果のデータベースを SQL テストにおけるテスト終了時間を追跡します。  
  
14. テスト環境のすべてのサーバー上には、関連するパフォーマンス モニター カウンターを停止します。  
  
15. 先ほど作成したテストの結果ディレクトリへのテスト データを保存します。  
  
16. 次のテストの実行のために必要なクリーンアップを実行します。  
  
 上記の手順のいずれかの各は、BizUnit を使用して自動化できます。 BizUnit は、既存のテスト ステップ資産を利用するなど、迅速かつ簡単に生成できます、自動化されたパフォーマンス テスト、BizTalk Server ソリューションをします。 パフォーマンスのための BizUnit を使用してテストを自動化することの主な利点の 1 つは、つまり、結果の分析の準備ができて毎朝夜間: テストを実行する柔軟性です。 これにより、プロジェクト チームでのパフォーマンス テストの負荷が大幅に減少します。  
  
## <a name="the-microsoft-biztalk-loadgen-2007-tool"></a>Microsoft BizTalk LoadGen 2007 ツール  
 BizTalk LoadGen 2007 ツール (LoadGen) は、ロード テストのストレスおよびパフォーマンスのテストをチームで BizTalk Server 2006 製品グループによって開発されたツールです。 LoadGen は、すばやく、簡単かつ確実に実稼働レベルのメッセージのボリュームをシミュレートするロード テストを定義するように設計されました。 LoadGen は、マルチ スレッド、構成に基づく、複数のトランスポートをサポートします。 製品の BizTalk グループを毎日; LoadGen を使用します。したがって、高度な確実なツールがある、持続性のある目的のために合わせてとさまざまな BizTalk シナリオをシミュレートすることができます。  
  
 LoadGen は 3 つの層で構成されているモジュール形式デザイン:**プレゼンテーション**、 **framework**と**コンポーネント**です。 プレゼンテーション層は、コマンド ライン ドライバーを促進するために、フレームワークで構成されます。 Framework レイヤーは、構成ファイルを読み取ります、その中に指定されたコンポーネントを実行します。 コンポーネントの層は、3 種類のコンポーネントで構成されます:**ジェネレーターを読み込めません**、**作成者をメッセージ**と**コント ローラーのスロットル**です。 これらの各コンポーネントは、独自に作成して、シナリオのニーズに対応する LoadGen に接続できるように、拡張できます。 LoadGen は、BizTalk Server の製品グループによって開発された、ために、ボックスのコンポーネントがほとんどのロード テスト要件を満たすことがあります。 これらの各コンポーネントについてより詳細には、ここで説明します。  
  
-   **ジェネレーターを読み込めません**特定のトランスポート経由でメッセージを送信する役割を担当します。 次のトランスポートは、ロード ジェネレーターが用意されています。  
  
    -   ファイル  
  
    -   HTTP  
  
    -   MQSeries  
  
    -   MSMQLarge  
  
    -   MSMQ (MSMQ)  
  
    -   SOAP  
  
    -   Web Services Enhancements (WSE)  
  
    -   Windows SharePoint Services (WSS)  
  
    -   Windows Communication Foundation (WCF)  
  
-   **メッセージの作成者**固有のデータを含むメッセージを生成する必要がある場合に使用できるオプションのコンポーネントは、します。 作成元のメッセージを使用して作成; の 2 つのモードのいずれか同期および非同期です。 同期メッセージの作成モードを指定すると場合、LoadGen は、シングル スレッドのみを使用して、各メッセージに一意のペイロードが含まれていることを確認するメッセージを作成します。 同期モードでは、各メッセージ内で一意のデータを保証、中にこのモードにはスケーラビリティが制限されます。 LoadGen は、複数の実行スレッドを使用して非同期メッセージ作成者も用意されています。これにより、LoadGen を (ためより多くのスレッドを作成することでは単に) ターゲット メッセージ レートを満たすようになります。 非同期モードでは、ランダムにデータを変更する各メッセージのメッセージの作成者を構成することがあります。 ただし、複数のスレッドを使用しているためとは限りませんが、テスト中に生成されたすべてのメッセージが一意のペイロードに含まれます。  
  
-   **コント ローラーのスロットル**によってテストの実行中にロード ジェネレーターを制御するメッセージが、安定した速度で送信されることを確認してください。 LoadGen も公開カスタム制限など、条件に基づいてメッセージのフローを制御できます。  
  
    -   フォルダー内のファイルの数  
  
    -   データベース テーブル内の行の数  
  
    -   MSMQ または MQSeries メッセージ キューの深さ  
  
 Microsoft [BizTalk LoadGen 2007 ツール](http://go.microsoft.com/fwlink/?LinkId=59841)ダウンロードは[http://go.microsoft.com/fwlink/?LinkId=59841](http://go.microsoft.com/fwlink/?LinkId=59841) (http://go.microsoft.com/fwlink/?LinkId=59841)。  
  
### <a name="sample-loadgen-configuration-file"></a>LoadGen 構成ファイルのサンプル  
 LoadGen のすべての構成情報については、xml ファイルに格納されます。 LoadGen 構成ファイルが含まれています、 \<CommonSection\> LoadGen シナリオでの LoadGen のすべてのタスクの既定の設定を構成する要素。 1 つまたは複数が、LoadGen 構成ファイルに含めることもできます\<セクション\>LoadGen の特定のタスクの構成設定を提供する要素。 内のエントリ、\<セクション\>要素で指定された既定の値を置き換える、 \<CommonSection\>要素。  
  
 これに続くサンプル LoadGen 構成ファイルでは、少し変更したバージョンの \ConfigFiles\ConsoleConfigFiles、LoadGen インストール ディレクトリのサブディレクトリに含まれている FileToFileLG.xml サンプル構成ファイルが。 このテストは、25 のメッセージを送信\<LotSizePerInterval\> 200 ミリ秒ごと\<SleepInterval\>、負荷ジェネレーターあたりのスレッド数 5 \<NumThreadsperSection\>負荷は停止されます5000 のメッセージの後にテスト\<NumFiles\>送信されました。  
  
 ファイルの制限コント ローラーがで指定された、 \<ThrottleController\>セクションです。 値は、 \<ThresholdRange\> 1000-2000、つまり C:\Scenarios\FileToFile\Receive (パラメーター) ファイルの場所が 1000 未満または 2000 では複数のファイル、制限コント ローラーは、ファイルを制限する場合に設定されています。ジェネレーターと拡大/縮小を必要に応じて読み込みます。 ファイルの場所にファイルの数になります 1000 ミリ秒ごとにチェック\<SleepInterval\>です。 \<FileSection\>要素ロード ジェネレーターによって送信されるメッセージのプロパティを定義します。 FileToFileLG.xml ファイル\<SrcFilePath\> filedrop C:\Scenarios\FileToFile\Receive に LoadGen をコピーする\<DstFilePath >。 指定された既定のトランスポートはこのため、ファイル トランスポートはここで使用、\<トランスポート名\>内の要素、 \<CommonSection\>要素。  
  
```  
<LoadGenFramework>  
   <CommonSection>  
      <LoadGenVersion>2</LoadGenVersion>  
      <OptimizeLimitFileSize>204800</OptimizeLimitFileSize>  
      <NumThreadsPerSection>5</NumThreadsPerSection>  
      <SleepInterval>200</SleepInterval>  
      <LotSizePerInterval>25</LotSizePerInterval>  
      <RetryInterval>10000</RetryInterval>  
      <StopMode Mode="Files">  
         <NumFiles>5000</NumFiles>  
      </StopMode>  
      <Transport Name="FILE">  
         <Assembly>FileTransport.dll/FileTransport.FileTransport</Assembly>  
      </Transport>  
      <ThrottleController Mode="Custom">  
         <Monitor Name="File">  
            <Assembly>FileMonitor.dll/DropLocationFileMonitor.DropLocationFileMonitor</Assembly>  
            <ThresholdRange>1000-2000</ThresholdRange>  
            <SleepInterval>1000</SleepInterval>  
            <Parameters>C:\Scenarios\FileToFile\Receive</Parameters>  
         </Monitor>  
         <ThrottleCondition>File</ThrottleCondition>  
      </ThrottleController>  
   </CommonSection>  
   <Section Name="FileSection">  
      <SrcFilePath>C:\LoadGen\ConfigFiles\ConsoleConfigFiles\FileToFileLG.xml</SrcFilePath>  
      <DstLocation>  
         <Parameters>  
            <DstFilePath>C:\Scenarios\FileToFile\Receive</DstFilePath>  
         </Parameters>  
      </DstLocation>  
   </Section>  
</LoadGenFramework>  
```  
  
### <a name="using-bizunit-to-drive-loadgen"></a>BizUnit をドライブ LoadGen を使用しました。  
 BizUnit は、 **LoadGenExecuteStep**が自動のパフォーマンスと安定性のテストを容易になります。 **TestExecution**を使用するサンプルのための BizUnit 構成ファイルのステージ**LoadGenExecuteStep**次のコード例に示します。 この手順が LoadGen 構成ファイルの場所である 1 つの構成パラメーターを受け入れることに注意してください。  
  
```  
<TestCase testName="Test_LoadGen">  
   <TestSetup>  
   </TestSetup>  
   <TestExecution>  
      <TestStep assemblyPath="" typeName="BizUnit.LoadGenExecuteStep, BizUnit.LoadGenSteps">  
         <LoadGenTestConfig>..\..\..\PerfGuideFiletoFile.xml</LoadGenTestConfig>  
      </TestStep>  
   </TestExecution>  
   <!-- Test cleanup: test cases should always leave the system in the state they found it -->  
   <TestCleanup>  
   </TestCleanup>  
</TestCase>  
```  
  
 このトピックの残りの部分では、パフォーマンスの LoadGen のテストを自動化するための BizUnit テスト ケースの構成ファイルについて説明します。  
  
> [!NOTE]  
>  この構成ファイルは、BizUnit とパフォーマンス テストの一部として LoadGen を簡単に統合するテンプレートとして使用できます。 このテスト_ケースを実行する前に、環境の構成ファイルをカスタマイズする必要があります。 カスタマイズする必要がある構成ファイルのセクションでは、それに応じて示されます。  
  
 まず始めの値を指定、 **testName** BizTalk ソリューションを適切なパラメーターです。  
  
```  
<TestCase testName="Performance-Guide-Sample-Loadgen-Test">  
```  
  
 コンテキストの変数を追加、 **TestSetup**段階です。 これらのコンテキスト変数は、テスト_ケースの全期間にわたって参照されます。 この構成ファイルを使用する指定された値を変更**TestCaseResultsDir** (C:\Dev Work\Perf ガイド Demos\PerfResults\\) および**マシン**(BIZTALKADMIN01) 一致するように、環境。  
  
```  
<TestSetup>  
   <!-- Context property: name of test run -->  
   <TestStep assemblyPath="" typeName="BizUnit.ContextManipulatorStep">  
      <ContextItem contextKey="TestRunName">  
         <ItemTest takeFromCtx="BizUnitTestCaseName"></ItemTest>  
         <ItemTest>_%DateTime%</ItemTest>  
      </ContextItem>  
   </TestStep>  
   <!-- Context property: name of test directory to store results -->  
   <TestStep assemblyPath="" typeName="BizUnit.ContextManipulatorStep">  
      <ContextItem contextKey="TestCaseResultsDir">  
         <ItemTest>C:\Dev Work\Perf Guide Demos\PerfResults\</ItemTest>  
         <ItemTest takeFromCtx="TestRunName"></ItemTest>  
      </ContextItem>  
   </TestStep>  
   <!-- Context property: perfmon log file -->  
   <TestStep assemblyPath="" typeName="BizUnit.ContextManipulatorStep">  
      <ContextItem contextKey="PerfMonFilePath">  
         <ItemTest takeFromCtx="TestCaseResultsDir"></ItemTest>  
         <ItemTest>\PerfCounters.blg</ItemTest>  
      </ContextItem>  
   </TestStep>  
   <!-- Context property: destintation for app event log on test computer -->  
   <TestStep assemblyPath="" typeName="BizUnit.ContextManipulatorStep">  
      <ContextItem contextKey="DestPath- BIZTALKADMIN01-AppEventLog">  
         <ItemTest takeFromCtx="TestCaseResultsDir"></ItemTest>  
         <ItemTest> BIZTALKADMIN01_ApplicationLog.evt</ItemTest>  
      </ContextItem>  
   </TestStep>  
   <!-- Clear the application event log on test computer -->  
   <TestStep assemblyPath="" typeName="BizUnit.EventLogClearStep">  
      <Machine>BIZTALKADMIN01</Machine>  
      <EventLog>Application</EventLog>  
   </TestStep>  
   <!-- Create the directory to save all the test results -->  
   <TestStep assemblyPath="" typeName="BizUnit.CreateDirectory">  
      <DirectoryName takeFromCtx="TestCaseResultsDir" ></DirectoryName>  
   </TestStep>  
</TestSetup>  
```  
  
 完了した後、 **TestSetup**段階では、入力、 **TestExecution**段階です。 最初の手順では、BizTalk ホスト インスタンスを停止します。 個別の**BizUnit.HostConductorStep**セクションは、個別のホスト インスタンスごとに追加する必要があります。 環境内をこの構成ファイルを使用している場合は、適切な値を入力する必要があります**HostInstanceName**、**サーバー**、**ログオン**、および**パスワード**です。  
  
```  
<TestExecution>  
   <!-- Step 1: Stop BizTalk Hosts -->  
   <TestStep assemblyPath="" typeName="BizUnit.HostConductorStep, BizUnit.BizTalkSteps">  
      <Action>stop</Action>  
      <HostInstanceName>BizTalkServerApplication</HostInstanceName>  
      <Server>BizTalkAdmin01</Server>  
      <Logon>ServerName\Administrator</Logon>  
      <PassWord>Pass@word1</PassWord>  
      <GrantLogOnAsService>true</GrantLogOnAsService>  
   </TestStep>  
```  
  
 すべてのホスト インスタンスを停止した後、bts_CleanupMsgBox を使用して、BizTalk メッセージ ボックス データベースをクリーンアップおストアド プロシージャです。 この手順を使用するには、値を変更する必要があります**ConnectionString**環境に合わせてです。  
  
```  
<!-- Step 2: Clean Up MessageBox -->  
<TestStep assemblyPath="" typeName="BizUnit.DBExecuteNonQueryStep">  
   <DelayBeforeExecution>1</DelayBeforeExecution>  
   <ConnectionString>Persist Security Info=False;Integrated Security=SSPI;database=BizTalkMsgBoxDb;server=BIZTALKADMIN01;Connect Timeout=30</ConnectionString>  
   <SQLQuery>  
      <RawSQLQuery>[dbo].[bts_CleanupMsgbox]</RawSQLQuery>  
   </SQLQuery>  
</TestStep>  
```  
  
 手順 3 の**TestExecution**段階、テンプレート ファイルで指定されているパフォーマンス モニター (PerfMon) カウンターの開始。 テンプレート ファイルの例がサンプルの下に一覧表示**BizUnit.PerfmonCountersStep**以下です。 テンプレート ファイルを使用するには、指定された値を変更する必要があります**CountersListFilePath**環境に合わせてです。 サンプル パフォーマンス モニター カウンター テンプレート ファイルを変更して監視したり、自分のシナリオに無関係なものをすべて削除したいパフォーマンス モニターのカウンターが含まれます。  
  
```  
<!-- Step 3: Start Perfmon counters -->  
<TestStep assemblyPath="" typeName="BizUnit.PerfmonCountersStep">  
   <PerfmonAction>Start</PerfmonAction>  
   <CounterSetName>PerfGuidePerfmonCounters</CounterSetName>  
   <CountersListFilePath>C:\Dev Work\Perf Guide Demos\Test_06_PerfCounters.txt</CountersListFilePath>  
   <SampleInterval>5</SampleInterval>  
   <PerfmonLogFilePath takeFromCtx="PerfMonFilePath"></PerfmonLogFilePath>  
</TestStep>  
```  
  
 **サンプル パフォーマンス モニター カウンター テンプレート ファイル (Test_06_PerfCounters.txt、BizUnit.PerfmonCountersStep によって参照される):**  
  
```  
\Processor(*)\*  
\Process(*)\*  
\Memory\*  
\PhysicalDisk(*)\*  
\System\Context Switches/sec  
\System\Processor Queue Length  
\BizTalk:FILE Receive Adapter(*)\*  
\BizTalk:File Send Adapter(*)\*  
\BizTalk:FTP Receive Adapter(*)\*  
\BizTalk:FTP Send Adapter(*)\*  
\BizTalk:HTTP Receive Adapter(*)\*  
\BizTalk:HTTP Send Adapter(*)\*  
\BizTalk:Message Agent(*)\*  
\BizTalk:Messaging(*)\*  
\BizTalk:Message Box:General Counters(*)\*  
\BizTalk:Message Box:Host Counters(*)\*  
\BizTalk:Messaging Latency(*)\*  
\BizTalk:SOAP Receive Adapter(*)\*  
\BizTalk:SOAP Send Adapter(*)\*  
\BizTalk:TDDS(*)\*  
\XLANG/s Orchestrations(*)\*  
```  
  
 ここでは、BizTalk Server ホスト インスタンスを開始します。 個別の**BizUnit.HostConductorStep**セクションは、個別のホスト インスタンスごとに追加する必要があります (distinct を含むホストの複数のインスタンスのサーバーにわたる)。 環境内をこの構成ファイルを使用している場合は、適切な値を入力する必要があります**HostInstanceName**、**サーバー**、**ログオン**、および**パスワード**です。  
  
```  
<!-- Step 4: Start BizTalk Hosts -->  
<TestStep assemblyPath="" typeName="BizUnit.BizTalkSteps.HostConductorStep, BizUnit.BizTalkSteps, Version=3.0.0.0, Culture=neutral, PublicKeyToken=7eb7d82981ae5162">  
   <Action>start</Action>  
   <HostInstanceName>BizTalkServerApplication</HostInstanceName>  
   <Server>BizTalkAdmin01</Server>  
   <Logon>ServerName\Administrator</Logon>  
   <PassWord>Pass@word1</PassWord>  
   <GrantLogOnAsService>true</GrantLogOnAsService>  
</TestStep>  
```  
  
 手順 5"primes"システム BizTalk Server を使用するいくつかのメッセージを送信することによって**BizUnit.LoadGenExecuteStep**; の値を変更、 **LoadGenTestConfig**環境と一致するパラメーターです。  
  
```  
<!-- Step 5: Send Priming messages -->  
<TestStep assemblyPath="" typeName="BizUnit.LoadGenExecuteStep, BizUnit.LoadGenSteps">  
   <LoadGenTestConfig>C:\Program Files\LoadGen\ConfigFiles\ConsoleConfigFiles\PerfGuideFiletoFile.xml</LoadGenTestConfig>  
</TestStep>  
```  
  
 手順 6 LoadGen 構成ファイルをメモリに書き込みますテストが完了すると、テスト結果のデータベースに記述し、できます。  
  
```  
  
      <!-- Step 6: Read loadgen file into context variable -->  
<TestStep assemblyPath="" typeName="BizUnit.FileReadAndLoadToContext">  
   <FilePath>C:\Program Files\LoadGen\ConfigFiles\ConsoleConfigFiles\PerfGuideFiletoFile.xml</FilePath>  
   <ContextPropertyName>LoadGenFileContent</ContextPropertyName>  
</TestStep>  
```  
  
 これでテスト結果データベースにテストの開始時刻を記述します。 変更、 **ConnectionString**と**RawSQLQuery**環境と一致するパラメーターです。  
  
```  
<!-- Step 7: Update test results DB with test start time -->  
<TestStep assemblyPath="" typeName="BizUnit.DBExecuteNonQueryStep">  
   <DelayBeforeExecution>1</DelayBeforeExecution>  
   <ConnectionString>Persist Security Info=False;Integrated Security=SSPI;database=TestResults;server=BizTalkAdmin01;Connect Timeout=30</ConnectionString>  
   <SQLQuery>  
      <RawSQLQuery>INSERT INTO tblPerformanceResults (Test_ID, StartTime,LoadGenFile) VALUES ('{0}',GetDate(),'{1}' )</RawSQLQuery>  
      <SQLQueryParams>  
         <SQLQueryParam takeFromCtx="TestRunName"></SQLQueryParam>  
         <SQLQueryParam takeFromCtx="LoadGenFileContent"></SQLQueryParam>  
      </SQLQueryParams>  
   </SQLQuery>  
</TestStep>  
```  
  
 手順 8 がある場所の実際のパフォーマンス テストを使用して開始**BizUnit.LoadGenExecuteStep**です。 この手順は、手順 5 で使用された同じ LoadGen 構成ファイルを指定し、任意の有効な LoadGen 構成ファイルを次を指定することができます。 **BizUnit.DelayStep**の時間を開始、システム経由でやり取りされるメッセージを許可する、5 秒の遅延を強制する手順 9. で使用します。 使用してホスト キューの長さを計算**BizUnit.PerMonCounterMonitorStep**です。 このパラメーターには、手順 10 で指定されている 1 の値に達すると、テストが終了します。 値を変更、 **InstanceName**と**サーバー**ホスト インスタンスと、環境内を監視するサーバーの名前に一致するパラメーターです。  
  
```  
<!-- Step 8: LoadGen: Load actual perf test -->  
<TestStep assemblyPath="" typeName="BizUnit.LoadGenSteps.LoadGenExecuteStep, BizUnit.LoadGenSteps , Version=3.0.0.0, Culture=neutral, PublicKeyToken=7eb7d82981ae5162">  
   <LoadGenTestConfig>C:\Program Files\LoadGen\ConfigFiles\ConsoleConfigFiles\PerfGuideFiletoFile.xml</LoadGenTestConfig>  
</TestStep>  
<!-- Step 9: Delay for 5 secs to allow msgs to start flowing -->  
<TestStep assemblyPath="" typeName="BizUnit.DelayStep">  
   <Delay>5000</Delay>  
</TestStep>  
<!-- Step 10: Wait for Orch Host Queue depth to reach one -->  
<TestStep assemblyPath="" typeName="BizUnit.PerfMonCounterMonitorStep">  
   <CategoryName>BizTalk:Message Box:Host Counters</CategoryName>  
   <CounterName>Host Queue - Length</CounterName>  
   <InstanceName>BizTalkServerApplication:biztalkmsgboxdb:BizTalkAdmin01</InstanceName>  
   <Server>BizTalkAdmin01</Server>  
   <CounterTargetValue>1</CounterTargetValue>  
</TestStep>  
```  
  
 使用して、テストの終了時に**BizUnit.DBExecuteNonQueryStep**をテスト結果のデータベースを更新します。 このステップの完了が、終了によって示される、テスト実行のステージの終わりを示す\</TestExecution\>タグ。 ここでも、変更する必要があります、 **ConnectionString**と**RawSQLQuery**環境と一致するパラメーターです。  
  
```  
   <!-- Step 11: Update test results DB with test stop time -->  
   <TestStep assemblyPath="" typeName="BizUnit.DBExecuteNonQueryStep">  
      <DelayBeforeExecution>1</DelayBeforeExecution>  
      <ConnectionString>Persist Security Info=False;Integrated Security=SSPI;database=TestResults;server=BIZTALKADMIN01;Connect Timeout=30</ConnectionString>  
      <SQLQuery>  
         <RawSQLQuery>UPDATE tblPerformanceResults SET EndTime = GetDate() WHERE Test_ID = '{0}'</RawSQLQuery>  
         <SQLQueryParams>  
            <SQLQueryParam takeFromCtx="TestRunName"></SQLQueryParam>  
         </SQLQueryParams>  
      </SQLQuery>  
   </TestStep>  
</TestExecution>  
```  
  
 実行のステージの終了時に、テスト クリーンアップ ステージを入力します。 このステージで使用**BizUnit.PerfmonCountersStep**前 (手順 3) で開始されたパフォーマンス モニター カウンターを停止します。  
  
```  
<TestCleanup>  
      <!-- Return system to state prior to test -->  
      <!-- Stop perfmon counters -->  
      <TestStep assemblyPath="" typeName="BizUnit.PerfmonCountersStep" failOnError="false">  
         <PerfmonAction>Stop</PerfmonAction>  
         <CounterSetName>PerfGuidePerfmonCounters</CounterSetName>  
      </TestStep>  
   </TestCleanup>  
</TestCase>  
```  
  
 この例では、BizUnit を結合してで LoadGen をパフォーマンス テストを自動化する方法を説明します。 ロード テストのための BizUnit 構成ファイルで説明されているは、機能テストと同じ方法で、Visual Studio のテスト ツールから実行できます。 この手法を採用するには、一元的に管理、管理、およびパフォーマンスのテストにデータを収集することができます。  
  
 BizUnit と LoadGen を使用して、自動化された方法で、通常の業務時間中に分析のための十分なテスト結果を提供する営業時間外の中に発生する複数のテストの実行をスケジュールする非常に簡単です。 パフォーマンス テストを自動化するときに、予期される運用メッセージ ボリュームのことを通じて、システム負荷が異なるモデルを例にすること (75%、100%、125%) のさまざまな程度をシミュレート LoadGen スクリプトの使用を検討します。 ロード テストを実行するときは、オーバー ロードまたは"無効な day"シナリオをテストする特に重要です。 システムを実稼働環境に配置する、前に、BizTalk Server 環境内の各テスト・ケースの最大スループット (MST) を知っておく必要があります。 維持可能な最大のパフォーマンスに関する詳細については、次を参照してください。[維持可能なパフォーマンスは何ですか。](http://go.microsoft.com/fwlink/?LinkID=132304) (http://go.microsoft.com/fwlink/?LinkID=132304)、BizTalk Server 2009 マニュアルを参照します。  
  
### <a name="the-complete-bizunit-loadgen-sample-configuration-file"></a>完了のための BizUnit LoadGen サンプル構成ファイル  
 次の一覧には、前出 BizUnit 構成ファイルの内容全体が含まれています。  
  
```  
<TestCase testName="Performance-Guide-Sample-Loadgen-Test">  
   <TestSetup>  
      <!-- Context property: name of test run -->  
      <TestStep assemblyPath="" typeName="BizUnit.ContextManipulatorStep">  
         <ContextItem contextKey="TestRunName">  
            <ItemTest takeFromCtx="BizUnitTestCaseName"></ItemTest>  
            <ItemTest>_%DateTime%</ItemTest>  
         </ContextItem>  
      </TestStep>  
      <!-- Context property: name of test directory to store results -->  
      <TestStep assemblyPath="" typeName="BizUnit.ContextManipulatorStep">  
         <ContextItem contextKey="TestCaseResultsDir">  
            <ItemTest>C:\Dev Work\Perf Guide Demos\PerfResults\</ItemTest>  
            <ItemTest takeFromCtx="TestRunName"></ItemTest>  
         </ContextItem>  
      </TestStep>  
      <!-- Context property: perfmon log file -->  
      <TestStep assemblyPath="" typeName="BizUnit.ContextManipulatorStep">  
         <ContextItem contextKey="PerfMonFilePath">  
            <ItemTest takeFromCtx="TestCaseResultsDir"></ItemTest>  
            <ItemTest>\PerfCounters.blg</ItemTest>  
         </ContextItem>  
      </TestStep>  
      <!-- Context property: destintation for app event log on BTSSVR-001 -->  
      <TestStep assemblyPath="" typeName="BizUnit.ContextManipulatorStep">  
         <ContextItem contextKey="DestPath-BTSSVR-001-AppEventLog">  
            <ItemTest takeFromCtx="TestCaseResultsDir"></ItemTest>  
            <ItemTest>BTSSVR-001_ApplicationLog.evt</ItemTest>  
         </ContextItem>  
      </TestStep>  
      <!-- Clear the application event log on BTSSVR-001 -->  
      <TestStep assemblyPath="" typeName="BizUnit.EventLogClearStep">  
         <Machine>BIZTALKADMIN01</Machine>  
         <EventLog>Application</EventLog>  
      </TestStep>  
      <!-- Create the directory to save all the test results -->  
      <TestStep assemblyPath="" typeName="BizUnit.CreateDirectory">  
         <DirectoryName takeFromCtx="TestCaseResultsDir" ></DirectoryName>  
      </TestStep>  
   </TestSetup>  
  
   <TestExecution>  
      <!-- Step 1: Stop BizTalk Hosts -->  
      <TestStep assemblyPath="" typeName="BizUnit.HostConductorStep, BizUnit.BizTalkSteps">  
         <Action>stop</Action>  
         <HostInstanceName>BizTalkServerApplication</HostInstanceName>  
         <Server>BizTalkAdmin01</Server>  
         <Logon>ServerName\Administrator</Logon>  
         <PassWord>Pass@word1</PassWord>  
         <GrantLogOnAsService>true</GrantLogOnAsService>  
      </TestStep>  
      <!-- Step 2: Clean Up MessageBox -->  
      <TestStep assemblyPath="" typeName="BizUnit.DBExecuteNonQueryStep">  
         <DelayBeforeExecution>1</DelayBeforeExecution>  
         <ConnectionString>Persist Security Info=False;Integrated Security=SSPI;database=BizTalkMsgBoxDb;server=BIZTALKADMIN01;Connect Timeout=30</ConnectionString>  
         <SQLQuery>  
            <RawSQLQuery>[dbo].[bts_CleanupMsgbox]</RawSQLQuery>  
         </SQLQuery>  
      </TestStep>  
      <!-- Step 3: Start Perfmon counters -->  
      <TestStep assemblyPath="" typeName="BizUnit.PerfmonCountersStep">  
         <PerfmonAction>Start</PerfmonAction>  
         <CounterSetName>PerfGuidePerfmonCounters</CounterSetName>  
         <CountersListFilePath>C:\Dev Work\Perf Guide Demos\Test_06_PerfCounters.txt</CountersListFilePath>  
         <SampleInterval>5</SampleInterval>  
         <PerfmonLogFilePath takeFromCtx="PerfMonFilePath"></PerfmonLogFilePath>  
      </TestStep>  
      <!-- Step 4: Start BizTalk Hosts -->  
      <TestStep assemblyPath="" typeName="BizUnit.BizTalkSteps.HostConductorStep, BizUnit.BizTalkSteps, Version=3.0.0.0, Culture=neutral, PublicKeyToken=7eb7d82981ae5162">  
         <Action>start</Action>  
         <HostInstanceName>BizTalkServerApplication</HostInstanceName>  
         <Server>BizTalkAdmin01</Server>  
         <Logon>ServerName\Administrator</Logon>  
         <PassWord>Pass@word1</PassWord>  
         <GrantLogOnAsService>true</GrantLogOnAsService>  
      </TestStep>  
      <!-- Step 5: Send Priming messages -->  
      <TestStep assemblyPath="" typeName="BizUnit.LoadGenExecuteStep, BizUnit.LoadGenSteps">  
         <LoadGenTestConfig>C:\Program Files\LoadGen\ConfigFiles\ConsoleConfigFiles\PerfGuideFiletoFile.xml</LoadGenTestConfig>  
      </TestStep>  
      <!-- Step 6: Read loadgen file into context variable -->  
      <TestStep assemblyPath="" typeName="BizUnit.FileReadAndLoadToContext">  
         <FilePath>C:\Program Files\LoadGen\ConfigFiles\ConsoleConfigFiles\PerfGuideFiletoFile.xml</FilePath>  
         <ContextPropertyName>LoadGenFileContent</ContextPropertyName>  
      </TestStep>  
      <!-- Step 7: Update test results DB with test start time -->  
      <TestStep assemblyPath="" typeName="BizUnit.DBExecuteNonQueryStep">  
         <DelayBeforeExecution>1</DelayBeforeExecution>  
         <ConnectionString>Persist Security Info=False;Integrated Security=SSPI;database=TestResults;server=BizTalkAdmin01;Connect Timeout=30</ConnectionString>  
         <SQLQuery>  
            <RawSQLQuery>INSERT INTO tblPerformanceResults (Test_ID, StartTime,LoadGenFile) VALUES ('{0}',GetDate(),'{1}' )</RawSQLQuery>  
            <SQLQueryParams>  
               <SQLQueryParam takeFromCtx="TestRunName"></SQLQueryParam>  
               <SQLQueryParam takeFromCtx="LoadGenFileContent"></SQLQueryParam>  
            </SQLQueryParams>  
         </SQLQuery>  
      </TestStep>  
      <!-- Step 8: LoadGen: Load actual perf test -->  
      <TestStep assemblyPath="" typeName="BizUnit.LoadGenSteps.LoadGenExecuteStep, BizUnit.LoadGenSteps , Version=3.0.0.0, Culture=neutral, PublicKeyToken=7eb7d82981ae5162">  
        <LoadGenTestConfig>C:\Program Files\LoadGen\ConfigFiles\ConsoleConfigFiles\PerfGuideFiletoFile.xml</LoadGenTestConfig>  
      </TestStep>  
      <!-- Step 9: Delay for 5 secs to allow msgs to start flowing -->  
      <TestStep assemblyPath="" typeName="BizUnit.DelayStep">  
         <Delay>5000</Delay>  
      </TestStep>  
      <!-- Step 10: Wait for Orch Host Queue depth to reach one -->  
      <TestStep assemblyPath="" typeName="BizUnit.PerfMonCounterMonitorStep">  
         <CategoryName>BizTalk:Message Box:Host Counters</CategoryName>  
         <CounterName>Host Queue - Length</CounterName>  
         <InstanceName>BizTalkServerApplication:biztalkmsgboxdb:BizTalkAdmin01</InstanceName>  
         <Server>BizTalkAdmin01</Server>  
         <CounterTargetValue>1</CounterTargetValue>  
      </TestStep>  
      <!-- Step 11: Update test results DB with test stop time -->  
      <TestStep assemblyPath="" typeName="BizUnit.DBExecuteNonQueryStep">  
         <DelayBeforeExecution>1</DelayBeforeExecution>  
         <ConnectionString>Persist Security Info=False;Integrated Security=SSPI;database=TestResults;server=BIZTALKADMIN01;Connect Timeout=30</ConnectionString>  
         <SQLQuery>  
            <RawSQLQuery>UPDATE tblPerformanceResults SET EndTime = GetDate() WHERE Test_ID = '{0}'</RawSQLQuery>  
            <SQLQueryParams>  
               <SQLQueryParam takeFromCtx="TestRunName"></SQLQueryParam>  
            </SQLQueryParams>  
         </SQLQuery>  
      </TestStep>  
   </TestExecution>  
  
   <TestCleanup>  
      <!-- Return system to state prior to test -->  
      <!-- Stop perfmon counters -->  
      <TestStep assemblyPath="" typeName="BizUnit.PerfmonCountersStep" failOnError="false">  
         <PerfmonAction>Stop</PerfmonAction>  
         <CounterSetName>PerfGuidePerfmonCounters</CounterSetName>  
      </TestStep>  
   </TestCleanup>  
</TestCase>  
```  
  
## <a name="see-also"></a>参照  
 [自動テストを容易にするための BizUnit の使用](../technical-guides/using-bizunit-to-facilitate-automated-testing.md)