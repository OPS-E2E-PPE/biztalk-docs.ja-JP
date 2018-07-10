---
title: 基本またはカスタムの構成を使用して構成する |Microsoft Docs
description: 手順を BizTalk Server の基本またはカスタム構成を行い、各構成で発生する内容について説明します。
ms.custom: ''
ms.date: 08/14/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 861a1237-d77a-42db-b563-d83f7930add6
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a74d7e03582e9da54d0fec25eeeb6edb409e328a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983691"
---
# <a name="configure-biztalk-server"></a>BizTalk Server の構成
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、基本構成またはカスタム構成を使用して構成できます。

## <a name="basic-configuration-vs-custom-configuration"></a>基本構成と[ユーザー構成]

* 構成にドメイン グループを使用する場合は、カスタム構成を行います。
* 構成で既定のグループ名の代わりにカスタム グループ名を使用する場合は、カスタム構成を行います。
* 構成で既定のデータベース名の代わりにカスタム データベース名を使用する場合は、カスタム構成を行います。
* [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] と SQL Server が別のコンピューターにインストールされている場合は、ドメイン グループが必要です。 そのため、カスタム構成を行う必要があります。
* BAM 分析は、名前付きインスタンスの基本的な構成を使用して SQL Server を構成することはできません。 名前付きインスタンスを使用している場合に BAM 分析を構成するには、カスタム構成を行います。
* 基本構成は、1 台のサーバーで実行される [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] と SQL Server の完全なインストールをセットアップするユーザーに推奨されます。
* 基本構成では、既定の名前を使用して自動的にローカル グループとデータベースを作成するため、短時間で構成することができます。


## <a name="before-you-begin"></a>アンインストールの準備
* [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、SQL Server の既定のインスタンスと名前付きインスタンスを使用して構成できます。 
* ログオンに使用するアカウントは、ローカルの管理者グループに属している必要があります。また SQL Server に対するシステム管理者 (SA) の権限が必要です。
* ドメイン グループを使用する場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を構成する*前*にそのドメイン グループが存在している必要があります。
* [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] によって生成され、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 構成で一覧表示される既定のアカウントは、ローカル グループに属しています。 マルチサーバー環境では、ローカル グループをドメイン グループに置き換える必要があります。
* BAM Analysis Services を構成する場合、ログオンに使用するアカウントは、OLAP コンピューターの OLAP 管理者グループのメンバーに属している必要があります。


## <a name="basic-configuration"></a>基本構成

1. スタート メニューの **BizTalk Server 構成** を右クリックして選択し、**管理者として実行** を選択します。 これにより構成ウィザードが開きます。 
2. 次のオプションを選択します。 
    1. **[基本構成]** を選択します。
    2. **[データベース サーバー名]** の既定は、自動的にローカル コンピューター名になります。   
    3. BizTalk Server のサービスを実行するアカウントの **[ユーザー名]** と **[パスワード]** を入力します。 ベスト プラクティスとして、一意のアカウントを作成することをお勧めします。 個人ユーザー名は使用しないでください。  
        ![bts2016BasicConfig](../install-and-config-guides/media/bts2016basicconfig.gif)  
    このコンピューターの管理資格を持つユーザー名を入力すると、警告が表示されます。 これは正常です。 **[OK]** をクリックし、続行します。

3. **[構成]** を選択します。
4. 構成の詳細を確認し、**[次へ]** を選択します。
5. 構成ウィザードが完了したら、**[完了]** を選択します。

構成ログ ファイルが `
C:\Users\username\AppData\Local\Temp\ConfigLog(01-12-2017 0h37m59s).log` などの一時フォルダーに生成されます。

基本構成を行うと、次のようになります。

- すべてのデータベース名が [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] によって自動的に生成されます。
- 該当するすべてのデータベース ログオン情報が、入力したアカウントで実行されます。 
- すべての BizTalk Services が [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] によって自動的に生成されます。
- すべての BizTalk Services が、入力したアカウントで実行されます。 構成処理によって、SQL Server のサーバーとオブジェクトに対して必要となるセキュリティ権限がこのアカウントに付与されます。
- すべての機能は、コンピューターにインストールした必要なソフトウェアに基づいて構成されます。
- グループは、既定のグループ名を使用してコンピューターのローカルに自動的に作成されます。
- インターネット インフォメーション サービス (IIS) の既定の Web サイトは、IIS を必要とするすべての機能に対して使用されます。

## <a name="custom-configuration"></a>カスタム構成

1. スタート] メニューの **[BizTalk Server 構成]** を右クリックして選択し、**[管理者として実行]** を選択します。 これにより構成ウィザードが開きます。
2. **[カスタム構成]**、**[構成]** の順に選択します。

