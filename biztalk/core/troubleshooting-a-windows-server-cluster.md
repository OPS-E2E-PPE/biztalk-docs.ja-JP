---
title: Windows Server クラスターのトラブルシューティング |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 283cf4cd-ce40-48b7-8549-9ab17d7d2c34
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da1159bafc42f6cfbf47621e3b846764e50e5267
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279962"
---
# <a name="troubleshooting-a-windows-server-cluster"></a>Windows Server クラスターのトラブルシューティング
Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、ホスト クラスター サポートを利用するために Windows Server クラスターをサポートし、エンタープライズ シングル サインオン (SSO) マスター シークレットおよび [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースの高可用性を実現します。 このトピックでは、Windows Server クラスター環境で [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を使用するための一般的なガイドラインを示し、Windows Server クラスター環境で [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を使用する際に発生する可能性がある既知の問題点について説明します。  
  
## <a name="general-guidelines"></a>一般的なガイドライン  
 Windows Server クラスターの生産性を最大化し、影響を与える可能性があります、Windows Server クラスターの問題のトラブルシューティングを行うに次の一般的なガイドラインに従って[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の完全な概念実証によって、仮想化されたサーバー環境で Windows Server クラスターを機能させることができます。  
  
     **仮想化されたサーバー環境を作成する、Windows Server 2008 で使用可能な HYPER-V の役割を使用できます。**  
  
    -   Windows Server 2008 HYPER-V の詳細を参照してください「の仮想化との統合」 [http://go.microsoft.com/fwlink/?LinkID=121187](http://go.microsoft.com/fwlink/?LinkID=121187)です。  
  
    -   HYPER-V で提供される仮想化テクノロジを活用することの利点の深さについての詳細は、"高度な仮想化の利点がありますの Windows Server 2008 のエディションの Enterprise"からダウンロードできるホワイト ペーパーを参照してください[。http://go.microsoft.com/fwlink/?LinkId=123530](http://go.microsoft.com/fwlink/?LinkId=123530)です。  
  
    -   HYPER-V を使用して、Windows Server 2008 クラスターを作成する手順については、「 [http://go.microsoft.com/fwlink/?LinkId=129680](http://go.microsoft.com/fwlink/?LinkId=129680)です。  
  
     [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の概念実証により仮想化されたサーバー環境で Windows Server クラスターを使用できるようになると、高い柔軟性が得られ、使用するハードウェア リソースも Windows Server クラスターに比べて大幅に削減できます。 この方法を利用する場合は、ホスト コンピューター上で同時に実行する各仮想マシンに対して 512 MB 以上のメモリを割り当て、ホスト オペレーティング システムには 512 MB のメモリを追加します。 たとえば、5 つの仮想マシン (BizTalk Server の 2 クラスター ノード、Microsoft SQL Server の 2 クラスター ノード、および 1 つのドメイン コントローラー) で構成した Windows Server クラスターを使用する [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のソリューションでは、ホスト コンピューターに 3 GB のメモリをインストールすることを計画します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の概念実証の環境で 2 GB を超えるメモリが必要な場合は、インストールしたすべてのメモリにホスト オペレーティング システムからアクセスできるように、ホスト コンピューターには 64 ビット版 Windows のインストールを検討してください (Hyper-V の役割に必要)。  
  
## <a name="troubleshooting-resources"></a>トラブルシューティングのリソース  
 **Windows Server 2008 フェールオーバー クラスタ リングのトラブルシューティングに関するリソース**  
  
-   確認、[フェールオーバー クラスターの検証および Windows Server 2008 でのトラブルシューティング](http://go.microsoft.com/fwlink/?LinkId=129729)Microsoft TechNet Web サイト上の TechNet web キャストします。 この Web キャストでは、Windows Server 2008 でフェールオーバー クラスターの検証とトラブルシューティングの方法が説明されています。  
  
-   Windows Server 2008 フェールオーバー クラスタ リングに関する問題の分析の詳細については、のトピックを参照します[フェールオーバー クラスターのビュー イベントおよびログ](http://go.microsoft.com/fwlink/?LinkId=129730)Microsoft TechNet Web サイトにします。  
  
## <a name="known-issues"></a>既知の問題  
  
#### <a name="any-attempt-to-bring-a-clustered-msdtc-resource-online-fails-which-causes-dependent-biztalk-server-services-to-fail"></a>MSDTC のクラスター化リソースをオンラインにしようとすると、依存関係のある BizTalk Server サービスが動作しなくなる  
  
##### <a name="problem"></a>問題  
 クラスター化された分散トランザクション コーディネーター (MSDTC) リソースをオンラインにすることはできません、**オンライン**オプション クラスター アドミニストレーターで、これにより、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MSDTC に依存している実行時の操作トランザクションのサポートが失敗します。  
  
##### <a name="cause"></a>原因  
 MSDTC のクラスター化リソースで発生するエラーには、次のような理由が考えられます。  
  
-   MSDTC のクラスター リソースが正しいディスクを使用して構成されていないと、ネットワーク名リソースの依存関係またはリソースの依存関係が失敗しています。  
  
-   アクセス許可に問題があり、MSDTC のクラスター化リソースのアクティブ化を妨げています。  
  
##### <a name="resolution"></a>解決策  
 **Windows Server 2008 クラスターで、次の手順を行います。**  
  
-   手順に従います[チェックリスト: Windows Server 2008 フェールオーバー クラスターでの MS DTC リソースの作成](http://go.microsoft.com/fwlink/?LinkId=129677)Windows Server 2008 フェールオーバー クラスターで 1 つまたは複数のクラスター化された MSDTC リソースを作成するためです。  
  
## <a name="see-also"></a>参照  
 [Windows Server クラスターを使用して BizTalk Server Hosts2 の高可用性を実現するには](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md)   
 [BizTalk Server データベースをクラスタ リング](../core/clustering-the-biztalk-server-databases1.md)   
 [サンプル BizTalk Server の高可用性のシナリオ](../core/sample-biztalk-server-high-availability-scenarios.md)   
 [高可用性 SSO インストール オプション](../core/high-availability-sso-installation-options.md)