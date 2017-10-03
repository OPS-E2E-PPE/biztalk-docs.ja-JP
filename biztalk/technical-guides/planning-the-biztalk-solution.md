---
title: "BizTalk ソリューションの計画 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 30d56a04-966a-46b1-861d-f5be4e58b7d2
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74b7cbe23a6fc818428478859ea021d4fbf38546
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="planning-the-biztalk-solution"></a>BizTalk ソリューションの計画
主な設計目標の 1 つ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]できるだけ多くの処理シナリオに対応するために最大限の柔軟性を提供することです。 この柔軟のための機能を最大限に使用で利用できるようにする方法を決定する主に、BizTalk ソリューションの開発者が直面する課題の 1 つは[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]最適なビジネス ニーズに対応します。 計画、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]以下にまとめますフェーズに分けることができます。  
  
## <a name="scoping-the-solution"></a>ソリューションのスコープ  
  
### <a name="performance-considerations"></a>パフォーマンスに関する考慮事項  
 BizTalk ソリューションを限定するときは、次を考慮してください。  
  
-   どのアダプターやアクセラレータが必要ですか。  
  
-   ソリューションのオーケストレーションを実装するための要件とは  
  
-   ドキュメントのスループットの要件: ソリューションの最大スループット要件は何ですか?  
  
-   待機時間の要件: 応答は、ソリューションである必要な送信請求-応答と要求-応答のシナリオのですか?  
  
-   ソリューションは、ピーク時のドキュメントの読み込みの期間からどの程度回復しますか。  
  
-   ソリューションの高可用性の要件とは  
  
-   ソリューションのドキュメント追跡の要件とは  
  
-   リモートの Web サービスやその他のシステムなど、依存するアプリケーションのパフォーマンス特性を挙げてください。 依存するアプリケーションを必要な負荷で保持しない場合、システム全体のパフォーマンスが低下するそれに応じて。  
  
-   BizTalk アプリケーションが消費しているデータベースに関連していない[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]しますか? たとえば、BizTalk アプリケーションには、SQL アダプターを使用して SQL Server データベースのテーブルが使用して場合、は、テーブル効率的に構成しますか。  
  
### <a name="hardware-considerations"></a>ハードウェアについての注意事項  
 ソリューションを限定するときは、次のハードウェアの高度なダイアグラムを作成します。  
  
-   (X86、x64、および IA64) などのコンピューターのアーキテクチャ  
  
-   (種類、速度、数、コア、ハイパー スレッドの使用など) の CPU 要件  
  
-   各コンピューターの RAM の要件  
  
-   ローカル ディスク ストレージ (型、サイズ、速度)  
  
-   SAN (記憶域の要件: LUN の数SAN カードの種類)  
  
-   ネットワーク カード (1 ギガビットと 100 メガ ビット (Mbps) は、各コンピューターの数 (1 Gbps) です)。  
  
-   ファイアウォールをソリューションに展開するにはどうされますか。  
  
-   ハードウェアのネットワーク負荷分散が使用されますか。  
  
-   クラスター化する特定のコンピューターとは  
  
-   Microsoft HYPER-V Server またはその他の仮想化製品に関連する仮想環境を使用するか。  
  
## <a name="planning-the-solution"></a>ソリューションの計画  
  
### <a name="solution-milestones-timeline"></a>ソリューションのマイルス トーンのタイムライン  
 BizTalk ソリューションの特定の側面を完了するためのマイルス トーンをスケジュールを作成します。 特定のマイルス トーンを設定するソリューションとなる可能性が高くなりますが、適切なタイミングで完了しました。  
  
### <a name="non-microsoft-software-considerations"></a>Microsoft 以外のソフトウェアの考慮事項  
 Microsoft 以外のソフトウェアが、ソリューションで使用する場合は、次を考慮します。  
  
-   ソフトウェアまたはハードウェアは必要のある方法の決定を取得します。  
  
-   容量計画を作成し、サイズ変更する Microsoft 以外のソフトウェアを確実には、ソリューション内のボトルネックにはなりません。  
  
-   必要な Microsoft 以外のソフトウェアをインストールするためのアクションのプランを決定します。  
  
