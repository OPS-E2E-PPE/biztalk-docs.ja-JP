---
title: マルチ サーバーの BizTalk インストールで Active Directory のアクセス許可を実装するためのガイドライン |Microsoft Docs
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
ms.openlocfilehash: dad79e7e3003f8ee66aab0838b10f44f8b519258
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65332506"
---
# <a name="guidelines-for-implementing-active-directory-permissions-on-multi-server-biztalk-installations"></a>複数サーバーの BizTalk インストールでの Active Directory アクセス許可の実装に関するガイドライン
このトピックでは、Active Directory 組織単位をユーザー アカウントと、Microsoft で使用するグループの構成を作成するためのガイドラインを説明します。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インストールします。  
  
 ここに作成されたアカウントでは、通常のユーザーのもの以外のドメインのアクセス許可は必要ありません。 ドメイン アカウントが含まれる信頼境界内で昇格された特権を必要があります。  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
- Microsoft [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] (上、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] server)  
  
- Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]  
  
- 外部データベース 1  
  
- 外部データベース 2  
  
- 外部データベース*N*  
  
  たとえば、ドメイン アカウントでは、外部データベースをホストしているシステム上の特定のアクションを実行する権限を付与する必要があります。 別のケースでは、アカウントをフォルダーへの書き込みアクセスを必要とする、ファイル ドロップ フォルダーにファイルを書き込む必要があります。  
  
  使用して、 **Active Directory ユーザーとコンピューター**コンソールを作成してドメイン ユーザーおよびグループ アカウントを管理します。 クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、順にクリックします**Active Directory ユーザーとコンピューター**に開始、 **Active Directory ユーザーとコンピューター**コンソール。  
  
## <a name="biztalk-server-installation-and-configuration-account"></a>BizTalk Server のインストールと構成のアカウント  
 開発環境で、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インストール プログラムと[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]構成ウィザードで管理者権限を持つアカウントを使用する必要、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]システム。 権限を取り消すにはまたはのセットアップと構成が完了するとすぐに、アカウントが無効にします。 アカウントは、次のセクションで説明したいくつかの BizTalk グループにも属する必要があります。  
  
> [!NOTE]
>  インストールに使用されるアカウントは、サーバーは異なる Active Directory フォレストに属している場合は、SSO コンポーネントを構成することはできません。 ない場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インストーラー アカウントは、SSO 構成用のローカル管理者アカウントを使用します。 この方法論では、別の資格情報を使用してリソースにログオンする必要があるなどのインストール中に、その他の問題を作成できます。  
  
## <a name="biztalk-server-development-accounts"></a>BizTalk Server 開発アカウントします。  
 行うユーザー[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]開発アダプターへのアクセスを必要と、受信し送信ハンドラー、および受信場所。 このアクセスがドメインの開発者グループのメンバーである必要があります、 **BizTalk Server 管理者**と**SSO 関連管理者**グループ。  
  
> [!NOTE]
>  Active Directory には、外部ドメインのユーザーを含むことのできるグループの種類とその他のグループに格納できるグループの種類に関する制限があります。 グループとの下に作成されたアカウントは、1 つのドメインのマルチ サーバー環境でテストされます。  
  
