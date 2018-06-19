---
title: データベースの高可用性 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 63813d87-1ce4-4645-bb2a-d55e413fcace
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 24e17afbf9e33f3e12553d7ded5068370d8ca085
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26009363"
---
# <a name="high-availability-for-databases"></a>データベースの高可用性
BizTalk Server に大きく依存して SQL Server のデータ ストアとデータの永続化します。 その他すべての BizTalk Server コンポーネントおよびホストにも、多種多様な業務アプリケーション (メッセージの受信、処理、ルーティングなど) を統合するプロセスにおいて、それぞれ固有の役割がありますが、この作業をディスクに取り込み、維持するという役割は、データベース コンピューターにあります。 たとえば、BizTalk Server が受信メッセージを受信すると受信ホストに永続化、メッセージ ボックス データベースの他のホストは、オーケストレーションの処理および送信のメッセージを取得する前にします。 BizTalk ソリューションには、オーケストレーションが含まれている場合、BizTalk Server は (処理ホスト)、ビジネス プロセスを実行し、オーケストレーションの完了後に、メッセージをメッセージ ボックス データベースに保存します。 ホストにメッセージをルーティングします。 その後、送信ホストが、そのメッセージをデータベースから取り出し、適切な送信アダプターを使って外部のアプリケーションに送信します。  
  
 BizTalk Server データベースの高可用性を実現するには、サーバー クラスターを作成するのに SQL Server を実行している 2 つ以上のコンピューターを構成するのに Windows クラスタ リングを使用します。 このサーバーのクラスター化は、冗長性と、BizTalk Server データベースのフォールト トレランスを提供します。 複数のコンピューターを並列に運用して可用性とスケーラビリティを高めようとする負荷分散クラスタリングとは異なり、サーバー クラスタリングでは通常、2 台のデータベース コンピューターをアクティブ/パッシブ構成で使用します。この構成では、一方のコンピューターが他方のコンピューターのバックアップ リソースを提供します。  
  
 次の図は、アクティブ/パッシブ構成のサーバー クラスタリングによって高可用性を実現した BizTalk Server のデータベース層を示しています。  
  
 ![BizTalk Server のデータベース層](../core/media/tdi-highava-sqlcluster.gif "TDI_HighAva_SQLCluster")  
  
 アクティブ側のデータベース コンピューターでエラーや障害が発生した場合、障害の起きたコンピューターが復旧するまでの間、パッシブ側のコンピューターがアクティブになり、データベース リソースの管理を引き継ぎます。 データベース サービスは、フェールオーバーしデータ接続を新しいアクティブなコンピューターに復元され、継続して機能する BizTalk アプリケーションを有効にします。  
  
## <a name="biztalk-server-databases"></a>BizTalk Server データベース  
 Microsoft BizTalk Server によって、SQL Server にいくつかのデータベースがインストールされます。 次の表は、BizTalk Server データベースの一般的な使用状況特性を示します。  
  
