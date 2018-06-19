---
title: Windows Server Cluster2 に BizTalk Server をインストールするための考慮事項 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Configure Your Server Wizard
- installing, Windows Server cluster
- BizTalk Server Configuration Wizard
- Windows Server cluster, warnings
- high availability, Windows Server cluster
- clustering, Windows Server cluster
- domain groups
- Windows Server cluster, Configure Your Server Wizard
- Network DTC access
- MSDTC
ms.assetid: 4daea7c6-7d26-440c-a2a0-fa018a25b2b3
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 38bd34862efb0cd73e66a2c694abd26b823766db
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22237938"
---
# <a name="considerations-for-installing-biztalk-server-on-a-windows-server-cluster"></a>BizTalk Server を Windows Server クラスターにインストールする際の考慮事項
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を Windows Server クラスターにインストールする場合は特別な注意が必要です。 このトピックでは、これらの注意事項について説明します。  
  
## <a name="a-non-clustered-biztalk-host-instance-should-not-be-run-on-a-windows-server-cluster-where-the-enterprise-sso-service-is-clustered"></a>エンタープライズ SSO サービスがクラスター化されている Windows Server クラスターでは、クラスター化されていない BizTalk ホスト インスタンスを実行しない  
 エンタープライズ シングル サインオンのマスター シークレット サーバーを、アクティブ/パッシブ構成でクラスター化することは、マスター シークレット サーバーの高可用性を実現する上で適切な手段と言えます。 エンタープライズ SSO サービスのクラスター化されていない BizTalk ホスト インスタンスとクラスター化されたインスタンスを同じクラスター ノードで実行している場合、クラスター化されたエンタープライズ SSO サービスがクラスター内の別のノードに移動されると、BizTalk ホスト インスタンスは失敗します。 BizTalk ホストでは、エンタープライズ SSO サービスのローカルで実行されているインスタンスに対する依存関係を維持します。 したがって、エンタープライズ SSO サービスがクラスター化リソースとして構成されている場合、同じクラスター グループ内のクラスター化リソースとして、クラスター ノードで実行されているすべての BizTalk ホストを構成する必要があります。  
  
## <a name="configure-the-microsoft-distributed-transaction-coordinator-msdtc-as-a-clustered-resource-before-installing-biztalk-server-on-a-cluster"></a>BizTalk Server をクラスター上にインストールする前に Microsoft 分散トランザクション コーディネーター (MSDTC) をクラスター化リソースとして構成する  
 BizTalk Server を Windows Server クラスターにインストールする場合は、先に Microsoft 分散トランザクション コーディネーターをクラスター化する必要があります。  
  
 Windows Server 2008 フェールオーバー クラスターで MSDTC をクラスター化」の手順に従います[チェックリスト: Windows Server 2008 フェールオーバー クラスターでの MS DTC リソースの作成](http://go.microsoft.com/fwlink/?LinkID=129677)  
  
## <a name="network-dtc-access-must-be-enabled-on-all-biztalk-servers-and-on-the-sql-server-before-installing-or-configuring-biztalk-server"></a>BizTalk Server をインストールまたは構成する前に、すべての BizTalk Server および SQL Server でネットワーク DTC アクセスを有効にしておく必要がある  
 各クラスター ノード上だけでなく、BizTalk Server データベースをホストする SQL Server 上のネットワーク DTC アクセスを有効にする」の手順に従います[Web サーバーで MSDTC を有効にする方法](http://go.microsoft.com/fwlink/?LinkId=189701)(http://go.microsoft.com/fwlink/?LinkId=189701)。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のトランザクション機能に対応できるように、ネットワーク DTC アクセスを有効にしておく必要があります。 このサポート技術情報の資料に記載された手順を実行した後、すべてのサーバーを再起動することをお勧めします。  
  
## <a name="you-must-manually-create-domain-groups-in-active-directory-before-you-configure-biztalk-server"></a>BizTalk Server を構成する前に、Active Directory にドメイン グループを手動で作成しておく必要がある  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を複数のコンピューターにインストールする場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 構成ウィザードでドメイン グループおよびユーザー アカウントを指定する必要があります。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の構成にドメイン グループを使用する場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を構成する前に、グループを手動で作成しておくことが必要です。