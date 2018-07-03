---
title: テスト シナリオの概要 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cde553ad-2540-40d9-a74b-928fee873c31
caps.latest.revision: 32
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c30bf4102da74869e596af32f8c9361fc796ce7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997691"
---
# <a name="test-scenario-overview"></a>テスト シナリオの概要
このトピックでは、テスト アプリケーションの概要します。テストの使用、方法論とリストの説明を主要業績評価指標 (Kpi) は、ロード テスト中にキャプチャされます。  

## <a name="test-application"></a>アプリケーションをテストします。  
 要求-応答の同期アプリケーションは、物理ハードウェアで実行されている BizTalk Server、HYPER-V 上で実行される BizTalk Server のパフォーマンスを比較に使用されました。 このアプリケーションは、のパフォーマンスを示すために使用された、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]低待機時間に合わせて調整されているソリューションです。 低待機時間のメッセージングは、クライアントが要求を送信し、非常に短い間隔 (たとえば < 3 秒) に含まれる応答メッセージが必要ですが、オンライン バンキングなどの特定のシナリオにとって重要です。  

 次の図は、使用される、高度なアーキテクチャを示しています。 Visual Studio Team System (VSTS) 2008 Test Load Agent の起動負荷を生成する、WCF トランスポートを使用するカスタムのテスト クラス、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]このシナリオでアプリケーションの公開、Wcf-basichttp を使用して要求-応答の受信場所。 同時スレッド数の合計、VSTS 2008 Test Load Agent は、優れた柔軟性が提供するため、テスト クライアントとして使用された、送信メッセージの数を構成する機能を含むされ、要求間のスリープ間隔が送信されます。  

 VSTS 2008 Test Load Agent の複数のコンピューターは、現実世界のロード パターンをシミュレートするために連携して実行できます。 これらのテストでは、VSTS 2008 Test Load Agent のコンピューターが BizUnit 3.0 を実行していたも単一の VSTS 2008 Test Load エージェント コント ローラー コンピューターで駆動します。 一貫性のある負荷が物理および仮想の両方に送信された結果として、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューター。 VSTS 2008 Test Edition を使用して、テスト用にシミュレートされた負荷を生成する方法の詳細については、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkID=132311](http://go.microsoft.com/fwlink/?LinkID=132311)します。  

 ![アプリケーションのアーキテクチャ](../technical-guides/media/testapplicationarchitecture.gif "TestApplicationArchitecture")  
テスト アプリケーションのアーキテクチャ  

1. Wcf-basichttp または Wcf-custom 受信場所の要求-応答は、Test Load Agent のコンピューターから新しい CalculatorRequest を受信します。  

2. XML 逆アセンブラー コンポーネントは、メソッドの CalculatorRequest xml ドキュメントの内部要素を昇格させます。 メッセージ エージェントは、メッセージ ボックス データベース (BizTalkMsgBoxDb) への受信メッセージを送信します。  

3. 受信要求は、LogicalPortsOrchestration の新しいインスタンスを開始します。 このオーケストレーションは、メソッドの昇格させたプロパティを持つ CalculatorRequest メッセージを受信する、直接バインド ポートを使用して"LogicalPortsOrchestration"を = です。  

4. LogicalPortsOrchestration では、ループを使用して、操作を取得して、各アイテムの論理送信請求-応答ポートを使用して、ダウン ストリーム電卓 WCF web サービスを呼び出します。 電卓 WCF web サービスの要求メッセージはヘルパー コンポーネントを使用して作成し、MessageBox に公開します。  

5. 要求メッセージは、Wcf-basichttp 送信ポートによって使用されます。  

6. Wcf-basichttp 送信ポートを呼び出すのいずれか (加算、減算、乗算、除算)、電卓の WCF web サービスによって公開されています。  

7. 電卓 WCF web サービスは、応答メッセージを返します。  

8. 応答メッセージは、メッセージ ボックスに公開されます。  

9. LogicalPortsOrchestration 呼び出し元に応答メッセージが返されます。 オーケストレーションでは、受信 CalculatorRequest xml ドキュメント内の各操作に対してこのパターンが繰り返されます。  

10. LogicalPortsOrchestration CalculatorResponse メッセージをメッセージ ボックス データベースに発行します。  

11. 応答メッセージは、要求-応答、Wcf-basichttp 受信場所で取得されます。  

12. 応答メッセージは、ロード テスト エージェント コンピューターに返されます。  

    ロード テスト中に使用するオーケストレーションのスクリーン ショットは、以下に示します。  

> [!NOTE]  
>  わかりやすくするためには、次のようなオーケストレーションは、ロード テスト中には実際に使用されたオーケストレーションの簡略化されたバージョンです。 ロード テスト中に使用するオーケストレーションには、複数のスコープ、エラー処理ロジック、およびその他のポートの種類が含まれています。  

 ![テスト アプリケーション オーケストレーション](../technical-guides/media/logicalportsorchestration.gif "LogicalPortsOrchestration")  
テスト アプリケーション オーケストレーション  

## <a name="testing-methodology"></a>テスト方法  
 パフォーマンスをテストするには、多くのタスクで、手動で実行する場合は、繰り返し発生する、単調には、およびエラーが発生する必要があります。 テストの効率性を向上し、テストの実行の間の一貫性を維持するために[!INCLUDE[btsVStudio2008](../includes/btsvstudio2008-md.md)]テスト プロセス中に必要なタスクを自動化するための BizUnit 3.0 での Team System (VSTS) テスト Edition が使用されました。 システムに対するメッセージ負荷を生成する VSTS 2008 Test Load Agent コンピューター、テスト クライアントとして使用され、各テストの一貫性を向上させるために実行で同じメッセージ型が使用されました。 このプロセスに従うすべてのテスト実行の一貫性のある一連のデータを提供します。 BizUnit 3.0 の詳細については、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkID=85168](http://go.microsoft.com/fwlink/?LinkID=85168)します。 詳細については[!INCLUDE[btsVStudio2008](../includes/btsvstudio2008-md.md)]Team System Test Edition を参照してください[ http://go.microsoft.com/fwlink/?LinkID=141387](http://go.microsoft.com/fwlink/?LinkID=141387)します。  

 次の手順が自動化。  

- BizTalk ホストを停止します。  

- テスト ディレクトリをクリーンアップします。  

- IIS を再起動します。  

- クリーンアップ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージ ボックス データベースです。  

- [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]を再起動します。  

- イベント ログのクリアします。  

- 関連するパフォーマンス メトリックを格納すると、ログ ファイルには、各実行のテスト結果フォルダーを作成します。  

- BizTalk ホストを開始します。  

- パフォーマンス モニター カウンターを読み込みます。  

- ウォーム アップ BizTalk 環境の負荷が小さい。  

- 実行担当者から送信します。  

- 結果フォルダーには、パフォーマンス ログを書き込みます。  

- アプリケーション ログを収集し、結果フォルダーで .csv ファイルに書き込みます。  

- 統計情報、グラフ、およびレポートを生成するために収集されたパフォーマンス ログに対してパフォーマンス分析のログ (PAL) ツール、Relog と Log Parser ツールを実行します。 詳細については、PAL、Relog、および Log Parser は、次を参照してください。[付録 d: ツールのパフォーマンスを測定](../technical-guides/appendix-d-tools-for-measuring-performance.md)します。  

> [!NOTE]  
>  すべての追跡が無効にし、テスト中に、BizTalk Server SQL Server エージェント ジョブが無効にします。  

 このラボの結果のパフォーマンスの比較を提供することが確実に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]物理と HYPER-V 環境では、パフォーマンス メトリックとログが各テストの実行の 1 か所に収集されました。  

 テスト クライアントは、各テストの実行の一意の結果ディレクトリを作成に使用されました。 このディレクトリは、すべてのパフォーマンス ログ、イベント ログに含まれているし、テストに必要なデータが関連付けられています。 このアプローチでは、遡及解析前のテストの実行時に必要な情報が必要でした。 提供されています。 各テストの最後に、生データが一貫性のある結果と主要業績評価指標 (Kpi) のセットにコンパイルされました。 一貫性のある結果の収集設定物理および仮想のマシンを別のテストの実行や異なる環境間で必要な比較のポイントを提供します。 含まれるデータが収集されます。  

