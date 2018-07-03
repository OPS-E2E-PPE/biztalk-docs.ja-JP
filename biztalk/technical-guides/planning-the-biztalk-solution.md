---
title: BizTalk ソリューションの計画 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 30d56a04-966a-46b1-861d-f5be4e58b7d2
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f337efa7b72a40c37a4cc3f42a2bd5d846923dc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970955"
---
# <a name="plan-for-your-biztalk-solution"></a>BizTalk ソリューションを計画します。
主な設計目標の 1 つ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]できるだけ多くの処理のシナリオに対応するために最大限の柔軟性を提供することです。 この柔軟性により機能の最適な使用で使用できるようにする方法を決定する BizTalk ソリューションの開発者が直面する主な課題の 1 つは[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ビジネスに合わせて必要があります。 計画、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]は以下に示す種類のフェーズに分けることができます。  
  
## <a name="scoping-the-solution"></a>ソリューションのスコープ  
  
### <a name="performance-considerations"></a>パフォーマンスに関する考慮事項  
 BizTalk ソリューションをスコープとは、次を考慮してください。  
  
- どのアダプターとアクセラレータが必要ですか。  
  
- ソリューションにオーケストレーションを実装するための要件とは  
  
- スループットの要件を文書化: ソリューションの最大持続可能スループットの要件は何ですか?  
  
- 待機時間の要件: どのように応答性の高いソリューションにする必要は送信請求-応答と要求-応答のシナリオのでしょうか。  
  
- ソリューションは、ピーク時のドキュメントの読み込みの期間からどの程度回復か。  
  
- ソリューションの高可用性の要件とは  
  
- ソリューションのドキュメント追跡の要件とは  
  
- リモートの Web サービスまたはその他のシステムなど、あらゆる依存アプリケーションのパフォーマンス特性を挙げてください。 必要な負荷に依存するアプリケーションは保持しない場合は、システム全体のパフォーマンスを適宜デグレードされます。  
  
- BizTalk アプリケーションはデータベースに関連していないを消費する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]でしょうか。 たとえば、BizTalk アプリケーションが SQL アダプターを使用して SQL Server データベースのテーブルを使用する場合はテーブル効率的に構成しますか。  
  
### <a name="hardware-considerations"></a>ハードウェアについての注意事項  
 ソリューションをスコープには、以下を含むハードウェアの高度なダイアグラムを作成します。  
  
-   コンピューターのアーキテクチャ (x86、x64、IA64 など)  
  
-   CPU 要件 (など、種類、速度、数、コア、ハイパースレッディングを使用)  
  
-   各コンピューターの RAM の要件  
  
-   ローカル ディスク ストレージ (型、サイズ、速度)  
  
-   SAN (記憶域の要件: LUN の数SAN カードの種類)  
  
-   ネットワーク カード (1 ギガビットと 100 メガビット (Mbps) は、各コンピューターの数 (1 Gbps).)  
  
-   ファイアウォールは、ソリューションでどのように展開されますか。  
  
-   ネットワーク負荷分散ハードウェアが使用されますか。  
  
-   クラスター化する特定のコンピューターか?  
  
-   Microsoft HYPER-V Server またはその他の仮想化製品に関連する仮想環境を使用するでしょうか。  
  
## <a name="planning-the-solution"></a>ソリューションの計画  
  
### <a name="solution-milestones-timeline"></a>ソリューションのマイルス トーンのタイムライン  
 BizTalk ソリューションの特定の側面を完了するためのマイルス トーンでは、スケジュールを作成します。 特定のマイルス トーンを設定するソリューションとなる可能性が高く、適切なタイミングで完了します。  
  
### <a name="non-microsoft-software-considerations"></a>Microsoft 以外のソフトウェアの考慮事項  
 Microsoft 以外のソフトウェアは、ソリューションで使用される場合は、次を検討します。  
  
-   ソフトウェアまたはハードウェアの必要のある判断を取得します。  
  
-   容量の計画し、する Microsoft 以外のソフトウェアを確実にサイズ変更が、ソリューション内のボトルネックになりません。  
  