### <a name="configure-enterprise-single-sign-on-sso"></a>Enterprise Single Sign-on (SSO) の構成

* SSO が構成されると、BizTalk Server の構成を使用して再構成できません。 SSO を再構成するには、BizTalk Server 管理を使用します。
* ローカル アカウントを使用して SSO Windows アカウントを構成する場合、アカウント名のみを入力します。 コンピューター名は入力しないでください。
* ローカルの SQL Server の名前付きのインスタンスをデータ ストアとして使用する場合、`LocalMachineName\InstanceName` を使用します。 `LocalMachineName\InstanceName, PortNumber` は使用しないでください。 

1. **[Enterprise SSO]** を選択します。
2. 次の内容を構成します。


   |                     項目                      |                                                                                                                                                                                                                                                                                                                           目的                                                                                                                                                                                                                                                                                                                            |
   |---------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | [このコンピュータでエンタープライズ シングル サインオンを有効にする] |                                                                                                                                                                                                                                                                                                            SSO 設定を、このサーバーに構成します。                                                                                                                                                                                                                                                                                                             |
   |              [新しい SSO システムを作成]              | これが構成する最初の SSO サーバーである場合、このオプションを選択します。 これにより SSO データベースが作成および構成され、マスター シークレット (暗号化済みのセキュリティ キー) が作成され、SSO が使用するサービスがインストールされます。 このシークレット サーバーのシークレットをバックアップする必要もあります。<br/><br/>キーの詳細: <br/><ul><li>マスター シークレット サーバーは、スタンドアロン サーバーとして構成することをお勧めします。</li><li>この構成作業は、SSO 管理者が行う必要があります。</li><li>1 つの BizTalk グループに関連付けることができるマスタ シークレット サーバーは 1 台のみです。 2 台のマスタ シークレット サーバーを同じ BizTalk グループに関連付けることはできません。</li></ul> |
   |            [既存の SSO システムに参加]            |                                                                                                                          既存のグループに [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を追加する場合、このオプションを選択します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、グループ内の他の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] と、同じ SSO 構成およびデータベースを共有します。                                                                                                                          |
   |                    [データ ストア]                    |                                                                                                                                                                                                                                   SSO サーバーのサーバー名を入力します。 SSO サーバーを使用している場合は、ローカル サーバー名を選択します。 **SSODB** を既定のデータベース名として使用することも、独自のものを入力することも可能です。                                                                                                                                                                                                                                    |
   |                  [Windows サービス]                  |                                                                                                                                                                                                                                                              Enterprise Single Sign-On サービスを実行するために使用したアカウントを入力します。 SQL Server が別のコンピューターである場合、ドメイン アカウントを入力します。                                                                                                                                                                                                                                                               |
   |                 Windows アカウント                  |                                                                                                                                                                                                                                                                既定のグループ名を使用することも、独自のものを入力することも可能です。 SQL Server が別のコンピューター上にある場合は、ドメイン アカウントを入力します。                                                                                                                                                                                                                                                                |


3. **[Enterprise SSO シークレットのバックアップ]** を選択します。 このオプションは、マスター シークレットを暗号化されたバックアップ ファイルに保存します。 
4. 次の内容を構成します。  

    |項目|目的|
    | --- | --- |
    |[シークレット バックアップ パスワード] | マスター シークレットのパスワードを入力します。|
    |[パスワードの確認入力]|マスター シークレットのパスワードを再入力します。|
    |[パスワード関連語句]|入力するパスワードの関連語句を入力します。 この手順は必ず実行してください。 |
    |[バックアップ ファイルの場所]|バックアップ ファイルの名前と場所を一覧表示します。 これは、既定で \Program Files\Common Files\Enterprise Single Sign-On\ *FileName*.bak に格納されます。|

マスター シークレットは、**必ず**バックアップし、別の BizTalk 管理者とそのパスワードを共有するようにしてください。

### <a name="configure-groups"></a>グループの構成

* ローカルの SQL Server の名前付きのインスタンスをデータ ストアとして使用する場合、`LocalMachineName\InstanceName` を使用します。 `LocalMachineName\InstanceName, PortNumber` は使用しないでください。

