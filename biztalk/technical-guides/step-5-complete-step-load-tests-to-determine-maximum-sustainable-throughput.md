---
title: "手順 5: 維持可能な最大のスループットを判断するステップ ロード パターンのテストを実行 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8056ced6-1f04-4be2-878a-48a427a93dad
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f9794634b5a782ef6d9bce4e819e759fd47ba1a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-5-perform-step-load-pattern-tests-to-determine-maximum-sustainable-throughput"></a>手順 5: が維持可能な最大のスループットを判断するステップ ロード パターンのテストを実行します。
Visual Studio ロード テストでの BizTalk Server ソリューションの最大持続可能なスループット (MST) を決定するため最も簡単な方法は、ステップ ロード パターンを行い、1 秒あたりに処理された合計のドキュメントを 1 秒あたりに受信したドキュメントの総数を比較するには. 1 秒あたりに処理された平均合計のドキュメントは、テストの実行中の 1 秒あたりに受信したドキュメントの平均総数以上には、限り負荷は維持可能なと見なされます。 あたりに受信したドキュメントの総数、平均が 2 つ目は、テストの実行中の 1 秒あたりに処理されたドキュメントの平均総数よりも大きい後ロードとは見なされません維持可能なおよびの値に対応する拡張によってこの確認は、Biztalk: メッセージ ボックス: 一般的な Counters\Spool サイズ カウンターです。 最終的に、制限の条件が引き起こされるのパフォーマンスが大幅に低下するメッセージ ボックス データベースに蓄積されます未処理のドキュメントでは、BizTalk Server アプリケーションが処理できるほど大量のドキュメントを受信すると、時間の経過と共に、BizTalk Server アプリケーションです。  
  
## <a name="configure-the-load-test-with-a-step-load-pattern-appropriate-for-your-application"></a>ステップ ロード パターンをアプリケーションに適切にロード テストを構成します。  
 トピックの手順に従って[手順 3: を実行複数単体テストを同時にロード テストを作成](../technical-guides/step-3-create-a-load-test-to-perform-multiple-unit-tests-simultaneously.md)ステップ ロード パターンを使用してロード テストを作成します。 適切なタイミングでドキュメントを処理する BizTalk Server アプリケーションの機能に影響する要因は次のとおりです。  
  
-   **グループ内の BizTalk Server コンピューターの台数**-別の BizTalk Server は、追加の処理機能を提供します。  
  
-   **処理されるメッセージのサイズ**-サイズの大きいメッセージは、追加の処理リソースを必要とします。  
  
-   **ドキュメントのマッピングの量が実行される**-マッピングには、追加の処理リソースが必要です。  
  
-   **受信または送信パイプラインは、アプリケーションで必要な**します。 -複雑なパイプラインでは、追加の処理リソースが必要です。  
  
-   **アダプターやアクセラレータが BizTalk Server アプリケーションで使用される**– 一部のアダプターやアクセラレータは、他のユーザーよりも多くの処理リソースを必要とします。  
  
-   **メッセージの追跡に必要な量**– メッセージの追跡がリソースを消費します。  
  