- **環境 –** 物理ハードウェア上の BizTalk Server または HYPER-V での BizTalk Server のいずれかに対して、テストの実行されている環境を記録します。  

- **テスト実行の数 –** 各テストの実行を一意に識別するには  

- **テスト ケース –** テスト中に使用される BizTalk Server ソリューションのアーキテクチャを記録します。 (インラインを使用するオーケストレーションと論理ポートとオーケストレーションの送信など)  

- **日付-** 実行された日付を記録し、テストするには  

- **時間の開始 –** が開始した最初の VSTS ロード テスト エージェントによって報告されました。  

- **時間の停止 –** を完了する最後の VSTS のロード テスト エージェントによって報告されました。  

- **テスト継続時間を分単位 –** テストの期間を記録します。  

- **合計-で送信されたメッセージ**テスト中に、BizTalk Server コンピューターにロード エージェント コンピューターから送信されたメッセージの合計数を記録します。  

- **1 秒あたりに送信されたメッセージ**テスト中に BizTalk Server コンピューターにロード エージェント コンピューターからの 1 秒間送信メッセージを記録します。  

- **– クライアントの待機時間の平均**Test Load Agent のクライアントがへの要求を開始し、ロード テスト中に、BizTalk Server コンピューターからの応答を受け取りました間の時間の平均値を記録します。  

