---
title: "側開始 SSO のホストの要件を構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- service accounts, granting privileges [SSO]
- host initiated SSO, configuring
- domain function level [SSO]
- host initiated SSO, Transaction Integrator (TI)
- SPN [SSO]
- managing [SSO], granting TCB privileges
- Transaction Integrator (TI)
- host initiated SSO, SPN
- host initiated SSO, TCB privileges
- configuring, host initiated SSO
- creating, SPNs [SSO]
- TCB privileges [SSO]
- managing [SSO], host initiated
- host initiated SSO, domain function level
- service accounts, SSO
- SSO, host initiated
- managing [SSO], creating SPNs
- SSO, service accounts
ms.assetid: 91d77c9f-bab2-4f6e-8bce-e31c59cebb20
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9f8a004c1883a05c3fcf60324f428144591cff4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-requirements-for-host-initiated-sso"></a>ホスト側開始 SSO の要件を構成する方法
エンタープライズ SSO とホスト側開始 SSO にはある共通点がありますが、特定のプラットフォームおよび Active Directory の要件はホスト側開始 SSO に対して一意です。 このトピックでは、これらの要件について説明し、システムで要件を確認または作成する手順を示します。  
  
-   ホスト側開始 SSO は、ネイティブの Windows Server 2008 ドメイン環境でのみ実行できます。  
  
-   ホスト側開始 SSO を実行している SSO サービスのサービス アカウントは、TCB 特権が付与されるように構成する必要があります (これは、ドメイン セキュリティ ポリシーのサービス アカウントに対して構成できます)。  
  
 また、ホスト側開始処理にトランザクション インテグレータを使用する場合は、特定の要件が必要です。 HIP の TI は、ホスト側開始 SSO を利用して、Windows 以外のユーザーのシングル サインオンを実現します。  
  
 たとえば、HIP サービスの TI のサービス アカウントは、domainname\hipsvc サービス アカウントで実行されます。 このサービスは、Windows 以外のアカウントに対応する Windows アカウントを使用して Windows 上のリモート リソースまたはローカル リソースにアクセスするアプリケーションをホストできます。  
  
 domainname\hipsvc アカウントは、シングル サインオンに使用される関連アプリケーションのアプリケーション管理者グループ アカウントに属している必要があります。  
  
 domainname\hipsvc アカウントには、ホスト側開始シングル サインオンを使用するための制約付き委任の特権を付与する必要があります。 これは、Active Directory のドメイン管理者が構成できます。 委任は、SPN を登録したアカウントに対して構成できます。 制約付き委任が付与されたサービス アカウントは、管理者が指定するコンポーネントにのみアクセスできます。  
  
### <a name="to-check-your-domain-function-level"></a>ドメインの機能レベルを確認するには  
  
1.  **Active Directory Domains and Trusts** MMC スナップインで、右側には、ノードをクリックして**Active Directory Domains and Trusts**、クリックして**フォレストの機能レベルを上げる**します。  
  
2.  機能レベルがあることを確認**Windows Server 2008**です。 機能レベルが異なる場合は、設定を変更する前に Active Directory のドキュメントを参照してください。  
  
### <a name="to-create-an-spn"></a>SPN を作成するには  
  
1.  ダウンロード、 **setspn**次の場所からユーティリティ: [http://go.microsoft.com/fwlink/?LinkId=33178](http://go.microsoft.com/fwlink/?LinkId=33178)です。  
  
2.  **[スタート]** メニューの **[ファイル名を指定して実行]**をクリックします。  
  
3.  **実行** ダイアログ ボックスで、「 **cmd**、順にクリック**OK**です。  
  
4.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定値は\<ドライブ >: \program files \common files \enterprise シングル サインオンします。  
  
5.  型**setpsn hipsvc\computername.domain.com の domain \hissvc-**  
  
     ここで**hipsvc\computername.domain.com**で実行されているコンピューターと、操作を実行するサービスと**domain \hissvc** hipsvc のサービス アカウントは、します。  
  
 この操作後、Active Directory でこのサービス アカウント (domain\hissvc) 用の制約付き委任を、ネットワーク内の適切なリソースにアクセスするように構成できます。  
  
#### <a name="to-give-tcb-privileges-for-the-sso-service-account"></a>SSO サービス アカウントの TCB 特権を付与するには  
  
-   下にある、**ドメイン セキュリティ ポリシーのローカル ポリシー - ユーザー権利の割り当て**、SSO サービス アカウントを追加、**オペレーティング システムの一部として動作する**ポリシー。  
  
     Kerberos プロトコル遷移および制約付き委任の詳細についてを参照してください[http://go.microsoft.com/fwlink/?LinkId=195484](http://go.microsoft.com/fwlink/?LinkId=195484)です。  
  
## <a name="see-also"></a>参照  
 [ホスト側開始 SSO](../core/host-initiated-sso.md)