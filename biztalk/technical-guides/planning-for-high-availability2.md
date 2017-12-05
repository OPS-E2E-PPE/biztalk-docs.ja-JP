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
ms.openlocfilehash: f9b5ff05391eed424e7b910296cc5aa801f8cab1
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="planning-for-high-availability"></a>高可用性の計画
BizTalk Server の高可用性は、BizTalk Server の展開での可用性を低下させている機能のコンポーネントの復旧について説明します。  
  
 BizTalk Server での高可用性を示すためには、エラーが発生して、復旧で、製品の有効性を測定する必要があります。 BizTalk Server の高可用性展開をエラーと障害透過的な外部のアプリケーションやシステムでは、しにより、すべてのサービス継続して正しく機能している中断を最小限にします。  
  
 高可用性を提供する BizTalk Server の展開を設計するには、アプリケーションの統合またはビジネス プロセス統合シナリオで関連する各機能コンポーネントの冗長性を実装することが含まれます。 BizTalk Server は、概念的には、データから分離することによってこれらのシナリオの実装を簡素化、*ホスト*データを処理します。 A*ホスト*BizTalk の論理的なコンテナーは、オーケストレーションなどの項目の送信ハンドラー、および受信ハンドラー。 作成する*のホスト インスタンスの*し、ホストに割り当てます。 ホスト インスタンスとは、特定のサーバー上のホストを物理的に表現したものです。 BizTalk Server サービス プロセス BTSNTSvc.exe と呼ばれるまたは別のプロセス、たとえば、IIS プロセスのいずれかをお勧めします。 BizTalk Server が実行中の複数含まれる場合、高可用性を実現する*のホスト インスタンスの*と次のように、BizTalk Server データベースをクラスタ リングします。  
  
-   **BizTalk ホストのアーキテクチャ**です。 BizTalk Server では、ホストを分離し、メッセージの受信、オーケストレーション、処理、およびメッセージを送信するなどの主要機能のための高可用性を実現する複数のホスト インスタンスを実行することができます。 これらのホストは不要クラスタ リングを追加または負荷分散メカニズムは、BizTalk Server では、ホスト インスタンスを通じて複数のコンピューターに、ワークロードを自動的に分散するためです。 ただし、ホスト、HTTP アダプタと SOAP アダプタに必要な負荷分散メカニズムなどネットワーク負荷分散 (NLB) の高可用性を実現すると、FTP の受信ハンドラーを実行しているホスト、MSMQ、POP3、SQL、および SAP を必要と受信ハンドラーを実行して、高可用性を実現するためのメカニズムをクラスター化します。  
  
    > [!NOTE]  
    >  常に、SAP がクラスター化する必要があります受信アダプタは、2 フェーズ コミットのシナリオに対応します。  
  
-   **BizTalk Server データベースのアーキテクチャ**です。 BizTalk Server データベースの高可用性構成は通常、アクティブ/パッシブのサーバー クラスター構成で構成されている 2 つ以上の SQL Server データベース コンピューターで構成されます。 これらのコンピューターに共通のディスク リソースを共有する (など、RAID 1 + 0 SCSI ディスク アレイやストレージ エリア ネットワーク) Windows フェールオーバー クラスタ リングを使用してバックアップの冗長性とフォールト トレランスを提供します。  
  
 高可用性のために重要な別の BizTalk 機能コンポーネントは、マスター シークレット サーバーです。 BizTalk Server は、暗号化キーを取得するには、このサービスに依存します。  
  
 このセクションでは、これらの各カテゴリでの高可用性に対処する方法に関する情報を提供します。 BizTalk Server の高可用性ソリューションが Windows および SQL Server に組み込まれているために、BizTalk Server 用のホストを構成する前に、高可用性とこれらの製品を展開することを確認します。 こうした基盤となる製品の高可用性を実現する方法については、次のリンクを参照してください。  
  
