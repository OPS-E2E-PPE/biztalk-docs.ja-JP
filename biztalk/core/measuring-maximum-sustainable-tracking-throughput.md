---
title: 維持可能な最大の追跡スループットの測定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 35605427-0217-4bdd-8b4a-3e68b3f5f452
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d68d1661a86858b8d2bca1bb067c8fa17ea421e3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37017062"
---
# <a name="measuring-maximum-sustainable-tracking-throughput"></a>維持できる最大の追跡スループットの測定
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] プラットフォームに基幹業務ソリューションを展開した後、次の事項を理解するためにシステムを追跡および監視する必要があります。  
  
- システムの動作の状況  
  
- 発生するエラーと例外の内容および発生する理由  
  
- BizTalk ソリューションとして実装されているビジネス プロセスの現在の状態  
  
  多くの組織にとっても重要です、否認不可のために、システムを流れる実際のメッセージを記録します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] これらの要件に対処する 2 つの種類の追跡機能を提供します。  
  
- **データの追跡およびアクティビティ (DTA) 追跡**します。 DTA は、さまざまなユーザー定義メッセージ プロパティ、オーケストレーション デバッグ イベント、メッセージ フロー イベント、およびサービス インスタンス ステータスを追跡します。 追跡を使用して、BizTalk DTA 追跡データベース (BizTalkDTADb) に格納されたデータに対するクエリを実行できます。 DTA 追跡には、否認不可および問題解決を目的として、メッセージ本文の追跡も含まれています。  
  
- **ビジネス アクティビティ監視 (BAM) 追跡**します。 BAM はユーザー定義追跡プロファイルを使用してビジネス プロセスの状態を追跡し、特別な BAM データベースに記録します。  
  
  このトピックでは、DTA アーキテクチャ、および DTA を使用するシステムが無限に維持できる最大スループットを決定する体系的な手法について説明します。 DTA と BAM は同じアーキテクチャ コンポーネントを共有しますが、このトピックでは DTA の動作のみ説明します。 BAM アーキテクチャについては、次を参照してください。[ビジネス アクティビティ監視 (BAM)](../core/business-activity-monitoring-bam.md)します。  
  
## <a name="overview-of-dta-tracking-architecture"></a>DTA 追跡アーキテクチャの概要  
 メッセージがシステムに送信されると、メッセージの本文、プロパティ、イベントなどさまざまな追跡対象の要素は一連のプロセスおよびデータベースを通過しますが、最終的に BizTalkDTADb データベースに書き込まれます。 要素が BizTalkDTADb データベースに書き込まれた後で、追跡を使用して、追跡した情報に対するクエリを実行できます。 データベースの設定および BizTalkDTADb を使用する方法については、追跡を参照してください[履歴の表示と追跡データ](../core/viewing-historical-and-tracked-data.md)します。  
  
 システムが維持可能で、特定のメッセージ フロー レートで無期限に動作できるようにするには、追跡対象の要素の経路が BizTalkDTADb データベースまでの固有のパスを通り、データベース自体が正常な状態を維持している必要があります。 たとえば、データベース テーブル内の途中、または DTA でメッセージがたまると、データベース ファイルが無制限に増える可能性があります。これらは、適切に管理しないと維持できません。  
  
 最初に、アーキテクチャおよび追跡情報が通る経路について説明します。 ここでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] エンジンを通過するメッセージ トラフィックを追跡システムが適正に追跡しているかを判断する場合に、監視対象となる主要なリソースおよびパフォーマンス インジケーターを示します。  
  
 次の図は、DTA 追跡アーキテクチャおよび経路の概要を示しています。  
  
 ![DTA 追跡の概要](../core/media/dtatrackingoverview.gif "DTATrackingOverview")  
  
 図に示された番号付きプロセスを順にたどると、すべての DTA 追跡データは次のように BizTalkDTADb データベースに入ったり、データベースから出たりしています。  
  
