---
title: マルチ サーバーの BizTalk 環境に Active Directory アクセス許可を実装するためのガイドライン |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 315e25c4-b21d-4b5f-a1d2-1e2777b57f9e
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ff7b45e560278053cec99208fd06917d079d6b8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25975976"
---
# <a name="guidelines-for-implementing-active-directory-permissions-on-multi-server-biztalk-installations"></a>複数サーバーの BizTalk インストールでの Active Directory アクセス許可の実装に関するガイドライン
このトピックでは、Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] インストールで使用するユーザー アカウントとグループから構成される Active Directory 組織単位を作成する際のガイドラインを示します。  
  
 ここに作成されたアカウントは、ドメインにおいて一般ユーザーのアクセス許可以上のアクセス許可を必要としません。 このドメイン アカウントは、次に示す信頼の境界内では高度な特権を必要とする場合があります。  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
-   Microsoft [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] ([!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] サーバー上)  
  
-   Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]  
  
-   外部データベース 1  
  
-   外部データベース 2  
  
-   外部データベース*N*  
  
 たとえば、ドメイン アカウントには、外部データベースをホストしているシステムで特定のアクションを実行する権限を付与する必要が生じる場合があります。 また、アカウントは、ファイル ドロップ フォルダーにファイルを書き込む必要があることもあり、この場合は、そのフォルダーへの書き込みアクセス許可が必要になります。  
  
 使用して、 **Active Directory ユーザーとコンピューター**コンソールを作成してドメイン ユーザー アカウントとグループ アカウントを管理します。 をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、順にクリック**Active Directory ユーザーとコンピューター**に開始、 **Active Directory ユーザーとコンピューター**コンソールです。  
  
## <a name="biztalk-server-installation-and-configuration-account"></a>BizTalk Server のインストールと構成のアカウント  
 開発環境で、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] インストール プログラムと [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 構成ウィザードを実行するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] システムおよび [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] システムの管理権限を持つアカウントを使用する必要があります。 セットアップと構成の完了後すぐに、権限を取り消したり、アカウントを無効にしたりすることができます。 アカウントは、いくつかの BizTalk グループに属する必要もあります。これについては、次のセクションで説明します。  
  
> [!NOTE]
>  インストールに使用するアカウントがサーバーと異なる Active Directory フォレストに属している場合、SSO コンポーネントを構成することはできません。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] インストーラー アカウントがない場合は、SSO 構成用のローカル管理者アカウントを使用します。 この方法では、インストール中に、別の資格情報を使用してリソースにログオンすることが必要になるなど、別の問題が発生する可能性があります。  
  
## <a name="biztalk-server-development-accounts"></a>BizTalk Server 開発アカウント  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 開発を行うユーザーは、アダプター、受信ハンドラーと送信ハンドラー、および受信場所へのアクセスが必要です。 このアクセスには、メンバーであるドメインの開発者グループが必要です、 **BizTalk Server 管理者**と**SSO 関連管理者**グループ。  
  
> [!NOTE]
>  Active Directory では、外部のドメイン ユーザーを含むことができるグループの種類と他のグループに含まれることが可能なグループの種類に関して制限があります。 以下で作成するグループとアカウントは、単一ドメインのマルチサーバー環境でテストされます。  
  
## <a name="biztalk-server-deployment-accounts"></a>BizTalk Server 展開アカウント  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリケーションを展開するユーザーは、ローカル システムの管理者である必要があり、その環境の他のアクセス許可が必要になる場合もあります。 BizTalk Server 展開アカウントをこのトピックで示しているのはこのためです。  
  
 このアクセスが、ドメイン展開グループのメンバーである必要があります、 **BizTalk Server 管理者**と**SSO 関連管理者**グループ。  
  
> [!NOTE]
>  インストールに使用するアカウントがサーバーと異なる Active Directory フォレストに属している場合、SSO コンポーネントを構成することはできません。 BizTalk Server 展開アカウントがない場合は、SSO 構成用のローカル管理者アカウントを使用します。 この方法では、インストール中に、別の資格情報を使用してリソースにログオンすることが必要になるなど、別の問題が発生する可能性があります。  
  