-   **高可用性ソリューション (SQL Server)] (https://docs.microsoft.com/sql/sql-server/failover-clusters/high-availability-solutions-sql-server)**  
  
-   **[Windows Server のフェールオーバー クラスタ リング](https://docs.microsoft.com/windows-server/failover-clustering/failover-clustering-overview)**
  
## <a name="understanding-the-impact-of-a-component-failure"></a>コンポーネントの障害の影響を理解します。  
 次の表では、コンポーネントまたは依存関係が失敗した場合、コンポーネントと、BizTalk Server 環境と、BizTalk Server 環境への影響の依存関係を一覧表示します。 コンポーネントまたは依存関係をクラスター化するかどうかを決定する際に、潜在的な障害の範囲を検討してください。  
  
|コンポーネントまたは依存関係|障害の範囲|  
|-----------------------------|----------------------|  
|SQL Server|システム全体です。 SQL Server が失敗した場合、BizTalk Server ことはできませんドキュメントを処理します。|  
|[マスター シークレット サーバー]|システム全体です。 マスター シークレット サーバーが失敗した場合、BizTalk Server ことはできませんドキュメントを処理します。 <br/>**注:**マスター シークレット サーバーが失敗した場合、BizTalk グループ内の各 BizTalk サーバーは BizTalk server のエンタープライズ SSO サービスが再起動されるまでは、マスター シークレットのメモリ内のキャッシュされたコピーを使用して引き続きです。 BizTalk サーバーで、エンタープライズ SSO サービスが再起動された場合は、キャッシュされたマスター シークレットのコピーがメモリから解放し、BizTalk server は、マスター シークレットの別のコピーを取得する場合は、マスター シークレット サーバーに接続できないする必要があります。 マスター シークレット サーバーは失敗し、BizTalk server のドキュメントの処理を続行する場合、グループ内 BizTalk サーバーでエンタープライズ SSO サービスを再開しないしないでください。|  
|MSDTC|サーバー。 MSDTC が失敗した場合、トランザクションのサポートを必要とするサーバー上のコンポーネントは失敗します。 <br/>**注:** SQL サーバーとマスター シークレット サーバーはトランザクションのサポートに MSDTC に依存するため、障害の範囲になるシステム全体で SQL server またはマスター シークレット サーバー上の MSDTC が失敗した場合。 BizTalk Server では、実行時の操作中に SQL Server およびマスター シークレット サーバーと通信するときに、トランザクションのサポートが必要です。|  
|BizTalk ホスト インスタンス|サーバー。 BizTalk ホスト インスタンスに格納されていたすべてのコンポーネントは、ホスト インスタンスが失敗した場合は、ドキュメント処理に参加することができません。|  
|Microsoft メッセージ キュー (MSMQ)|サーバー。 MSMQ は失敗し、ドキュメントの処理など、MSMQ アダプター、MSMQ サービスに依存している場合は、サーバーに中止されます。|  
|ファイル システム|サーバー。 ファイル システムは失敗し、ドキュメントの処理、ファイル アダプターなど、ファイル システムに依存している場合は、サーバーに中止されます。|  
  
 高可用性の BizTalk Server システムを効率よく管理できるようにするには、BizTalk スタックの十分な理解が必要: Windows サーバー、DC (DNS、DHCP)、BizTalk Server、SQL Server、IIS サーバー、ファイル サーバー、MSMQ サーバー、外部アプリケーションです。 このセクションでは、BizTalk Server と依存する SQL Server コンピューターの高可用性について説明します。  
  
## <a name="biztalk-server-high-availability-examples"></a>BizTalk Server の高可用性の例  
 ホストのスケール アウト層による高可用性を提供する Microsoft BizTalk Server のサンプル シナリオを参照してください。[サンプル BizTalk Server 高可用性のシナリオ](../core/sample-biztalk-server-high-availability-scenarios.md)です。
  
## <a name="see-also"></a>参照  
 [BizTalk ホストの高可用性](../technical-guides/high-availability-for-biztalk-hosts.md)   
 [データベースの高可用性](../technical-guides/high-availability-for-databases.md)   
 [マスター シークレット サーバーの高可用性](../technical-guides/high-availability-for-the-master-secret-server.md)   
 [チェックリスト: ディザスター リカバリーによる可用性の向上](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md)