-   必要な Microsoft 以外のソフトウェアをインストールするための行動計画を決定します。  
  
-   アクションを構成し、必要な Microsoft 以外のソフトウェアを最適化するための計画を作成します。  
  
## <a name="preparing-for-the-solution"></a>ソリューションの準備  
 準備フェーズでは、次の要素を含めます。  
  
### <a name="detailed-design-of-the-solution-platform"></a>ソリューション プラットフォームの詳細な設計  
 詳細なソリューションの設計では、通信を容易を俊敏性とすべてのアクティビティの有効性を改善する前提条件を回避できます。 完全に、次の要素を文書化する必要があります。  
  
- BizTalk Server データベースとコンピューター間での分散方法。  
  
- BizTalk ホストの設計と各ホストとそれらのインスタンスの説明。  
  
- 各オーケストレーションの説明です。  
  
- 各パイプラインの説明です。  
  
- .NET アセンブリなどのカスタム コンポーネントと COM + コンポーネントの説明。  
  
  **メッセージ フロー図**  
  
  混乱や false にメッセージを処理中に発生することは想定されて内容に関する前提条件を回避するための詳細なメッセージ フロー ダイアグラムを作成します。 メッセージのフロー ダイアグラムを作成するときに、次の詳細を検討してください。  
  
- 結果として得られるすべてのメッセージが送信され、すべての関連する処理が完了するまで、受信場所に到着した時点からのメッセージの種類ごとのライフ サイクルについて説明します。  
  
- 処理のエラー条件を変更する方法について説明します。  
  
- 相関関係、配信通知、および受信確認の詳細が含まれます。  
  
- 待機時間とスループットに関するパフォーマンス要件の情報が含まれます。  
  
  **Microsoft 以外のソフトウェアの詳細**  
  
  詳細なソリューション設計の一部として使用されるすべての Microsoft 以外のソフトウェアを完全に記述する必要があります。  
  
  **詳細なハードウェア スタック**  
  
  以前に作成した高レベルのハードウェア図上の構築、次のハードウェア情報が完全に記述します。  
  
- [プロセッサ]  
  
  -   型  
  
  -   速度  
  
  -   コアの数  
  
  -   ハイパー スレッド  
  
- Memory  
  
  -   Amount  
  
  -   速度  
  
  -   パリティ  
  
- ネットワーク  
  
  -   ネットワーク インターフェイス カード (Nic) の数  
  
  -   ネットワークの速度  
  
- SAN  
  
  -   各コンピューターでの SAN のカードの数  
  
  -   各コンピューターと各 LUN の目的の論理ユニット番号 (Lun) の数  
  
  -   速度の記憶域ネットワーク (SAN) カード  
  
  -   SAN カード構成の詳細  
  
  -   SAN ディスク割り当て、書式設定、およびパーティション分割  
  
- [ディスク]  
  
  -   各コンピューターのローカル ディスクの詳細  
  
  -   ローカル ディスクとして使用される書式設定  
  
  -   ローカル ディスクのパーティション分割の詳細  
  
- Cache  
  
  -   L2 キャッシュの量  
  
  -   L3 キャッシュ容量  
  
  **詳細なソフトウェア スタック**  
  
  次のソフトウェアの情報を文書化する必要があります。  
  
- 特定のオペレーティング システムのバージョン、エディション、およびアーキテクチャ  
  
- 特定のオペレーティング システムの機能  
  
- 各コンピューターにインストールされている特定のソフトウェア  
  
- 特定のドライバー  
  
- サービス パックとその他の更新  
  
- 既定値からずれている場合に使用されるすべてのソフトウェアとオペレーティング システムの機能の構成値  
  
## <a name="building-out-the-environment-for-the-solution"></a>ソリューションの環境の構築  
 インストール手順の詳細な[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]とソフトウェア要件、 [BizTalk Server インストール ガイド](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md)します。
  
## <a name="see-also"></a>参照  
 [BizTalk Server 層の計画](../technical-guides/planning-the-biztalk-server-tier.md)
