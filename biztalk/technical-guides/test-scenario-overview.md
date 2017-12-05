---
title: "テスト シナリオの概要 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cde553ad-2540-40d9-a74b-928fee873c31
caps.latest.revision: "32"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86fd882f89caee27211c03a4e13e617fe12faef1
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="test-scenario-overview"></a>テスト シナリオの概要
このトピックでは、テスト アプリケーションの概要テスト手法の使用、およびリストの説明、主要業績評価指標 (Kpi) は、ロード テスト中にキャプチャされます。  
  
## <a name="test-application"></a>アプリケーションをテストします。  
 要求-応答の同期アプリケーションは、物理ハードウェア上で実行されている BizTalk Server に HYPER-V で実行されている BizTalk Server のパフォーマンスの比較に使用されました。 このアプリケーションは、のパフォーマンスを説明するために使用された、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]低待機時間の調整されているソリューションです。 低待機時間のメッセージングは、クライアントが要求を送信し、非常に短い間隔 (たとえば < 3 秒) に含まれる応答メッセージが必要ですが、オンライン バンキングなどの特定のシナリオにとって重要です。  
  
 次の図は、使用する高レベルなアーキテクチャを示しています。 Visual Studio Team System (VSTS) 2008 のテストをロード エージェントに負荷を生成する、WCF トランスポートを使用するカスタムのテスト クラスが呼び出される[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]このシナリオでのアプリケーションが公開される要求-応答受信場所が Wcf-basichttp を使用しています。 VSTS 2008 Test Load Agent は、柔軟で提供されるため、テスト用クライアントとして使用された、メッセージの数を構成する機能を含めの総数に対する同時スレッドは、送受信要求間スリープ状態の間隔の送信です。  
  
 いくつかの VSTS 2008 Test Load Agent コンピューターは、現実世界のロード パターンをシミュレートするために並行して実行できます。 これらのテストでは、VSTS 2008 Test Load Agent コンピューターに起因 BizUnit 3.0 にも実行されていた 1 台の VSTS 2008 テスト ロード エージェント コント ローラー コンピューター。 その結果、一貫した負荷が物理と仮想の両方に送信されました[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューター。 VSTS 2008 Test Edition を使用して、テスト用にシミュレートされた負荷を生成する方法の詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkID=132311](http://go.microsoft.com/fwlink/?LinkID=132311)です。  
  
 ![アプリケーション アーキテクチャ](../technical-guides/media/testapplicationarchitecture.gif "TestApplicationArchitecture")  
アプリケーション アーキテクチャをテストします。  
  
1.  Wcf-basichttp または Wcf-custom 受信場所の要求-応答は、Test Load Agent コンピューターから新しい CalculatorRequest を受信します。  
  
2.  XML 逆アセンブラー コンポーネントは、CalculatorRequest xml ドキュメント内のメソッドの要素を昇格させます。 メッセージ エージェントは、メッセージ ボックス データベース (BizTalkMsgBoxDb) に着信メッセージを送信します。  
  
3.  受信要求は、LogicalPortsOrchestration の新しいインスタンスを開始します。 このオーケストレーションは、メソッドの昇格させたプロパティを持つ CalculatorRequest メッセージを受信する、直接バインド ポートを使用して"LogicalPortsOrchestration"を = です。  
  
4.  LogicalPortsOrchestration では、ループを使用して、操作を取得して、各項目の論理送信請求-応答ポートを使用して、ダウン ストリーム電卓 WCF web サービスを呼び出します。 電卓 WCF web サービスの要求メッセージはヘルパー コンポーネントを使用して作成し、MessageBox に公開します。  
  
5.  Wcf-basichttp 送信ポートで要求メッセージが消費されます。  
  
6.  Wcf-basichttp 送信ポートを呼び出すのいずれか (加算、減算、乗算、除算)、電卓 WCF web サービスによって公開されています。  
  
7.  電卓 WCF web サービスでは、応答メッセージを返します。  
  
8.  応答メッセージは、メッセージ ボックス データベースに発行されます。  
  
9. LogicalPortsOrchestration 呼び出し元には、応答メッセージが返されます。 オーケストレーションでは、受信 CalculatorRequest xml ドキュメント内の各操作にこのパターンが繰り返されます。  
  
10. LogicalPortsOrchestration CalculatorResponse メッセージをメッセージ ボックス データベースに発行します。  
  
11. 応答メッセージは、要求-応答、Wcf-basichttp 受信場所で取得されます。  
  
12. 応答メッセージには、ロード テスト エージェント コンピューターが返されます。  
  
 ロード テスト中に使用するオーケストレーションのスクリーン ショットを次に示します。  
  
> [!NOTE]  
>  わかりやすくするため、ロード テスト中に使用された実際には、オーケストレーションの簡素化されたバージョンは次に示すオーケストレーションです。 ロード テスト中に使用するオーケストレーションには、複数のスコープ、エラー処理ロジック、およびその他のポートの種類が含まれています。  
  
 ![テスト アプリケーション オーケストレーション](../technical-guides/media/logicalportsorchestration.gif "LogicalPortsOrchestration")  
テスト アプリケーション オーケストレーション  
  
## <a name="testing-methodology"></a>テスト方法  
 パフォーマンス テストするには、多くのタスクで、手動で実行する場合は、反復的な単調、およびエラーが発生する必要があります。 テストの効率を向上し、テストの実行の間の一貫性を確保するために[!INCLUDE[btsVStudio2008](../includes/btsvstudio2008-md.md)]テスト プロセス中に必要なタスクを自動化する BizUnit 3.0 では Team System (VSTS) テスト Edition が使用されました。 システムに対するメッセージ負荷を生成する VSTS 2008 Test Load Agent コンピューター、テスト用クライアントとして使用され、各テストの一貫性を向上させるために実行で、同じメッセージ型が使用されました。 このプロセスに従うすべてのテスト実行の一貫性のある一連のデータを提供します。 BizUnit 3.0 の詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkID=85168](http://go.microsoft.com/fwlink/?LinkID=85168)です。 詳細については[!INCLUDE[btsVStudio2008](../includes/btsvstudio2008-md.md)]Team System テスト Edition を参照してください[http://go.microsoft.com/fwlink/?LinkID=141387](http://go.microsoft.com/fwlink/?LinkID=141387)です。  
  
 次の手順が自動化されました。  
  
-   BizTalk ホストを停止します。  
  
-   テスト ディレクトリをクリーンアップします。  
  
-   IIS を再起動します。  
  
-   クリーンアップ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージ ボックス データベースです。  
  
-   [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]を再起動します。  
  
-   イベント ログのクリアします。  
  
-   関連するパフォーマンス メトリックを保存し、ログ ファイルを実行するたびにテスト結果フォルダーを作成します。  
  
-   BizTalk ホストを起動します。  
  
-   パフォーマンス モニター カウンターを読み込みます。  
  
-   ウォーム アップの負荷が小規模の BizTalk 環境。  
  
-   実行担当者によって送信されます。  
  
-   結果のフォルダーには、パフォーマンス ログを書き込みます。  
  
-   アプリケーション ログを収集し、結果フォルダーで .csv ファイルに書き込みます。  
  
-   統計情報、グラフ、およびレポートを生成するために収集されたパフォーマンス ログに対してパフォーマンス分析のログ (PAL) のツール、Relog とログ パーサーのツールを実行します。 PAL、Relog、およびログ パーサーの詳細については、次を参照してください。[付録 d: ツールのパフォーマンスの測定](../technical-guides/appendix-d-tools-for-measuring-performance.md)です。  
  
> [!NOTE]  
>  すべての追跡が無効になり、テスト中に、BizTalk Server SQL Server エージェント ジョブが無効になっています。  
  
 この演習の結果がのパフォーマンスの比較を提供できることを確認する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が物理的な HYPER-V 環境で、パフォーマンス メトリック、ログがテストの実行ごとに 1 か所に収集されました。  
  
 各テストの実行の一意の結果ディレクトリを作成、テスト用クライアントが使用されました。 このディレクトリは、すべてのパフォーマンス ログとイベント ログが含まれているし、テストに必要なデータが関連付けられています。 このアプローチには、以前のテストの振り返り分析の実行時に必要な情報が必要でしたが用意されています。 各テストの最後に、生データが一貫性のある結果と主要業績評価指標 (Kpi) のセットにコンパイルされました。 別のテストの実行や異なる環境間で必要な比較のポイントを指定された物理および仮想のマシンの設定一貫性のある結果を収集します。 含まれるデータが収集されます。  
  
-   **環境 –** 、物理ハードウェア上の BizTalk Server または HYPER-V での BizTalk Server のいずれかに対して、テストの実行されている環境を記録します。  
  
-   **テスト実行の数:**各テストの実行を一意に識別するには  
  
-   **テスト ケース –**テスト中に使用される BizTalk Server ソリューションのアーキテクチャを記録します。 (たとえばインラインを使用するオーケストレーションと論理ポートをオーケストレーションに送信する)  
  
-   **日付-**記録された日付と時刻のテストを実行  
  
-   **時刻 – 開始**開始される最初の VSTS ロード テスト エージェントによって報告されました。  
  
-   **時刻の停止 –**を完了する最後の VSTS ロード テスト エージェントによって報告されました。  
  
-   **テスト期間 (分) –**テストの期間を記録します。  
  
-   **合計-で送信されたメッセージ**テスト中に、BizTalk Server コンピューターにロード エージェント コンピューターから送信されたメッセージの合計数を記録します。  
  
-   **– 1 秒あたりに送信されたメッセージ**から送信された 1 秒あたりロード エージェント コンピューターを BizTalk Server コンピューターにテスト中にメッセージを記録します。  
  
-   **クライアントの待機時間: 平均**ロード エージェントのテスト クライアントに要求を開始したし、ロード テスト中に、BizTalk Server コンピューターからの応答を受け取りました間の時間の平均値を記録します。  
  
-   **要求-応答の期間平均 (ms) –**によって報告された、 **BizTalk: メッセージング Latency\Request-応答の待機時間 (秒)** BizTalkServerIsolatedHost のパフォーマンス モニター カウンター  
  
    > [!NOTE]  
    >  複数の仮想化された BizTalk ホストが実行されているこれらのカウンターの平均として計算されるログからが使用されました。  
  
-   **1 秒間 – オーケストレーション完了**によって報告された、 **xlang/s Orchestrations (BizTalkServerApplication) \Orchestrations が 1 秒あたりに完了した**パフォーマンス モニター カウンターです。 このカウンターは、のスループットのよい尺度、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソリューションです。  
  
-   **< 3 秒 – メッセージ処理の %**テスト中に 3 秒以内に処理されるメッセージの合計数を記録します。  
  
 VSTS 2008 ロード テストは、すべてのテスト全体で一貫した負荷の生成に使用されました。 次のテストの実行設定と、ロード パターンは、各テストのロード プロファイルを調整するテスト中に変更されました。  
  
-   **テストの実行設定**  
  
     次のテストの実行設定は、実行されているテストによって変更されました。  
  
    -   **実行の継続時間:**テストの実行時間を指定します。  
  
     ![テストの実行設定](../technical-guides/media/wcfloadtestrunsettings.gif "WCFLoadTestRunSettings")  
テスト実行設定  
  
-   **テスト パターン設定**  
  
     次のテスト パターン設定は、実行されているテストによって変更されました。  
  
    1.  **パターン:**ロード テスト中に、シミュレートされたユーザー ロードを調整する方法を指定します。 ロード パターンは、いずれかの**定数**、**ステップ**、または**目標**ベースです。 すべてのロード テスト、定数または手順のいずれかが実行されます。  
  
        > [!NOTE]  
        >  このガイドの目的で使用されるいずれかのすべてのテストの実行、**定数**ロード パターン、または**ステップ**ロード パターンです。 持続ロード パターン、およびステップ ロード パターンは、次の機能を提供します。  
        >   
        >  -   **持続ロード パターン –**ロード パターンが、同じテストの実行中には、シミュレートされたユーザーの数は、定義済みのレベルで開始しては変わりません。  
        > -   **ステップ ロード パターン –**ロード パターンがテストの実行中に増加しました。 シミュレートされたユーザーの数が定義済みのレベルで開始するとはずつ事前定義された事前定義された間隔で、テストの実行中です。  
  
    2.  **ユーザー数の定数 (定数ロード パターン) –** Visual Studio ロード テスト プロジェクトの app.config ファイルで指定されたエンドポイントのアドレスに対する負荷を生成している仮想ユーザーの数。 この値は、ロード テストに使用されるロード パターン設定で指定されます。  
  
    3.  **初期のユーザー カウント (ステップ ロード パターン) –**テストのステップ ロード パターンの先頭に指定したエンドポイント アドレスに対する負荷を生成している仮想ユーザーの数。 この値は、ロード テストに使用されるロード パターン設定で指定されます。  
  
    4.  **最大ユーザー カウント (ステップ ロード パターン) –**テストのステップ ロード パターンの末尾に指定したエンドポイント アドレスに対する負荷を生成している仮想ユーザーの数。 この値は、ロード テストに使用されるロード パターン設定で指定されます。  
  
    5.  **ステップ実行間隔 (ステップ ロード パターン) –**仮想ユーザーがロード テストのステップの指定したエンドポイント アドレスに対する負荷を生成する秒数。  
  
    6.  **ユーザー カウントのステップ (ステップ ロード パターン) –**ステップ ロード パターンを使用する場合は、各ステップで増加する仮想ユーザーの数。  
  
     ![テスト パターン設定](../technical-guides/media/wcfloadtestpatternsettings.gif "WCFLoadTestPatternSettings")  
テスト パターン設定  
  
 ロード テストでの操作の詳細については[!INCLUDE[btsVStudio2008](../includes/btsvstudio2008-md.md)]、トピックを参照して**ロード テストの操作**で、 [!INCLUDE[btsVStudio2008](../includes/btsvstudio2008-md.md)] Team System のマニュアル[http://go.microsoft.com/fwlink/?LinkId=141486](http://go.microsoft.com/fwlink/?LinkId=141486)です。  
  
## <a name="key-performance-indicators-measured-during-testing"></a>テスト中に測定する主要業績評価指標  
 次のパフォーマンス モニター カウンターは、すべてのテスト実行の主要業績評価指標 (KPI) としてキャプチャされました。  
  
> [!NOTE]  
>  パフォーマンス モニター カウンターでのパフォーマンスの評価の詳細については、次を参照してください。[チェックリスト: Hyper-v でのパフォーマンスの測定](../technical-guides/checklist-measuring-performance-on-hyper-v.md)です。  
  
 **BizTalk Server KPI**  
  
-   **– 1 秒あたりに処理されたドキュメント**によって測定される、 **BizTalk: メッセージング ドキュメント処理数/秒**カウンターです。  
  
-   **待機時間:** VSTS 2008 ロード テスト コント ローラーによって返されるを測定します。  
  
 **SQL Server KPI**  
  
-   **SQL Server のプロセッサ使用率 –**によって測定される、 **SQL\Processor(Total)\\% Processor Time**カウンターです。 このカウンターの CPU 使用率を測定する[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]に処理を[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]コンピューター。  
  
-   **Transact SQL コマンドの処理パフォーマンス –**によって測定される、 **\SQL Server:SQL Statistics\Batch 要求数/秒**カウンターです。 このカウンターは、1 秒あたりに受信した TRANSACT-SQL コマンド バッチの数を計測します。 このカウンターを使用してのスループットを測定する、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]コンピューター。  
  
 **KPI のネットワーク**  
  
-   **BizTalk Server ネットワークのスループット:**によって測定される、 **\Network インターフェイス (\*) \Bytes total/sec**でパフォーマンス モニター カウンター、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューター。  
  
-   **SQL Server ネットワークのスループット:**によって測定される、 **SQL Network interface \bytes total/sec (Avg)** VSTS 2008 ロード テスト コント ローラーによって返されます。  
  
 **KPI のメモリ**  
  
-   **使用可能なメモリ –**によって測定される、 **\Memory\Available Mbytes**カウンター、さまざまなシナリオをします。  
  
## <a name="physical-infrastructure-specifics"></a>物理インフラストラクチャの詳細  
 各インストールされたサーバーに対して、次の設定が調整されます。  
  
 **すべてのサーバー。**  
  
-   ページング ファイルは、割り当てられた物理メモリのサイズの 1.5 倍に設定されました。 ページング ファイルは、初期サイズと最大値は mb 単位で同一ことにより、固定サイズに設定されました。  
  
-   高度なシステムのプロパティ 画面から「最適なパフォーマンスを調整する」のパフォーマンス オプションが選択されました。  
  
-   システムが最適なパフォーマンスをシステムのプロパティの [パフォーマンス オプション] セクションでバック グラウンド サービスの調整されたことが確認されました。  
  
-   [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]各仮想マシンのゲスト オペレーティング システムにインストールされました。  
  
-   Windows Update は、最新のセキュリティ更新プログラムをインストールするためのすべてのサーバーで正常に実行されました。  
  
 **SQL server:**  
  
-   SQL Server のインストールで使用可能なインストール ガイドに従って[http://go.microsoft.com/fwlink/?LinkId=141021](http://go.microsoft.com/fwlink/?LinkId=141021)です。  
  
-   [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]使用の SAN Lun 構成いた次の表に従ってします。 Lun を可能なディスク I/O の競合を減らすために次のようにわたってを区切った、データベースとログ ファイル。  
  
    -   Data_Sys ボリュームは、メッセージ ボックス データベースと TempDb データベースを除くすべてのデータベース ファイル (システムと BizTalk データベースを含む) を格納する使用されました。  
  
    -   Log_Sys ボリュームは、すべてのログ ファイルの保存に使用された (システムを含むと[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース)、メッセージ ボックス データベースと TempDb データベースを除きます。  
  
    -   Data_TempDb ボリュームは、TempDb データベース ファイルの格納に使用されました。  
  
    -   TempDb ログ ファイルを格納する Logs_TempDb ボリュームが使用されました。  
  
    -   Data_BtsMsgBox ボリュームで、メッセージ ボックス データベース ファイルが格納されているし、ログ ファイルが Log_BtsMsgBox ボリュームに格納されています。  
  
-   さらに、個別の LUN が指定されて、MSDTC ログ ファイルの。 高スループット BizTalk システムで、MSDTC ログ ファイルのアクティビティが表示する I/O のボトルネックが発生する場合は、オペレーティング システムと同じ物理ドライブにはそのままにします。  
  
    |ボリューム名|[ファイル]|LUN サイズ (GB)|ホスト パーティション サイズ (GB)|クラスターのサイズ|  
    |-----------------|-----------|-----------------|----------------------------|------------------|  
    |Data_Sys|マスターおよび MSDB のデータ ファイル|10|10|64 KB|  
    |Logs_Sys|MASTER および MSDB のログ ファイル|10|10|64 KB|  
    |Data_TempDb|TempDB データ ファイル|50|50|64 KB|  
    |Logs_TempDb|TempDB ログ ファイル|50|50|64 KB|  
    |Data_BtsMsgBox|BizTalkMsgBoxDb データ ファイル|300|100|64 KB|  
    |Logs_BtsMsgBox|BizTalkMsgBoxDb ログファイル|100|100|64 KB|  
    |Data_BAMPrimaryImport|BAMPrimaryImport のデータ ファイル|10|10|64 KB|  
    |Logs_BAMPrimaryImport|BAMPrimaryImport のログ ファイル|10|10|64 KB|  
    |Data_BizTalkDatabases|他の BizTalk データベース データ ファイル|20|20|64 KB|  
    |Logs_BizTalkDatabases|その他の BizTalk データベースのログ ファイル|20|20|64 KB|  
    |なし|MSDTC ログ ファイル|5|5|なし|  
  
-   BizTalk Server のインストールで使用可能なインストール ガイドに従って[http://go.microsoft.com/fwlink/?LinkId=128383](http://go.microsoft.com/fwlink/?LinkId=128383)です。  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ベスト プラクティス アナライザー (BPA) ツールを使用して、システムが構成されていたとプラットフォームの検証を実行します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] BPA は、「 [http://go.microsoft.com/fwlink/?LinkId=67150](http://go.microsoft.com/fwlink/?LinkId=67150)です。  
  
## <a name="virtualization-specifics"></a>仮想化の詳細  
 各 HYPER-V 仮想マシンのオペレーティング システムをホストする 1 つ 50 GB の固定 VHD が使用されました。  
  
 これらにすぐがホストされているドライブ上のファイルを VHD の最大記憶域を割り当てるために、サイズが動的に設定された Vhd ではなく容量固定の Vhd が使用されました。 これにより、ディスク I/O パフォーマンスを向上させる、ホストされている、物理ドライブで発生している VHD ファイルの断片化が減少します。  
  
 セットアップに仮想マシンのインストール[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]1 つの VHD で 64 ビット版が実行されました。 すべての適切な更新プログラムがインストールされたら、基本の仮想マシン イメージを作成したと共にインストールされている sysprep ユーティリティを使用して[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]、%WINDIR%\system32\sysprep ディレクトリにします。  
  
 このベース VHD がコピーし、環境全体で展開されているすべての HYPER-V 仮想マシンの基礎として使用します。 開始する前にシステムのセキュリティ識別子をリセットするベース VHD イメージで Sysprep が実行された[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]または[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]バイナリは、システムに配置されました。  
  
> [!NOTE]  
>  BizTalk Server をインストールし、サーバー上で構成した後、Sysprep を実行しているが、Sysprep 応答ファイルおよび BizTalk Server で提供するスクリプトを使用して実現できます。 これらのサンプル スクリプトがの 32 ビットおよび 64 ビット バージョンにインストールされている BizTalk Server で使用できるように設計[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]のみです。 詳細については、BizTalk Server のオンライン マニュアルを参照してください。  
  
 Windows の無人セットアップ リファレンスについては、「 [http://go.microsoft.com/fwlink/?LinkId=142364](http://go.microsoft.com/fwlink/?LinkId=142364)です。  
  
## <a name="see-also"></a>参照  
 [付録 C: BizTalk Server と SQL Server の Hyper-V のサポート性](../technical-guides/appendix-c-biztalk-server-and-sql-server-hyper-v-supportability.md)