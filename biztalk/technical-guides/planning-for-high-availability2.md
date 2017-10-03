---
title: "高 Availability2 の計画 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 65271fd5-5294-406f-87f8-3aa394c235a2
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 310414b094b7175c6b07fc92697b460e6dd2a830
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="planning-for-high-availability"></a>高可用性の計画
[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] の高可用性は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 展開の可用性を低下させている機能コンポーネントの復旧にかかっています。  
  
 高可用性をデモンストレーションする[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]エラーが発生して、復旧で、製品の有効性を測定する必要があります。 高可用性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]展開エラーと障害は透過的に実行外部のアプリケーションやシステムとにより、すべてのサービス継続して正しく機能している中断を最小限にします。  
  
 設計、[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]アプリケーション統合またはビジネス プロセス統合シナリオに関連する各機能コンポーネントの冗長性を実装する高可用性を提供する展開が含まれます。 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]概念的には、データから分離することでこれらのシナリオの実装を簡素化し、*ホスト*データを処理します。 A*ホスト*BizTalk の論理的なコンテナーは、オーケストレーションなどの項目の送信ハンドラー、および受信ハンドラー。 作成する*のホスト インスタンスの*し、ホストに割り当てます。 ホスト インスタンスとは、特定のサーバー上のホストを物理的に表現したものです。 いずれかである、[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]サービス プロセス BTSNTSvc.exe または別のプロセスと呼ばれるなど、IIS を処理します。 高可用性を実現する手段[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]は、実行中の複数*のホスト インスタンスの*とクラスタ リング、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースを次のように。  
  
-   **BizTalk ホストのアーキテクチャ**です。 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]ホストを分離し、メッセージの受信、オーケストレーション、処理、およびメッセージを送信するなどの主要機能のための高可用性を実現する複数のホスト インスタンスを実行できます。 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] ではホスト インスタンスを通じて複数のコンピューターに自動的に負荷が分散されるため、これらのホストにクラスタリングを追加したり、負荷分散メカニズムを適用する必要はありません。 ただし、ホスト、HTTP アダプタと SOAP アダプタに必要な負荷分散メカニズムなどネットワーク負荷分散 (NLB) の高可用性を実現すると、FTP の受信ハンドラーを実行しているホスト、MSMQ、POP3、SQL、および SAP を必要と受信ハンドラーを実行して、高可用性を実現するためのメカニズムをクラスター化します。  
  
    > [!NOTE]  
    >  常に、SAP がクラスター化する必要があります受信アダプタは、2 フェーズ コミットのシナリオに対応します。  
  
-   **BizTalk Server データベースのアーキテクチャ**です。 高可用性構成を[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]データベースは一般に、2 つ以上の構成されます。[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]アクティブ/パッシブのサーバー クラスター構成で構成されているコンピューターのデータベースです。 これらのコンピューターに共通のディスク リソースを共有する (など、RAID 1 + 0 SCSI ディスク アレイやストレージ エリア ネットワーク) Windows フェールオーバー クラスタ リングを使用してバックアップの冗長性とフォールト トレランスを提供します。  
  
 高可用性のために重要な別の BizTalk 機能コンポーネントは、マスター シークレット サーバーです。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]暗号化キーを取得するには、このサービスに依存します。  
  
 このセクションでは、これらの各カテゴリでの高可用性に対処する方法に関する情報を提供します。 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]高可用性ソリューションが上に構築された[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]と[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]、用のホストを構成する前に、高可用性とこれらの製品を展開することを確認してください[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]です。 こうした基盤となる製品の高可用性を実現する方法については、次のリンクを参照してください。  
  