## <a name="biztalk-server-deployment-accounts"></a>BizTalk Server 展開アカウントします。  
 展開するユーザー[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーションは、システムのローカル管理者である必要があり、環境内の他のアクセス許可を必要があります。 BizTalk Server 展開アカウントは、この目的のため、このトピックで参照されます。  
  
 このアクセスがドメインの配置グループのメンバーである必要があります、 **BizTalk Server 管理者**と**SSO 関連管理者**グループ。  
  
> [!NOTE]
>  インストールに使用されるアカウントは、サーバーは異なる Active Directory フォレストに属している場合は、SSO コンポーネントを構成することはできません。 BizTalk Server 展開アカウントがいない場合は、SSO 構成用ローカル管理者アカウントを使用します。 この方法論では、別の資格情報を使用してリソースにログオンする必要があるなどのインストール中に、その他の問題を作成できます。  
  
## <a name="biztalk-server-support-accounts"></a>BizTalk Server サポート アカウントします。  
 サポートしている個人[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーションをシステムのローカル管理者である必要があります。 BizTalk サポート アカウントは、この目的のため、このトピックで参照されます。  
  
 このアクセスが、ドメインのサポート グループのメンバーである必要があります、 **BizTalk Server 管理者**グループ。  
  
## <a name="sql-server-service-accounts"></a>SQL Server サービス アカウント  
 サービスの実行、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスは、インストール、開発、および展開アカウントと同じ Active Directory ドメインに属している必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンポーネント。  
  
- 使用**SQLAdmin**管理機能 (対話型ログオン)。  
  
- 使用**SQLService**サービス (対話型ログオンなし) を管理します。  
  
- 使用**SQLAccess**外部データベースにアクセスします。  
  
- SQLAdmin にローカルの Administrators グループのメンバーである必要があります、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]システム。  
  
- SQLService でローカルの Administrators グループのメンバーである必要があります、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]システムと付与する必要がある、**サービスとしてログオン**ユーザー権限。  
  
- SQLAccess には、リモート データベース サーバーに対する適切な権限が必要があります。  
  
  **SQL アカウント:**  
  
|**ユーザー名**|**[First Name]**|**[Last Name]**|**[名前]**|  
|-------------------|--------------------|-------------------|-------------------|  
|SQLService |SQL|SQLService |SQL サービス アカウント|  
|SQLAdmin|管理|SQLService |SQL 管理者アカウント|  
|Sqlaccess に|アクセス|SQLService |SQL アクセス アカウント|  
  
 社内基準に従ってアカウントのパスワードを設定します。  
  
> [!IMPORTANT]
>  実行するコンピューターで[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]、SQLService アカウントと資格情報を使用する SQL Server および SQLServerAgent サービス起動時のパラメーターを変更します。  
> 
> [!NOTE]
>  ユーザー名フィールドはサンプルです。その他の Active Directory アカウントと競合するを回避するために名前を変更する必要があります。  
  
## <a name="windows-sharepoint-services-account"></a>Windows SharePoint Services アカウント  
 インストールする前に、Windows SharePoint Services アカウントを作成する必要があります[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]します。  
  
 推奨事項とに関する注意事項、[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]アカウント。  
  
- SharePoint Admin アカウント (SPAdmin) を使用して、管理機能、SharePoint Timer Service とそのすべての[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]アクセスします。  
  
- SPAdmin はサイト所有者であり、電子メール エイリアスは必要があります。  
  
- SPAdmin は、ローカルのローカルの administrators グループのメンバーである必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューター (Windows SharePoint Services のセットアップは、これを行います)。  
  
- SPAdmin は、セキュリティ管理者とデータベース作成者ロールをいる必要があります、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]コンピューター (Windows SharePoint Services のセットアップは、これを行います)。  
  
  **Sharepoint アカウント:**  
  
|**ユーザー名**|**[First Name]**|**[Last Name]**|**[名前]**|  
|-------------------|--------------------|-------------------|-------------------|  
|SPAdmin|管理|SPService|SharePoint Admin アカウント|  
  
 社内基準に従ってアカウントのパスワードを設定し、構成手順中にこれらのパスワードを取得できるようにします。 参照してください、**パスワード**に関する問題については、このトピックのセクションで生成されたパスワード。  
  