1. **[グループ]** を選択します。
2. 次の内容を構成します。


   |                       項目                        |                                                                                                                                         目的                                                                                                                                          |
   |-------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |     [このコンピューターで BizTalk Server グループを有効にする]      |                                                                                                 このサーバーに新しい BizTalk グループを作成するか、既存のグループに参加するには、このオプションを選択します。                                                                                                 |
   |              [新しい BizTalk グループを作成します]               |                                       これがグループの最初の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] である場合、このオプションを選択します。 このオプションを使用すると、データベースを作成し、グループを追加できます。                                       |
   |            [既存の BizTalk グループに参加します]             |                                                                    この [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を既存のグループに追加する場合は、このオプションを選択します。                                                                     |
   | [追跡集計用の分析データベースを作成する] |                                                                                  SQL Server Analysis Services をインストールし、稼働状況を監視する OLAP キューブを追跡および格納する場合、このオプションを選択します。                                                                                  |
   |                      [データ ストア]                      | BizTalk データベースをホストするサーバー名を入力します。 このサーバーに BizTalk と SQL の両方がインストールされている場合は、ローカル サーバー名を入力します。 SQL Server が別のコンピューター上にある場合は、SQL Server 名を入力します。<br/><br/>既定のデータベース名を使用することも、独自のものを入力することも可能です。 |
   |             [BizTalk 管理ロール]              |                                                                              既定のグループ名を使用することも、独自のものを入力することも可能です。 SQL Server が別のコンピューター上にある場合は、ドメイン アカウントを入力します。                                                                              |

### <a name="configure-the-biztalk-runtime"></a>BizTalk ランタイムの構成

* ランタイムは一度構成すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 構成を使用して再構成はできません。 ランタイムを再構成するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理を使用します。
* グループに作成する最初のホストは、インプロセス ホストとホスト インスタンスである必要があります。
* 同じグループの複数の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] にランタイムを構成した場合、同じサービス アカウントを信頼されているホスト アプリケーションと信頼されていないホスト アプリケーションの両方に構成することはできません。 信頼されているアプリケーションと信頼されていないアプリケーションには、一意のアカウントを使用する必要があります。 

1. **[BizTalk ランタイム]** を選択します。
2. 次の内容を構成します。


   |                                                      項目                                                      |                                                                                                                                                                                                                                                                                                                                                                                                                 目的                                                                                                                                                                                                                                                                                                                                                                                                                  |
   |--------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | [[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ランタイム コンポーネントを登録する] |                                                                                                                                                                                                                                                                                                                                            この [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] にホストとホスト インスタンスを作成するには、このオプションを選択します。                                                                                                                                                                                                                                                                                                                                            |
   |                                        インプロセス ホストとインスタンスを作成する                                         | このコンピューターに、BizTalkServerApplication ホストとインスタンスを作成します。<br/><br/>その他のオプション: <ul><li>**信頼済み**: メッセージをメッセージ ボックス データベースに送信する際に、送信者の資格情報 (SSID やパーティ ID) を渡します。 この操作は、サーバー間の信頼関係を作成することと同じです。 多くのホストやインスタンスは信頼されていません。</li><li>**32 ビットのみ**: 32 ビット プロセスで実行できるのは一部のアダプターのみで、多くは 64 ビットに対応しています。 この設定は、BizTalk の構成後に BizTalk 管理で有効または無効にできます。 そのため、これについてあまり注意しすぎる必要はありません。</li><li>**ホスト名**: 既定値は BizTalkServerApplication です。 BizTalk 管理で新しいホストとインスタンスを作成する場合、TrackingHost または ReceivingHost など具体的な名前を付けられます。 そのため、これはそのままにしておきます。</li></ul> |
   |                                         分離ホストとインスタンスを作成する                                          |                                                                         分離ホストは IIS 内で実行されます。 多くの環境では、既定値を使用することをお勧めします。<br/><br/>その他のオプション: <ul><li>**信頼済み**: メッセージをメッセージ ボックス データベースに送信する際に、送信者の資格情報 (SSID やパーティ ID) を渡します。 この操作は、サーバー間の信頼関係を作成することと同じです。 多くのホストやインスタンスは信頼されていません。</li><li>**32 ビットのみ**: 32 ビット プロセスで実行できるのは一部のアダプターのみで、多くは 64 ビットに対応しています。 この設定は、BizTalk の構成後に BizTalk 管理で有効または無効にできます。</li><li>**分離ホスト名**: 既定値は BizTalkServerIsolatedHost です。 これはそのままにしておきます。 </li></ul>                                                                          |
   |                                                  [Windows サービス]                                                   |                                                                                                                                                                                                                                                                                                                                                             ホスト インスタンスを実行するために使用したアカウントを入力します。 SQL Server が別のコンピューター上にある場合は、ドメイン アカウントを入力します。                                                                                                                                                                                                                                                                                                                                                             |
   |                                                   [Windows グループ]                                                   |                                                                                                                                                                                                                                                                                                                                                      既定のグループ名を使用することも、独自のものを入力することも可能です。 SQL Server が別のコンピューター上にある場合は、ドメイン アカウントを入力します。                                                                                                                                                                                                                                                                                                                                                      |

### <a name="configure-business-rules-engine-bre"></a>ビジネス ルール エンジン (BRE) の構成

BRE を使用しない場合、この手順は省略してください。

- ビジネス ルール エンジンを構成する前に、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] グループを構成することをお勧めします。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] グループを構成する前に BRE を構成すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 構成によってグループ関連の管理ロールがルール エンジン データベースに追加されません。