-   **ホワイト ペーパー: 高可用性: Always On Technologies**いただけます[http://go.microsoft.com/fwlink/?LinkId=156812](http://go.microsoft.com/fwlink/?LinkId=156812)です。  
  
-   Windows Server 2008 での問題のトラブルシューティングに関する詳細情報、 [Windows Server 2008 の展開、管理およびトラブルシューティングのページ](http://go.microsoft.com/fwlink/?LinkId=156813)(http://go.microsoft.com/fwlink/?LinkId=156813)。  
  
-   Windows Server 2008 での可用性とスケーラビリティに関する詳しい情報を入手[可用性とスケーラビリティ](http://go.microsoft.com/fwlink/?LinkId=156814)(http://go.microsoft.com/fwlink/?LinkId=156814)。  
  
-   参照してください、**高可用性**のセクションで、 [Windows Server 2008 R2 記事およびホワイト ペーパー ページ](http://go.microsoft.com/fwlink/?LinkId=157760)(http://go.microsoft.com/fwlink/?LinkId=157760)。  
  
## <a name="understanding-the-impact-of-a-component-failure"></a>コンポーネントの障害の影響を理解します。  
 次の表は、コンポーネントとの依存関係、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境およびへの影響、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンポーネントまたは依存関係が失敗した場合、環境。 コンポーネントまたは依存関係をクラスター化するかどうかを決定する際に、潜在的な障害の範囲を検討してください。  
  
|コンポーネントまたは依存関係|障害の範囲|  
|-----------------------------|----------------------|  
|[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]|システム全体です。 場合[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]が失敗した[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ドキュメントを処理することはできません。|  
|[マスター シークレット サーバー]|システム全体です。 マスター シークレット サーバーが、失敗した場合は[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ドキュメントを処理することはできません。 **注:**マスター シークレット サーバーが失敗した場合、BizTalk グループ内の各 BizTalk サーバーは BizTalk server のエンタープライズ SSO サービスが再起動されるまでは、マスター シークレットのメモリ内のキャッシュされたコピーを使用して引き続きです。 BizTalk サーバーで、エンタープライズ SSO サービスが再起動された場合は、キャッシュされたマスター シークレットのコピーがメモリから解放し、BizTalk server は、マスター シークレットの別のコピーを取得する場合は、マスター シークレット サーバーに接続できないする必要があります。 マスター シークレット サーバーは失敗し、BizTalk server のドキュメントの処理を続行する場合、グループ内 BizTalk サーバーでエンタープライズ SSO サービスを再開しないしないでください。|  
|MSDTC|サーバー。 MSDTC が失敗した場合、トランザクションのサポートを必要とするサーバー上のコンポーネントは失敗します。 **注:**ため[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]とマスター シークレット サーバーはトランザクションのサポートに MSDTC に依存するが、SQL server またはマスター シークレット サーバー上の MSDTC が失敗した場合、障害の範囲はシステム全体になります。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通信するときに、トランザクションのサポートを必要と[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]と実行時の操作中にマスター シークレット サーバーです。|  
|BizTalk ホスト インスタンス|サーバー。 BizTalk ホスト インスタンスに格納されていたすべてのコンポーネントは、ホスト インスタンスが失敗した場合は、ドキュメント処理に参加することができません。|  
|Microsoft メッセージ キュー (MSMQ)|サーバー。 MSMQ は失敗し、ドキュメントの処理など、MSMQ アダプター、MSMQ サービスに依存している場合は、サーバーに中止されます。|  
|ファイル システム|サーバー。 ファイル システムは失敗し、ドキュメントの処理、ファイル アダプターなど、ファイル システムに依存している場合は、サーバーに中止されます。|  
  
 高可用性を効率よく管理できる[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]システム、BizTalk スタックをよく理解する必要があります: [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]、DC (DNS、DHCP)、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]、IIS サーバー、ファイル サーバー、MSMQ サーバー、外部アプリケーションです。 このセクションの高可用性の焦点[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]および依存する[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]コンピューター。  
  
## <a name="biztalk-server-high-availability-examples"></a>BizTalk Server の高可用性の例  
 Microsoft ではサンプル シナリオの[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ホストのスケール アウト層を経由の高可用性を実現するを参照してください[サンプル BizTalk Server 高可用性のシナリオ](http://go.microsoft.com/fwlink/?LinkId=156815)(http://go.microsoft.com/fwlink/?LinkId=156815)。  
  
## <a name="see-also"></a>参照  
 [BizTalk ホストの高可用性](../technical-guides/high-availability-for-biztalk-hosts.md)   
 [データベースの高可用性](../technical-guides/high-availability-for-databases.md)   
 [マスター シークレット サーバーの高可用性](../technical-guides/high-availability-for-the-master-secret-server.md)   
 [チェックリスト: 災害復旧と可用性の向上](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md)