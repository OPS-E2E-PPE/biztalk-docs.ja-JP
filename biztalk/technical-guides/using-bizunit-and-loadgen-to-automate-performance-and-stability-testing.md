---
title: パフォーマンスと安定性テストを自動化するための BizUnit と LoadGen を使用して |Microsoft Docs
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
ms.openlocfilehash: 84dda7f9312f92dd50138f230407c600fac27dda
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400366"
---
# <a name="using-bizunit-and-loadgen-to-automate-performance-and-stability-testing"></a>パフォーマンスと安定性テストを自動化するための BizUnit と LoadGen を使用します。
このトピックでは、BizUnit と Microsoft BizTalk LoadGen 2007 ツールを使用して、パフォーマンスと安定性は、BizTalk Server ソリューションのテストを自動化する方法について説明します。  
  
## <a name="biztalk-server-performance-testing-step-by-step"></a>BizTalk Server のパフォーマンス テスト、ステップ バイ ステップ  
 BizTalk Server パフォーマンス テストを自動化する方法を調査する前に、どのような手順は通常、パフォーマンス テストの実行を把握するのに役立ちます。 次の手順では、「標準」BizTalk Server パフォーマンスのテスト プロセスの担当者が。  
  
1. 結果とデータを収集、たとえば、イベント ログ、トレース ログ、パフォーマンス モニターのデータを格納するテスト結果ディレクトリを作成します。  
  
2. テスト環境内のすべてのサーバー上のイベント ログをオフにします。  
  
3. すべての BizTalk ホスト インスタンスを停止します。  
  
4. SOAP および HTTP 受信アダプターのハンドラーなど、BizTalk 分離ホストを実行しているすべての IIS インスタンスを停止します。  
  
5. BizTalk Server を実行しているコンピューターで使用される SQL Server のすべてのインスタンスを再起動します。  
  
6. 前のテストから残っているデータがないことを確認するメッセージ ボックス データベースをクリーンアップする次のコマンドを実行します。 これは、機能は、残っているデータは、テスト結果を傾斜でしたので重要です。  
  
7. BizTalk ホスト インスタンスを開始します。  
  
8. テスト環境ですべてのサーバー上で関連するパフォーマンス モニター カウンターを開始します。  
  
9. システム キャッシュを初期化するためにシステムで「準備」のメッセージを送信します。  
  
10. 事前通知メッセージが処理された後は、SQL Server のテスト結果のデータベースでのテストの開始時刻を追跡します。  
  
11. すべての LoadGen のテスト エージェントを起動して、パフォーマンス テストを開始します。  
  
12. テストが完了するまで待ちます – 多くの場合、これ行う体系的にホスト キューの長さなどのパフォーマンス モニター カウンターの値を測定します。  
  
13. 結果のデータベースを SQL テストでテスト終了時刻を追跡します。  
  
14. テスト環境ですべてのサーバー上で関連するパフォーマンス モニター カウンターを停止します。  
  
15. 先ほど作成したテスト結果ディレクトリには、テスト データを保存します。  
  
16. 次のテストの実行を必要なクリーンアップを実行します。  
  
    BizUnit を使用して、上記の手順のいずれかの各を自動化できます。 BizUnit は、既存のテスト ステップ資産を利用して、迅速かつ簡単に生成できます、BizTalk Server ソリューションの自動化されたパフォーマンス テストをします。 パフォーマンスのための BizUnit を使用してテストを自動化することの主な利点の 1 つは、つまり、結果は分析の準備ができて、朝に – 夜間テストを実行する柔軟性です。 これには、プロジェクト チームでのパフォーマンス テストの負担が大幅に削減されます。  
  
