---
title: Windows Server クラスターのトラブルシューティング |Microsoft Docs
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
ms.openlocfilehash: 8c6c55660b886b1739326abef13e1dc5f2c829ff
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243228"
---
# <a name="troubleshooting-a-windows-server-cluster"></a>Windows Server クラスターのトラブルシューティング
Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ホスト クラスターのサポート、高可用性を実現して、エンタープライズ シングル サインオン (SSO) マスター シークレットの高可用性を実現するために Windows Server クラスターの使用をサポートする、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。 このトピックを使用するための一般的なガイドラインを提供します[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Windows server クラスター環境とを使用する場合に発生する既知の問題について説明します[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Windows Server クラスター環境にします。  
  
## <a name="general-guidelines"></a>一般的なガイドライン  
 Windows Server クラスターでの生産性を最大化してに影響する Windows Server クラスターの問題のトラブルシューティングを行う、次の一般的なガイドラインに従って[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  
  
1. 完全な[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]仮想化サーバー環境で Windows Server クラスターを機能させる概念を実証します。  
  
    **仮想化サーバー環境を作成する、Windows Server 2008 で使用可能な HYPER-V ロールを使用できます。**  
  
   - Windows Server 2008 の Hyper-v ホストに関する詳細についてを参照してください「仮想化と統合」 [ http://go.microsoft.com/fwlink/?LinkID=121187](http://go.microsoft.com/fwlink/?LinkID=121187)します。  
  
   - HYPER-V で提供される仮想化テクノロジを活用することの利点の深さについての詳細は、ホワイト ペーパー"高度な仮想化のメリットの Windows Server 2008 エディション for the Enterprise 』 からダウンロードできますを参照してください[。 http://go.microsoft.com/fwlink/?LinkId=123530](http://go.microsoft.com/fwlink/?LinkId=123530).  
  
   - HYPER-V を使用して、Windows Server 2008 クラスターを作成する手順については、「 [ http://go.microsoft.com/fwlink/?LinkId=129680](http://go.microsoft.com/fwlink/?LinkId=129680)します。  
  
     行う[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]仮想化サーバー環境で Windows Server クラスターの概念実証は優れた柔軟性を提供しも Windows Server クラスターに比べて大幅に削減のハードウェア リソースを使用します。 このアプローチを使用する場合は、少なくとも 512 MB のホスト コンピューターで同時に実行されている各仮想マシンのメモリと 512 MB の追加、ホスト オペレーティング システムのメモリを割り当てます。 たとえば、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 5 つの仮想マシン (BizTalk Server クラスターの 2 つのノード、2 つの Microsoft SQL Server クラスター ノード、および 1 つのドメイン コント ローラーで表示される)、3 GB のメモリがホスト上にインストールを計画してを使用する Windows Server クラスターを使用してソリューションコンピューター。 場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]概念実証環境が 2 GB を超えるメモリを必要と、ホスト オペレーティング システムからアクセス可能なメモリをすべてインストールされていることを確認する (HYPER-V の役割に必要な)、ホスト コンピューターで Windows の 64 ビット版のインストールを検討してください。  
  
## <a name="troubleshooting-resources"></a>トラブルシューティングのリソース  
 **Windows Server 2008 フェールオーバー クラスタ リングのトラブルシューティングに関するリソース**  
  
-   レビュー、[フェールオーバー クラスターの検証と Windows Server 2008 のトラブルシューティング](http://go.microsoft.com/fwlink/?LinkId=129729)Microsoft TechNet Web サイトに関する TechNet web キャスト。 この web キャストでは、フェールオーバー クラスターの検証と Windows Server 2008 のトラブルシューティングをトラブルシューティングする方法について説明します。  
  
-   Windows Server 2008 フェールオーバー クラスタ リングに関する問題の分析の詳細については、トピックを参照してください。[イベントを表示し、フェールオーバー クラスターのログを](http://go.microsoft.com/fwlink/?LinkId=129730)、Microsoft TechNet Web サイト。  
  
## <a name="known-issues"></a>既知の問題  
  
#### <a name="any-attempt-to-bring-a-clustered-msdtc-resource-online-fails-which-causes-dependent-biztalk-server-services-to-fail"></a>クラスター化された MSDTC リソースをオンラインにしようとするとは、それが原因で失敗に依存する BizTalk Server サービスが失敗しました。  
  
##### <a name="problem"></a>問題  
 クラスター化された分散トランザクション コーディネーター (MSDTC) リソースをオンラインにすることはできません、**オンライン**オプション クラスター アドミニストレーターで、これにより[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]MSDTC に依存する実行時の操作トランザクションのサポートが失敗します。  
  
##### <a name="cause"></a>原因  
 クラスター化された MSDTC リソースの障害は、さまざまな理由から、次に発生します。  
  
-   正しいディスクを使用したクラスター化された MSDTC リソースが構成されていないと、ネットワーク名リソースの依存関係またはリソースの依存関係が失敗します。  
  
-   アクセス許可の問題のため、クラスター化された MSDTC リソースをアクティブ化できません。  
  
##### <a name="resolution"></a>解決策  
 **Windows Server 2008 クラスターでは、次の手順を完了するには。**  
  
-   次の手順では、[チェックリスト。Windows Server 2008 フェールオーバー クラスターでの MS DTC リソースの作成](http://go.microsoft.com/fwlink/?LinkId=129677)を Windows Server 2008 フェールオーバー クラスターに 1 つまたは複数のクラスター化された MSDTC リソースを作成するためです。  
  
## <a name="see-also"></a>参照  
 [Windows Server クラスターを使用して BizTalk Server Hosts2 の高可用性を実現するには](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md)   
 [BizTalk Server データベースをクラスタ リング](../core/clustering-the-biztalk-server-databases1.md)   
 [サンプル BizTalk Server の高可用性のシナリオ](../core/sample-biztalk-server-high-availability-scenarios.md)   
 [高可用性 SSO インストール オプション](../core/high-availability-sso-installation-options.md)