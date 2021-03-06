---
title: ボトルネックの調査 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2ab8e485-ffe5-4f71-9ce2-f72c0c939e5d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35bb2b4c9d8eef862b2a0b009802b3bd5801320e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65294806"
---
# <a name="investigating-bottlenecks"></a>ボトルネックの調査
このトピックでは、ボトルネックを調査するための推奨プロセスについて説明します。  
  
## <a name="what-is-the-source-of-the-problem"></a>問題の原因は何ですか。  
 ボトルネックの原因には、ハードウェアまたは関連するソフトウェアです。 リソースが使用されていない場合は、通常のボトルネックを示す値。 ボトルネックは、ハードウェアの制限、非効率的なソフトウェア構成、または両方によって発生することができます。  
  
 という 1 つのボトルネックを軽減する可能性が次の 1 つの探索段階的なプロセスは、ボトルネックを特定します。 識別して、これらのボトルネックを緩和の技術は、このトピックの目的です。 短時間のピーク時に実行するシステムのことができます。 ただし、維持可能なスループットのシステムのみを処理できます速度の遅いコンポーネント。  
  
## <a name="using-an-iterative-approach-to-testing"></a>テストを反復的なアプローチを使用します。  
 または (オーケストレーション/データベース) の中間に、システムのエンドポイント (入り口/出口) でボトルネックが発生することができます。 ボトルネックを特定した後は、ソースを識別するために構造化されたアプローチを使用します。 ボトルネックを緩和すると、それが、新たなボトルネックが導入されていない他の場所で、システムのことを確認するには、もう一度パフォーマンスを測定する重要です。  
  
 識別するボトルネックを修復するプロセスは、反復的な方法で行う必要があります。 一度に 1 つだけのパラメーターを異なる、各テストの実行中に同じ手順を繰り返しますおよびし、1 つの変更の影響を確認するパフォーマンスの測定します。 一度に 1 つ以上のパラメーターをさまざまな変更の効果を非表示でした。  
  
 たとえば、パラメーター 1 を変更するには、パフォーマンスが向上します。 ただし、パラメーター 1 の変更を組み合わせて 2 番目のパラメーターを変更することが悪影響を与えます、negate パラメーター 1 の変更の利点があります。 これを net 0 効果、さまざまなパラメーター 1 の効果が偽陰性、およびさまざまなパラメーター 2 の影響の偽陽性になります。  
  
## <a name="testing-consistency"></a>テストの一貫性  
 パフォーマンス特性を測定する設定を変更した後は、変更の結果の検証に行う必要があります。  
  
-   **ハードウェア -** ハードウェアのさまざまな一貫性のない動作が発生し、誤解を招く結果が生成するために、一貫性のあるハードウェアを使用します。 たとえば、BizTalk ソリューションのパフォーマンスをテストするのにラップトップ コンピューターを使用するはできません。  
  
-   **テスト実行の継続時間 -** 結果が維持可能なであることを確認する固定最低限の期間のパフォーマンスを測定します。 また、システムの場所のすべてのキャッシュを設定、データベース テーブルが予想の数に到達したおよび調整は 1 回のスループットを制御するための十分な時間を指定した定義済みの期間の初期のウォーム/ランプが行われたが長期にわたってテストの実行しきい値がヒットします。 このアプローチでは、最適なスループットを検出するのに役立ちます。  
  
-   **テスト パラメーター –** テストの実行するテストの実行からテストのパラメーターは変わりません。 たとえば、マップの複雑さやドキュメントのサイズをさまざまな異なるスループットと待機時間の結果を生成できます。  
  
