---
title: Large Distributed Architecture |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, examples
- data, domains
- corporate domains
- networks
- domain types, service
- domain types, processing
- screened subnet
- service domains
- domain types, corporate
- domain types, data
- perimeter networks
- processing domains
- demilitarized zone
- architecture, large distributions
ms.assetid: 3cfc07c4-0b1d-489b-9a29-55187fde0539
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c29bda1c60b59db42fabacaa0c02175aed90bda
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264794"
---
# <a name="large-distributed-architecture"></a>大規模な分散アーキテクチャ
詳細については、システムのアーキテクチャの[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]展開を参照してください[サンプル BizTalk Server アーキテクチャ](../core/sample-biztalk-server-architectures.md)です。  
  
 このセクションで示すアーキテクチャは実稼働環境用です。 テスト環境や開発環境、その環境に対する管理ネットワークの推奨事項は含まれていません。 構成、テスト環境を開発および運用環境にテストからの展開の詳細については、次を参照してください。 [BizTalk アプリケーションの配置](../core/deploying-biztalk-applications.md)です。  
  
 次の図は、高度な分散型 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アーキテクチャを示しています。このアーキテクチャは、重層的な防御について考慮されています。  
  
 ![Large Distributed Architecture](../core/media/06c5ae00-17aa-42f5-88d1-487bf7720183.gif "06c5ae00-17aa-42f5-88d1-487bf7720183")  