> [!NOTE]
>  このユーザー名フィールドはサンプルです。その他の AD アカウントを保護するには、この名前を変更する必要があります。  
> 
> [!IMPORTANT]
>  Windows SharePoint Services を実行しているコンピューターにインストールした後[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、SharePoint Timer Service の起動時のパラメーターが SPAdmin アカウントと資格情報を使用していることを確認します。  
  
## <a name="biztalk-groups-and-users"></a>BizTalk グループとユーザー  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] グループとユーザーは、実行する前に作成する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]構成ウィザード。 単一システムのインストールで[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ローカル グループと構成中に作成されるアカウントを使用します。 ただし、別[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ホストが展開されている場合、または[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]がインストールされている 2 つの異なるコンピューター上には、ドメイン ユーザーおよびグループ アカウントを使用する必要があります。  
  
> [!NOTE]
>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]構成ウィザードは、ドメイン アカウントを作成できません。  
  
 推奨事項と注意で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]サービスとユーザー アカウント。  
  
- 組織単位 (OU) を作成する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 すべてのアカウントとグループは、この OU に属しています。  
  
- わかりやすいもの; の完全名にします。次の表の名前には、構成時に適切なグループ/アカウント/ユーザーを選択するインストーラーが有効にする必要があります。  
  
- 名と姓は省略可能です。整合性のみに含まれています。  
  
- 差別化要因**BTService**と**BTUser**はサービス アカウント (オートマトン) と汎用/共有の人間のユーザーを指します。  
  
- ドメイン アカウントを作成し、ユーザーの ADSI スクリプトとアップ ラインの環境のグループ アカウントの作成を使用してそれらを設定します。  
  
  **BizTalk サービス アカウントします。**  
  
|**ユーザー名**|**[First Name]**|**[Last Name]**|**[名前]**|  
|-------------------|--------------------|-------------------|-------------------|  
|BTService|BTS|BTService|BizTalk サービス アカウント|  
|BTServiceHost|ホスト|BTService|BizTalk ホスト インスタンス アカウント|  
|BTServiceHostIso|HostIso|BTService|BizTalk 分離ホスト インスタンス アカウント|  
|SSOService|SSO|BTService|エンタープライズ シングル サインオン サービス|  
|BTServiceREU|REU|BTService|ルール エンジン更新サービス|  
  
 会社と (たとえば、devBTService、alphabtservice など) 環境の基準に従ってユーザー名を設定します。 社内基準に従ってアカウントのパスワードを設定し、構成手順については、それらを取得できるようにします。 参照してください、**開発用のパスワードに関する考慮事項**に関する問題については、このトピックのセクションで生成されたパスワード。  
  
 インストーラーは、サービス アカウントが、非常に細分化された、によって作成されたサービスにほぼ一対一のマッピングに注意してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 粒度は、企業の IT セキュリティを追跡したり、必要に応じてアクセスを制限したりできます。 粒度を使用することをお勧めしますが、エンタープライズ環境で必要があるかを判断するには、システム デザイナーや企業のセキュリティ担当者の責任です。  
  
 前のグループのサービス アカウントは自動アクセス専用に、ユーザーが対話型ログオンの対象としています。  
  
#### <a name="to-set-the-appropriate-account-options"></a>適切なアカウント オプションを設定するには  
  
1. **Active Directory ユーザーとコンピューター**コンソールで、ドメインを展開する をクリックして展開し、**ユーザー**コンテナー。  
  
2. アカウントを右クリックし、**プロパティ**を表示する、**プロパティ**アカウントのダイアログ ボックス。  
  
3. をクリックして、**アカウント**のタブ、**プロパティ** ダイアログ ボックス。  
  
4. 次のオプションを確認する をクリックします。  
  
   -   **ユーザーがパスワードを変更できない**(エンタープライズ セキュリティのバッチは、パスワードの変更)。  
  
   -   **パスワードの有効期限が切れることはありません。**  
  
5. をクリックして、**ログに**を表示するボタン、**ログオンできるワークステーション** ダイアログ ボックス。  
  
6. オプションをクリックして **、次のコンピューター**を実行しているコンピューターをそれぞれ追加[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]、順にクリックします **[ok]** します。  
  
7. をクリックして、**リモート_コントロール**のタブ、**プロパティ**ダイアログ ボックスをクリックしてオプションをオフに**リモート_コントロールを有効にする**。  
  
