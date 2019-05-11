---
title: フェーズ 3:評価の準備 |Microsoft Docs
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
ms.openlocfilehash: 9df65cbac6b612db6faa979cd2ff57d1a53bd83f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399587"
---
# <a name="phase-3-preparing-for-the-assessment"></a>フェーズ 3:評価の準備
パフォーマンス評価の段階はスコープ フェーズのする「方法」として「と」と計画フェーズの準備の"when"。 この時点で、パフォーマンスの評価ですべての関係者必要があります合意している場合、engagement と、プランの演習を実行するためのスコープ。 パフォーマンスの評価、計画が実行され、パフォーマンス ラボの実行の準備の手順を実行の準備フェーズ中です。  
  
 このトピックでは、BizTalk Server のパフォーマンス評価の準備フェーズのさまざまな側面について説明します。  
  
## <a name="detailed-design-of-the-solution-platform"></a>ソリューション プラットフォームの詳細な設計  
 詳細なソリューションの設計では、通信を容易を俊敏性とすべてのアクティビティの有効性を改善する前提条件を回避できます。 完全に、次の要素を文書化する必要があります。  
  
-   **BizTalk Server データベースとコンピューター間での分散方法**-SQL Server のパフォーマンスは、BizTalk Server の全体的なパフォーマンスで重要な要因の 1 つです。 SQL Server には、リソースの制約が発生する場合これはメッセージを処理する BizTalk Server の機能に影響します。 BizTalk データベースのパフォーマンスに影響する主な要因は、上でホストされているディスクの速度です。 各 BizTalk のトランザクション ログとデータベース ファイルを分離する別々 のドライブまたは SAN LUN の上にデータベースが示されている非常に BizTalk Server の全体的なパフォーマンスが向上します。 そのため、簡単にアクセスできる方法でこの情報が記録されることが重要です。 詳細なソリューションの設計、運用環境で使用される値を文書化する必要があります。 次の表では、この実行方法の例を示します。  
  
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
    |BizTalk 追跡、管理、シングル サインオン、およびルール エンジン データベース|Data_TempDb_3|TEMPDB、MASTER、MSDB、BizTalkDTADb、BizTalkMgmtDb、ENTSSO、および BizTalkRuleEngineDb のデータ ファイル|9|67|  
    ||Logs_TempDb_3|TEMPDB、MASTER、MSDB、BizTalkDTADb、BizTalkMgmtDb、ENTSSO、および BizTalkRuleEngineDb のトランザクション ログ ファイル|10|67|  
  
-   **BizTalk ホストの設計と各ホストとそれらのインスタンスの説明。**  
  
-   **各オーケストレーションの説明です。**  
  
-   **各パイプラインの説明です。**  
  
-   **.NET アセンブリなどのカスタム コンポーネントと COM + コンポーネントの説明。**  
  
## <a name="detailed-architecture-diagram"></a>詳細なアーキテクチャの図  
 次の図は、パフォーマンス評価のために使用できるアーキテクチャの図を示します。  
  
 ![BizTalk アーキテクチャ図](../technical-guides/media/architecturediagram.gif "ArchitectureDiagram")  
BizTalk アーキテクチャ図  
  
## <a name="message-flow-diagrams"></a>メッセージ フロー図  
 メッセージを処理中に発生するにどのようなことは想定されてに関する混乱や false の前提条件を防ぐための詳細なメッセージ フロー ダイアグラムを作成します。  
  
 BizTalk ソリューションを包括的考えた場合、システム内のメッセージ フローと考える傾向があります。 このメッセージ フローのパースペクティブは、パフォーマンス、フローのすべての部分は、潜在的なボトルネックとして考慮する必要がありますので、テストを実施する際に特に重要です。 混乱を防ぎますがメッセージのフロー ダイアグラムをまたはにメッセージを各テスト中に発生することは想定されて内容に関する間違った前提を実行します。  
  
 次の例では、単純な Visio の図形を使用して作成背景に関係なく、プロジェクトの全員すばやく理解できるシステムにメッセージを取得する方法、ソリューションの部分と、メッセージの対話および最後にした後、メッセージがアクセスしました。処理しています。  
  
 ![Message Flow Diagram](../technical-guides/media/11c5afac-5c1b-42a5-8947-7c6d0ca4e2df.gif "11c5afac-5c1b-42a5-8947-7c6d0ca4e2df")  
メッセージ フロー図  
  
 メッセージのフロー ダイアグラムを作成するときに、次の詳細を検討してください。  
  
-   結果として得られるすべてのメッセージが送信され、すべての関連する処理が完了するまで、受信場所に到着した時点からのメッセージの種類ごとのライフ サイクルについて説明します。  
  
-   処理のエラー条件を変更する方法について説明します。  
  
-   相関関係、配信通知、および受信確認の詳細が含まれます。  
  
-   外部システムへの依存度に関する詳細が含まれます。  
  
-   待機時間とスループットに関するパフォーマンス要件の情報が含まれます。  
  
## <a name="third-party-software-details"></a>サード パーティ製ソフトウェアの詳細  
 詳細なソリューション設計の一部として使用されるすべての Microsoft 以外のソフトウェアを完全に記述する必要があります。  
  
## <a name="detailed-lab-hardware-stack"></a>詳細なラボ ハードウェア スタック  
 以前に作成した高度なハードウェア図上の構築、次のハードウェア情報が完全に記述します。  
  
-   [プロセッサ]  
  
    -   型  
  
    -   速度  
  
    -   コアの数  
  
    -   ハイパー スレッド  
  
-   Memory  
  
    -   Amount  
  
    -   速度  
  
    -   パリティ  
  
-   ネットワーク  
  
    -   ネットワーク インターフェイス カード (Nic) の数  
  
    -   ネットワークの速度  
  
-   SAN  
  
    -   各コンピューターでの SAN のカードの数  
  
    -   各コンピューターと各 LUN の目的の論理ユニット番号 (Lun) の数  
  
    -   速度の記憶域ネットワーク (SAN) カード  
  
    -   SAN カード構成の詳細  
  
    -   SAN ディスク割り当て、書式設定、およびパーティション分割  
  
-   Disk  
  
    -   各コンピューターのローカル ディスクの詳細  
  
    -   ローカル ディスクとして使用される書式設定  
  
    -   ローカル ディスクのパーティション分割の詳細  
  
-   Cache  
  
    -   L2 キャッシュの量  
  
    -   L3 キャッシュ容量  
  
## <a name="detailed-lab-software-stack"></a>詳細なラボ ソフトウェア スタック  
 次のソフトウェアの情報を文書化する必要があります。  
  
-   特定のオペレーティング システムのバージョン、エディション、およびアーキテクチャ  
  
-   特定のオペレーティング システムの機能  
  
-   各コンピューターにインストールされている特定のソフトウェア  
  
-   特定のドライバー  
  
-   サービス パックとその他の更新  
  
-   既定値からずれている場合に使用されるすべてのソフトウェアとオペレーティング システムの機能の構成値  
  
## <a name="see-also"></a>参照  
 [パフォーマンス評価のフェーズ](../technical-guides/phases-of-a-performance-assessment.md)