## <a name="biztalk-server-support-accounts"></a>BizTalk Server サポート アカウント  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリケーションをサポートするユーザーは、ローカル システムの管理者である必要があります。 BizTalk サポート アカウントをこのトピックで示しているのはこのためです。  
  
 このアクセスが、ドメインのサポート グループのメンバーである必要があります、 **BizTalk Server 管理者**グループ。  
  
## <a name="sql-server-service-accounts"></a>SQL Server サービス アカウント  
 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] インスタンスを実行しているサービスは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンポーネントのインストール、開発、展開を行うアカウントと同じ Active Directory ドメインに属している必要があります。  
  
-   使用して**SQLAdmin**管理関数 (対話型ログオン)。  
  
-   使用して**SQLService** (対話型ログオンなし)、サービスを管理します。  
  
-   使用して**SQLAccess**外部データベースにアクセスします。  
  
-   SQLAdmin は、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] システムのローカル管理者グループのメンバーである必要があります。  
  
-   SQLService のローカルの Administrators グループのメンバーである必要があります、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]システムとを許可する必要があります、**サービスとしてログオン**ユーザー権限。  
  
-   SQLAccess には、リモート データベース サーバーに対する適切な権限が必要です。  
  
 **SQL アカウント:**  
  
|**ユーザー名**|**[First Name]**|**[Last Name]**|**[名前]**|  
|-------------------|--------------------|-------------------|-------------------|  
|SQLService |SQL|SQLService |SQL サービス アカウント|  
|SQLAdmin|管理|SQLService |SQL Admin アカウント|  
|SQLAccess|アクセス|SQLService |SQL アクセス アカウント|  
  
 社内基準に従ってアカウントのパスワードを設定します。  
  
> [!IMPORTANT]
>  [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] を実行しているコンピューターで、SQLService アカウントと資格情報を使用するように SQL Server サービスおよび SQLServerAgent サービスのスタートアップ パラメーターを変更します。  
  
> [!NOTE]
>  "ユーザー名" フィールドはサンプルです。他の Active Directory アカウントとの競合しないよう必要に応じて名前を変更します。  
  
## <a name="windows-sharepoint-services-account"></a>Windows SharePoint Services アカウント  
 Windows SharePoint Services アカウントは、[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] をインストールする前に作成されている必要があります。  
  
 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] アカウントに関する推奨事項と注意事項を次に示します。  
  
-   SharePoint Admin アカウント (SPAdmin) は、管理機能、SharePoint Timer Service およびすべての [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] アクセスに使用します。  
  
-   SPAdmin はサイト所有者で、電子メール エイリアスが必要になります。  
  
-   SPAdmin は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューターのローカル管理者グループのメンバーである必要があります (これは、Windows SharePoint Services セットアップで行います)。  
  
-   SPAdmin は、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] コンピューターのセキュリティ管理者ロールとデータベース作成者ロールを持っている必要があります (これは、Windows SharePoint Services セットアップで行います)。  
  
 **Sharepoint アカウント:**  
  
|**ユーザー名**|**[First Name]**|**[Last Name]**|**[名前]**|  
|-------------------|--------------------|-------------------|-------------------|  
|SPAdmin|管理|SPService|SharePoint Admin アカウント|  
  
 社内基準に従ってアカウントのパスワードを設定し、構成手順の間にこのパスワードを取得できるようにします。 参照してください、**パスワード**に関する問題については、このトピックのセクションでは、パスワードを生成します。  
  
> [!NOTE]
>  この "ユーザー名" フィールドはサンプルです。他の AD アカウントを保護するため必要に応じてこの名前を変更します。  
  
> [!IMPORTANT]
>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を実行しているコンピューターに Windows SharePoint Services をインストールしたら、SharePoint Timer Service のスタートアップ パラメーターが SPAdmin アカウントと資格情報を使用していることを確認します。  
  
