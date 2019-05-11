---
title: 手順 5:維持可能な最大のスループットを判断するステップ ロード パターン テストの実行 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8056ced6-1f04-4be2-878a-48a427a93dad
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb2288d651641aef7ac5fc40e5966900ce9bdf06
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400688"
---
# <a name="step-5-perform-step-load-pattern-tests-to-determine-maximum-sustainable-throughput"></a>手順 5:維持可能な最大のスループットを判断するステップ ロード パターン テストを実行します。
Visual Studio ロード テストでの BizTalk Server ソリューションの最大持続可能なスループット (MST) を決定するため最も簡単な方法は、ステップ ロード パターンを実行し、1 秒あたりに処理された合計のドキュメントを 1 秒あたりに受信したドキュメントの総数を比較するには. 1 秒あたりに処理された平均の合計ドキュメントは、テストの実行時間の 1 秒あたりに受信したドキュメントの平均総数以上には、負荷は維持可能なと見なされます。 負荷が維持可能なと見なされないしの値に対応する拡張によってこの確認はあたりに受信したドキュメントの総数、平均値が 2 つ目は、テストの実行中の 1 秒あたりに処理された平均の合計ドキュメントよりも大きい場合、BizTalk:Message ボックス: 一般的な Counters\Spool サイズ カウンター。 BizTalk Server アプリケーションが処理できるより多くのドキュメントを受信すると、時間の経過と共に、未処理のドキュメントが最終的に、制限の条件を誘発しのパフォーマンスが大幅に低下すると共に、メッセージ ボックス データベースに蓄積されます、BizTalk Server アプリケーションです。  
  
## <a name="configure-the-load-test-with-a-step-load-pattern-appropriate-for-your-application"></a>アプリケーションに適したステップ ロード パターンでロード テストを構成します。  
 トピックの手順に従って[手順 3。実行複数単体テストを同時にロード テストを作成](../technical-guides/step-3-create-a-load-test-to-perform-multiple-unit-tests-simultaneously.md)ステップ ロード パターンを使用するロード テストを作成します。 適切なタイミングでドキュメントを処理する BizTalk Server アプリケーションの機能に影響する要因は次のとおりです。  
  
- **数、グループ内の BizTalk Server コンピューター** -別の BizTalk Server は、追加の処理機能を提供します。  
  
- **処理されるメッセージのサイズ**-サイズの大きいメッセージは、追加の処理リソースを必要とします。  
  
- **ドキュメントのマッピングの量が実行される**-マッピングには、追加の処理リソースが必要です。  
  
- **受信または送信パイプラインは、アプリケーションで必要な**します。 -複雑なパイプラインには、追加の処理リソースが必要です。  
  
- **アダプターやアクセラレータは、BizTalk Server アプリケーションによって使用される**– 一部のアダプターやアクセラレータは、他のユーザーより多くの処理リソースを必要とします。  
  
- **メッセージの追跡に必要な量**– メッセージの追跡がリソースを消費します。  
  
