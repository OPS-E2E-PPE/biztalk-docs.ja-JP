---
title: Windows Server の Cluster2 を BizTalk Server をインストールするための考慮事項 |Microsoft Docs
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
ms.openlocfilehash: 368b2c33ab81a63a870258da4077eb5e68164e53
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354789"
---
# <a name="considerations-for-installing-biztalk-server-on-a-windows-server-cluster"></a>Windows Server クラスターでの BizTalk Server のインストールに関する注意点
インストールするときに、特別な考慮事項を行う必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を Windows Server クラスターにします。 このトピックでは、これらの考慮事項を示します。  
  
## <a name="a-non-clustered-biztalk-host-instance-should-not-be-run-on-a-windows-server-cluster-where-the-enterprise-sso-service-is-clustered"></a>非クラスター化 BizTalk ホスト インスタンスを実行するか、Windows Server クラスターで、エンタープライズ SSO サービスがクラスター化されました。  
 クラスター、エンタープライズ シングル サインオン マスター シークレット サーバーをアクティブ/パッシブ構成で、マスター シークレット サーバーの高可用性を実現することをお勧めします。 非クラスター化 BizTalk ホスト インスタンスとエンタープライズ SSO サービスのクラスター化されたインスタンスを同じクラスター ノードで実行している場合、クラスター化されたエンタープライズ SSO サービスがクラスター内の異なるノードに移動した場合、BizTalk ホスト インスタンスは失敗します。 BizTalk ホストは、エンタープライズ SSO サービスのローカルで実行中のインスタンスへの依存関係を維持します。 したがって、エンタープライズ SSO サービスはクラスター化リソースとして構成する場合、同じクラスター グループのクラスター化リソースとして、クラスター ノードで実行されているすべての BizTalk ホストを構成する必要があります。  
  
## <a name="configure-the-microsoft-distributed-transaction-coordinator-msdtc-as-a-clustered-resource-before-installing-biztalk-server-on-a-cluster"></a>クラスター化リソースとしてクラスター上の BizTalk Server をインストールする前に Microsoft 分散トランザクション コーディネーター (MSDTC) を構成します。  
 Windows Server クラスターで BizTalk Server をインストールする場合は、まず Microsoft 分散トランザクション コーディネーターをクラスターする必要があります。  
  
 Windows Server 2008 フェールオーバー クラスターで MSDTC をクラスターに」の手順に従います[チェックリスト。Windows Server 2008 フェールオーバー クラスターでの MS DTC リソースの作成](http://go.microsoft.com/fwlink/?LinkID=129677)  
  
## <a name="network-dtc-access-must-be-enabled-on-all-biztalk-servers-and-on-the-sql-server-before-installing-or-configuring-biztalk-server"></a>すべての BizTalk Server と SQL Server のインストールまたは BizTalk Server を構成する前に、ネットワーク DTC アクセスを有効にする必要があります。  
 BizTalk Server データベースをホストする SQL Server と各クラスター ノードで、ネットワーク DTC アクセスを有効にするに記載されている手順に従います[Web サーバーで MSDTC を有効にする方法](http://go.microsoft.com/fwlink/?LinkId=189701)(<http://go.microsoft.com/fwlink/?LinkId=189701>)。 トランザクションのサポートの対応するために、ネットワーク DTC アクセスを有効にする必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 このサポート技術情報記事の手順を完了した後、各サーバーを再起動することをお勧めします。  
  
## <a name="you-must-manually-create-domain-groups-in-active-directory-before-you-configure-biztalk-server"></a>BizTalk Server を構成する前に Active Directory にドメイン グループに作成すること手動である必要があります。  
 インストールする場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]複数のコンピューターでは、ドメイン グループとユーザー アカウントを指定する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]構成ウィザード。 ドメイン グループを使用する場合、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 、構成する必要があります手動でグループを作成して構成する前に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。