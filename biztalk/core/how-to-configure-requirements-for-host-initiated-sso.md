---
title: 側開始 SSO のホストの要件を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f3319c0d8157ebe0c71c36a2494b3bda641181c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341220"
---
# <a name="how-to-configure-requirements-for-host-initiated-sso"></a>側開始 SSO のホストの要件を構成する方法
エンタープライズ SSO とホスト側開始 SSO 共通の特定の側面がありますが、特定のプラットフォームおよび Active Directory の要件はホスト側開始 SSO に固有です。 このトピックでは、これらの要件について説明しを確認するか、システムを作成する手順について説明します。  
  
- ホスト側開始 SSO は、ネイティブの Windows Server 2008 ドメイン環境でのみ実行できます。  
  
- ホストが実行している SSO サービスのサービス アカウント側開始 SSO は、TCB 特権を構成する必要があります。 (することができますこれを構成、ドメイン セキュリティ ポリシー内のサービス アカウント。)  
  
  さらに、ホスト側開始処理をトランザクション インテグレーターを使用する場合は、特定の要件は必要です。 TI ホストが Windows 以外のユーザーのシングル サインオンを実現するために SSO を開始の HIP を活用します。  
  
  たとえば、HIP サービスの TI のサービス アカウントは、domainname \hipsvc サービス アカウントで実行されます。 このサービスは、リソースにアクセスするリモートまたはローカル Windows で Windows アカウントを使用して、Windows 以外のアカウントに対応する必要があるアプリケーションをホストできます。  
  
  Domainname \hipsvc アカウントは、シングル サインオン用に使用されている関連アプリケーションのアプリケーション管理者グループのアカウントに属する必要があります。  
  
  Domainname \hipsvc アカウントに委任を制限する必要がありますが、シングル サインオンが開始したホストを使用する特権。 これは、Active Directory でドメイン管理者によって構成できます。 Spn を登録したアカウントの委任を構成できます。 制約付き委任は、管理者が指定されているコンポーネントのみにアクセスするサービス アカウントを許可します。  
  
### <a name="to-check-your-domain-function-level"></a>ドメインの機能レベルを確認するには  
  
1.  **Active Directory Domains and Trusts** MMC スナップインで、適切なノードをクリックします。 **Active Directory Domains and Trusts**、 をクリックし、**フォレスト機能レベルを上げる**します。  
  
2.  機能レベルがあることを確認**Windows Server 2008**します。 そうでない場合は、設定を変更しようとする前に、Active Directory のドキュメントを参照します。  
  
### <a name="to-create-an-spn"></a>SPN を作成するには  
  
1. ダウンロード、 **setspn**次の場所からユーティリティ: [ http://go.microsoft.com/fwlink/?LinkId=33178](http://go.microsoft.com/fwlink/?LinkId=33178)します。  
  
2. **[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。  
  
3. **実行**ダイアログ ボックスに「 **cmd**、順にクリックします**OK**します。  
  
4. コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定値は\<ドライブ\>: \Program Files\Common \enterprise シングル サインオンします。  
  
5. 型**setpsn hipsvc\computername.domain.com の domain \hissvc-**  
  
    場所**hipsvc\computername.domain.com**で実行されているコンピューターと、操作を実行するサービスと**domain \hissvc** hipsvc のサービス アカウントします。  
  
   これを行うには、ネットワーク内の適切なリソースにアクセスするこのサービス アカウント (domain \hissvc) 用の Active Directory で制約付き委任を構成できます。  
  
#### <a name="to-give-tcb-privileges-for-the-sso-service-account"></a>SSO サービス アカウントの TCB 特権を付与するには  
  
-   で、**ドメイン セキュリティ ポリシー - ローカル ポリシー - ユーザー権利の割り当て**、SSO サービス アカウントを追加、**オペレーティング システムの一部として機能**ポリシー。  
  
     Kerberos プロトコル遷移および制約付き委任の詳細についてを参照してください[ http://go.microsoft.com/fwlink/?LinkId=195484](http://go.microsoft.com/fwlink/?LinkId=195484)します。  
  
## <a name="see-also"></a>参照  
 [ホスト側開始 SSO](../core/host-initiated-sso.md)