- **要求-応答の期間平均 (ミリ秒) –** によって報告された、 **BizTalk: メッセージング Latency\Request-応答の待機時間 (秒)** BizTalkServerIsolatedHost のパフォーマンス モニター カウンター  

  > [!NOTE]  
  >  複数の仮想化された BizTalk ホストが実行されているこれらのカウンターの平均として計算される、ログから使用されました。  

- **1 秒間 – オーケストレーション完了**によって報告された、 **xlang/s Orchestrations (BizTalkServerApplication) \Orchestrations が 1 秒あたりに完了した**パフォーマンス モニター カウンター。 このカウンターのスループットの効果的な手段を提供する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソリューション。  

- **メッセージ処理の < 3 秒 – %** テスト中に 3 秒以内に処理されるメッセージの合計数を記録します。  

  VSTS 2008 のロード テストは、すべてのテスト全体で一貫性のある負荷の生成に使用されました。 次のテストの実行設定と、ロード パターンは、各テストのロード プロファイルを調整するテスト中に変更されました。  

- **テストの実行設定**  

   次のテストの実行設定は、実行中のテストによって変更されました。  

  - **実行の継続時間 –** テストの実行時間を指定します。  

    ![テストの実行設定](../technical-guides/media/wcfloadtestrunsettings.gif "WCFLoadTestRunSettings")  
    テスト実行設定  

- **テスト パターン設定**  

   実行中のテストによって、次のテスト パターン設定が変更されました。  

  1. **パターン:** ロード テスト中に、シミュレートされたユーザー ロードを調整する方法を指定します。 ロード パターンは**定数**、**手順**、または**目標**ベースします。 すべてのロード テスト、定数または手順のいずれかが実行されます。  

     > [!NOTE]
     >  このガイドの目的で使用されるいずれかを実行するすべてのテスト、**定数**ロード パターンまたは**手順**ロード パターン。 持続ロード パターンとステップ ロード パターンは、次の機能を提供します。  
     > 
     > - **持続ロード パターン –** ロード パターンが、同じテストの実行中には、シミュレートされたユーザーの数が定義済みのレベルで開始し、変更されません。  
     >   -   **ステップ ロード パターン –** テストの実行中のロード パターンの増加は、シミュレートされたユーザーの数が定義済みのレベルで開始して、テストの実行中、定義済みの量によって事前定義された間隔で増加します。  

  2. **持続ユーザー カウント (定数ロード パターン) –** Visual Studio ロード テスト プロジェクトの app.config ファイルで指定されたエンドポイントのアドレスに対する負荷を生成する仮想ユーザーの数。 この値は、ロード テストに使用されるロード パターン設定で指定されます。  

  3. **初期のユーザー カウント (ステップ ロード パターン) –** ステップ ロード パターン テストの先頭に指定したエンドポイント アドレスに対する負荷を生成する仮想ユーザーの数。 この値は、ロード テストに使用されるロード パターン設定で指定されます。  

  4. **最大ユーザー カウント (ステップ ロード パターン) –** ステップ ロード パターン テストの最後に、指定したエンドポイント アドレスに対する負荷を生成する仮想ユーザーの数。 この値は、ロード テストに使用されるロード パターン設定で指定されます。  

  5. **ステップ実行間隔 (ステップ ロード パターン) –** 仮想ユーザーが指定されたエンドポイントのアドレスをロード テストのステップに対する負荷を生成している秒数。  

  6. **ユーザー カウントのステップ (ステップ ロード パターン) –** ステップ ロード パターンを使用する場合は、各ステップで増加する仮想ユーザーの数。  

     ![テスト パターン設定](../technical-guides/media/wcfloadtestpatternsettings.gif "WCFLoadTestPatternSettings")  
     テスト パターン設定  

  ロード テストの操作の詳細については[!INCLUDE[btsVStudio2008](../includes/btsvstudio2008-md.md)]を参照してください**ロード テストの操作**で、 [!INCLUDE[btsVStudio2008](../includes/btsvstudio2008-md.md)] Team System のドキュメントで[ http://go.microsoft.com/fwlink/?LinkId=141486](http://go.microsoft.com/fwlink/?LinkId=141486)します。  

## <a name="key-performance-indicators-measured-during-testing"></a>テスト時に測定された主要業績評価指標  
 次のパフォーマンス モニターのカウンターは、すべてのテスト実行の主要業績評価指標 (KPI) としてキャプチャされました。  

> [!NOTE]  
>  パフォーマンス モニター カウンターでパフォーマンスの評価に関する詳細については、次を参照してください。[チェックリスト: Hyper-v のパフォーマンスを測定する](../technical-guides/checklist-measuring-performance-on-hyper-v.md)します。  

 **BizTalk Server KPI**  

- **1 秒あたりに処理されたドキュメント**によって測定される、 **BizTalk: メッセージング ドキュメント処理数/秒**カウンター。  

- **待機時間 –** VSTS 2008 ロード テスト コント ローラーによって返されるを測定します。  

  **SQL Server KPI**  

- **SQL Server のプロセッサ使用率 –** によって測定される、 **SQL\Processor(Total)\\% Processor Time**カウンター。 このカウンターの CPU 使用率を測定する[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]の処理、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]コンピューター。  

