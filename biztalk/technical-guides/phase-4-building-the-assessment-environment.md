---
title: "フェーズ 4: 評価環境を構築 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3b90d7c5-60ca-4a81-b3d9-6d4e9d91e684
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88fa45a17e1475aee989f22d2f8d1ef0d015a9ce
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="phase-4-building-the-assessment-environment"></a>フェーズ 4: 評価環境を構築します。
パフォーマンス評価のビルド ラボの段階を使用して、前のフェーズで行われた設計に関する決定事項への準拠のハードウェアとソフトウェア環境をインストールできます。 ビルド ラボ フェーズできますが、時間がかかるために、このフェーズの以前のフェーズを重複に通常とは異なるはできません。 多くのシナリオで、アプリケーションのアーキテクチャに関する最終的な判断が行わ前に、ハードウェアとオペレーティング システムをインストールすることがあります。 パフォーマンス評価のビルド ラボの段階には、通常、このトピックで説明したタスクが含まれます。  
  
## <a name="obtain-all-build-lab-infrastructure-at-least-a-week-in-advance-of-the-lab-start-date"></a>すべてのビルド ラボ インフラストラクチャ ラボの開始日を前もってお客様には、少なくとも 1 週間の取得します。  
 少なくとも週に、ラボの開始日前に、必要なハードウェアとソフトウェアの使用可能なすべてがあることを計画します。 貴重なラボの時間が必要なインフラストラクチャの浪費しないようになります。  
  
## <a name="configure-third-party-software-systems"></a>サード パーティ製ソフトウェア システムを構成します。  
 サードパーティ製システムを構築して、ラボを開始する前に構成する必要がある可能性があります。 領域の専門家該当がこれらのシステムに必要な場合は、ビルド出力とラボ実行段階でスケジュールされていることを確認します。 完全に文書化するの構築する手順を確認します。  
  
## <a name="install-and-configure-the-biztalk-server-environment"></a>インストールして、BizTalk Server 環境を構成します。  
 BizTalk Server と必要な依存関係のソフトウェアをインストールするための詳細な手順については、[インストールおよびアップグレード ガイド](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md)です。 正常にインストールし、BizTalk Server 環境を構成した後、次のタスクを行います。  
  
-   推奨事項に従う、[運用の準備のチェックリスト](operational-readiness-checklists.md)
  
-   推奨事項に従い[のパフォーマンスの最適化](../technical-guides/optimizing-performance.md)です。  
  
-   すべてのコンピューターの時刻が正しく同期されていることを確認します。  
  
-   環境内のすべてのコンピューター間で MSDTC 機能を確認します。  
  
-   本当に必要な場合を除き、任意のカスタムのトレース/ログが無効になっていることを確認します。  
  
-   ロード テストのための Visual Studio Ultimate edition をインストールします。  Visual Studio を使用して自動テストを実行する方法に関する詳細については、次を参照してください。[自動テストを容易にするために Visual Studio を使用して](../technical-guides/using-visual-studio-to-facilitate-automated-testing.md)です。  
  
-   必要に応じて、パフォーマンス モニター カウンターおよびログをセットアップします。  
  
-   デバッグ コードの変更が、パフォーマンスの評価のスコープ内にある場合は、ソリューションをデバッグするコンピューターをセットアップします。  
  
-   すべてのハード ドライブの断片化を解消します。  
  
-   ウイルス対策のリアルタイム スキャンを無効にします。  
  
-   エンタープライズ シングル サインオン マスター シークレットをバックアップします。  
  
## <a name="install-the-biztalk-server-application-to-be-tested"></a>テストする BizTalk Server アプリケーションをインストールします。  
 テストするアプリケーションのインストールには、通常、次の手順が含まれます。  
  
1.  BizTalk Server 管理コンソールを使用して、次の操作を行います。  
  
    -   ホストを作成します。  
  
    -   送信/受信ハンドラーを作成します。  
  
    -   ホスト インスタンスを作成します。  
  
    -   BizTalk Server アプリケーションを作成します。  
  
2.  アプリケーションのインストール:  
  
    1.  BizTalk Server グループを BizTalk Server のバイナリを展開します。  
  
    2.  BizTalk Server グループにバインドをインポートします。  
  
    3.  すべてのボックスで GAC の BizTalk Server と BizTalk Server 以外のバイナリです。  
  
    4.  依存関係コンポーネントのすべてのボックスに存在することを確認します。  
  
3.  依存アプリケーションをインストールします。  
  
4.  BizTalk Server 管理コンソールで、トランスポートと物理エンドポイントを構成します。  
  
5.  サービスを開始します。  
  
6.  基本的なスモーク テストの実行 – スモーク テストは、ソリューションの基本機能をテストするエンド ツー エンド機能テストします。  
  
## <a name="implement-automated-build-and-load-testing"></a>自動ビルドを実装し、ロード テスト  
 自動ビルドおよび負荷テスト プロセスの実装は、BizTalk Server のパフォーマンス評価のにとって重要ではほぼ間違いないです。 コードの変更が、パフォーマンスの評価のスコープ内にある場合は、自動ビルド プロセスを実装する必要があります。 すべてのロード テスト シナリオの自動化されたロード テストを実装する必要があります。 自動ビルドを実装して、ロード テストに必要な初期投資が削減すばやく、オートメーションはヒューマン エラーされる日常的なビルドまたはテストのタスクの繰り返しの高速かつ正確に対応します。 自動ビルドを実装して、プロセスのテストに関する詳細については、次を参照してください。[自動テストを実装する](../technical-guides/implementing-automated-testing.md)このガイドでします。  
  
## <a name="configure-performance-monitoring"></a>パフォーマンスの監視を構成します。  
 正確なパフォーマンスの監視は、パフォーマンスの評価の成功に不可欠です。 スコープ フェーズで定義されたスループットと待機時間の目標値に基づいてパフォーマンス メトリックを評価するかを決定します。 パフォーマンスの監視は、BizTalk Server 環境の各コンピューターで実行してください。 参照してください[パフォーマンス カウンター](../core/performance-counters.md)です。 ログのパフォーマンス分析ツール (PAL) を使用すると、視覚的に重要なパフォーマンス カウンターをグラフおよびこれらのカウンターのしきい値を超えた場合にアラートが生成される HTML レポートを生成できます。 S[パフォーマンス分析のログ (PAL) ツール](https://github.com/clinthuffman/PAL)です。  
  
## <a name="establish-and-document-the-solutions-baseline-performance"></a>確立して、ソリューションのベースライン パフォーマンスを文書化  
 パフォーマンス評価中に適用されるパフォーマンスの最適化の効果を測定することができるように、パフォーマンスの基準値を計算する必要があります。  
  
## <a name="see-also"></a>参照  
 [パフォーマンス評価のフェーズ](../technical-guides/phases-of-a-performance-assessment.md)