- **BizTalk Server アプリケーションで実行されているオーケストレーションの数と複雑さ**– オーケストレーションは非常にリソースを消費することができます。  
  
  ステップ ロード パターン テストを構成するときに指定された値を変更**ユーザー カウントの開始**と**最大ユーザー カウント**こと開始ユーザー数を簡単に、指定されたメッセージの数を確認するには時間と同様に、最大ユーザー カウントの指定されたメッセージ数のアプリケーションは、BizTalk Server によって処理される時間の経過と共に、BizTalk Server アプリケーションが処理できるよりも大きくは。 参照してください[ロード テストを追加し、ロード テスト シナリオ、カウンター セット、および実行設定を構成](../technical-guides/step-3-create-a-load-test-to-perform-multiple-unit-tests-simultaneously.md#BKMK_StepLoadTest)については、ロード テストのロード パターン設定を編集します。  
  
## <a name="ensure-that-the-correct-test-settings-are-used-for-the-step-pattern-load-test"></a>ステップ パターンのロード テストのテストの正しい設定が使用されることを確認します。  
 使用するロード テストの構成、**テストの設定**で作成した[をソリューションにテストを実行し、リモートでデータを収集するテスト設定ファイルを追加](../technical-guides/step-3-create-a-load-test-to-perform-multiple-unit-tests-simultaneously.md#BKMK_TestSettings)します。  
  
## <a name="configure-the-load-test-with-the-appropriate-performance-counters-and-run-the-step-pattern-load-test"></a>適切なパフォーマンス カウンターをロード テストを構成し、ステップ パターンのロード テストの実行  
 次の手順では、[にメジャー BizTalk Server 主要業績評価指標 (KPI) をカスタム カウンター セットを追加](../technical-guides/step-3-create-a-load-test-to-perform-multiple-unit-tests-simultaneously.md#BKMK_BTSCounters)BizTalk Server のパフォーマンスを測定するために使用するために必要な BizTalk Server パフォーマンス カウンターを追加するにはアプリケーションどの時点で、BizTalk Server アプリケーションがロード テスト エージェントによって作成されたメッセージの読み込みを維持することが不要になったと判断します。 これは、BizTalk:Message ボックス: 一般的な Counters\Spool サイズ カウンターの増加の値から見た、スプール テーブル内のメッセージのバックログの計上によって確認されます。 このカウンターの値が大幅に向上する場合、BizTalk Server アプリケーションの MST 可能性超えています。 1 回を BizTalk Server アプリケーションが多数のメッセージを受信するようをメモしておきます、ドキュメントの受信/秒これが発生するを処理できる不要になったメッセージの数を決定します。 この値をメモしてください。 することが重要トピック[手順 6。最大持続可能スループットのことを確認するための定数ロード パターン テストの実行](../technical-guides/step-6-complete-load-pattern-tests-to-verify-maximum-sustainable-throughput.md)は、最大持続可能なドキュメント受信/秒よりもやや小さい「定数ユーザー数」の値を持つ定数パターンのロード テストを実行する方法について説明します値。 これは、BizTalk Server アプリケーションが時間の経過と共に、このメッセージの数を処理できることを確認します。 カウンター セットの値を表示するには、まずテスト名 (例: BTS_Messaging_Step) を右クリックして、ロード テストを開始 をクリックし、**テストの実行**メニュー オプション。 パフォーマンス カウンターを初期化し、ロード テストを開始した後、Visual Studio は 4 つのグラフに同時に 1 から表示できるグラフ ウィンドウにフォーカスを切り替える自動的にします。 定義されているように主要業績評価指標を表示するだけに関心がある場合[にメジャー BizTalk Server 主要業績評価指標 (KPI) をカスタム カウンター セットを追加](../technical-guides/step-3-create-a-load-test-to-perform-multiple-unit-tests-simultaneously.md#BKMK_BTSCounters)、クリックして、**パネル**ドロップダウンの一覧は、ロード テスト メニューとオプションを選択**1 つのパネル**します。 順にクリックし、グラフの上部にあるドロップダウン リストをクリックします。**キー インジケーター**をリアルタイムで主要業績評価指標の値を表示します。  
  
> [!NOTE]  
>  特定の既定カウンター値が表示されるので、**キー インジケーター**グラフが表示され、カスタム カウンター セットを追加したカウンターの値を表示する可能性がありますが、ために手動で削除することで開始することも表示されるカウンターの**キー インジケーター**グラフが表示され、カスタム カウンター セットのカウンターを手動で追加します。 たとえば、少なくとも、カウンターを追加、少なくとも次の表に、BizTalk Server 環境が、負荷を処理する方法もと、ボトルネックが発生する可能性を判断する、グラフにすると。  
  
|カウンター カテゴリ|カウンター|Instance|[Computer]|  
|----------------------|-------------|--------------|--------------|  
|BizTalk:Message Box:General Counters|Spool Size|*BizTalk Server メッセージ ボックス データベース*:*BizTalk Server メッセージ ボックス データベースを格納する SQL Server インスタンス*|BizTalk Server 管理コンソールで、グループ内の BizTalk Server がインストールされます。|  
|BizTalk:メッセージング|ドキュメントの受信/秒|RxHost (または、受信ホストの名前)|*BizTalk Server グループ内の BizTalk Server コンピューター 1*|  
|BizTalk:メッセージング|ドキュメントの受信/秒|RxHost (または、受信ホストの名前)|*BizTalk Server グループ内の BizTalk Server コンピューター 2*|  
|BizTalk:メッセージング|ドキュメントの受信/秒|RxHost (または、受信ホストの名前)|*BizTalk Server グループ内の BizTalk Server コンピューター #n*|  
|BizTalk:メッセージング|ドキュメントの処理/秒|TxHost (または、送信ホストの名前)|*BizTalk Server グループ内の BizTalk Server コンピューター 1*|  
|BizTalk:メッセージング|ドキュメントの処理/秒|TxHost (または、送信ホストの名前)|*BizTalk Server グループ内の BizTalk Server コンピューター 2*|  
|BizTalk:メッセージング|ドキュメントの処理/秒|TxHost (または、送信ホストの名前)|*BizTalk Server グループ内の BizTalk Server コンピューター #n*|  
|プロセッサ|[% プロセッサ時間]|_Total|*BizTalk Server グループ内の BizTalk Server コンピューター 1*|  
|プロセッサ|[% プロセッサ時間]|_Total|*BizTalk Server グループ内の BizTalk Server コンピューター 2*|  
|プロセッサ|[% プロセッサ時間]|_Total|*BizTalk Server グループ内の BizTalk Server コンピューター #n*|  
|プロセッサ|[% プロセッサ時間]|_Total|*BizTalk Server データベースを格納する SQL Server インスタンス*|