## <a name="the-microsoft-biztalk-loadgen-2007-tool"></a>Microsoft BizTalk LoadGen 2007 ツール  
 BizTalk LoadGen 2007 ツール (LoadGen) は、負荷テストの BizTalk Server 2006 製品 グループで、ストレスおよびパフォーマンス テスト チームによって開発されたツールです。 LoadGen は、迅速、簡単かつ確実に実稼働レベルのメッセージのボリュームをシミュレートするロード テストを定義するように設計されました。 LoadGen は、マルチ スレッド、構成主導し、複数のトランスポートをサポートします。 BizTalk 製品グループは、毎日; LoadGen を使用します。そのためことから、このツールの目的のために合わせて持続性は自信を持っていて、さまざまな BizTalk のシナリオをシミュレートするために、高度なことができます。  
  
 LoadGen は、3 つの層で構成されているモジュール形式デザインを採用しています:**プレゼンテーション**、 **framework**と**コンポーネント**します。 コマンド ライン ドライバー、フレームワークの推進を担当は、プレゼンテーション層で構成されます。 Framework 層では、構成ファイルを読み取るし、し、その中に指定されたコンポーネントを実行します。 コンポーネントの層は、3 種類のコンポーネントで構成されます:**ロード ジェネレーター**、**メッセージの作成者**と**コント ローラーのスロットル**。 これらの各コンポーネントは、独自に作成し、それらのシナリオのニーズに対応する LoadGen に接続できるように、拡張可能です。 LoadGen は、BizTalk Server 製品グループによって開発されたため、ボックスのコンポーネントがほとんどのロード テスト要件を満たすことがわかります。 詳しくは、ここでは、これらの各コンポーネントについて説明します。  
  
- **ロード ジェネレーター**は、特定のトランスポートを経由してメッセージを送信するために責任があります。 次のトランスポートは、ロード ジェネレーターが用意されています。  
  
  -   ファイル  
  
  -   HTTP  
  
  -   MQSeries  
  
  -   MSMQLarge  
  
  -   MSMQ (MSMQ)  
  
  -   SOAP  
  
  -   Web Services Enhancements (WSE)  
  
  -   Windows SharePoint Services (WSS)  
  
  -   Windows Communication Foundation (WCF)  
  
- **メッセージの作成者**は一意のデータを含むメッセージを生成する必要がある場合に使用できるオプションのコンポーネント。 メッセージの作成者は、作成; の 2 つのモードのいずれかを使用します。同期および非同期です。 同期メッセージの作成モードが指定されている場合、LoadGen は、各メッセージに一意のペイロードが含まれていることを確認するメッセージを作成する 1 つのスレッドのみを使用します。 同期モードでは、各メッセージ内で一意のデータを保証、中にこのモードにはスケーラビリティが制限されます。 LoadGen は、複数の実行スレッドを使用して非同期メッセージ作成者も用意されています。これにより、(単により多くのスレッドを作成できます) ために、対象のメッセージのレートを満たすために LoadGen できます。 非同期モードでは、各メッセージのデータをランダムに変更するメッセージの作成者を構成できます。 ただし、複数のスレッドを使用しているためとは限りませんテスト中に生成されたすべてのメッセージに一意のペイロードにが含まれます。  
  