8. をクリックして、**ターミナル サービスのプロファイル**のタブ、**プロパティ** ダイアログ ボックス。  
  
9. オプションをオンにする をクリックします。**すべてのターミナル サーバーにログオンするには、このユーザー権限の拒否**します。  
  
10. をクリックして**OK**を閉じる、**プロパティ**アカウントのダイアログ ボックス。  
  
11. サービス アカウントごとに手順 3 ~ 10 を繰り返します。  
  
    **BizTalk ユーザー アカウントします。**  
  
|**ユーザー名**|**[First Name]**|**[Last Name]**|**[名前]**|  
|-------------------|--------------------|-------------------|-------------------|  
|BTUserAdmin|管理|BTUser|BizTalk 管理ユーザー アカウント|  
|BTUserDeploy|配置|BTUser|BizTalk 展開ユーザー アカウント|  
|BTUserHostInstance|しています|BTUser|BizTalk ホスト インスタンス アカウント|  
|BTUserHostIsolated|IsolatedlHost|BTUser|BizTalk 分離ホスト インスタンス アカウント|  
|BTUserInstall|インストール|BTUser|BizTalk インストール ユーザー アカウント|  
|BTUserSupport|サポート|BTUser|BizTalk サポート アクセス アカウント|  
  
#### <a name="to-set-the-appropriate-account-options-follow-these-steps"></a>オプションを適切なアカウントを設定するには、以下の手順  
  
1. **Active Directory ユーザーとコンピューター**コンソールをクリックして、ドメインを展開しをクリックして展開、**ユーザー**コンテナー。  
  
2. アカウントを右クリックし、**プロパティ**を表示する、**プロパティ**アカウントのダイアログ ボックス。  
  
3. をクリックして、**アカウント**のタブ、**プロパティ** ダイアログ ボックス。  
  
4. 次のオプションを確認する をクリックします。  
  
   -   **ユーザーがパスワードを変更できない**(エンタープライズ セキュリティのバッチは、パスワードの変更)。  
  
   -   **パスワードの有効期限が切れることはありません。**  
  
5. をクリックして、**ログに**を表示するボタン、**ログオンできるワークステーション** ダイアログ ボックス。  
  
6. オプションをクリックして **、次のコンピューター**を実行しているコンピューターをそれぞれ追加[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]、順にクリックします **[ok]** します。  
  
7. をクリックして、**リモート_コントロール**のタブ、**プロパティ** ダイアログ ボックスとオプションをオンにする をクリック**リモート_コントロールを有効にする**。  
  
8. をクリックして、**ターミナル サービスのプロファイル**のタブ、**プロパティ** ダイアログ ボックス。  
  
9. オプションをオフにする をクリックします。**すべてのターミナル サーバーにログオンするには、このユーザー権限の拒否**します。  
  
10. をクリックして**OK**を閉じる、**プロパティ**アカウントのダイアログ ボックス。  
  
11. ユーザー アカウントごとに手順 3 ~ 10 を繰り返します。  
  
    > [!NOTE]
    >  提供されるロールは、実際のユーザーに割り当てられている場合は、これらのアカウントを無効にできます。 リリース 1 と 2 つのリリースの初期の段階で開発、アルファ テスト、およびベータ版のテスト環境でこれらのアカウントを使用すると見なされます。  
  
    **BizTalk グループ アカウント**  
  