## <a name="biztalk-groups-and-users"></a>BizTalk のグループとユーザー  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のグループとユーザーは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 構成ウィザードを実行する前に作成されている必要があります。 単一システム インストールの [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、構成時に作成されたローカル グループとローカル アカウントを使用します。 ただし、別に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ホストを展開している場合、または [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] と [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] を 2 つの異なるコンピューターにインストールしている場合は、ドメイン ユーザー アカウントとドメイン グループ アカウントを使用する必要があります。  
  
> [!NOTE]
>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 構成ウィザードでは、ドメイン アカウントを作成できません。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] サービス アカウントとユーザー アカウントに関する推奨事項と注意事項を次に示します。  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の組織単位 (OU) を作成します。 アカウントとグループは、すべてこの OU に属することになります。  
  
-   フル ネームはわかりやすいものにします。次の表の名前は、構成時にインストーラーが適切なグループ/アカウント/ユーザーを選択できるようにする必要があります。  
  
-   名と姓は省略可能で、単に一貫性のために用意されています。  
  
-   差別化要因**BTService**と**BTUser**はサービス アカウント (オートマトン) と汎用/共有の人間のユーザーを参照します。  
  
-   ドメイン アカウントを作成して、アップ ラインの環境用のユーザー アカウントとグループ アカウントを生成するための ADSI スクリプトで、そのドメイン アカウントを設定します。  
  
 **BizTalk サービス アカウントします。**  
  
|**ユーザー名**|**[First Name]**|**[Last Name]**|**[名前]**|  
|-------------------|--------------------|-------------------|-------------------|  
|BTService|BTS|BTService|BizTalk サービス アカウント|  
|BTServiceHost|Host|BTService|BizTalk ホスト インスタンス アカウント|  
|BTServiceHostIso|HostIso|BTService|BizTalk 分離ホスト インスタンス アカウント|  
|SSOService|SSO|BTService|エンタープライズ シングル サインオン サービス|  
|BTServiceREU|REU|BTService|ルール エンジン更新サービス|  
  
 社内や環境の基準に従ってユーザー名を設定します (devBTService、alphaBTService など)。 社内基準に従ってアカウントのパスワードを設定し、構成手順については、それらを取得できるようにします。 参照してください、**開発のためのパスワードに関する考慮事項**に関する問題については、このトピックのセクションでは、パスワードを生成します。  
  
 インストール時、サービス アカウントが非常に細分化されており、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で作成されるサービスとほぼ一対一でマッピングされていることを確認できます。 この細分化により、企業の IT セキュリティでは、必要に応じてアクセスを追跡したり制限したりできます。 アカウントは細分化することをお勧めしますが、エンタープライズ環境で必要かどうかは、システム デザイナーや企業のセキュリティ担当者の判断によります。  
  
 前のグループのサービス アカウントは、自動アクセス専用で、ユーザーによる対話形式でのログオンは想定していません。  
  
#### <a name="to-set-the-appropriate-account-options"></a>適切なアカウント オプションを設定するには  
  
1.  **Active Directory ユーザーとコンピューター**コンソール、ドメインを展開する場合にクリックして展開し、**ユーザー**コンテナーです。  
  
2.  アカウントを右クリックし、**プロパティ**を表示する、**プロパティ**アカウントのダイアログ ボックス。  
  
3.  クリックして、**アカウント**のタブ、**プロパティ** ダイアログ ボックス。  
  
4.  次のオプションを確認する をクリックします。  
  
    -   **ユーザーがパスワードを変更できない**(エンタープライズ セキュリティ、バッチがパスワードを変更)。  
  
    -   **パスワードの有効期限が切れることはありません。**  
  
5.  クリックして、**ログに**を表示するボタン、**ログオンできるワークステーション** ダイアログ ボックス。  
  
6.  オプションをクリックして **、次のコンピューター**、実行する各コンピューターを追加[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]、クリックして **[ok]** です。  
  
