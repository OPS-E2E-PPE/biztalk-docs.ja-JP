---
title: データベースの高可用性 |Microsoft Docs
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
ms.openlocfilehash: 65e3a5f3c6f4bea186dfe75396016ddd45e8ffcf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983155"
---
# <a name="high-availability-for-databases"></a>データベースの高可用性
データ ストアとデータの永続化のため、BizTalk Server が SQL Server では大きく依存します。 その他すべての BizTalk Server コンポーネントおよびホストにも、多種多様な業務アプリケーション (メッセージの受信、処理、ルーティングなど) を統合するプロセスにおいて、それぞれ固有の役割がありますが、この作業をディスクに取り込み、維持するという役割は、データベース コンピューターにあります。 たとえば、BizTalk サーバーでは、受信メッセージを受信すると、受信ホストに永続化、メッセージ ボックス データベースの他のホストのオーケストレーションの処理および送信メッセージを取得する前に。 BizTalk ソリューションには、オーケストレーションが含まれている場合、BizTalk Server は、(処理ホスト)、ビジネス プロセスを実行し、オーケストレーションが実行した後は、メッセージをメッセージ ボックス データベースに保存します。 ホストにメッセージをルーティングします。 その後、送信ホストが、そのメッセージをデータベースから取り出し、適切な送信アダプターを使って外部のアプリケーションに送信します。  
  
 BizTalk Server データベースの高可用性を実現するには、サーバー クラスターを作成するのに SQL Server を実行している 2 つ以上のコンピューターを構成するのに Windows クラスタ リングを使用します。 このサーバーのクラスタ リングは、冗長性とフォールト トレランス、BizTalk Server データベースを提供します。 複数のコンピューターを並列に運用して可用性とスケーラビリティを高めようとする負荷分散クラスタリングとは異なり、サーバー クラスタリングでは通常、2 台のデータベース コンピューターをアクティブ/パッシブ構成で使用します。この構成では、一方のコンピューターが他方のコンピューターのバックアップ リソースを提供します。  
  
 次の図は、アクティブ/パッシブ構成のサーバー クラスタリングによって高可用性を実現した BizTalk Server のデータベース層を示しています。  
  
 ![BizTalk Server のデータベース層](../core/media/tdi-highava-sqlcluster.gif "TDI_HighAva_SQLCluster")  
  
 アクティブ側のデータベース コンピューターでエラーや障害が発生した場合、障害の起きたコンピューターが復旧するまでの間、パッシブ側のコンピューターがアクティブになり、データベース リソースの管理を引き継ぎます。 データベース サービスは、フェールオーバーしデータ接続を新しいアクティブなコンピューターに復元および、により、BizTalk アプリケーションに機能し続けるにします。  
  
## <a name="biztalk-server-databases"></a>BizTalk Server データベース  
 Microsoft BizTalk Server によって、SQL Server にいくつかのデータベースがインストールされます。 次の表では、BizTalk Server データベース用の一般的な使用状況特性を示します。  
  