|データベース|既定のデータベース名|使用状況特性|  
|--------------|---------------------------|---------------------------|  
|管理データベース|BizTalkMgmtDb|このデータベース ハンドル使用率の低いは読み取りおよび書き込み操作です。|  
|メッセージ ボックス データベース|BizTalkMsgBoxDb|このデータベース ハンドルの使用率の高いは、読み取りおよび書き込み操作です。|  
|追跡データベース|BizTalkDTADb|このデータベースは、追跡するために構成データの量に応じて可能性のある使用率の高い書き込み操作を処理し、使用率の低い読み取り操作します。|  
|SSO データベース|SSODB|このデータベース ハンドル使用率の低いは読み取りおよび書き込み操作です。|  
|BAM 分析データベース|BAMAnalysis|可能性のある使用率の高い読み取りおよび書き込み操作の実行の監視のレベルに応じて、この SQL Server Analysis Services データベースを処理します。|  
|BAM スター スキーマ データベース|BAMStarSchema|可能性のある使用率の高い読み取りおよび書き込み操作の実行の監視のレベルに応じて、この SQL Server Analysis Services データベースを処理します。|  
|BAM プライマリ インポート データベース|BAMPrimaryImport|可能性のある使用率の高い読み取りおよび書き込み操作の実行の監視のレベルに応じて、この SQL Server Analysis Services データベースを処理します。|  
|BAM アーカイブ データベース|BAMArchive|可能性のある使用率の高い読み取りおよび書き込み操作の実行の監視のレベルに応じて、この SQL Server Analysis Services データベースを処理します。|  
|ルール エンジン データベース|BizTalkRuleEngineDb|このデータベースは、ルールを更新する場合を除き、可能性のある使用率の低い読み取りおよび書き込み操作を処理します。|  
|Analysis Services データベースの追跡|BizTalkAnalysisDb|この SQL Server Analysis Services データベースの使用率の高い読み取りおよび書き込み操作のハンドル。|  
  
 BizTalk Server ランタイム操作は、通常、最初の 4 つのデータベース (管理データベース、メッセージ ボックス データベース、追跡データベース、および SSO データベース) を使用します。 によっては、これらのデータベース上のトラフィックを SQL Server を実行している別のコンピューター上に配置できます。 使用するデータベースは、BizTalk Server のどの機能を使うかによって異なります。表に示したデータベースを全部使用する場合も、一部だけを使用する場合もあります。 スケール アウトし、必要に応じて、これらのデータベースをクラスターできます。  
  
 データベースごとに別々 のディスクの使用などの適切な SQL Server 展開プラクティスに従うことを確認します。  
  
 BizTalk Server データベースでは、次を行うことをお勧めします。  
  
-   **フェールオーバー クラスタ リング設定**です。 フェールオーバー クラスタ リングにより、SQL Server が稼働中のサーバーに障害が発生したサーバーから SQL Server のインスタンスの処理を自動的に切り替わります。  
  
     BAM プライマリ インポート データベースは、イベント データを収集します。 障害が発生した場合、前回のバックアップ以降に BAM プライマリ インポート データベースに書き込まれたデータが失われます。 失われたイベントを再生成する方法はありません、ためには、BAM プライマリ インポート データベースに対してフェールオーバー クラスタ リングを有効にすることが特に重要です。  
  
-   **使用して SQL Server RAID 1 + 0 (独立したディスクの冗長アレイ)**、特に、メッセージ ボックス データベースおよび BAM プライマリ インポート データベースのです。  
  
 BizTalk Server データベースのバックアップの詳細については、次を参照してください。[災害復旧のためのベスト プラクティス](../technical-guides/best-practices-for-disaster-recovery.md)です。  
  
> [!NOTE]  
>  Microsoft SQL Server では、データベースが使用可能なである確率を高めるためのデータベース ミラーリングと呼ばれるソフトウェア ソリューションを提供します。 SQL Server データベース ミラーリングの使用は、現在、BizTalk Server データベースでトランザクションの一貫性を維持する潜在的な問題があるため、Microsoft BizTalk Server データベースの高可用性を確保するためのサポートされているソリューションではありません。  
>   
>  データベース ミラーリングと SQL Server のデータベースにまたがるトランザクションに関する詳細については、次を参照してください。[トランザクションの可用性グループとデータベース ミラーリング](https://docs.microsoft.com/sql/database-engine/availability-groups/windows/transactions-always-on-availability-and-database-mirroring)です。 BizTalk Server データベースを高可用性を確保する SQL Server クラスターにインストールする必要があり、災害復旧の目的には、ログ配布を利用する必要があります。  
>   
>  ログ配布の詳細については、次を参照してください[新機能は、BizTalk Server ログ配布しますか?。](../technical-guides/what-is-biztalk-server-log-shipping.md)  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [BizTalk Server データベースのクラスタリング](../technical-guides/clustering-the-biztalk-server-databases2.md)  
  
-   [BizTalk Server データベースのスケール アウト](../technical-guides/scaling-out-the-biztalk-server-databases.md)  
  
## <a name="see-also"></a>参照  
 [高可用性の計画](../technical-guides/planning-for-high-availability2.md)   
 [BizTalk ホストの高可用性](../technical-guides/high-availability-for-biztalk-hosts.md)   
 [マスター シークレット サーバーの高可用性](../technical-guides/high-availability-for-the-master-secret-server.md)   
 [ディザスター リカバリー](../technical-guides/disaster-recovery.md)