1. **[ビジネス ルール エンジン]** を選択します。
2. 次の内容を構成します。


   |                   項目                    |                                                                                                                                       目的                                                                                                                                        |
   |-----------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | [このコンピューターでビジネス ルール エンジンを有効にする] |                                                                           この [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で BRE を使用する場合、このオプションを選択します。                                                                           |
   |                  [データ ストア]                  | ルール データベースをホストするサーバー名を入力します。 このサーバーに BizTalk と SQL の両方がインストールされている場合は、ローカル サーバー名を入力します。 SQL Server が別のコンピューター上にある場合は、SQL Server 名を入力します。<br/><br/>既定のデータベース名を使用することも、独自のものを入力することも可能です。 |
   |                [Windows サービス]                |                                                                                 ルール更新サービスを実行するために使用したアカウントを入力します。 SQL Server が別のコンピューターである場合、ドメイン アカウントを入力します。                                                                                 |

### <a name="configure-bam-tools"></a>BAM ツールの構成

BAM ツールを使用しない場合、この手順は省略してください。

ビジネス アクティビティ監視ツールには、次が含まれます。

- Excel 用の BAM アドイン
- BAM マネージャー
- BAM ポータル


- BAM ツールを構成するには、SQL Server の特定の管理機能が必要であり、統合サービスがインストールされているコンピューターから実行する必要があります。
- BAM ツールは、複数の BizTalk グループによって使用される場合があります。 BAM ツールの構成を解除すると、BizTalk グループへの接続は削除されます。 ただし、BAM プライマリ インポート テーブルをポイントするその他の BizTalk グループはこの BAM SQL Server インフラストラクチャを使用し続けることができます。
- [ビジネス アクティビティの監視 - ツール] ページを使用すると、BAM データベースを実行時に再構成できます。 たとえば、既存の構成を削除することなく BAM データベースを再構成できます。 BAM データベースを再構成すると、既に展開されている OLAP ビューや、すべての警告が削除されます。 新しく構成したデータベースに既存のビューや警告を残しておきたい場合は、次のいずれかの操作を実行します。  
    - 再構成前に警告やビューの展開を解除し、再構成後に再展開します。 アーカイブされたデータはビューには残りません。
    - BAM 警告を使用していない場合は、再構成する前にデータベースをバックアップしてください。 再構成後に、新しく構成された場所にデータベースを復元します。
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースを統合する場合、BAM アーカイブおよび BAM 分析データベースを除外する必要があります。


1. **[BAM ツール]** を選択します。
2. 次の内容を構成します。

    |項目|目的|
    | --- | --- |
    |ビジネス アクティビティの監視ツールを有効にする | このコンピューターで BAM ツールを有効にし、インストールします。 |
    | BAM 集計用に Analysis Services を有効にする | BAM 警告の追跡情報が得られます。|
    |[データ ストア]| BAM データベースをホストするサーバー名を入力します。 このサーバーに BizTalk と SQL の両方がインストールされている場合は、ローカル サーバー名を入力します。 SQL Server が別のコンピューター上にある場合は、SQL Server 名を入力します。<br/><br/>既定のデータベース名を使用することも、独自のものを入力することも可能です。|
    |この Biztalk グループのビジネス アクティビティの監視ツールを削除する | BizTalk グループから BAM ツールをアンインストールおよび削除します。 |

   ### <a name="configure-bam-alerts"></a>BAM 警告の構成 

BAM 警告を使用するには、BAM ツールを有効にする必要があります。

1. **[BAM 警告]** を選択します。
2. 次の内容を構成します。

    |項目|目的|
    | --- | --- |
    | [BAM 警告を有効にする] | BAM 警告を使用する場合は、このオプションをオンにします。 <br/><br/>BAM 警告を使用するには、SQL Database メールが事前に構成されている必要があることに注意してください。 |
    | [Windows サービス] | BAM 警告サービスを実行するために使用したアカウントを入力します。 SQL Server が別のコンピューターである場合、ドメイン アカウントを入力します。 |
    | BAM 警告 SMTP サーバー| SQL Database メールを構成した SMTP サーバーの名前を入力します。 |
    | BAM 警告ファイルの場所| BAM 警告を格納するネットワーク共有を入力します。 <br/><br/>**注** <br/>BAM 警告をファイルに格納できるようにするには、この共有を手動で作成する必要があります。|
    | 警告データベース用 SQL Server | 警告データベースをホストする SQL サーバー名を入力します。<br/><br/>**注** <br/>警告データベースに使用する NS SQL Server の指定時には、IPv6 アドレスを使用できません。 コンピュータ名で指定すると、DNS の変換機能により検索が実行されます。|
    |警告データベース名のプレフィックス| 警告データベースに使用するプレフィックスを入力します。|  

### <a name="configure-the-bam-portal"></a>BAM ポータルの構成

1. **[BAM ポータル]** を選択します。
2. 次の内容を構成します。

    |項目|目的|
    | --- | --- |
    |[BAM ポータルの有効化] | BAM ポータルを使用する場合、このオプションをオンにします。 | 
    |[Web サービス アカウント] | IIS サービスを実行するために使用したアカウントを入力します。 SQL Server が別のコンピューター上にある場合は、ドメイン アカウントを入力します。|
    |Windows グループ | 既定のグループ名を使用することも、独自のものを入力することも可能です。 SQL Server が別のコンピューターである場合、ドメイン アカウントを入力します。|
    |BAM ポータル Web サイト|BAM ポータルをホストするために使用する Web サイトを選択します。 一部の環境では、構成されている Web サイトは既定の Web サイトのみです。 |

### <a name="configure-biztalk-edias2-runtime"></a>BizTalk EDI/AS2 ランタイムの構成 

* Enterprise SSO、グループ、および BizTalk ランタイムは、BizTalk EDI/AS2 ランタイムの構成前に構成する必要があります。 
* BAM ツールは EDI/AS2 ランタイム状態レポート機能の構成前に有効にする必要があります。
* EDI のみ構成する場合、BAM は必要ありません。

1. **[BizTalk EDI/AS2 ランタイム]** を選択します。
2. 次の内容を構成します。

    |項目|目的|
    | --- | --- |
    |このコンピューターで BizTalk EDI/AS2 ランタイムを有効にする| 企業間取引のメッセージングに X12、EDIFACT または AS2 プロトコルを使用する場合、このオプションを選択します。 |
    |この BizTalk グループの BizTalk EDI を有効にする | X12 または EDIFACT を使用する場合に選択します。 |
    | この BizTalk グループの BizTalk AS2 を有効にする | AS2 を使用する場合に選択します。 |
    | この BizTalk グループの BizTalk EDI/AS2 ランタイム状態レポートを有効にする | EDI インターチェンジと確認の状態を提供するレポートをユーザーに対して有効にします。 |
    |この BizTalk グループから BizTalk EDI、AS2、および状態レポート機能を削除します。 | グループからのレポート機能をアンインストールおよび削除します。 |

### <a name="configure-windows-sharepoint-services-web-service---biztalk-server-2013-and-r2-only"></a>Windows SharePoint Services Web サービスの構成 - BizTalk Server 2013 および R2 のみ 

> [!IMPORTANT] 
> このセクションは、BizTalk Server 2013 R2 および BizTalk Server 2013 にのみ該当します。 BizTalk Server 2013 R2 または BizTalk Server 2013 を使用していない場合、この手順は省略してください。

* SharePoint Services Web サービス (SSOM) は、BizTalk Server 2016 以降削除され、BizTalk Server 2013 R2 では非推奨となっています。 これは、SharePoint Services アダプター (CSOM) に置き換わっています。 BizTalk の構成には CSOM オプションは表示されません。 CSOM オプションは、ファイル アダプターや HTTP アダプターが自動的にインストールされるのと同様に、BizTalk と共に自動的にインストールされます。

1. **[Windows SharePoint Services アダプター]** を選択します。
2. 次の内容を構成します。

    |項目|目的|
    | --- | --- |
    | このコンピューターで Windows SharePoint Services アダプターを有効にする | 選択すると、SharePoint Services Web サービスがインストールされます。 IIS Web サービスが SharePoint Services コンピューターにインストールされます。このコンピューターは、BizTalk Server のコンピューターと同じでも別でもかまいません。 多くの環境で BizTalk Server と SharePoint Services は別のコンピューターにあります。|
    |[Windows グループ]|既定のグループ名を使用することも、独自のものを入力することも可能です。 |
    |[Windows SharePoint Services アダプタの Web サイト]|Windows SharePoint Service アダプター Web サービスをホストする Web サイトを選択します。|


### <a name="apply-your-configuration"></a>構成の適用

**[構成の適用]** を選択し、構成を続行します。 

1. **[概要]** で、選択したコンポーネントを確認して、**[次へ]** を選択します。
2. 完了したら、**[完了]** を選択します。

完了すると、構成ログ ファイルが `
C:\Users\username\AppData\Local\Temp\ConfigLog(1-12-2017 2h39m30s).log` などの一時フォルダーに生成されます。

## <a name="iis-application-pools-and-web-sites"></a>IIS アプリケーション プールおよび web サイト
構成した後[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、次のインターネット インフォメーション サービス (IIS) アプリケーション プールと仮想アプリケーションを作成することがあります。 

### <a name="application-pools"></a>アプリケーション プール  

|アプリケーション プール|既定のアプリケーション プール ID|説明|  
|----------------------|---------------------------------------|-----------------|  
|BAMAppPool|*ユーザー定義*|BAM ポータルのアプリケーション プール。|  
|BTSSharePointAdapterWSAppPool|*ユーザー定義*|Windows SharePoint Services アダプター Web サービスのアプリケーション プール。|  
|STSWebServiceAppPool|*ユーザー定義*|取引先管理ツールのアプリケーション プール。|  
|TpmWSAppPool|*ユーザー定義*|TPM 管理 Web サービスのアプリケーション プール。|  

### <a name="virtual-applications"></a>仮想アプリケーション  

|仮想アプリケーション|既定のアプリケーション プール|説明|  
|-------------------------|------------------------------|-----------------|  
|BAM|BAMAppPool|BAM ポータル コンポーネント (ページ、画像、プリコンパイル済みコード、および他のリソース) をホストする仮想アプリケーション。 この仮想アプリケーションは、BAMManagementService アプリケーションを呼び出して、BAM データベースと通信します。 **注:** BAM ポータルをブランド化するには、このアプリケーションの内容を変更することができます。|  
|BAMManagementService|BAMAppPool|BAMManagementService Web サービスをホストする仮想アプリケーション。 この Web サービスは、BAM ポータル アプリケーションで BAM プライマリ インポート テーブル (PIT) との通信に使用されます。 データベースとの通信は、構成中に作成されたレジストリに保存されている、権限を借用した資格情報を使用して行われます。 この Web サービスで公開されたメソッドは、カスタム クライアントによって、任意のユーザーのビューおよびその詳細、関連アクティビティ、およびピボットテーブル レイアウトを取得するために使用されます。 さらに、データベース内の警告の管理にも使用できます。|  
|BTSharePointAdapterWS|BTSSharePointAdapterWSAppPool|Windows SharePoint Service アダプター Web サービスをホストする仮想アプリケーション。 BizTalk Server 2013 R2 および 2013 のみに適用されます。|  


## <a name="more-configuration-topics"></a>構成に関するその他のトピック  

 [Azure VM での BizTalk Server の構成](http://msdn.microsoft.com/library/azure/jj248689.aspx)  

[BizTalk Server のクラスター構成](../install-and-config-guides/configure-biztalk-server-in-a-cluster.md)

[環境を最適化するための構成後の手順](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md)

 [BizTalk Server の安全な展開](../install-and-config-guides/securing-your-biztalk-server-deployment.md)  


