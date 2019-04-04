---
title: SSO のセキュリティに関する推奨事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO, deploying
- Kerberos protocol, SSO
- deploying, SSO
- user accounts, SSO
- deploying, security
- SQL Server, SSO
- security, SSO
- SSO, Kerberos protocol
- SSO, auditing
- best practices, deploying
- SSO, Windows groups
- SSO, best practices
- SSO, perimeter network
- Windows groups, SSO
- SSO, SQL Server access
- best practices, security
- Master Secret server, clustering
- perimeter networks
- auditing [SSO]
- SSO, security
- SSO, user accounts
- Master Secret server, best practices
ms.assetid: 7ae922b4-fd48-41f4-aaab-419a5e22c753
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4877bdb4ea7f19a1ff8ec93dcee2e6910ef8891f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007123"
---
# <a name="sso-security-recommendations"></a>SSO のセキュリティに関する推奨事項
エンタープライズ シングル サインオン (SSO) システムを使用すると、ユーザーは 1 組の資格情報だけを使用してさまざまなシステムに接続できるようになります。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、SSO システムを機密情報の格納場所として使用しています。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ランタイムをインストールするたびにエンタープライズ シングル サインオンが自動的にインストールされますが、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境に関係なく、エンタープライズ シングル サインオンをスタンドアロン コンポーネントとしてインストールすることもできます。 エンタープライズ シングル サインオンに関する詳細については、[を使用して SSO](../core/using-sso.md)を参照してください。 SSO サービスとリソースをセキュリティで保護して環境に展開するには、次のガイドラインに従うことをお勧めします。  
  
## <a name="general-deployment-recommendations-for-sso"></a>SSO の展開に関する一般的な推奨事項  
  
-   ある 1 つだけのマスタ シークレット サーバーと、環境全体で SSO データベースを 1 つだけ場合でも、環境内で複数の BizTalk グループがあります。 これら 2 台のサーバーは、他の BizTalk Server コンピュータと SSO サーバーを構成する前に構成する必要があります。  
  
-   すべての SSO サーバーが同期されるように、環境内には 1 台のタイム サーバーを配置する必要があります。 SSO サーバー間で時刻が同期されていないことが原因で、環境のセキュリティが危険にさらされる場合があります。  
  
-   環境内に 1 台のマスタ シークレット サーバーしか存在しないことを考慮して、マスタ シークレット サーバーにはアクティブ/パッシブのクラスタ構成を使用することをお勧めします。 マスター シークレット サーバーをクラスタ リングの詳細については、[マスター シークレット サーバーをクラスター化する方法](../core/how-to-cluster-the-master-secret-server1.md)を参照してください。  
  
-   マスタ シークレット サーバーでは、SSO システムが SSO データベースに格納されている情報の暗号化に使用する暗号化キーを保持します。 マスタ シークレット サーバーには、他の製品やサービスをインストールまたは構成しないことをお勧めします。  
  
    > [!NOTE]
    >  マスタ シークレット サーバーをインストールおよび構成するコンピュータは、サーバーである必要はありません。  
  
-   マスタ シークレット サーバーは、マスタ シークレットをバックアップおよび復元するため、リムーバブル メディアまたは NTFS ファイル システム フォルダにアクセスできる必要があります。 リムーバブル メディアを使用する場合は、適切な手段を講じてリムーバブル メディアを保護してください。 NTFS ファイル システムにマスタ シークレットをバックアップする場合は、ファイルとフォルダを保護する必要があります。 また、このファイルには、SSO 管理者のみがアクセスできるようにする必要があります。  
  
-   マスタ シークレットは、マスタ シークレット サーバーによって生成されたら、すぐにバックアップする必要があります。 バックアップすると、マスタ シークレット サーバーで障害が発生した場合に、SSO データベースのデータを回復することができます。 マスター シークレットのバックアップの詳細については、[マスター シークレットの管理](../core/managing-the-master-secret.md)を参照してください。  
  
-   現在のシークレットをバックアップするか、または定期的 (月 1 回など) に新しいシークレットを生成します。 シークレットがないと、SSO データベースから情報を取得できません。 バックアップと、マスター シークレットの復元の詳細については、[マスター シークレットの管理](../core/managing-the-master-secret.md)を参照してください。  
  