-   **クリーンアップ状態 -** テストが完了した後は、テスト環境の状態が、次のテストを実行する前にクリーンであることを確認します。 たとえば、履歴データは、実行時のスループットに影響を与える、データベース構築できます。 サービス インスタンスのリサイクルは、メモリ、データベース接続、およびスレッドのようにキャッシュされたリソースを解放するのに役立ちます。 作成して」の説明に従って、bts_CleanupMsgbox ストアド プロシージャを実行することがあります、テスト環境内で[テスト環境でメッセージ ボックス データベースからデータを手動で消去する方法](http://go.microsoft.com/fwlink/?LinkId=158064)(http://go.microsoft.com/fwlink/?LinkId=158064)します。 このスクリプトは、実行の間を最新の状態に関しては、メッセージ ボックスに、BizTalk Server のテスト環境を返すものです。 スクリプトでは、実行中のすべてのインスタンスとすべての情報など、状態、メッセージ、およびサブスクリプションの場合、それらのインスタンスを削除しますが、すべてのアクティベーションのサブスクリプションのまま、オーケストレーションへの再参加またはポートを送信する必要はありませんので。 このツールが実稼働システムでサポートされていないことに注意してください。  
  
-   **パフォーマンス テストとチューニング -** このテスト カテゴリの目標は、アプリケーションのパフォーマンスとスループットを最大化し、システムの最大持続可能なスループット (MST) を検索します。  計画と維持可能な最大のパフォーマンスを計測の詳細については、次を参照してください[パフォーマンス維持の計画](http://go.microsoft.com/fwlink/?LinkId=158065)(http://go.microsoft.com/fwlink/?LinkId=158065)と[維持可能なパフォーマンスとは何ですか?。](http://go.microsoft.com/fwlink/?LinkId=132304) (http://go.microsoft.com/fwlink/?LinkId=132304)。  
  
     MST は、システムが実稼働環境で無制限に処理できるメッセージ トラフィックの最大負荷です。 実稼働に移行する前に、パフォーマンスとスループットのすべての BizTalk アプリケーションをテストしてください。 少なくとも最も一般的な使用状況を表すテスト ケースの代表的なセットを実行する必要があります。 予想される負荷をテストして、最大の負荷を別の環境、運用環境の特性に一致することをお勧めします。 この環境は、すべての企業の標準的なサービスをインストールし、監視エージェントは、ウイルス対策ソフトウェアなど、実行している必要があります。  
  
-   また、実行されているその他の BizTalk アプリケーションの横には、実稼働環境で同じハードウェア上での BizTalk アプリケーションをテストすることをお勧めします。 これら他の BizTalk アプリケーションでは、BizTalk Server、SQL Server、ネットワーク I/O、およびディスク I/O の負荷を高めます。 さらに、1 つの BizTalk アプリケーション (この場合、スプールの深さを取得が大きすぎて、たとえば) を調整する可能性があります。 すべての BizTalk アプリケーションがパフォーマンスにする必要があります/ストレス テストから実稼働に移行します。 さらに、ピーク ロードから回復するシステムにかかる時間を決定する必要があります。 システム完全復旧しないピーク ロードから [次へ] のピーク時の負荷が発生する前に、問題を取得しました。 システムがさらに表示されます、さらに分離されことはありませんできる完全に回復します。  
  
## <a name="expectations-throughput-vs-latency"></a>待機時間とスループットを期待します。  
 一定量のスループットや待機時間、デプロイされたシステムを想定できます。 反対側の要求をシステムに配置する高いスループットと低待機時間を同時に実現しようとしています。 妥当な待機時間の最適なスループットを期待できます。 システムが増加 (など、CPU 消費率が高い、高いディスク i/o の競合、メモリの負荷、およびロックの競合) と、スループットが向上しますが、強調します。 このような状況では、待機時間にマイナスの影響があります。 システムの最適な容量を検出、識別し、ボトルネックを最小限に抑えることお勧めします。  
  
 データベース内に存在する完成したインスタンスのボトルネックを引き起こすことができます。 ボトルネックが発生すると、パフォーマンスが低下することができます。 ドレインするまでにシステムのための十分な時間には、問題を修正するのに役立ちます。 バックログが蓄積された原因を特定し、問題の修正に協力が重要です。  
  
 バックログの原因を検出するには、履歴データを分析し、(を使用状況のパターンを検出し、バックログの原因の診断) パフォーマンス カウンターを監視できます。 一般的には、大量のデータを毎晩バッチ方式で処理されるときにバックログが発生します。 システムとのバックログから回復するには、その機能の容量を検出すると便利です。 この情報は、予想外のピーク スループットを処理するために、システム内に対応する overdrive シナリオとバッファーの大きさを処理するためのハードウェア要件を評価するのに役立ちます。  
  
 パフォーマンス カウンターの監視は、実行時に発生する可能性がある潜在的なボトルネックを individuate に役立ちます。 ただし、疑いソリューションを構成するカスタム コンポーネントの 1 つを CPU またはメモリのボトルネックの原因である可能性がありますが、ときに強くお勧めで使用する、プロファイリング ツールこのような Visual Studio Profiler または ANTS パフォーマンス Profiler パフォーマンス テスト対象を絞り込み、問題を生成するクラスに確信を持って individuate します。 当然ながら、アプリケーションのプロファイリングは、パフォーマンスが妨害されます。 そのため、メモリ消費量、CPU 使用率や待機時間が発生するこれらのコンポーネントを individuating に注目する必要がありますがこれらのテストと、これらのテスト中に収集された図形を破棄する必要があります。  
  
 最適なスループットの詳細に必要です、システムの調整、デプロイされたアプリケーション、長所と、システムの脆弱性、および、特定のシナリオの使用量パターンの理解します。 ボトルネックを特定しするものに近いトポロジで徹底的なテストを明確に最適なスループットを予測する唯一の方法は、実稼働環境で使用されます。 別のホスト インスタンスに 1 つの成果物 (受信場所、送信ポート、オーケストレーション) を分離して、パフォーマンス モニター ツール内で適切なカウンターの設定は、絞り込むために重要な特定のユース ケースに対してロード テストとストレス テストを実行するときに、ボトルネックの原因。  
  
 このセクションの他のトピックでは、そのトポロジを定義するプロセスについて説明し、短縮するには、ボトルネックを回避する方法に関するガイダンスを提供します。  
  
## <a name="scaling"></a>スケーリング  
 展開されたトポロジのさまざまな段階でボトルネックが発生することができます。 いくつかのボトルネックは、スケール アップまたはスケール アウト環境のいずれかでアドレス指定できます。 スケール アップは、既存のコンピューターをアップグレードするプロセスです。 たとえば、8 プロセッサ コンピューターでは、だけでなく置き換える既存の Cpu と RAM を追加する 4 つのプロセッサのコンピューターから BizTalk Server コンピューターをアップグレードできます。 この方法では、ドキュメントの解析とマッピングなどのリソースを消費するタスクを高速化できます。 スケール アウトは、サーバーのデプロイに追加のプロセスです。 スケール アップまたはアウトする意思決定は、ボトルネックと構成対象のアプリケーションの種類によって異なります。 アプリケーションは、スケール アップとスケール アウトを活用できるゼロから構築する必要があります。次のガイダンスでは、発生したボトルネックに基づいてハードウェア展開トポロジを変更する方法について説明します。  
  
 **スケール アップ**BizTalk ソリューションを実行していることを意味 (例では、追加の CPU およびメモリ) のハードウェアをアップグレードします。 1) スケール アウトは、高価すぎる、または 2) スケール アウトが解決しないボトルネックになっているときにスケール アップを確認する必要があります。 たとえば、変換、および高速なマシンでタスクを実行する場合は、サイズの大きいメッセージを処理に費やされた時間を大幅に短縮できます。  
  
 **スケール アウト**アプリケーション プラットフォームは、BizTalk Server グループに BizTalk のノードを追加し、それらを使用して、ソリューションの 1 つまたは複数の部分を実行するので構成されています。 スケール アウト処理、ホストの追跡、送信の分離の [受信] に必要な 1) 場合や、2) と確認する必要がありますメモリ、I/O またはネットワーク I/O のリソースが 1 台のサーバーの限界です。 複数のサーバーの負荷を分散できます。ただし、BizTalk Server グループに新しいノードの追加と、メッセージ ボックス データベースのロックの競合が増加することができます。  
  
 これがスケール アップするかスケール アウトしますか。 1 つのタスクを可能になったため BizTalk ソリューションの待機時間を短縮できるスケール アップお使いのプラットフォーム (たとえば、メッセージのマッピング) 高速に実行します。 スケール アウトできます最大持続可能な・ スループットとスケーラビリティを向上、BizTalk ソリューションのため、複数のマシンにワークロードを分散することができます。  
  
## <a name="see-also"></a>参照  
 [ボトルネックの検索と解消](../technical-guides/finding-and-eliminating-bottlenecks.md)