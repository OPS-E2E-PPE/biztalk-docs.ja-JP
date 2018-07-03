---
title: 高 Availability2 の計画 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 65271fd5-5294-406f-87f8-3aa394c235a2
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac94e56775badc3aa610505ad1fb441f85e9262e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988507"
---
# <a name="planning-for-high-availability"></a>高可用性の計画
BizTalk Server の高可用性は、BizTalk Server の展開での可用性を低下させている機能のコンポーネントの復旧について説明します。  
  
 BizTalk Server での高可用性を示すためには、エラーが発生して、復旧で、製品の効果を測定する必要があります。 BizTalk Server の高可用性展開は、外部アプリケーションとシステムに、エラーや障害を透明とによりすべてのサービスは引き続き正常に機能の中断を最小限に。  
  
 高可用性を提供する BizTalk Server 展開の設計には、アプリケーションの統合またはビジネス プロセス統合シナリオに関連する各機能コンポーネントの冗長性を実装する必要があります。 BizTalk Server は、概念的には、データから分離することでこれらのシナリオの実装を簡略化、*ホスト*データを処理します。 A*ホスト*BizTalk の論理コンテナーには、オーケストレーションなどの項目の送信ハンドラー、および受信ハンドラー。 作成する*インスタンスをホスト*しホストに割り当てます。 ホスト インスタンスとは、特定のサーバー上のホストを物理的に表現したものです。 BizTalk Server サービス プロセス BTSNTSvc.exe と呼ばれるまたは別のプロセス、たとえば、IIS プロセスのいずれかになります。 BizTalk Server が実行中の複数含まれる場合、高可用性を実現する*インスタンスをホスト*と次のように、BizTalk Server データベースをクラスタ リングします。  
  
- **BizTalk ホストのアーキテクチャ**します。 BizTalk Server では、ホストを分離し、メッセージの受信、処理オーケストレーション、メッセージを送信するなどの主要機能の高可用性を実現する複数のホスト インスタンスを実行することができます。 これらのホストは不要クラスタ リングを追加または負荷分散メカニズムは、BizTalk Server は自動的にホスト インスタンスを通じて複数のコンピューター間でワークロードを分散するためです。 ただし、HTTP および SOAP アダプターの負荷分散などネットワーク負荷分散 (NLB) 高可用性を提供するメカニズムが必要し、FTP の受信ハンドラーを実行しているホスト、MSMQ、POP3、SQL、および SAP が必要に、受信ハンドラーを実行しているをホストします。高可用性を実現するためのメカニズムをクラスタ リングします。  
  
  > [!NOTE]  
  >  常に、SAP がクラスター化する必要があります受信アダプタは、2 フェーズ コミットのシナリオに対応します。  
  
- **BizTalk Server データベースのアーキテクチャ**します。 通常、BizTalk Server データベースの高可用性構成は、アクティブ/パッシブのサーバー クラスター構成で構成されている 2 つ以上の SQL Server データベース コンピュータで構成されます。 これらのコンピューターが共通のディスク リソースを共有 (など、RAID 1 + 0 SCSI ディスク アレイやストレージ エリア ネットワーク) Windows フェールオーバー クラスタ リングを使用してバックアップの冗長性とフォールト トレランスを提供します。  
  
  高可用性のために重要なもう 1 つの BizTalk の機能コンポーネントは、マスター シークレット サーバーです。 BizTalk Server は、暗号化キーを取得するには、このサービスに依存します。  
  
  このセクションでは、これらの各カテゴリでの高可用性に対処する方法について説明します。 Windows と SQL Server では、BizTalk Server の高可用性ソリューションがビルドするため、BizTalk Server のホストを構成する前に、高可用性を備えた、これらの製品をデプロイすることを確認します。 こうした基盤となる製品の高可用性を実現する方法については、次のリンクを参照してください。  
  