7.  をクリックして、**リモート_コントロール**のタブ、**プロパティ** ダイアログ ボックスをクリックし、オプションをオフに**リモート_コントロールを有効にする**です。  
  
8.  クリックして、**ターミナル サービスのプロファイル**のタブ、**プロパティ** ダイアログ ボックス。  
  
9. クリックすると、チェック ボックスを**任意のターミナル サーバーにログオンするには、このユーザー権限を拒否する**です。  
  
10. をクリックして**OK**を閉じる、**プロパティ**アカウントのダイアログ ボックス。  
  
11. 各サービス アカウントについて、手順 3. ～ 10. を繰り返します。  
  
 **BizTalk ユーザー アカウントします。**  
  
|**ユーザー名**|**[First Name]**|**[Last Name]**|**[名前]**|  
|-------------------|--------------------|-------------------|-------------------|  
|BTUserAdmin|管理|BTUser|BizTalk 管理ユーザー アカウント|  
|BTUserDeploy|配置|BTUser|BizTalk 展開ユーザー アカウント|  
|BTUserHostInstance|HostInstance|BTUser|BizTalk ホスト インスタンス アカウント|  
|BTUserHostIsolated|IsolatedlHost|BTUser|BizTalk 分離ホスト インスタンス アカウント|  
|BTUserInstall|Install|BTUser|BizTalk インストール ユーザー アカウント|  
|BTUserSupport|サポート|BTUser|BizTalk サポート アクセス アカウント|  
  
#### <a name="to-set-the-appropriate-account-options-follow-these-steps"></a>適切なアカウント オプションを設定するには、次の手順を実行します。  
  
1.  **Active Directory ユーザーとコンピューター**コンソールをクリックして、ドメインを展開しを展開しをクリックして、**ユーザー**コンテナーです。  
  
2.  アカウントを右クリックし、**プロパティ**を表示する、**プロパティ**アカウントのダイアログ ボックス。  
  
3.  クリックして、**アカウント**のタブ、**プロパティ** ダイアログ ボックス。  
  
4.  次のオプションを確認する をクリックします。  
  
    -   **ユーザーがパスワードを変更できない**(エンタープライズ セキュリティ、バッチがパスワードを変更)。  
  
    -   **パスワードの有効期限が切れることはありません。**  
  
5.  クリックして、**ログに**を表示するボタン、**ログオンできるワークステーション** ダイアログ ボックス。  
  
6.  オプションをクリックして **、次のコンピューター**、実行する各コンピューターを追加[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]、クリックして **[ok]** です。  
  
7.  をクリックして、**リモート_コントロール**のタブ、**プロパティ**、チェック ボックスをクリックしてダイアログ ボックスで、**リモート_コントロールを有効にする**です。  
  
8.  クリックして、**ターミナル サービスのプロファイル**のタブ、**プロパティ** ダイアログ ボックス。  
  
9. オプションをオフにする をクリックします。**任意のターミナル サーバーにログオンするには、このユーザー権限を拒否する**です。  
  
10. をクリックして**OK**を閉じる、**プロパティ**アカウントのダイアログ ボックス。  
  
11. 各ユーザー アカウントについて、手順 3. ～ 10. を繰り返します。  
  
    > [!NOTE]
    >  提供されるロールが現行のユーザーに割り当てられている場合、設定したアカウントは任意で無効にすることができます。 リリース 1 とリリース 2 の初期段階では、これらのアカウントは、開発環境、アルファ テスト環境、ベータ テスト環境で使用されることを前提としています。  
  
 **BizTalk グループ アカウント**  
  