|[データベース]|既定のデータベース名|使用状況特性|  
|--------------|---------------------------|---------------------------|  
|管理データベース|BizTalkMgmtDb|このデータベース ハンドル使用頻度の低いは読み取りおよび書き込み操作です。|  
|メッセージ ボックス データベース|BizTalkMsgBoxDb|このデータベース ハンドルの使用率の高いは、読み取りおよび書き込み操作です。|  
|追跡データベース|BizTalkDTADb|このデータベースは、可能性のある使用率の高い書き込み操作を追跡するように構成データの量に応じてを処理し、使用頻度の低い読み取り操作します。|  
|SSO データベース|SSODB|このデータベース ハンドル使用頻度の低いは読み取りおよび書き込み操作です。|  
|BAM 分析データベース|BAMAnalysis|可能性のある使用率の高い読み取りおよび書き込み操作の実行の監視のレベルに応じて、この SQL Server Analysis Services データベースを処理します。|  
|BAM スター スキーマ データベース|BAMStarSchema|可能性のある使用率の高い読み取りおよび書き込み操作の実行の監視のレベルに応じて、この SQL Server Analysis Services データベースを処理します。|  
|BAM プライマリ インポート データベース|BAMPrimaryImport|可能性のある使用率の高い読み取りおよび書き込み操作の実行の監視のレベルに応じて、この SQL Server Analysis Services データベースを処理します。|  
|BAM アーカイブ データベース|BAMArchive|可能性のある使用率の高い読み取りおよび書き込み操作の実行の監視のレベルに応じて、この SQL Server Analysis Services データベースを処理します。|  
|ルール エンジン データベース|BizTalkRuleEngineDb|このデータベースは、ルールを更新する場合を除き、可能性のある使用率の低い読み取り/書き込み操作を処理します。|  
|Analysis Services データベースの追跡|BizTalkAnalysisDb|この SQL Server Analysis Services データベースの使用率の高い読み取りおよび書き込み操作のハンドル。|  
  
 BizTalk Server ランタイム操作は、通常、最初の 4 つのデータベース (管理データベース、メッセージ ボックス データベース、追跡データベース、および SSO データベース) を使用します。 によってこれらのデータベース上のトラフィック、SQL Server を実行している別のコンピューター上に配置できます。 使用するデータベースは、BizTalk Server のどの機能を使うかによって異なります。表に示したデータベースを全部使用する場合も、一部だけを使用する場合もあります。 必要に応じて、これらのデータベースをクラスターし、スケール アウトできます。  
  
 データベースごとに個別のディスクの使用などの適切な SQL Server 展開プラクティスに従うことを確認します。  
  
 BizTalk Server データベースの場合、次を行うことお勧めします。  
  
- **フェールオーバー クラスタ リングをセットアップ**します。 フェールオーバー クラスタ リングにより、SQL Server が稼働中のサーバーに障害が発生したサーバーから SQL Server のインスタンスの処理を自動的に切り替わります。  
  
   BAM プライマリ インポート データベースは、イベント データを収集します。 障害が発生した場合、前回のバックアップ以降に BAM プライマリ インポート データベースに書き込まれたデータが失われます。 失われたイベントを再生成する方法はありません、ために、BAM プライマリ インポート データベースに対してフェールオーバー クラスタ リングを有効にすることは特に重要ですが。  
  
- **使用して、SQL Server RAID 1 + 0 (独立したディスクの冗長アレイ)**、特にメッセージ ボックス データベースおよび BAM プライマリ インポート データベースの。  
  
  BizTalk Server データベースのバックアップについては、次を参照してください。[ディザスター リカバリーのベスト プラクティス](../technical-guides/best-practices-for-disaster-recovery.md)します。  
  
> [!NOTE]  
>  Microsoft SQL Server では、データベースが使用可能なである確率を高めるためのデータベース ミラーリングと呼ばれるソフトウェア ソリューションを提供します。 SQL Server データベース ミラーリングの使用は、現在、BizTalk Server データベースでトランザクションの一貫性を維持する潜在的な問題のため、Microsoft BizTalk Server データベースの高可用性を確保するためのサポートされているソリューションではありません。  
>   
>  データベース ミラーリングと SQL Server データベースにまたがるトランザクションの詳細については、次を参照してください。[トランザクション - 可用性グループとデータベース ミラーリング](https://docs.microsoft.com/sql/database-engine/availability-groups/windows/transactions-always-on-availability-and-database-mirroring)します。 BizTalk Server データベースを高可用性を確保する SQL Server クラスターにインストールする必要があり、ディザスター リカバリーの目的でログ配布を使用する必要があります。  
>   
>  ログ配布の詳細については、次を参照してください[内容は、BizTalk Server のログ配布しますか?。](../technical-guides/what-is-biztalk-server-log-shipping.md)  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [BizTalk Server データベースのクラスタリング](../technical-guides/clustering-the-biztalk-server-databases2.md)  
  
-   [BizTalk Server データベースのスケール アウト](../technical-guides/scaling-out-the-biztalk-server-databases.md)  
  
## <a name="see-also"></a>参照  
 [高可用性の計画](../technical-guides/planning-for-high-availability2.md)   
 [BizTalk ホストの高可用性](../technical-guides/high-availability-for-biztalk-hosts.md)   
 [マスター シークレット サーバーの高可用性](../technical-guides/high-availability-for-the-master-secret-server.md)   
 [ディザスター リカバリー](../technical-guides/disaster-recovery.md)