---
title: フェーズ 4:評価環境の構築 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3b90d7c5-60ca-4a81-b3d9-6d4e9d91e684
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1b9829591af749f5e253cc7873af4ab114af542
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65249650"
---
# <a name="phase-4-building-the-assessment-environment"></a>フェーズ 4:評価環境を構築します。
パフォーマンス評価のビルド ラボの段階を使用して、前のフェーズで行われた設計の決定に準拠して、ハードウェアとソフトウェア環境をインストールできます。 ビルド ラボ フェーズな時間がかかるので、このフェーズの前のフェーズを重複に異常はありません。 多くのシナリオで、アプリケーションのアーキテクチャに関する最終決定が行わには、ハードウェアとオペレーティング システムをインストールすることがあります。 通常、パフォーマンス評価のビルド ラボの段階には、このトピックで説明したタスクが含まれます。  
  
## <a name="obtain-all-build-lab-infrastructure-at-least-a-week-in-advance-of-the-lab-start-date"></a>すべてのビルド ラボ インフラストラクチャのラボの開始日の前に、少なくとも週を取得します。  
 少なくとも 1 週間、ラボの開始日前に、必要なハードウェアとソフトウェアの使用可能なすべてがあることを計画します。 これにより、ラボの貴重な時間が必要なインフラストラクチャの浪費されていないことが保証されます。  
  
## <a name="configure-third-party-software-systems"></a>サード パーティのソフトウェア システムを構成します。  
 サード パーティ システムを構築し、ラボを開始する前に構成する必要がある可能性があります。 領域の専門家 (Sme) がこれらのシステムに必要な場合は、ビルド、ラボの実行段階中にスケジュールされていることを確認します。 完全に文書化するの構築する手順を確認します。  
  
## <a name="install-and-configure-the-biztalk-server-environment"></a>インストールして、BizTalk Server 環境の構成  
 BizTalk Server と必要な依存関係のソフトウェアをインストールするための詳細な手順は、[インストールおよびアップグレード ガイド](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md)します。 正常にインストールし、BizTalk Server 環境を構成した後、次のタスクを行います。  
  
-   推奨事項に従って、[運用準備チェックリスト](operational-readiness-checklists.md)
  
-   推奨事項に従い[のパフォーマンスの最適化](../technical-guides/optimizing-performance.md)します。  
  
-   すべてのコンピューターの時刻が正しく同期されていることを確認します。  
  
-   環境内のすべてのコンピューター間の MSDTC 機能を確認します。  
  
-   本当に必要な場合を除き、カスタム トレース/ログ記録が無効になっていることを確認します。  
  
-   ロード テスト用の Visual Studio Ultimate edition をインストールします。  Visual Studio を使用して自動テストを実行する方法の詳細については、次を参照してください。[自動テストを容易にするために Visual Studio を使用して](../technical-guides/using-visual-studio-to-facilitate-automated-testing.md)します。  
  
-   必要に応じて、パフォーマンス モニター カウンターおよびログを設定します。  
  
-   デバッグ コードの変更がパフォーマンス評価のスコープ内にある場合は、ソリューションをデバッグするコンピューターをセットアップします。  
  
-   すべてのハード ドライブを最適化します。  
  
-   ウイルス対策のリアルタイム スキャンを無効にします。  
  
-   エンタープライズ シングル サインオン マスター シークレットをバックアップします。  
  
## <a name="install-the-biztalk-server-application-to-be-tested"></a>テストする BizTalk Server アプリケーションをインストールします。  
 テストするアプリケーションのインストールには、通常、次の手順が含まれます。  
  
1.  次に、BizTalk Server 管理コンソールを使用します。  
  
    -   ホストを作成します。  
  
    -   送信/受信ハンドラーを作成します。  
  
    -   ホスト インスタンスを作成します。  
  
    -   BizTalk Server アプリケーションを作成します。  
  
2.  アプリケーションのインストール:  
  
    1.  BizTalk Server グループに BizTalk Server のバイナリを展開します。  
  
    2.  BizTalk Server グループにバインドをインポートします。  
  
    3.  すべてのボックスで GAC の BizTalk Server と BizTalk Server 以外のバイナリ。  
  
    4.  すべてのボックスに依存関係コンポーネントの存在を確認します。  
  
3.  アプリケーションの依存関係をインストールします。  
  
4.  BizTalk Server 管理コンソールで、トランスポートおよび物理エンドポイントを構成します。  
  
5.  サービスを開始します。  
  
6.  基本的なスモーク テストの実行 – スモーク テストは、ソリューションの基本的な機能をテストするエンド ツー エンド機能テスト。  
  
## <a name="implement-automated-build-and-load-testing"></a>自動化されたビルドを実装し、ロード テスト  
 自動化ビルドおよびロード テストのプロセスの実装は、BizTalk Server のパフォーマンス評価の基盤ではほぼ間違いなくです。 コードの変更がパフォーマンス評価のスコープ内にある場合は、自動化されたビルド プロセスを実装する必要があります。 自動化されたロード テストは、すべてのロード テストのシナリオを実装する必要があります。 自動化されたビルドを実装して、ロード テストに必要な初期投資が迅速に削減、オートメーションは人的エラー対象である、日常的なビルド/テストのタスクの繰り返しを迅速かつ正確なに対応します。 自動化されたビルドを実装して、テストのプロセスの詳細については、次を参照してください。[自動テストを実装する](../technical-guides/implementing-automated-testing.md)このガイドでします。  
  
## <a name="configure-performance-monitoring"></a>パフォーマンス監視を構成します。  
 正確なパフォーマンスの監視は、パフォーマンス評価の成功に不可欠です。 スコープ フェーズで定義されたスループットと待機時間の目標に基づいてパフォーマンス メトリックを評価するかを判断します。 パフォーマンスの監視は、BizTalk Server 環境の各コンピューターで実行する必要があります。 参照してください[パフォーマンス カウンター](../core/performance-counters.md)します。 ログのパフォーマンス分析ツール (PAL) を使用すると、視覚的に重要なパフォーマンス カウンターをグラフし、これらのカウンターのしきい値を超えた場合にアラートが生成される HTML レポートを生成します。 S[パフォーマンス分析のログ (PAL) ツール](https://github.com/clinthuffman/PAL)します。  
  
## <a name="establish-and-document-the-solutions-baseline-performance"></a>確立して、ソリューションのベースライン パフォーマンスを文書化  
 パフォーマンスの評価中に適用されるパフォーマンスの最適化の効果を測定できるように、ベースライン パフォーマンスを計算する必要があります。  
  
## <a name="see-also"></a>参照  
 [パフォーマンス評価のフェーズ](../technical-guides/phases-of-a-performance-assessment.md)