- **高可用性ソリューション (SQL Server)] (https://docs.microsoft.com/sql/sql-server/failover-clusters/high-availability-solutions-sql-server)**  
  
- **[Windows Server フェールオーバー クラスタ リング](https://docs.microsoft.com/windows-server/failover-clustering/failover-clustering-overview)**
  
## <a name="understanding-the-impact-of-a-component-failure"></a>コンポーネントの障害の影響を理解します。  
 次の表では、コンポーネントまたは依存関係が失敗した場合、コンポーネントと BizTalk Server 環境と、BizTalk Server 環境への影響の依存関係を一覧表示します。 コンポーネントまたは依存関係をクラスター化するかどうかを決定する際に、潜在的な障害の範囲を検討してください。  
  
|コンポーネントまたは依存関係|障害の範囲|  
|-----------------------------|----------------------|  
|SQL Server|システム全体。 SQL Server が失敗した場合は、BizTalk Server がドキュメントを処理できませんするされます。|  
|[マスター シークレット サーバー]|システム全体。 マスター シークレット サーバーが失敗した場合、BizTalk Server はできませんドキュメントを処理できません。 <br/>**注:** BizTalk server のエンタープライズ SSO サービスが再起動されるまでに、マスター シークレットのキャッシュされたメモリ内コピーを使用する BizTalk グループ内の各 BizTalk サーバーは引き続き、マスター シークレット サーバーが失敗した場合。 BizTalk サーバーで、エンタープライズ SSO サービスが再起動された場合は、キャッシュされたマスター シークレットのコピーがメモリから解放し、BizTalk server は、マスター シークレットの別のコピーを取得するマスター シークレット サーバーに接続できる必要があります。 マスター シークレット サーバーは失敗し、BizTalk サーバー ドキュメントの処理を続行する場合、グループの BizTalk サーバーでエンタープライズ SSO サービスを再開しない操作を行います。|  
|MSDTC|サーバー。 MSDTC がトランザクションのサポートを必要なサーバー上の任意のコンポーネントは失敗します。 <br/>**注:** のため、SQL Server とマスター シークレット サーバーは、トランザクションのサポートに MSDTC に依存するは、障害の範囲になるシステム全体に SQL server またはマスター シークレット サーバーで MSDTC が失敗した場合。 BizTalk Server では、実行時の操作中に SQL Server とマスター シークレット サーバーと通信するときにトランザクションのサポートが必要です。|  
|BizTalk ホスト インスタンス|サーバー。 BizTalk ホスト インスタンスに格納されているすべてのコンポーネントは、ホスト インスタンスが失敗した場合は、ドキュメントの処理に参加できません。|  
|Microsoft メッセージ キュー (MSMQ)|サーバー。 MSMQ は失敗し、ドキュメントの処理など、MSMQ アダプター、MSMQ サービスに依存する場合は、サーバーに中止されます。|  
|ファイル システム|サーバー。 ファイル システムには、ドキュメント処理し、ファイル アダプターなど、ファイル システムに依存しているが失敗した場合は、サーバーに中止されます。|  
  
 高可用性 BizTalk Server システムを効率的に管理できるようにするには、BizTalk スタックの適切な理解があります。 Windows Server、DC (DNS、DHCP)、BizTalk Server、SQL Server、IIS サーバー、ファイル サーバー、MSMQ サーバー、外部のアプリケーション。 このセクションでは、BizTalk Server と依存の SQL Server コンピューターの高可用性について説明します。  
  
## <a name="biztalk-server-high-availability-examples"></a>BizTalk Server の高可用性の例  
 ホストのスケール アウト層による高可用性を提供する Microsoft BizTalk Server のサンプル シナリオを参照してください。[サンプル BizTalk Server 高可用性シナリオ](../core/sample-biztalk-server-high-availability-scenarios.md)します。
  
## <a name="see-also"></a>参照  
 [BizTalk ホストの高可用性](../technical-guides/high-availability-for-biztalk-hosts.md)   
 [データベースの高可用性](../technical-guides/high-availability-for-databases.md)   
 [マスター シークレット サーバーの高可用性](../technical-guides/high-availability-for-the-master-secret-server.md)   
 [チェックリスト: ディザスター リカバリーによる可用性の向上](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md)