|**グループ名**|**グループの種類**|**メンバー**|  
|--------------------|--------------------|-----------------|  
|BizTalk Application Users|グローバルまたはユニバーサル|-BTServiceHost<br />-BTUserHostInstance|  
|BizTalk 開発ユーザー|グローバルまたはユニバーサル|(開発ユーザーのローカル ドメイン アカウント)**注:** ベスト プラクティスとして有効にしないアップラインの環境で BizTalk 開発ユーザー グループ。|  
|BizTalk 展開ユーザー|グローバルまたはユニバーサル|(展開ユーザーのローカル ドメイン アカウント)|  
|BizTalk ホスト ユーザー|グローバルまたはユニバーサル|BTUserHostInstance|  
|BizTalk 分離ホスト ユーザー|グローバルまたはユニバーサル|-BTServiceHostIso<br />-BTUserHostInstance|  
|BizTalk Server 管理者|グローバルまたはユニバーサル|-BTUserAdmin<br />-BTUserInstall<br />BizTalk 開発ユーザー<br />BizTalk 展開ユーザー|  
|BizTalk サポート ユーザー|グローバルまたはユニバーサル|BTUserSupport (サポート ユーザーのローカル ドメイン アカウント)|  
|SSO 管理者|グローバルまたはユニバーサル|-SSOService<br />-BTUserInstall<br />ローカル管理者|  
|SSO 関連管理者|グローバルまたはユニバーサル|BizTalk 開発ユーザー<br />BizTalk 展開ユーザー<br />-BTServiceHostIso<br />-   \<コンソール ユーザー\>|  
|Windows SharePoint Services 管理者|グローバルまたはユニバーサル|-SPAdmin<br />-BTUserInstall<br />-BTUserDeploy<br />BizTalk 開発ユーザー<br />BizTalk 展開ユーザー|  
  
 ドメイン グループに関する推奨事項と注意事項を次に示します。  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] をインストールする前に、グループを作成してメンバーを追加します。  
  
-   ドメイン グループは、グローバル グループにもユニバーサル グループにもすることができます。  
  
-   使用して *\<DomainName\>\\< ユーザー名\>* 構成ウィザードでドメイン アカウント情報を指定する場合。  
  
-   グループとユーザー アカウントおよびサービス アカウントは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューターが属しているドメインに属する必要があります (これは構成ウィザードで確認され、他のドメインのアカウントや他のドメインのアカウントを含むグループは表示されません)。  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、すべてのクラスタリング シナリオに対応するドメイン アカウントが必要です。  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のインストール時、コンソール ユーザーは次のグループのメンバーである必要があります。  
  
    -   BizTalk Server 管理者  
  
    -   SSO 管理者 (マスター シークレット サーバーを構成する場合のみ)  
  
    -   Windows 管理者  
  
    -   [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]管理者  
  
    -   OLAP 管理者  
  
     BTUserInstall アカウントは、インストールと構成に使用し、構成が完了したら無効にする必要があります。  
  
-   メッセージ イベントとサービス インスタンス追跡でオーケストレーションをデバッガーに接続できるように、開発者は、する必要があります、BizTalk Server 管理者グループに属しているセクションで説明したよう**BizTalk 開発アカウント**.  
  
## <a name="local-administrator-accounts"></a>ローカル管理者アカウント  
 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] コンピューターで、次のアカウントとグループの中にローカル管理者グループに属していないものがあれば、追加します。  
  
-   ドメイン\BTUserInstall (構成が完了したら無効にします)  
  
-   ドメイン\BTUserDeploy (構成が完了したら運用環境で無効にします)  
  
-   ドメイン\SPAdmin  
  
-   ドメイン\SQLAdmin  
  
-   ドメイン\SQLService  
  
-   \Biztalk 開発ユーザー (でアップ ラインの環境)  
  
-   ドメイン\BizTalk 展開ユーザー (開発環境では除外します)  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューターで、次のアカウントとグループの中にローカル管理者グループに属していないものがあれば、追加します。  
  
-   ドメイン\BTUserInstall (構成が完了したら無効にします)  
  
-   ドメイン\BTUserDeploy (構成が完了したら運用環境で無効にします)  
  
-   ドメイン\BTUserSupport  
  
-   ドメイン\SPAdmin  
  
-   ドメイン\BizTalk 開発ユーザー (アップラインの環境では除外します)  
  