|**グループ名**|**グループの種類**|**メンバー**|  
|--------------------|--------------------|-----------------|  
|BizTalk Application Users|グローバルまたはユニバーサル|-   BTServiceHost<br />-   BTUserHostInstance|  
|BizTalk 開発ユーザー|グローバルまたはユニバーサル|(開発ユーザーのローカル ドメイン アカウント)**に注意してください。** ベスト プラクティスとして有効にしないアップラインの環境で BizTalk 開発ユーザー グループ。|  
|BizTalk 展開ユーザー|グローバルまたはユニバーサル|(展開ユーザーのローカル ドメイン アカウント)|  
|BizTalk ホスト ユーザー|グローバルまたはユニバーサル|BTUserHostInstance|  
|BizTalk 分離ホスト ユーザー|グローバルまたはユニバーサル|-   BTServiceHostIso<br />-   BTUserHostInstance|  
|BizTalk Server 管理者|グローバルまたはユニバーサル|-BTUserAdmin<br />-BTUserInstall<br />-BizTalk 開発ユーザー<br />BizTalk 展開ユーザー|  
|BizTalk サポート ユーザー|グローバルまたはユニバーサル|BTUserSupport (サポート ユーザーのローカル ドメイン アカウント)|  
|SSO 管理者|グローバルまたはユニバーサル|-SSOService<br />-BTUserInstall<br />ローカル管理者|  
|SSO 関連管理者|グローバルまたはユニバーサル|-BizTalk 開発ユーザー<br />BizTalk 展開ユーザー<br />-   BTServiceHostIso<br />-   \<コンソール ユーザー\>|  
|Windows SharePoint Services 管理者|グローバルまたはユニバーサル|-SPAdmin<br />-BTUserInstall<br />-   BTUserDeploy<br />-BizTalk 開発ユーザー<br />BizTalk 展開ユーザー|  
  
 推奨事項とドメイン グループに関する注意事項:  
  
- グループを作成してインストールする前にメンバーを追加する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  
  
- ドメイン グループは、グローバルまたはユニバーサル グループにすることができます。  
  
- 使用 *\<DomainName\>\\< ユーザー名\>* 構成ウィザードでドメイン アカウント情報を指定する場合。  
  
- グループおよびユーザー/サービス アカウントをドメインに属している必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューターが属している (構成ウィザードは、このフラグをチェックし、アカウントや他のドメイン アカウントを含むグループが表示されない)。  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] すべてのクラスタ リングのシナリオのドメイン アカウントが必要です。  
  
- インストールするときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンソールのユーザーは、次のグループのメンバーである必要があります。  
  
  - BizTalk Server 管理者  
  
  - SSO 管理者 (マスタ シークレット サーバーを構成する) の場合のみ  
  
  - Windows 管理者  
  
  - [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 管理者  
  
  - OLAP 管理者  
  
    BTUserInstall アカウントは、インストールと構成に使用する必要があり、構成が完了したら、無効にする必要があります。  
  
- 開発者が必要、BizTalk Server 管理者グループに属している、セクションでは上記で説明したメッセージ イベントおよびサービス インスタンス追跡でオーケストレーションをデバッガーにアタッチできるように、 **BizTalk 開発アカウント**.  
  
## <a name="local-administrator-accounts"></a>ローカル管理者アカウント  
 確認またはのローカル Administrators グループに次のアカウントとグループを追加、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]コンピューター。  
  
- Domain\BTUserInstall (構成が完了したら無効にする)  
  
- Domain\BTUserDeploy (展開が完了すると、実稼働環境で無効)  
  
- Domain\SPAdmin  
  
- Domain\SQLAdmin  
  
- Domain\SQLService  
  
- ドメイン \biztalk 開発ユーザーが (アップ ラインの環境で省略)  
  
- ドメイン \biztalk 展開ユーザーが (開発環境での省略)  
  
  確認またはのローカル Administrators グループに次のアカウントとグループを追加、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンピューター。  
  
- Domain\BTUserInstall (構成が完了したら無効にする)  
  
- Domain\BTUserDeploy (展開が完了すると、実稼働環境で無効)  
  
- Domain\BTUserSupport  
  
- Domain\SPAdmin  
  
- ドメイン \biztalk 開発ユーザー (アップラインの環境で)  
  
- ドメイン \biztalk 展開ユーザーが (開発環境での省略)  
  