## <a name="security-recommendations-for-sso-groups-and-accounts"></a>SSO グループとアカウントのセキュリティに関する推奨事項  
  
-   特に SSO 管理者グループと SSO 関連管理者グループについては、単独のユーザー アカウントではなく Windows グループを使用することをお勧めします。 これらのグループには、少なくとも 2 つのユーザー アカウントがメンバとして常に含まれている必要があります。  
  
-   SSO ランタイム サービス アカウントと SSO 管理者ユーザー アカウントが同じ SSO 管理者グループのメンバである場合も、これらのアカウントには、別のアカウントを使用することをお勧めします。 シークレットの生成やバックアップなどの管理タスクを実行する SSO 管理者ユーザーは、Windows 管理者である必要がありますが、SSO ランタイム サービス アカウントは Windows 管理者である必要はありません。  
  
    > [!IMPORTANT]
    >  Windows 管理者のユーザー権限は、SSO 管理者のユーザー権利に代わるものではありません。 SSO 管理者レベルのタスクを実行するには、Windows 管理者であっても、SSO 管理者グループのメンバでなければなりません。  
  
-   SSO のチケット発行機能を使用する場合、処理ドメイン (SSO サーバーが配置されているドメイン) のコンピュータで認識されるドメイン アカウントを使用する必要があります。  
  
-   マスタ シークレット サーバーに対応する SSO サービスには、一意なサービス アカウントを使用することをお勧めします。  
  
-   SSO 管理者アカウントは、SSO システムに対して高いレベルの特権を持っており、SSO データベースが格納されている SQL Server コンピュータの SQL Server 管理者アカウントでもあります。 SSO 管理者には専用のアカウントを用意し、他の目的には使用しないでください。 また、SSO 管理者グループのメンバシップは、SSO システムの実行と保守にかかわるアカウントのみに与えるようにしてください。  
  
-   BizTalk 管理者は、SSO データベースで、アダプターの構成情報を保存する SSO システムを活用できるように、BizTalk 管理者グループを「SSO 関連管理者グループに手動で追加する必要があります。 SSO 関連管理者グループのメンバにする必要があるのは、アダプタを管理している BizTalk 管理者のみです。 すべての BizTalk 管理者を、SSO 管理者にする必要はありません。  
  
## <a name="security-recommendations-for-an-sso-deployment"></a>SSO 展開のセキュリティに関する推奨事項  
  
