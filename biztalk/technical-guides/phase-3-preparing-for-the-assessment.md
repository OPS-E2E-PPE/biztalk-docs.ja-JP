---
title: 'フェーズ 3: 評価の準備中 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d153ed62-f2cc-4080-8912-c98ecdd329f5
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 890047f6a13352d89d33d9514883dc20eacd4001
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22301842"
---
# <a name="phase-3-preparing-for-the-assessment"></a>フェーズ 3: が評価用に準備します。
パフォーマンス評価の段階できますと考えるのスコープのフェーズに「方法」"what"と計画フェーズの準備の「ときです」 この時点でパフォーマンス評価はすべての利害関係者必要があります、ラボを実行するため、活動、およびプランのスコープによって、合意しています。 ここで、プランを実行し、パフォーマンス ラボの実行用に準備する手順を実行のパフォーマンス評価の準備フェーズになります。  
  
 このトピックでは、BizTalk Server のパフォーマンス評価の準備フェーズのさまざまな側面について説明します。  
  
## <a name="detailed-design-of-the-solution-platform"></a>ソリューション プラットフォームの詳細な設計  
 詳細なソリューションの設計では、コミュニケーションを促進し、前提条件、機敏性とすべてのアクティビティの有効性が向上を回避できます。 次の要素完全に文書化する必要があります。  
  
-   **BizTalk Server データベースおよび複数のコンピューターでの分散方法**-SQL Server のパフォーマンスは、BizTalk Server の全体的なパフォーマンスで重要な要因の 1 つです。 SQL Server には、リソースの制約が発生していますが、これはメッセージを処理する BizTalk Server の機能が影響します。 BizTalk データベースのパフォーマンスに影響を与える主な要因は、上でホストされているディスクの速度です。 各 BizTalk のトランザクション ログとデータベース ファイルの分離を別々 のドライブまたは SAN LUN にデータベースが表示非常に BizTalk Server の全体的なパフォーマンスを向上させる。 そのため、これが簡単にアクセスできるように、この情報を記録することが重要です。 実稼働環境で使用される値は、詳細なソリューションの設計で文書化する必要があります。 次の表は、この実行方法の例を示します。  
  
    |BizTalk データベース|ボリューム名|[ファイル]|LUN # または ml _ #|物理的な LUN のサイズ (GB)|  
    |----------------------|-----------------|-----------|---------------------|------------------------------|  
    |メッセージ ボックス|Data_TempDb_1|TEMPDB、マスターおよび MSDB のデータ ファイル|1|134|  
    ||Logs_TempDb_1|TEMPDB、マスターおよび MSDB のトランザクション ログ ファイル|2|134|  
    ||Data_BtsMsgBox|BizTalkMsgBoxDb データ ファイル|3|134|  
    ||Logs_BtsMsgBox|BizTalkMsgBoxDb トランザクション ログ ファイル|4|134|  
    |BAM|Data_TempDb_2|TEMPDB、マスターおよび MSDB のデータ ファイル|5|67|  
    ||Logs_TempDb_2|TEMPDB、マスターおよび MSDB のトランザクション ログ ファイル|6|67|  
    ||Data_BAM|BAMPrimaryImport のデータ ファイル|7|134|  
    ||Logs_BAM|BAMPrimaryImport のトランザクション ログ ファイル|8|134|  
    |BizTalk 追跡、管理、シングル サインオンおよびルール エンジン データベース|Data_TempDb_3|TEMPDB、MASTER、MSDB、BizTalkDTADb、BizTalkMgmtDb、ENTSSO、および BizTalkRuleEngineDb のデータ ファイル|9|67|  
    ||Logs_TempDb_3|TEMPDB、MASTER、MSDB、BizTalkDTADb、BizTalkMgmtDb、ENTSSO、および BizTalkRuleEngineDb のトランザクション ログ ファイル|10|67|  
  
-   **BizTalk ホストの設計と各ホストおよびそのインスタンスの説明。**  
  
-   **各オーケストレーションの説明です。**  
  
-   **各パイプラインの説明です。**  
  
-   **.NET アセンブリなどのカスタム コンポーネント、COM + コンポーネントの説明です。**  
  
## <a name="detailed-architecture-diagram"></a>詳細なアーキテクチャ ダイアグラム  
 次の図は、パフォーマンスの評価のために使用できるアーキテクチャの図を示しています。  
  
 ![BizTalk アーキテクチャ図](../technical-guides/media/architecturediagram.gif "ArchitectureDiagram")  
BizTalk アーキテクチャ図  
  
## <a name="message-flow-diagrams"></a>メッセージ フロー図  
 メッセージを処理中に発生することにどのようななってに関する混乱または false の前提条件を防ぐために役立つ詳細なメッセージのフロー チャートを作成します。  
  
 を検討するとき、BizTalk ソリューションに関する包括的なシステムのメッセージ フローと考える傾向があります。 このメッセージの流れパースペクティブは、パフォーマンス、フローのすべての部分は、潜在的なボトルネックと見なされる必要があるためにテストを実施する際に特に重要です。 メッセージ フロー図を持つ、混乱を防止またはメッセージを各テスト中に発生することにどのようななってに関する誤った想定を実行します。  
  
 次の例では、単純なの Visio 図形を使用して作成された背景に関係なく、プロジェクトのすべてのユーザーにすばやく理解できるシステムにメッセージを取得する方法、ソリューションのどの部分と対話し、メッセージを最後にした後、メッセージが入る場所処理しています。  
  
 ![Message Flow Diagram](../technical-guides/media/11c5afac-5c1b-42a5-8947-7c6d0ca4e2df.gif "11c5afac-5c1b-42a5-8947-7c6d0ca4e2df")  
メッセージ フロー図  
  
 メッセージのフロー チャートを作成するときに、次の詳細を検討してください。  
  
-   すべての結果として得られるメッセージが送信され、すべての関連する処理が完了するまで、受信場所に到着した時点からのメッセージの種類ごとのライフ サイクルについて説明します。  
  
-   エラー条件の処理がどのように変化するかについて説明します。  
  
-   詳細についてには、相関関係、配信通知、および受信確認が含まれます。  
  
-   外部システムへの依存度に関する詳細が含まれます。  
  
-   待機時間とスループットに関するパフォーマンスの要件の情報が含まれます。  
  
## <a name="third-party-software-details"></a>サード パーティ製ソフトウェアの詳細  
 詳細なソリューション設計の一部として使用されるすべての Microsoft 以外のソフトウェアを完全に記載されています。  
  
## <a name="detailed-lab-hardware-stack"></a>詳細なラボ ハードウェア スタック  
 以前に作成した高度なハードウェア図上の構築、次のハードウェア情報を完全に記述します。  
  
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
  
## <a name="detailed-lab-software-stack"></a>詳細なラボ ソフトウェア スタック  
 次のソフトウェアの情報を文書化する必要があります。  
  
-   特定のオペレーティング システムのバージョン、エディション、およびアーキテクチャ  
  
-   特定のオペレーティング システムの機能  
  
-   各コンピューターにインストールされている特定のソフトウェア  
  
-   特定のドライバー  
  
-   サービス パックおよびその他の更新プログラム  
  
-   既定値と異なっている場合に使用されるすべてのソフトウェアとオペレーティング システムの機能の構成値  
  
## <a name="see-also"></a>参照  
 [パフォーマンス評価の段階](../technical-guides/phases-of-a-performance-assessment.md)