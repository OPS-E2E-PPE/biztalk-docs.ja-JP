---
title: マスター シークレット サーバーをクラスタ リング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 14aa3622-8462-4ed9-abde-40090d4f96ff
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50813db21de9505b6c417be8950279fcd62a37cf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65277197"
---
# <a name="clustering-the-master-secret-server"></a>マスター シークレット サーバーをクラスタ リング
BizTalk Server アプリケーション サービスと共にインストールされているエンタープライズ シングル サインオン (SSO) サービスにハード コーディングされた依存関係を維持する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 SSO サービスは、開始する場合は、マスター シークレット サーバーと通信できる必要があります。 マスター シークレット サーバーのフォールト トレランスを提供するマスタ シークレット サーバーで SSO サービスをクラスター化することをお勧めします。 詳細については、次を参照してください。[高可用性 SSO インストール オプション](http://go.microsoft.com/fwlink/?LinkId=156838)(<http://go.microsoft.com/fwlink/?LinkId=156838>) BizTalk Server のヘルプ。  
  
## <a name="preparing-for-clustering-the-master-secret-server"></a>マスター シークレット サーバーをクラスター化するための準備  
  
### <a name="deciding-whether-to-use-a-dedicated-cluster-or-the-sql-server-cluster"></a>専用のクラスターまたは SQL Server クラスターを使用するかどうかを決定します。  
 ハードウェア クラスタ リングが高くなります。 高可用性ソリューションのハードウェア リソースを減らすためには、マスター シークレット サーバーを追加でクラスター リソースとして、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベース クラスター。 使用する場合、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]データベース クラスターでは、メッセージ ボックス データベースと同じアクティブなノードでマスター シークレット サーバーに配置しないことお勧めします。 メッセージ ボックス データベースは、他のデータベースよりも通常はビジー状態です。 マスター シークレット サーバーが多くのハードウェア リソースを使用しない場合でも、メッセージ ボックス データベースのアクティブ ノードから別のアクティブなクラスター ノードに移動することをお勧めします。  
  
### <a name="clustering-the-sso-database"></a>SSO データベースをクラスタ リング  
 マスター シークレット サーバーは、SSO データベースに依存します。 高可用性 SSO をビルドするには、SSO データベースをクラスター化する必要があります。 BizTalk データベースをクラスタ リングの詳細については、次を参照してください。 [、BizTalk Server Databases2 をクラスタ リング](../technical-guides/clustering-the-biztalk-server-databases2.md)します。  
  
### <a name="creating-domain-groups-and-accounts"></a>ドメイン グループおよびアカウントの作成  
 マスター シークレット サーバーをクラスター化する前に、次のドメイン グループおよびアカウントを構成する必要があります。  
  
-   SSO 管理者および SSO 関連管理者の名前を持つドメイン グループを作成します。 エンタープライズ SSO サービスのクラスター化されたインスタンスを作成するには、ドメイン グループとして SSO 管理者および SSO 関連管理者のグループを作成する必要があります。  
  
-   作成または SSO 管理者のドメイン グループのメンバーであるドメイン アカウントを指定します。 各ノードで、エンタープライズ SSO サービスは、このドメイン アカウントとしてログオンするように構成されます。 このアカウントは、「サービスとしてログオン」権限をクラスター内の各ノードが必要です。 このアカウントは、クラスターへのフル コントロール アクセスを付与する必要があります。  
  
## <a name="clustering-the-master-secret-server"></a>マスター シークレット サーバーをクラスタ リング  
 マスター シークレット サーバーをクラスター化するための基本的な手順を次に示します。  
  
1. インストールし、クラスター ノードにエンタープライズ SSO を構成します。  
  
2. クラスター化されたエンタープライズ SSO リソースと依存するリソースを作成します。  
  
3. 2 番目のクラスター ノードでマスター シークレットを復元します。 マスター シークレット サーバーをクラスターに移動する場合も最初のクラスター ノード上にマスター シークレットを復元する必要があります。  
  
4. オンライン SSO サービスを含むクラスター グループを表示します。  
  
5. 管理データベースのマスター シークレットの名前を更新します。  
  
   マスター シークレット サーバーをクラスタ リングの詳細な手順は、次を参照してください。[マスター シークレット サーバーをクラスター化する方法](http://go.microsoft.com/fwlink/?LinkId=156839)(<http://go.microsoft.com/fwlink/?LinkId=156839>) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  
  
## <a name="see-also"></a>参照  
 [新しいマスター シークレット サーバーを手動で指定する](../technical-guides/designating-a-new-master-secret-server-manually.md)