- ネットワークが Kerberos 認証をサポートしている場合、すべての SSO サーバーを登録する必要があります。 マスタ シークレット サーバーと SSO データベース間に Kerberos 認証を使用する場合、SSO データベースが存在する SQL Server コンピュータにサービス プリンシパル名 (SPN) を構成する必要があります。 サービス プリンシパル名を構成する方法の詳細については、Microsoft ダウンロード Web サイトを参照して[ http://go.microsoft.com/fwlink/?LinkId=195797](http://go.microsoft.com/fwlink/?LinkId=195797)します。  
  
- [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] または [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] を実行していて、マスター シークレット サーバーが他の SSO サーバーや SSO データベースと異なるドメインに配置されている場合、マスター シークレット サーバー、処理ドメイン内のコンピューターを処理している SSO サーバー、および SSO データベースで、コンピューター間のデータ トランザクション コーディネーター (DTC) 認証に使用している RPC セキュリティを無効にする必要があります。 RPC セキュリティは、[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] および [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] の DTC 機能です。 RPC セキュリティを無効にすると、RPC 呼び出しの DTC 認証セキュリティ レベルは、Microsoft Windows Server 2003 で利用できるレベルに戻ります。  
  
- SSO 管理者は、マスタ シークレット サーバーと SSO サーバーのイベント ログで SSO 監査イベントを定期的に監視することをお勧めします。  
  
- すべての SSO サーバーと SSO データベース間に、ファイアウォールに加えて、インターネット プロトコル セキュリティ (IPsec) または Secure Sockets Layer (SSL) を使用することをお勧めします。 SSL の詳細については、Microsoft ヘルプとサポート Web サイトを参照して[ http://go.microsoft.com/fwlink/?LinkId=195798](http://go.microsoft.com/fwlink/?LinkId=195798)します。 詳細については、すべての SSO サーバーと SSO データベース間で SSL を使用して、[SSO の SSL を有効にする方法](../core/how-to-enable-ssl-for-sso.md)を参照してください。  
  
## <a name="perimeter-network"></a>境界ネットワーク  
 インターネット インフォメーション サービス (IIS) とエンタープライズ シングル サインオンを実行する際は、次の推奨事項に従ってください。  
  
-   IIS が境界ネットワーク (DMZ、非武装地帯、スクリーン サブネットとも呼ばれます) に配置されている場合、SSO システムに接続するために別の IIS サーバーをファイアウォールの内側に配置します。  
  
-   IIS ではリモート プロシージャ コール (RPC) ポートを開かないでください。  
  
## <a name="sql-server-access"></a>SQL Server へのアクセス  
 すべての SSO サーバーでは SQL Server に格納されている SSO データベースへのアクセスが発生します。 SQL Server データベースをセキュリティで保護する方法の詳細については、[ http://go.microsoft.com/fwlink/?LinkId=33175](http://go.microsoft.com/fwlink/?LinkId=33175)を参照してください。  
  
 Secure Sockets Layer (SSL)、インターネット プロトコル セキュリティ (IPsec) のいずれか、またはその両方を使用して、SSO サーバーと SSO データベース間でのデータの移動をセキュリティで保護することをお勧めします。 SSL の使用方法の詳細については、[ http://go.microsoft.com/fwlink/?LinkId=195798](http://go.microsoft.com/fwlink/?LinkId=195798)を参照してください。  
  
 SSO サーバーと SSO データベース間の接続のみで SSL を有効にする場合は、ssoconfig ユーティリティを使用して、すべての SSO サーバーに SSL サポートを設定できます。 このオプションを使用すると、SSO サーバーでは、SSO データベースにアクセスするときに必ず SSL が使用されるようになります。 詳細については、[SSO の SSL を有効にする方法](../core/how-to-enable-ssl-for-sso.md)を参照してください。  
  
## <a name="strong-passwords"></a>強力なパスワード  
 すべてのアカウントには、強力なパスワードを使用する必要があります。特に SSO 管理者グループのメンバ アカウントは SSO システム全体を制御できるので、強力なパスワードを使用することが重要になります。  
  
## <a name="sso-administrator-accounts"></a>SSO 管理者アカウント  
 SSO サービスのサービス アカウントには、コンピュータごとに別のアカウントを使用することをお勧めします。 SSO サービス アカウントには、シークレットの生成やバックアップなどの管理タスクを実行する SSO 管理者アカウントを使用しないでください。 SSO サービス アカウントに、コンピュータのローカル管理者アカウントを使用することはお勧めしませんが、SSO 管理者が実行する管理タスクには、ローカル管理者の権利が必要なものもあります。  
  
## <a name="master-secret-server"></a>マスタ シークレット サーバー  
 マスタ シークレット サーバーは、セキュリティで保護し、ロックダウンすることを強くお勧めします。 マスタ シークレット サーバーは、処理サーバーとして使用しないでください。 このサーバーは、マスタ シークレットを保持する目的にのみ使用してください。 このコンピュータの物理的なセキュリティを確保し、このコンピュータには SSO 管理者のみがアクセスできるようにする必要があります。  
  
## <a name="kerberos"></a>Kerberos  
 SSO では Kerberos 認証がサポートされているため、SSO に Kerberos 認証を設定することをお勧めします。 SSO に Kerberos を設定するには、SSO サービスのサービス プリンシパル名 (SPN) を登録する必要があります。 既定では、Kerberos を設定すると、SSO では SPN を使用して、SSO サービスを使用するコンポーネントを認証します。 SSO で管理しているサブサービスと SSO サーバー間には、Kerberos 認証を設定することをお勧めします。 また、SSO サーバー間、SSO サーバーと SSO データベースが格納されている SQL Server コンピュータ間に Kerberos 認証を使用することもできます。  
  
 Kerberos 認証を設定および確認するには、setspn ユーティリティと kerbtray ユーティリティを使用します。 これらのユーティリティの詳細については、[ http://go.microsoft.com/fwlink/?LinkId=33178](http://go.microsoft.com/fwlink/?LinkId=33178)を参照してください。  
  
## <a name="delegation"></a>委任  
 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] または [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] を使用している場合、制約付き委任を使用できますが、シングル サインオン管理者のタスクの実行には委任を使用しないことをお勧めします。 また、シングル サインオン管理者には、追加のタスクやユーザー権利を委任しないことをお勧めします。  
  
## <a name="auditing"></a>監査  
 監査は、環境内の情報を追跡するための重要なメカニズムです。 エンタープライズ シングル サインオン (SSO) では、SSO データベースで行われたすべての操作が監査対象になります。 SSO では、データベースに備わっているイベント ログと監査ログを使用します。 SSO には、シングル サインオン サーバーに対して次の 2 つの監査レベルが用意されています。  
  
- "成功" 監査レベルでは、成功した操作を監査します。  
  
- "失敗" 監査レベルでは、失敗した操作を監査します。  
  
  SSO 管理者は、企業の規定に応じて、成功と失敗の監査レベルを設定できます。  
  
  成功と失敗の監査は、次のレベルのいずれかに設定できます。  
  
  0 = オフ。 このレベルでは、監査メッセージは発行されません。  
  
  1 = 低。  
  
  2 = 中。  
  
  3 = 高。 このレベルでは、できるだけ多くの監査メッセージが発行されます。  
  
  成功の監査の既定値は 0 (オフ)、失敗の監査の既定値は 1 (低) です。 これらの値は、SSO システムで必要な監査レベルに応じて変更できます。  
  
> [!IMPORTANT]
>  エンタープライズ シングル サインオンの監査では、シングル サインオン サービスによって生成されたメッセージを発行します。 これはセキュリティ監査ではないため、SSO システムでは、イベント ログのセキュリティ ログには情報を保存しません。 SSO システムは、SSO 監査メッセージをアプリケーション イベント ログに直接保存します。  
  
### <a name="database-level-auditing"></a>データベース レベルの監査  
 SSO システムによるデータベース レベルの監査では、SSO データベースで実行された操作を SSO データベースの監査テーブルで追跡します。 これらの監査テーブルのサイズは、SSO システム レベルで定義されています。 関連アプリケーションやマッピングの削除、資格情報の参照などの操作を監査できます。 既定では、監査テーブルのサイズは 1,000 エントリに設定されています。 SSO 管理者は、企業のポリシーに応じて、このサイズを変更できます。  
  
## <a name="using-sso-accounts"></a>SSO アカウントの使用  
 このセクションでは、エンタープライズ シングル サインオン (SSO) システムでドメイン グループ、ローカル グループ、および単独アカウントを使用する際のベスト プラクティスを紹介します。  
  
### <a name="domain-windows-groups-and-accounts"></a>ドメイン Windows グループとアカウント  
 ドメイン Windows グループを使用する場合は、以下のような推奨事項があります。  
  
- ドメイン グループとドメイン アカウントを使用します。  
  
- [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] または [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] を使用する場合、ENTSSO サービス アカウントは、Network Service アカウントで実行されるように構成できます。 ただし、この構成では Network Service アカウントに SSO 管理者権限を与える必要があるため、セキュリティ上の理由により推奨されていません。 代わりに、ENTSSO サービスに対する一意のドメイン サービス アカウントを使用することをお勧めします。  
  
- SSO 管理者にはドメイン グループを使用します。 単独のドメイン アカウントは別の単独アカウントに変更することができません。そのため、単独のドメイン アカウントを SSO 管理者として指定しないことをお勧めします。  
  
- SSO 関連管理者として単独のドメイン アカウントを指定することはできますが、SSO 関連管理者にはドメイン グループを使用することをお勧めします。  
  
- アプリケーション管理者として単独のドメイン アカウントを指定することはできますが、アプリケーション管理者にはドメイン グループを使用することをお勧めします。  
  
- アプリケーション ユーザー アカウントには、ドメイン グループを使用する必要があります。 SSO アプリケーション ユーザー アカウントでは、個人用アカウントはサポートされません。  
  
- これらの各 SSO アクセス アカウントには、複数のアカウントを指定できます。  
  
## <a name="see-also"></a>参照  
 [エンタープライズ シングル サインオン サーバーのポート](../core/ports-for-the-enterprise-single-sign-on-servers.md)   
 [セキュリティ保護のための最小ユーザー権限](../core/minimum-security-user-rights.md)