-   アクションを構成し、必要な Microsoft 以外のソフトウェアを最適化するためのプランを作成します。  
  
## <a name="preparing-for-the-solution"></a>ソリューションの準備をしています  
 準備フェーズでは、次の要素を含めます。  
  
### <a name="detailed-design-of-the-solution-platform"></a>ソリューション プラットフォームの詳細な設計  
 詳細なソリューションの設計では、コミュニケーションを促進し、前提条件、機敏性とすべてのアクティビティの有効性が向上を回避できます。 次の要素完全に文書化する必要があります。  
  
-   BizTalk Server データベースと複数のコンピューターでの分散方法。  
  
-   BizTalk ホストの設計と各ホストおよびそのインスタンスの説明。  
  
-   各オーケストレーションの説明です。  
  
-   各パイプラインの説明です。  
  
-   .NET アセンブリなどのカスタム コンポーネント、COM + コンポーネントの説明です。  
  
 **メッセージ フロー図**  
  
 メッセージを処理中に発生することにどのようななってに関する混乱や false 前提条件を回避するための詳細なメッセージ フロー図を作成します。 メッセージのフロー チャートを作成するときに、次の詳細を検討してください。  
  
-   すべての結果として得られるメッセージが送信され、すべての関連する処理が完了するまで、受信場所に到着した時点からのメッセージの種類ごとのライフ サイクルについて説明します。  
  
-   エラー条件の処理がどのように変化するかについて説明します。  
  
-   詳細についてには、相関関係、配信通知、および受信確認が含まれます。  
  
-   待機時間とスループットに関するパフォーマンスの要件の情報が含まれます。  
  
 **Microsoft 以外のソフトウェアの詳細**  
  
 詳細なソリューション設計の一部として使用されるすべての Microsoft 以外のソフトウェアを完全に記載されています。  
  
 **詳細なハードウェア スタック**  
  
 以前に作成した高レベルのハードウェア図上の構築、次のハードウェア情報を完全に記述します。  
  
-   [プロセッサ]  
  
    -   型  
  
    -   速度  
  
    -   コアの数  
  
    -   ハイパースレッディングが有効  
  
-   [メモリ]  
  
    -   Amount  
  
    -   速度  
  
    -   パリティ  
  
-   ネットワーク  
  
    -   ネットワーク インターフェイス カード (Nic) の数  
  
    -   ネットワークの速度  
  
-   SAN  
  
    -   各コンピューターでの SAN カードの数  
  
    -   各コンピューターと各 LUN の目的の論理ユニット番号 (Lun) の数  
  
    -   記憶域の速度のネットワーク (SAN) カード  
  
    -   SAN 構成の詳細をカードします。  
  
    -   SAN ディスクの割り当て、書式設定、およびパーティション分割  
  
-   [ディスク]  
  
    -   各コンピューターのローカル ディスクの詳細  
  
    -   ローカル ディスクの使用の書式設定  
  
    -   ローカル ディスクのパーティション分割の詳細  
  
-   Cache  
  
    -   L2 キャッシュの容量  
  
    -   L3 キャッシュ容量  
  
 **詳細なソフトウェア スタック**  
  
 次のソフトウェアの情報を文書化する必要があります。  
  
-   特定のオペレーティング システムのバージョン、エディション、およびアーキテクチャ  
  
-   特定のオペレーティング システムの機能  
  
-   各コンピューターにインストールされている特定のソフトウェア  
  
-   特定のドライバー  
  
-   サービス パックおよびその他の更新プログラム  
  
-   既定値と異なっている場合に使用されるすべてのソフトウェアとオペレーティング システムの機能の構成値  
  
## <a name="building-out-the-environment-for-the-solution"></a>ソリューションの環境の構築  
 インストール手順の詳細な[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と必要な依存関係のソフトウェアをダウンロードできる BizTalk Server のインストール ガイドで見つかること[BizTalk Server 2010 ドキュメント](http://go.microsoft.com/fwlink/?LinkId=183138)(http://go.microsoft.com/fwlink/ しますか。LinkId = 183138)。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server 層の計画](../technical-guides/planning-the-biztalk-server-tier.md)