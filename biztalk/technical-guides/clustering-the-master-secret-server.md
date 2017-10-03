---
title: "マスター シークレット サーバーをクラスター化 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 14aa3622-8462-4ed9-abde-40090d4f96ff
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 674cbf64e11817c951d3841ebdc9f6ee979c0e8c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="clustering-the-master-secret-server"></a>マスター シークレット サーバーをクラスタ リング
[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]アプリケーション サービスがインストールされているエンタープライズ シングル サインオン (SSO) サービスに依存してハード コーディングされたを維持[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。 SSO サービスは、開始する場合は、マスター シークレット サーバーと通信できる必要があります。 マスター シークレット サーバーのフォールト トレランスを提供する、マスター シークレット サーバーで SSO サービスをクラスター化することをお勧めします。 詳細については、次を参照してください。[高可用性 SSO インストール オプション](http://go.microsoft.com/fwlink/?LinkId=156838)(http://go.microsoft.com/fwlink/?LinkId=156838) で[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]ヘルプ。  
  
## <a name="preparing-for-clustering-the-master-secret-server"></a>マスター シークレット サーバーをクラスターの準備  
  
### <a name="deciding-whether-to-use-a-dedicated-cluster-or-the-sql-server-cluster"></a>専用のクラスターまたは SQL Server クラスターを使用するかどうかを決定します。  
 クラスタ リングのハードウェアが高くなります。 高可用性ソリューションのハードウェア リソースを減らすためには、クラスター リソースとして、マスター シークレット サーバーを追加することができます、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベース クラスター。 使用する場合、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベース クラスターでは、ことをお勧め、メッセージ ボックス データベースと同じアクティブなノードでマスター シークレット サーバーを配置しないことです。 メッセージ ボックス データベースは、他のデータベースよりも通常ビジー状態です。 マスター シークレット サーバーが多くのハードウェア リソースを利用していない場合でも、メッセージ ボックス データベースのアクティブ ノードから別のアクティブなクラスター ノードに移動することをお勧めします。  
  
### <a name="clustering-the-sso-database"></a>SSO データベースをクラスタ リング  
 マスター シークレット サーバーは、SSO データベースに依存します。 高可用性 SSO をビルドするには、SSO データベースをクラスター化する必要があります。 BizTalk データベースをクラスタ リングの詳細については、次を参照してください。 [BizTalk Server Databases2 をクラスタ リング](../technical-guides/clustering-the-biztalk-server-databases2.md)です。  
  
### <a name="creating-domain-groups-and-accounts"></a>ドメイン グループおよびアカウントの作成  
 マスター シークレット サーバーをクラスター化する前に、次のドメイン グループとアカウントを構成する必要があります。  
  
-   SSO 管理者と SSO 関連管理者の名前とドメイン グループを作成します。 エンタープライズ SSO サービスのクラスター化されたインスタンスを作成するには、ドメイン グループとして、SSO 管理者および SSO 関連管理者グループを作成する必要があります。  
  
-   作成または SSO 管理者のドメイン グループのメンバーであるドメイン アカウントを指定します。 各ノードのエンタープライズ SSO サービスは、このドメイン アカウントとしてログオンする構成されます。 このアカウントによっては、クラスター内の各ノードに「サービスとしてログオン」権限が必要です。 このアカウントは、クラスターへのフル コントロール アクセスを付与する必要があります。  
  
## <a name="clustering-the-master-secret-server"></a>マスター シークレット サーバーをクラスタ リング  
 マスター シークレット サーバーをクラスタ リング用の基本的な手順を次に示します。  
  
1.  インストールし、クラスター ノードにエンタープライズ SSO を構成します。  
  
2.  クラスター化されたエンタープライズ SSO リソースと依存するリソースを作成します。  
  
3.  2 番目のクラスター ノードでマスター シークレットを復元します。 マスター シークレット サーバーをクラスターに移動する場合も最初のクラスター ノードでマスター シークレットを復元する必要があります。  
  
4.  オンライン SSO サービスを含むクラスター グループを表示します。  
  
5.  管理データベースにマスター シークレット名を更新します。  
  
 マスター シークレット サーバーをクラスタ リングの詳細な手順については、次を参照してください。[マスター シークレット サーバーをクラスター化する方法](http://go.microsoft.com/fwlink/?LinkId=156839)(http://go.microsoft.com/fwlink/?LinkId=156839) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  
  
## <a name="see-also"></a>参照  
 [新しいマスター シークレット サーバーを手動で指定します。](../technical-guides/designating-a-new-master-secret-server-manually.md)