- **コント ローラーのスロットル**によって、テストの実行中には、ロード ジェネレーターを制御する一定の速度でメッセージが送信されることを確認します。 LoadGen も公開カスタム調整などの条件に基づいてメッセージの流れを制御できます。  
  
  -   フォルダー内のファイルの数  
  
  -   データベース テーブル内の行の数  
  
  -   MSMQ または MQSeries メッセージ キューの深さ  
  
  Microsoft [BizTalk LoadGen 2007 ツール](http://go.microsoft.com/fwlink/?LinkId=59841)でダウンロードいただけます[ http://go.microsoft.com/fwlink/?LinkId=59841 ](http://go.microsoft.com/fwlink/?LinkId=59841) (http://go.microsoft.com/fwlink/?LinkId=59841)します。  
  
### <a name="sample-loadgen-configuration-file"></a>LoadGen のサンプル構成ファイル  
 すべての LoadGen の構成情報は、xml ファイルに格納されます。 LoadGen 構成ファイルの内容を\<CommonSection\> LoadGen シナリオでの LoadGen のすべてのタスクの既定の設定を構成する要素。 1 つまたは複数が、LoadGen 構成ファイルに含めることもできます\<セクション\>LoadGen の特定のタスクの構成設定を提供する要素。 内のエントリを\<セクション\>要素で指定されたすべての既定値を置き換える、 \<CommonSection\>要素。  
  
 続くサンプル LoadGen 構成ファイルは、少し変更を加えたバージョンの LoadGen のインストール ディレクトリの \ConfigFiles\ConsoleConfigFiles サブディレクトリに含まれている FileToFileLG.xml サンプル構成ファイルです。 このテストは、25 のメッセージを送信します\<LotSizePerInterval\> 200 ミリ秒ごと\<SleepInterval\>、ロード ジェネレーターあたりのスレッド数 5 \<NumThreadsperSection\>負荷は停止されます。5000 メッセージの後にテスト\<NumFiles\>送信されました。  
  
 ファイルの制限コント ローラーがで指定された、 \<ThrottleController\>セクション。 値は、 \<ThresholdRange\> C:\Scenarios\FileToFile\Receive (パラメーター) ファイルの場所が 1000 未満または 2000 では複数のファイル、制限コント ローラーは、ファイルを制限することを意味する 1000 2000 に設定されています。ジェネレーターおよび拡大/縮小は、必要に応じて読み込みます。 ファイルの場所にファイルの数になります 1000 ミリ秒ごとにチェック\<SleepInterval\>します。 \<FileSection\>要素は、ロード ジェネレーターによって送信されるメッセージのプロパティを定義します。 FileToFileLG.xml ファイル\<SrcFilePath\> filedrop C:\Scenarios\FileToFile\Receive に LoadGen によってコピーされる\<DstFilePath >。 ファイル トランスポートはこれは、既定のトランスポートで指定されたため、ここでは使用、\<トランスポート名\>内の要素、 \<CommonSection\>要素。  
  
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
  
### <a name="using-bizunit-to-drive-loadgen"></a>BizUnit をドライブ LoadGen を使用してください。  
 BizUnit は、 **LoadGenExecuteStep**自動化されたパフォーマンスと安定性テストを容易にします。 **TestExecution**使用するための BizUnit 構成ファイルのサンプルのステージ**LoadGenExecuteStep**次のコード例に示します。 この手順が LoadGen 構成ファイルの場所である 1 つの構成のパラメーターを受け入れることに注意してください。  
  
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
  
 このトピックの残りの部分では、パフォーマンスのテストを LoadGen を自動化するための BizUnit テスト_ケースの構成ファイルについて説明します。  
  
> [!NOTE]  
>  この構成ファイルは、BizUnit と LoadGen は、パフォーマンス テストの一部としてを迅速に統合するテンプレートとして使用できます。 このテスト_ケースを実行する前に、環境の構成ファイルをカスタマイズする必要があります。 カスタマイズする必要があります構成ファイルのセクションでは、適宜示されます。  
  
 まず始めの値を指定、 **testName** BizTalk ソリューションの適切なパラメーター。  
  
```  
<TestCase testName="Performance-Guide-Sample-Loadgen-Test">  
```  
  
 コンテキスト変数を追加し、 **TestSetup**ステージ。 これらのコンテキスト変数は、テスト_ケースの全期間にわたって参照されます。 この構成ファイルを使用して、指定された値を変更**TestCaseResultsDir** (C:\Dev Work\Perf ガイド Demos\PerfResults\\) と**マシン**(BIZTALKADMIN01) 一致するように、環境。  
  
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
  
 完了した後、 **TestSetup**ステージでは、入力、 **TestExecution**ステージ。 最初の手順では、BizTalk ホスト インスタンスを停止します。 個別の**BizUnit.HostConductorStep**セクションは、個別のホスト インスタンスごとに追加する必要があります。 環境内でこの構成ファイルを使用する場合も必要がありますが、適切な値を入力します**HostInstanceName**、 **Server**、**ログオン**、および**パスワード**します。  
  
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
  
 すべてのホスト インスタンスを停止した後 bts_CleanupMsgBox を使用して、BizTalk メッセージ ボックス データベースをクリーンアップするストアド プロシージャです。 この手順を使用するには、値を変更する必要があります**ConnectionString**環境と一致します。  
  
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
  
 手順 3 の**TestExecution**段階、テンプレート ファイルで指定されているパフォーマンス モニター (PerfMon) カウンターの開始。 サンプル テンプレート ファイルが、サンプルの下に表示されている**BizUnit.PerfmonCountersStep**以下。 テンプレート ファイルを使用するには、指定された値を変更する必要があります**CountersListFilePath**環境と一致します。 監視または実際のシナリオに関連のないものを削除したいパフォーマンス モニターのカウンターを含めるサンプル パフォーマンス モニター カウンター テンプレート ファイルを変更します。  
  
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
  
 これで、BizTalk Server ホスト インスタンスを開始します。 個別の**BizUnit.HostConductorStep**セクションは、個別のホスト インスタンスごとに追加する必要があります (distinct を含むホストの複数のインスタンスのサーバー間で)。 環境内でこの構成ファイルを使用する場合も必要がありますが、適切な値を入力します**HostInstanceName**、 **Server**、**ログオン**、および**パスワード**します。  
  
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
  
 手順 5"primes"システムを使用して BizTalk Server にいくつかのメッセージを送信して**BizUnit.LoadGenExecuteStep**; の値を変更、 **LoadGenTestConfig**環境に合わせてパラメーター。  
  
```  
<!-- Step 5: Send Priming messages -->  
<TestStep assemblyPath="" typeName="BizUnit.LoadGenExecuteStep, BizUnit.LoadGenSteps">  
   <LoadGenTestConfig>C:\Program Files\LoadGen\ConfigFiles\ConsoleConfigFiles\PerfGuideFiletoFile.xml</LoadGenTestConfig>  
</TestStep>  
```  
  
 手順 6 は、そのことができますしするのに書き込まれるように、テスト結果のデータベース、テストが完了すると、LoadGen 構成ファイルをメモリに書き込みます。  
  
```  
  
      <!-- Step 6: Read loadgen file into context variable -->  
<TestStep assemblyPath="" typeName="BizUnit.FileReadAndLoadToContext">  
   <FilePath>C:\Program Files\LoadGen\ConfigFiles\ConsoleConfigFiles\PerfGuideFiletoFile.xml</FilePath>  
   <ContextPropertyName>LoadGenFileContent</ContextPropertyName>  
</TestStep>  
```  
  
 今すぐテストの開始時刻を記述、テスト結果データベースにします。 変更、 **ConnectionString**と**RawSQLQuery**環境に合わせてパラメーター。  
  
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
  
 手順 8 がある場合は、実際のパフォーマンス テストを使用して開始**BizUnit.LoadGenExecuteStep**します。 この手順は、手順 5 でサポートされている同じ LoadGen 構成ファイルを指定しますが、任意の有効な LoadGen 構成ファイルをここで指定できます。 **BizUnit.DelayStep**手順 9. で時間を開始、システムを流れるメッセージを確保する 5 秒の遅延を強制するために使用します。 使用してホスト キューの長さを計算**BizUnit.PerMonCounterMonitorStep**します。 このパラメーターには、手順 10 で指定されている 1 の値に達すると、テストが終了しました。 値を変更、 **InstanceName**と**Server**環境内で監視したいサーバー、ホスト インスタンスの名前と一致するパラメーター。  
  
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
  
 使用して、テストの終了時に**BizUnit.DBExecuteNonQueryStep**テスト結果のデータベースを更新します。 終了が示すとおり、このステップの完了がテスト実行のステージでの終了を意味\</TestExecution\>タグ。 ここでも、変更する必要があります、 **ConnectionString**と**RawSQLQuery**環境に合わせてパラメーター。  
  
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
  
 実行のステージの終了時に、テストのクリーンアップのステージを入力します。 この段階で**BizUnit.PerfmonCountersStep**前 (手順 3) で開始されたパフォーマンス モニターのカウンターを停止します。  
  
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
  
 この例では、BizUnit を組み合わせる LoadGen パフォーマンス テストの自動化に使用する方法を示します。 ロード テストのための BizUnit の構成ファイルで説明されているは、機能テストと同様に、Visual Studio のテスト ツールから実行できます。 この手法を採用するには、一元的に管理、管理、およびパフォーマンス テストにデータを収集することができます。  
  
 BizUnit と LoadGen を使用して、自動化によるアプローチで、非常に簡単に通常の業務時間中に十分なテスト結果の分析を提供する時間帯の中に発生する複数のテストの実行をスケジュールになります。 パフォーマンス テスト、自動化することを検討 LoadGen スクリプトを使用してシステムを通じてさまざまなモデルを読み込みます、たとえば (75%、100% および 125%) をさまざまなレベルをシミュレートするためにすることがあります。メッセージの量が予想される稼働環境です。 ロード テストを実行する場合は、オーバー ロードまたは"無効な day"のシナリオをテストするは特に重要です。 運用環境にシステムを配置する前に、BizTalk Server 環境では、各テスト・ケースの最大持続可能スループット (MST) を知っておくべきです。 維持可能な最大のパフォーマンスの詳細については、次を参照してください[維持可能なパフォーマンスとは何ですか?。](http://go.microsoft.com/fwlink/?LinkID=132304) (http://go.microsoft.com/fwlink/?LinkID=132304) BizTalk Server 2009 ドキュメント。  
  
### <a name="the-complete-bizunit-loadgen-sample-configuration-file"></a>完了のための BizUnit LoadGen サンプル構成ファイル  
 次の一覧には、前述のための BizUnit 構成ファイルの内容全体が含まれています。  
  
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