## <a name="sql-server-administrator-accounts"></a>SQL Server の管理者アカウント  
 セットアップ プログラムでは、インストーラーと割り当ての SQL ロールからユーザーとグループへの入力を受け入れます。  
  
- 中に[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]セットアップ、SPAdmin アカウント権限が与えられますセキュリティ管理者とデータベース作成者で、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]コンピューター。 SPAdmin アカウントがローカルの Administrators グループのメンバーである場合、これらの権利を削除できます。  
  
## <a name="e-mail-account"></a>電子メール アカウント  
 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 特定のシステム イベントに基づいてメールを送信します。 セットアップは、構成プロセス中に、電子メール アドレスを求めます。 この目的のための電子メール エイリアスを作成し、セットアップと単体テスト中に、エイリアスを監視します。 運用環境でこのアカウントはシステムの監視はシステム管理者によってアクセス可能にする必要があります。  
  
 によって使用される電子メール アカウント[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]は、 **WSS 管理者の電子メール**アカウント。  
  
## <a name="password-considerations-for-development"></a>開発用のパスワードに関する考慮事項  
 開発およびテスト環境では、アカウントのパスワードは標準で設定できるし、する再頒布可能。 インストーラーの標準が異なります。このトピックでは、先頭の大文字、小文字の省略形 (サービスまたはユーザー) のアカウントの残りの部分で後に、サービス コンポーネントを続けたテンプレートを使用します。 、サービス アカウントは、このトピックでは、このトピックでは 'User' を使用してユーザー アカウントを 'Serv' を使用します。  
  
 例 :  
  
- Windows SharePoint Services (SharePoint) サービスと管理者アカウント (SPAdmin) のパスワード:' SPServ'。  
  
- BizTalk サービス アカウントのパスワード:' BTServ'。  
  
- BizTalk ユーザー アカウントのパスワード:' BTUser'。  
  
  一部の IT 環境では、非英数字や数字の文字を含むパスワードが必要です。 このシナリオでは、"s"とに"at"記号のドル記号 ($) を置き換えることができます (@) の"a"です。 シンボルはサンプルです。半パブリックなパスワードでアカウントを共有するのに最適なパターンを開発します。  
  
  開発環境で使用されている再頒布可能パッケージのパスワードをサンプルは次のとおりです。  
  
- BT erv99 BizTalk サービス アカウントします。  
  
- BTU er99 BizTalk ユーザー アカウントします。  
  
- SP erv99 WSS サービス アカウント (SPAdmin)  
  
- SQL erv99 SQL サービス/アクセス/admin アカウント  
  
> [!NOTE]
>  これらの推奨事項は、開発および共有環境でのみとをお勧めしますおよびありません企業のパスワード ポリシーの使用を防止します。 ネットワーク管理者のパスワード要件を参照してください。  
  
> [!NOTE]
>  企業のパスワード ポリシーには、生成されたパスワードが含まれている場合は、いくつかの記号と記号の組み合わせのどちらが XML に特殊な用途の文字であることを推奨します。 これらの文字を不適切に使用すると、構成 XML ファイルが、構成プロセス中に開かれているできなくなります。 これらのシンボルを含める"&"、"\<「,」\>"、1 つに、二重引用符、および他のユーザーを含めることができます。 ファイル ベースの構成を実行する前に、構成 XML ファイルをテストします。 これをテストする確実に適切な XML の書式設定を Internet Explorer (または XML エディター) でドキュメントを開くことで、生成されたパスワードを埋め込んだとします。  
  
 アップラインの環境でセキュリティで保護されたパスワードの展開の詳細については (テストするメソッドを含む、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]構成ファイル) を参照してください[BizTalk Server 2013 および 2013 R2 の構成の概要](http://msdn.microsoft.com/library/aa58c43f-8f0e-4a5c-89b9-db7b8a852a72)します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server のアクセス許可のトラブルシューティング](../core/troubleshooting-biztalk-server-permissions.md)