-   ドメイン\BizTalk 展開ユーザー (開発環境では除外します)  
  
## <a name="sql-server-administrator-accounts"></a>SQL Server 管理者アカウント  
 セットアップ プログラムによりインストーラーからの入力が受け付けられ、SQL ロールがユーザーとグループに割り当てられます。  
  
-   [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] のセットアップ中、SPAdmin アカウントには、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] コンピューターのセキュリティ管理者権限とデータベース作成者権限が付与されます。 SPAdmin アカウントがローカル管理者グループのメンバーの場合、この権限を削除することができます。  
  
## <a name="e-mail-account"></a>電子メール アカウント  
 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] は、特定のシステム イベントに基づいてメールを送信します。 構成時に、電子メール アドレスの入力を求めるメッセージを設定します。 セットアップと単体テストの間に、電子メール エイリアスをこの目的で作成してエイリアスを監視します。 運用環境では、システムを監視しているシステム管理者がこのアカウントにアクセスできる必要があります。  
  
 使用される電子メール アカウント[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]は、 **WSS 管理者の電子メール**アカウント。  
  
## <a name="password-considerations-for-development"></a>開発時のパスワードに関する考慮事項  
 開発環境とテスト環境では、アカウントのパスワードは標準で設定され、配布可能です。 インストーラーの標準はさまざまです。このトピックでは、サービス コンポーネントの先頭の大文字を取り、その後にアカウントの残り (サービスまたはユーザー) の小文字部分を省略したものを続けたテンプレートを使用します。 このトピックでは、サービス アカウントには 'Serv' を、ユーザー アカウントには 'User' を使用します。  
  
 例:  
  
-   Windows SharePoint Services (SharePoint) サービスと管理者アカウント (SPAdmin) のパスワード: 'SPServ' です。  
  
-   BizTalk サービス アカウントのパスワード: 'BTServ' です。  
  
-   BizTalk ユーザー アカウントのパスワード: 'BTUser' です。  
  
 IT 環境によっては、パスワードに英字以外の文字や数字を含める必要があります。 このシナリオでは、"s" の代わりにドル記号 ($) を使用したり、"a" の代わりに アット マーク (@) を使用することもできます。 これらの記号はサンプルです。半パブリックなパスワードの共有アカウントのために、最適なパターンを開発します。  
  
 開発環境で使用される再配布可能なサンプル パスワードを次に示します。  
  
-   BT$erv99           BizTalk サービス アカウント  
  
-   BTU$er99          BizTalk ユーザー アカウント  
  
-   SP$erv99           WSS サービス アカウント (SPAdmin)  
  
-   SQL$erv99         SQL サービス/アクセス/Admin アカウント  
  
> [!NOTE]
>  これらの推奨事項は開発環境、共有環境に限定されるもので、社内のパスワード ポリシーの使用を勧めたり妨げるものではありません。 パスワードの要件については、ネットワーク管理者に確認してください。  
  
> [!NOTE]
>  社内のパスワード ポリシーに生成されたパスワードが含まれる場合、記号やその組み合わせには XML の特殊用途の文字もあることに注意してください。 これらの文字を不適切に使用すると、構成時に、構成 XML ファイルを開けなくなります。 これらのシンボルを含める"&"、"\<「,」\>"、1 つに、二重引用符、他のユーザーを含めることがあります。 ファイル ベースの構成を実行する前に、構成 XML ファイルをテストしてください。 生成されたパスワードを埋め込んだドキュメントを Internet Explorer (または XML エディター) で開くことで、適切な XML 書式設定について、これを確実にテストすることができます。  
  
 アップラインの環境でセキュリティで保護されたパスワードの展開の詳細については (テストするメソッドを含む、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]構成ファイル) を参照してください[BizTalk Server 2013 および 2013 R2 の構成の概要](http://msdn.microsoft.com/library/aa58c43f-8f0e-4a5c-89b9-db7b8a852a72)です。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server のアクセス許可のトラブルシューティング](../core/troubleshooting-biztalk-server-permissions.md)