1. BizTalk Server ランタイム プロセスには、インターセプターというコンポーネントが含まれます。 インターセプターのジョブは、実行時に追跡要素をキャッシュし、次の MessageBox データベースとのやり取りで (たとえば、MessageBox データベースにメッセージをキューに入れるとき)、キャッシュした要素を MessageBox データベースに転送します。 インターセプターは、追跡構成 (追跡プロファイルとも呼ばれる) を参照して追跡する要素を決定します。追跡構成は、管理データベースから取得され、インターセプターが使用できるように各ホスト ランタイム インスタンスにキャッシュされます。  
  
    この図に示したように、MessageBox データベースへのデータ ストリームは 2 つあります。  
  
   - 1 つはスプール テーブルによって表されています。  
  
   - もう 1 つは TrackingData テーブルによって表されています。  
  
     追跡されるメッセージ本文は両方のストリームを使用します。 つまり、メッセージ本文 (データの BLOB と見なす) は、スプール テーブルによって表されるテーブルのセットを介して処理されます。 メッセージ本文に関連付けられたメッセージ イベント (たとえば、メッセージ識別子、メッセージ本文がいつ追跡されたか、メッセージ本文がどのインスタンスに関連付けられているか) は、TrackingData テーブルを介して処理されます。 メッセージ本文の追跡に関連付けられていないすべての追跡要素は、TrackingData テーブルを介してのみ処理されます。  
  
2. MessageBox データベースは、追跡データの単なる最初の停止であり、その後の追跡データ処理によって直接ブロックされることなくランタイムが処理を続行できるように追跡データをキャッシュするために使用されます。  
  
    追跡メッセージ本文 (BLOB) を表示したり、より永続的なストレージにアーカイブできる、BizTalkDTADb データベースに転送するために、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、TrackedMessages_Copy_BizTalkMsgBoxDb という SQL エージェント ジョブを使用します。これは、各 MessageBox データベース サーバーで動作します。 このジョブは、追跡のマークの付いたメッセージ本文を BizTalkDTADb データベースにコピーします。  
  
3. TDDS というサービスによって、メッセージ本文以外の追跡データはすべて MessageBox データベースから BizTalkDTADb データベースに移動されます。このサービスは、1 つ以上の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ホストで動作します。 BizTalk Server 管理コンソールのホスト プロパティ ページでホストが [Hosts Tracking] として構成されていない限り、TDDS サブサービスはそのホストの各インスタンスで実行されます。  
  
4. BizTalkDTADb データベースは、定期的に削除しない限り、無限に成長し、最終的に運用上の問題を引き起こします。 DTA Purge and Archive (BizTalkDTADb) と呼ばれる 1 つの SQL エージェント ジョブがあります。このジョブは、BizTalkDTADb データベースを削除するタスクを実行します。 既定では、このジョブは 1 分ごとに実行され、ユーザーが構成した時間 (たとえば 24 時間) が経過した完了済みインスタンスをすべて削除します。  
  
    詳細については、DTA Purge and Archive ジョブに関する、参照してください[DTA Purge and Archive ジョブを構成する方法](../core/how-to-configure-the-dta-purge-and-archive-job.md)します。  
  
5. 必要に応じて、DTA Purge and Archive ジョブで、データの長期保管またはオフライン表示のために、BizTalkDTADb データを SQL バックアップとしてアーカイブすることもできます。 アーカイブ済みの BizTalkDTADb データにクエリを実行する必要がある場合は、最初に、SQL Server の新しいデータベースとして復元してから、追跡または SQL クエリ アナライザーを使用してクエリを実行します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [DTA 追跡のパフォーマンス特性を理解します。](../core/understanding-dta-tracking-performance-behavior.md)  
  
-   [DTA 追跡の MST を測定するためのテスト シナリオ](../core/test-scenarios-for-measuring-mst-of-dta-tracking.md)  
  
-   [DTA 追跡の MST を特定するためのヒントとテクニック](../core/tips-and-tricks-for-finding-mst-of-dta-tracking.md)  
  
## <a name="see-also"></a>参照  
 [追跡データベースのサイズに関するガイドライン](../core/tracking-database-sizing-guidelines.md)