- **Transact SQL コマンドの処理のパフォーマンス –** によって測定される、 **\SQL Server:SQL Statistics\Batch 要求数/秒**カウンター。 このカウンターは、1 秒あたりに受信した TRANSACT-SQL コマンド バッチの数を測定します。 このカウンターを使用してでスループットを測定する、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]コンピューター。  

  **KPI のネットワーク**  

- **BizTalk Server のネットワーク スループット –** によって測定される、 **\Network Interface (\*) \Bytes total/sec**でパフォーマンス モニター カウンター、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューター。  

- **SQL Server ネットワークのスループット –** によって測定される、 **SQL Network interface \bytes total/sec (Avg)** VSTS 2008 ロード テスト コント ローラーによって返されます。  

  **KPI のメモリ**  

- **使用可能なメモリは –** によって測定される、 **\Memory\Available Mbytes**さまざまなシナリオのためのカウンター。  

## <a name="physical-infrastructure-specifics"></a>物理インフラストラクチャの詳細  
 各インストールされたサーバーに対して次の設定を調整されました。  

 **すべてのサーバー。**  

- ページング ファイルは、割り当てられた物理メモリのサイズの 1.5 倍に設定されました。 ページング ファイルは、初期サイズと最大値はでした (mb) と同じことを確認して、固定サイズに設定されました。  

- 高度なシステムのプロパティ 画面から「最高のパフォーマンスの調整をする」のパフォーマンス オプションが選択されました。  

- これには、システムのプロパティのパフォーマンス オプション セクションではバック グラウンド サービスの最適なパフォーマンス、システムが調整されたことが検証されました。  

- [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] 各仮想マシンのゲスト オペレーティング システムとしてインストールされました。  

- Windows 更新プログラムは、最新のセキュリティ更新プログラムをインストールするためのすべてのサーバーで正常に実行されました。  

  **SQL server:**  