分散型 BizTalk Server のセキュリティ保護アーキテクチャ  
  
 このアーキテクチャには、次の 5 つのドメインが含まれています。  
  
 **境界ネットワーク。** 境界ネットワーク (DMZ、非武装地帯、スクリーン サブネットとも呼ばれます) には、企業が使用するインターネット関連のサービスを提供するサーバーが含まれています。 このドメインには、インターネットに接続されたトランスポートが [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] との間でメッセージを送受信する物理的な場所があるサーバーが含まれています。 このドメインには、BizTalk Server、BizTalk 受信場所、エンタープライズ シングル サインオン サーバーはありません。 SOAP または HTTP のアダプターを使用する場合は、リバース プロキシ ルール (Forefront Threat Management Gateway 2010 サーバー実装では Web 公開と呼ばれます) を使用して、インターネットと接するファイアウォール (FW4) からサービス インターフェイス ドメインを保護するファイアウォール (FW3) までメッセージをリレーすることができます。 Web 公開ルールの詳細については、Microsoft Web サイトを参照してください。 [http://go.microsoft.com/fwlink/?LinkID=205340](http://go.microsoft.com/fwlink/?LinkID=205340) (http://go.microsoft.com/fwlink/?LinkID=205340)。  
  
 上記の図では、境界ネットワーク内のサーバーは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境の外部のドメインにあるサーバーを表しています。 そのため、一部のサーバーはリモートの場所にある場合があります。 たとえば、ファイル転送プロトコル (FTP) サーバーが、リモートの場所になります。簡易メール転送プロトコル (SMTP) サーバーには、会社の電子メール サーバー、インターネット サービス プロバイダー (ISP) の可能性がありますサーバー、またはリモート SMTP サーバー。  
  
 **サービス インターフェイス ドメイン。** メッセージの処理が開始されるドメインです。 このドメインには、BizTalk の受信ハンドラーと送信ハンドラーを備えたサーバーが含まれます。 ここには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のポート、受信場所、パイプライン、マップ、スキーマ、およびアセンブリがメッセージを受信、ルーティング、および送信するために配置されています。 このドメイン内の BizTalk Server の数は、企業のパフォーマンス要件に必要なホストとホスト インスタンスの数によって異なります。  
  
 **サービスのドメイン。** このドメインには、サービス インターフェイス ドメイン内のサーバーによって信頼されていて、メッセージが正常に処理される必要があり、BizTalk オーケストレーション、パイプライン、エンタープライズ シングル サインオン (SSO) サービス、ビジネス ルール エンジン、その他のビジネス プロセスを備えた処理サーバーなどの境界ネットワークからの攻撃を防御する、追加の層を必要とするサービスが含まれています。  
  
 また、企業ドメインからのアクセスが必要で、外部の脅威から保護する必要があるサービスも含まれています。 このドメイン内のサーバーの 1 つのホスト、管理ツール: BizTalk 管理コンソールおよびエンタープライズ シングル サインオン (SSO) 管理ユーティリティです。 また、SSO マスター シークレット サーバーも含まれています。このサーバーでは SSO システムで SSO データベース内のデータの暗号化に使用するマスター シークレット (暗号化キー) を保持します。 このドメインのいずれかのサーバーには、稼働状況の監視データおよびビジネスの監視データの追跡をサポートするホストのインスタンスがあります。  
  
> [!NOTE]
>  エンタープライズ シングル サインオン システムの場合、一部の処理サーバーには BizTalk Server コンポーネントは含まれず、SSO サービスだけが含まれる場合があります。 詳細については、次を参照してください。[エンタープライズ シングル サインオンの高可用性](../core/high-availability-for-enterprise-single-sign-on.md)です。  
  
 **データ ドメイン。** データ ドメインは、インターネットから最も離れた位置にあるドメインで、重要なビジネス データと処理データを格納する SQL Server データベースが含まれています。このドメインは、他のドメインを信頼しません。 SQL Server が実行されている別のサーバーに各 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースがある場合、実行する処理の主な種類 (読み取り操作中心、書き込み操作中心、またはその両方) に基づいてデータベースを結合することをお勧めします。  
  
-   各メッセージ ボックス データベース用の SQL Server。 負荷分散のため、他のメッセージ ボックス データベースを追加できます。 追加するデータベースは、読み取り中心のデータベースと書き込み中心のデータベースです。  
  
-   SSO データベース用の SQL Server。 BizTalk Server は、このデータベースに対して読み取り操作を主に実行します。 このデータベースは機密データが格納されるので、最も制限されたアクセス許可が必要です。  
  
-   BizTalk 管理データベース、およびビジネス ルール エンジン データベース用の SQL Server。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ほとんどの場合、読み取り操作でこれらのデータベースです。 このサーバーには、書き込み中心のデータベースである追跡データベースも含まれます。  
  
-   分析サーバーの追跡データベース用の SQL Server。  
  
-   Microsoft Operations Manager (MOM) データベース用の SQL Server。  
  
-   ログ配布用の送信先システムの SQL Server。  
  
> [!IMPORTANT]
>  フェールオーバー保護の場合は、各 BizTalk データベースをクラスター化するをお勧めします。 SQL Server フェールオーバー クラスタ リングの詳細については、Microsoft MSDN Web サイトを参照してください。 [http://go.microsoft.com/fwlink/?LinkId=131016](http://go.microsoft.com/fwlink/?LinkId=131016)です。  
  
> [!NOTE]
>  ログ配布用に送信先システムの詳細については、次を参照してください。[をバックアップおよび BizTalk Server データベースの復元](../core/backing-up-and-restoring-the-biztalk-server-databases.md)です。  
  
 上記の図では、Forefront Threat Management Gateway (TMG) 2010 サーバーがソフトウェア ファイアウォールの役割を担い、これらの各ドメインを保護すると共に境界となっています。 また、各ドメインには独自のドメイン コントローラーがあります。このドメイン コントローラーは、重要なサーバーを含むドメイン (データ ドメイン) から外部に接続されたサーバー (境界ネットワークおよび企業ドメイン) への信頼関係が確立されていて、サーバーには接続する必要がある他のドメイン内のサービスにのみアクセス権が与えられています。 サービス インターフェイス ドメインとサービス ドメインの両方からデータ ドメインへのトラフィックを制限するファイアウォール (FW1) があります。 同様に、サービス インターフェイス ドメインと操作ドメインの両方からサービス ドメインへのトラフィックを制限するファイアウォール (FW2) もあります。  
  
 **企業ドメイン。** このドメインはイントラネット ドメインで、企業や部門内のすべてのデスクトップ コンピューターと、企業内のインフォメーション ワーカーにサービスを提供するすべてのサーバーが含まれています。 このドメインには、2 つの一意な論理コンテナーがあります。  
  
-   **イントラネット サービス。** このコンテナーには、内部パートナーとの間でメッセージを送受信する、SQL アダプターおよびファイル アダプター用のサーバーがあります。 これはイントラネットですが、多くのユーザーがアカウントやサービスを持っている企業ネットワークとは異なります。 図中の境界ネットワークと同様に、このコンテナー内の一部のサーバーは、別の場所にある場合があります。 たとえば、SQL Server が実行されている SQL アダプターのサーバーはサービス インターフェイス ドメインにありますが、ファイル アダプターの送信場所と受信場所 (フォルダー) はサービス インターフェイス ドメインの外部に存在する層にあります。  
  
-   **操作です。** このコンテナーには、IT プロフェッショナルが環境内のすべてのサーバーのパフォーマンスや状態をリモートで管理、保守、および監視するために使用するターミナル サービス クライアントがあります。 IT プロフェッショナルは、ターミナル サービスを使用してサービス ドメイン内の管理サーバーに接続し、そこから環境内のすべてのサーバーに対して管理タスクを実行します。  
  
 企業ドメイン内に開発コンピューターが存在する場合がありますが、それらのコンピューターの構成についてはこのドキュメントでは説明しません。  
  
 インフォメーション ワーカー サービスを含む BizTalk Server アーキテクチャの詳細については、次を参照してください。[インフォメーション ワーカー サービスで大規模な分散アーキテクチャ](../core/large-distributed-architecture-with-information-worker-services.md)です。  
  
 ドメイン間の信頼関係は次のとおりです。  
  
-   データ ドメインは他のドメインを信頼しません。  
  
-   サービス インターフェイス ドメインは、データ ドメインを信頼します。  
  
-   サービス ドメインはデータ ドメインを信頼します。  
  
-   企業ドメインはサービス ドメインを信頼します。  
  
 ドメインと信頼関係に対してファイアウォールを構成する方法の詳細については、Microsoft ヘルプとサポート Web サイトを参照してください。 [http://go.microsoft.com/fwlink/?LinkId=25230](http://go.microsoft.com/fwlink/?LinkId=25230)です。  
  
 上記の図はセキュリティに焦点を当てていますが、可用性とパフォーマンスにネットワーク負荷分散 (NLB) とクラスター サービスを使用して、アーキテクチャを拡張することもできます。  
  
 高可用性の詳細については、次を参照してください。[高可用性の計画](../core/planning-for-high-availability3.md)です。  
  
 パフォーマンスの詳細については、次を参照してください。[継続的なパフォーマンスの計画](../core/planning-for-sustained-performance.md)です。  
  
 次の表は、実現するサービス レベル契約 (SLA) に応じたネットワーク負荷分散 (NLB) を構成できるサーバーの種類を示しています。  
  
|名前|型|[ドメイン]|  
|----------|----------|------------|  
|HTTP (推奨値)|[インターネット インフォメーション サービス]|境界ネットワーク|  
|受信ハンドラー (分離)|[インターネット インフォメーション サービス]|サービス インターフェイス ドメイン|  
|BAM ポータル|[インターネット インフォメーション サービス]|サービス インターフェイス ドメイン|  
  
 次の表は、実現するサービス レベル契約 (SLA) に応じてクラスター化できるサーバーの種類を示しています。  
  
|名前|型|[ドメイン]|  
|----------|----------|------------|  
|Exchange (送信)|Exchange Server|境界ネットワーク|  
|FTP アダプターおよび POP3 アダプターの受信ハンドラー (インプロセス ホスト)|BizTalk Server|サービス インターフェイス ドメイン<br /><br /> 企業ドメイン|  
|[マスター シークレット サーバー]|BizTalk Server|サービス ドメイン|  
|すべての SQL Server|SQL Server|データ ドメイン|  
  
 インフォメーション ワーカー サービスを含む BizTalk Server アーキテクチャの詳細については、次を参照してください。[インフォメーション ワーカー サービスで大規模な分散アーキテクチャ](../core/large-distributed-architecture-with-information-worker-services.md)です。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server のサンプル アーキテクチャ](../core/sample-biztalk-server-architectures.md)   
 [縮小されたアーキテクチャ](../core/scaled-down-architecture.md)