-   **BizTalk Server アプリケーションで実行されているオーケストレーションの数と複雑さ**– オーケストレーションは、リソースを使用するを指定できます。  
  
 ステップ ロード パターンのテストを構成する場合に指定された値を変更**ユーザー カウントの開始**と**最大ユーザー カウント**ことを確認する開始ユーザー カウントを簡単にすることが指定されたメッセージの数BizTalk Server によって処理される時間と同様に、最大ユーザー カウントの指定されたメッセージの数にわたるアプリケーションは、時間の経過と共に、BizTalk Server アプリケーションが処理できるよりも大きくします。 参照してください[ロード テストを追加して、ロード テスト シナリオ、カウンター セット、および実行設定を構成する](../technical-guides/step-3-create-a-load-test-to-perform-multiple-unit-tests-simultaneously.md#BKMK_StepLoadTest)については、ロード テストのロード パターン設定を編集します。  
  
## <a name="ensure-that-the-correct-test-settings-are-used-for-the-step-pattern-load-test"></a>ステップ パターンのロード テストのテストの正しい設定が使用されることを確認してください。  
 ロード テストを使用する構成、**テストの設定**で作成した[追加 A テスト設定ファイルがソリューションにテストを実行し、リモートでデータを収集する](../technical-guides/step-3-create-a-load-test-to-perform-multiple-unit-tests-simultaneously.md#BKMK_TestSettings)です。  
  
## <a name="configure-the-load-test-with-the-appropriate-performance-counters-and-run-the-step-pattern-load-test"></a>適切なパフォーマンス カウンターと、ロード テストを構成し、ステップ パターンのロード テストの実行  
 手順に従います[にメジャー BizTalk Server 主要業績評価指標 (KPI) をカスタム カウンター セットを追加](../technical-guides/step-3-create-a-load-test-to-perform-multiple-unit-tests-simultaneously.md#BKMK_BTSCounters)を BizTalk Server のパフォーマンスを測定するために使用するために必要な BizTalk Server パフォーマンス カウンターを追加するにはアプリケーションのどの個所で、BizTalk Server アプリケーションでロード テスト エージェントによって作成されたメッセージの読み込みを維持することが不要になったを決定します。 これは、BizTalk:Message ボックス: 一般的な Counters\Spool Size カウンタの値を大きくから見た、スプール テーブル内のメッセージのバックログの発生によって確認されます。 このカウンターの値の開始が大幅に増加する場合は、BizTalk Server アプリケーションの MST 可能性があります超えています。 1 回を BizTalk Server アプリケーションができなくを処理する多数のメッセージを受信するよう、メモしておきますドキュメントの受信/秒このエラーが発生するメッセージの数を決定しました。 いるため、この値をメモに重要なトピック[手順 6: 実行定数ロード パターン テスト最大スループットのことを確認する](../technical-guides/step-6-complete-load-pattern-tests-to-verify-maximum-sustainable-throughput.md)は「定数のユーザー数をカウント」の値を持つ定数パターン ロード テストを実行する方法を示します維持可能なドキュメント受信/秒の最大値より小さいです。 これは、BizTalk Server アプリケーションが時間の経過と共にこの数のメッセージを処理できることを確認します。 カウンター セットの値を表示するにまずテスト名 (例: BTS_Messaging_Step) を右クリックして、ロード テストを開始し、をクリックして、**テストの実行**メニュー オプション。 パフォーマンス カウンターを初期化すると、ロード テストを開始、Visual Studio は自動的にフォーカス ウィンドウに切り替えます。 グラフが 4 つのグラフを同時に 1 から表示できます。 関心がある場合、主に、主要業績評価指標を表示するだけで定義されている[にメジャー BizTalk Server 主要業績評価指標 (KPI) をカスタム カウンター セットを追加](../technical-guides/step-3-create-a-load-test-to-perform-multiple-unit-tests-simultaneously.md#BKMK_BTSCounters)をクリックして、**パネル**ドロップダウン リストが、ロード テスト メニューの一覧し、オプションを選択**1 つのパネル**です。 クリックし、グラフの上部にあるドロップダウン リストをクリックし、**キー インジケーター**をリアルタイムで主要業績評価指標の値を表示します。  
  
> [!NOTE]  
>  特定の既定カウンター値が表示されるので、**キー インジケーター**グラフが表示され、カスタム カウンター セットに追加したカウンターの値を表示するはおそらく、ためを手動で削除することで開始することも表示されるカウンターの**キー インジケーター**グラフが表示され、カスタム カウンター セットのカウンターを手動で追加します。 たとえば、少なくとも、カウンターを追加するには、少なくとも、以下の表に、BizTalk Server 環境は、負荷を処理する方法もと、ボトルネックが発生する可能性を判断する、グラフにするは。  
  
|カウンターのカテゴリ|カウンター|Instance|[Computer]|  
|----------------------|-------------|--------------|--------------|  
|BizTalk:Message Box:General Counters|Spool Size|*BizTalk Server メッセージ ボックス データベース*:*BizTalk Server メッセージ ボックス データベースを格納する SQL Server インスタンス*|BizTalk Server 管理コンソールで、グループ内の BizTalk サーバーがインストールされます。|  
|BizTalk:メッセージング|Documents received/Sec|RxHost (または、受信ホストの名前)|*BizTalk Server グループ内の BizTalk Server コンピューター 1*|  
|BizTalk:メッセージング|Documents received/Sec|RxHost (または、受信ホストの名前)|*BizTalk Server グループ内の BizTalk Server コンピューター 2*|  
|BizTalk:メッセージング|Documents received/Sec|RxHost (または、受信ホストの名前)|*BizTalk Server グループ内の BizTalk Server コンピューター #n*|  
|BizTalk:メッセージング|Documents processed/Sec|TxHost (または、送信ホストの名前)|*BizTalk Server グループ内の BizTalk Server コンピューター 1*|  
|BizTalk:メッセージング|Documents processed/Sec|TxHost (または、送信ホストの名前)|*BizTalk Server グループ内の BizTalk Server コンピューター 2*|  
|BizTalk:メッセージング|Documents processed/Sec|TxHost (または、送信ホストの名前)|*BizTalk Server グループ内の BizTalk Server コンピューター #n*|  
|プロセッサ|[% プロセッサ時間]|_Total|*BizTalk Server グループ内の BizTalk Server コンピューター 1*|  
|プロセッサ|[% プロセッサ時間]|_Total|*BizTalk Server グループ内の BizTalk Server コンピューター 2*|  
|プロセッサ|[% プロセッサ時間]|_Total|*BizTalk Server グループ内の BizTalk Server コンピューター #n*|  
|プロセッサ|[% プロセッサ時間]|_Total|*BizTalk Server データベースを格納する SQL Server インスタンス*|