- SQL Server のインストールで使用可能なインストール ガイドに従って[ http://go.microsoft.com/fwlink/?LinkId=141021](http://go.microsoft.com/fwlink/?LinkId=141021)します。  

- [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 使用される SAN Lun を構成した次の表に従ってします。 データベースとログ ファイルは、可能なディスク I/O の競合を軽減するには、次のように、Lun に分けてください。  

  - メッセージ ボックス データベースと TempDb データベースを除くすべてのデータベース ファイル (システムと BizTalk データベースを含む) を格納する Data_Sys ボリュームが使用されました。  

  - Log_Sys ボリュームは、すべてのログ ファイルの格納に使用された (システムを含むと[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース)、メッセージ ボックス データベースと TempDb データベースを除きます。  

  - Data_TempDb ボリュームは、TempDb データベース ファイルの格納に使用されました。  

  - Logs_TempDb ボリュームは、TempDb のログ ファイルの格納に使用されました。  

  - Data_BtsMsgBox ボリュームに格納されたメッセージ ボックス データベースのファイルとログ ファイルが Log_BtsMsgBox ボリュームに保存されていた。  

- さらに、個別の LUN が指定されて、MSDTC ログ ファイル。 BizTalk システムを高スループットでは、MSDTC ログ ファイルの動作が示されている I/O のボトルネックが発生する場合は、オペレーティング システムと同じ物理ドライブに残ります。  


  |      ボリューム名      |               [ファイル]               | LUN サイズ (GB) | ホスト パーティション サイズ (GB) | クラスター サイズ |
  |-----------------------|-----------------------------------|-------------|------------------------|--------------|
  |       Data_Sys        |    マスターおよび MSDB のデータ ファイル    |     10      |           10           |     64 KB     |
  |       Logs_Sys        |     MASTER および MSDB のログ ファイル     |     10      |           10           |     64 KB     |
  |      Data_TempDb      |         TempDB データ ファイル          |     50      |           50           |     64 KB     |
  |      Logs_TempDb      |          TempDB ログ ファイル          |     50      |           50           |     64 KB     |
  |    Data_BtsMsgBox     |     BizTalkMsgBoxDb データ ファイル     |     300     |          100           |     64 KB     |
  |    Logs_BtsMsgBox     |     BizTalkMsgBoxDb ログファイル      |     100     |          100           |     64 KB     |
  | Data_BAMPrimaryImport |    BAMPrimaryImport のデータ ファイル     |     10      |           10           |     64 KB     |
  | Logs_BAMPrimaryImport |     BAMPrimaryImport のログ ファイル     |     10      |           10           |     64 KB     |
  | Data_BizTalkDatabases | その他の BizTalk データベースのデータ ファイル |     20      |           20           |     64 KB     |
  | Logs_BizTalkDatabases | その他の BizTalk データベースのログ ファイル  |     20      |           20           |     64 KB     |
  |          なし          |          MSDTC ログ ファイル           |      5      |           5            |     なし      |


- BizTalk Server のインストールで使用可能なインストール ガイドに従って[ http://go.microsoft.com/fwlink/?LinkId=128383](http://go.microsoft.com/fwlink/?LinkId=128383)します。  

- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ベスト プラクティス アナライザー (BPA) ツールを使用すると、システムが構成されているプラットフォームの検証を実行します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] BPA は、「 [ http://go.microsoft.com/fwlink/?LinkId=67150](http://go.microsoft.com/fwlink/?LinkId=67150)します。  

## <a name="virtualization-specifics"></a>仮想化の詳細  
 1 つ、50 GB の VHD を固定は、各 HYPER-V 仮想マシンのオペレーティング システムをホストに使用されました。  

 容量固定の Vhd は、すぐに、VHD がホストされているドライブ上のファイルへの最大の記憶域の割り当てがあるために、動的なサイズの Vhd の代わりに使用されました。 これにより、ディスク I/O パフォーマンスが向上しますがホストされている物理ドライブで発生している VHD ファイルの断片化が軽減されます。  

 セットアップに仮想マシンのインストール[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]1 つの VHD で 64 ビット エディションが実行されました。 すべての適切な更新プログラムをインストールすると、基本の仮想マシン イメージを作成したと共にインストールされている sysprep ユーティリティを使用して[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]、%WINDIR%\system32\sysprep ディレクトリにします。  

 このベース VHD が、コピーされ、環境間でデプロイされたすべての HYPER-V 仮想マシンの基礎として使用します。 前に、システムのセキュリティ識別子をリセットするベース VHD イメージで Sysprep が実行された[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]または[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]バイナリは、システムに配置されました。  

> [!NOTE]
>  Sysprep を実行している BizTalk Server にインストールされ、サーバーで構成した後は、Sysprep 応答ファイルおよび BizTalk Server に付属のスクリプトを使用して実現できます。 これらのサンプル スクリプトが BizTalk Server の 32 ビットおよび 64 ビット バージョンのインストールで使用するために設計された[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]のみです。 詳細については、BizTalk Server のオンライン ドキュメントを参照してください。  

 無人 Windows セットアップのリファレンスについては、「 [ http://go.microsoft.com/fwlink/?LinkId=142364](http://go.microsoft.com/fwlink/?LinkId=142364)します。  

## <a name="see-also"></a>参照  
 [付録 C: BizTalk Server と SQL Server の Hyper-V のサポート性](../technical-guides/appendix-c-biztalk-server-and-sql-server-hyper-v-supportability.md)