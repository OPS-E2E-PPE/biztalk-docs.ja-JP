---
title: 基本またはカスタムの構成を使用して構成する |Microsoft Docs
description: 手順を BizTalk Server の基本またはカスタム構成を行い、各構成で発生する内容について説明します。
ms.custom: ''
ms.date: 08/23/2018
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
ms.openlocfilehash: 7eba49561488669d3e14d8f3a9afb8a3fc0320ea
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400021"
---
# <a name="configure-biztalk-server"></a>BizTalk Server を構成します。
構成[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]基本的な構成またはカスタム構成を使用します。

## <a name="basic-configuration-vs-custom-configuration"></a>基本構成とします。カスタム構成

* 構成は、ドメイン グループを使用している場合は、カスタム構成を行います。
* 構成では、既定のグループ名の代わりにカスタム グループの名前を使用している場合は、カスタムの構成を行います。
* 構成では、既定のデータベース名の代わりにカスタム データベース名を使用している場合は、カスタムの構成を行います。
* 場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と SQL Server が別々 のコンピューターには、ドメイン グループが必要です。 その結果、カスタム構成の操作を行います。
* BAM 分析は、名前付きインスタンスの基本的な構成を使用して SQL Server を構成することはできません。 名前付きインスタンスを使用して、BAM 分析を構成する場合は、カスタム構成の操作を行います。
* ユーザーの完全なインストールの設定は基本的な構成が推奨[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と 1 台のサーバーで実行されている SQL Server。
* 基本的な構成は、ローカル グループを自動的に作成するため、および既定の名前を使用してデータベースに高速です。


## <a name="before-you-begin"></a>アンインストールの準備
* [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SQL Server の既定のインスタンスを使用して、名前付きインスタンスを構成できます。 
* アカウントをログオンには、ローカルの administrators グループのメンバーであるし、SQL Server のシステム管理者 (SA) 権限を持っている必要があります。
* ドメイン グループを使用する場合、ドメイン グループが存在する必要があります*する前に*構成[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。
* によって生成される既定のアカウント[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]の一覧に、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]構成は、ローカルのグループです。 マルチ サーバー環境では、ローカル グループにドメイン グループを置き換えます。
* BAM Analysis Services を構成する場合、アカウントをログオンには、OLAP コンピューターの OLAP 管理者グループのメンバーである必要があります。
* 累積的な更新プログラム (Cu) または機能パック (FPs) をインストール*後*BizTalk Server を構成します。 Cu または FPs に含まれる一部の更新プログラムを対象に構成されている成果物のみ。 構成を実行する前に Cu または FPs をインストールする場合は、Cu と FPs を再インストールし、構成した後。 これにより、すべてのコンポーネントが修正プログラムが適用され、アップグレードことを確認します。

## <a name="basic-configuration"></a>基本構成

1. スタート メニューの **BizTalk Server 構成** を右クリックして選択し、**管理者として実行** を選択します。 構成ウィザードが開きます。 
2. 次のオプションを選択します。 
    1. 選択**基本的な構成**します。
    2. **データベース サーバー名**自動的に既定値はローカル コンピューター名。   
    3. 入力、**ユーザー名**と**パスワード**BizTalk services を実行するアカウント。 ベスト プラクティスとしては、一意のアカウントを作成します。 個人ユーザー名は使用しないでください。  
        ![bts2016BasicConfig](../install-and-config-guides/media/bts2016basicconfig.gif)  
    このコンピューターの管理者資格情報でユーザー名を入力すると、警告が表示されます。 問題はありません。 選択**OK**を続行します。

3. **[構成]** を選択します。
4. 構成の詳細を確認し、選択**次**します。
5. 構成ウィザードが完了したら、選択**完了**します。

ような一時フォルダーに、構成ログ ファイルが生成されます:`
C:\Users\username\AppData\Local\Temp\ConfigLog(01-12-2017 0h37m59s).log`します。

基本的な構成を行うと、以下の処理が行われます。

- すべてのデータベース名がによって自動的に生成された[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。
- すべての該当するデータベース ログオン情報は、入力したアカウントで実行されます。 
- すべての BizTalk services はによって自動的に生成された[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。
- すべての BizTalk services は、入力したアカウントで実行します。 構成プロセスでは、このアカウントに、サーバーと SQL Server のオブジェクトに必要なセキュリティ アクセス許可が付与されます。
- すべての機能は、コンピューターにインストールされている前提条件のソフトウェアに基づいて構成されます。
- グループは、既定のグループ名を使用してコンピューターのローカルに自動的に作成されます。
- インターネット インフォメーション サービス (IIS) の既定の Web サイトは IIS を必要とするすべての機能の使用します。

## <a name="custom-configuration"></a>カスタム構成

1. スタート] メニューの **[BizTalk Server 構成]** を右クリックして選択し、**[管理者として実行]** を選択します。 構成ウィザードが開きます。
2. 選択**カスタム構成**、選び**構成**します。

### <a name="configure-enterprise-single-sign-on-sso"></a>エンタープライズ シングル サインオン (SSO) を構成します。

* SSO を構成すると、BizTalk Server 構成を使用してこれが再構成ことはできません。 SSO を再構成するには、BizTalk Server 管理コンソールを使用します。
* ローカル アカウントを使用して SSO Windows アカウントを構成する場合は、アカウント名のみを入力します。 コンピューター名を入力しないでください。
* 名前付きインスタンスのデータ ストアとして、ローカルの SQL Server を使用する場合を使用して、`LocalMachineName\InstanceName`します。 使用しない`LocalMachineName\InstanceName, PortNumber`します。 

1. 選択**Enterprise SSO**します。
2. 次を構成します。


   | プロパティ |  目的|
   |---|---|
   | このコンピューターでエンタープライズ シングル サインオンを有効にします。 | このサーバーは、SSO 設定を構成します。  |
   |  新しい SSO システムを作成します。  | 構成する最初の SSO サーバーの場合は、このオプションを選択します。 これは、コマンドで、作成、SSO データベースを構成しますとマスター シークレット (暗号化されたセキュリティ キー) を作成します、SSO によって使用されるサービスをインストールします。 また、このシークレット サーバーのシークレットをバックアップする必要があります。<br/><br/>キーの詳細: <br/><ul><li>スタンドアロン サーバーとして、マスター シークレット サーバーを構成することをお勧めします。</li><li>この構成タスクの実行中に、SSO 管理者があります。</li><li>1 つだけのマスター シークレット サーバーは、1 つの BizTalk グループを関連付けることができます。 同じ BizTalk グループに 2 つのマスター シークレット サーバーを関連付けることはサポートされていません。</li></ul> |
   | 既存の SSO システムに参加します。 | 追加する場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]既存のグループにこのオプションを選択します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]他と同じ SSO を構成およびデータベースを共有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループ内。  |
   |  データ ストア  |   SSO サーバーのサーバー名を入力します。 SSO サーバーの場合は、ローカル サーバー名を選択します。 おくと、 **SSODB**として既定のデータベース名、または独自のものを入力します。  |
   |   Windows サービス  |  エンタープライズ シングル サインオン サービスの実行に使用するアカウントを入力します。 SQL Server が別のコンピューターにある場合は、ドメイン アカウントを入力します。   |
   |  Windows アカウント  | 既定のグループの名前を保持するか、独自のものを入力できます。 SQL Server が別のコンピューターにある場合は、ドメイン アカウントを入力します。  |


3. 選択**エンタープライズ SSO シークレットのバックアップ**します。 このオプションは、マスター シークレットを暗号化されたバックアップ ファイルに保存します。 
4. 次を構成します。  

    |プロパティ|目的|
    | --- | --- |
    |シークレット バックアップ パスワード | マスター シークレットのパスワードを入力します。|
    |[パスワードの確認入力]|マスター シークレットのパスワードを再入力します。|
    |パスワード関連語句|入力したパスワードのリマインダーを入力します。 真剣にしないと、この手順をスキップします。 |
    |バックアップ ファイルの場所|バックアップ ファイルの名前と場所を一覧表示します。 既定では、\Program Files\Common \enterprise Single sign-on \ に格納*FileName*.bak です。|

**常に**マスター シークレットをバックアップし、別の BizTalk 管理者で、パスワードを共有します。

### <a name="configure-groups"></a>グループを構成します。

* 名前付きインスタンスのデータ ストアとして、ローカルの SQL Server を使用する場合を使用して、`LocalMachineName\InstanceName`します。 使用しない`LocalMachineName\InstanceName, PortNumber`します。

1. 選択**グループ**します。
2. 次を構成します。


   |  プロパティ | 目的 |
   |---|---|
   |  このコンピューターで BizTalk Server グループを有効にします。  | このサーバー上で新しい BizTalk グループを作成するには、このオプションを選択するか、既存のグループに参加します。 |
   |  新しい BizTalk グループを作成します。 | これは、最初場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] グループで、このオプションを選択します。 このオプションを使用して、データベースを作成し、グループを追加します。 |
   | 既存の BizTalk グループを参加させる |   これに参加する場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]既存のグループにこのオプションを選択します。  |
   | 追跡集計用の分析データベースを作成します。 | SQL Server の Analysis Services をインストールするには、このオプションを選択し、追跡および稼動状況監視 OLAP キューブを格納します。  |
   | データ ストア | BizTalk データベースをホストするサーバー名を入力します。 このサーバーに BizTalk と SQL の両方がインストールされている場合は、ローカル サーバー名を入力します。 SQL Server が別のコンピューターにある場合は、SQL Server 名を入力します。<br/><br/>既定のデータベース名を保持するか、独自のものを入力できます。 |
   |   BizTalk 管理ロール |  既定のグループの名前を保持するか、独自のものを入力できます。 SQL Server が別のコンピューターにある場合は、ドメイン アカウントを入力します。   |

### <a name="configure-the-biztalk-runtime"></a>BizTalk ランタイムを構成します。

* ランタイムを構成すると、そのように再構成できないを使用して[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]構成します。 ランタイムを再構成するには、次のように使用します。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理します。
* 最初のホスト グループを作成するには、インプロセス ホストおよびホスト インスタンスがあります。
* 複数のランタイムを構成するときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と信頼されていないホスト アプリケーションに同じグループに同じサービス アカウントでは使用できません。 信頼されたアプリケーション、および信頼されていないアプリケーションの一意のアカウントを使用する必要があります。 

1. 選択**BizTalk ランタイム**します。
2. 次を構成します。


   |   プロパティ | 目的  |
   |---|---|
   | 登録、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ランタイム コンポーネント |  このホストとホスト インスタンスを作成するには、このオプションを選択[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  |
   |  インプロセス ホストとインスタンスを作成します。  | このコンピューターに、BizTalkServerApplication ホストとインスタンスを作成します。<br/><br/>追加オプション: <ul><li>**信頼された**:メッセージ ボックス データベースにメッセージを送信するときに、送信者の資格情報 (SSID やパーティ ID) を渡します。 これは、サーバー間の信頼関係の作成と同じです。 ほとんどのホストとインスタンスは、信頼されていません。</li><li>**32 ビットのみ**:一部のアダプターは、32 ビット プロセスでのみ動作しますがほとんどは、64 ビット対応します。 この設定できる有効/無効にする BizTalk 管理コンソールで BizTalk を構成した後。 そのため、しないことに関する強調します。</li><li>**ホスト名**:[Biztalkserverapplication] では、既定値です。 場合は、BizTalk 管理コンソールで新しいホストとインスタンスを作成する、な名前または ReceivingHost など、名前を特定するできます。 としてそのためのままにします-です。</li></ul> |
   |  分離ホストとインスタンスを作成します。  |  分離ホストは、IIS 内で実行されます。 多くの環境では、既定値を保持することをお勧めします。<br/><br/>追加オプション: <ul><li>**信頼された**:メッセージ ボックス データベースにメッセージを送信するときに、送信者の資格情報 (SSID やパーティ ID) を渡します。 これは、サーバー間の信頼関係の作成と同じです。 ほとんどのホストとインスタンスは、信頼されていません。</li><li>**32 ビットのみ**:一部のアダプターは、32 ビット プロセスでのみ動作しますがほとんどは、64 ビット対応します。 この設定できる有効/無効にする BizTalk 管理コンソールで BizTalk を構成した後。</li><li>**分離ホスト名**:既定値は BizTalkServerIsolatedHost です。 としてのままにします-です。 </li></ul> |
   |   Windows サービス   |  ホスト インスタンスを実行するために使用するアカウントを入力します。 SQL Server が別のコンピューターにある場合は、ドメイン アカウントを入力します。  |
   |   [Windows グループ]  |  既定のグループの名前を保持するか、独自のものを入力できます。 SQL Server が別のコンピューターにある場合は、ドメイン アカウントを入力します。  |

### <a name="configure-business-rules-engine-bre"></a>ビジネス ルール エンジン (BRE) の構成します。

BRE を使用しない場合は、このセクションをスキップします。

- 構成することをお勧め、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ビジネス ルール エンジンを構成する前にグループ化します。 構成する前に BRE を構成する場合、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 、グループ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]構成は、ルール エンジン データベースにグループ関連の管理ロールに追加されません。

1. 選択**ビジネス ルール エンジン**します。
2. 次を構成します。


   |  プロパティ | 目的  |
   |---|---|
   | このコンピューターにビジネス ルール エンジンを有効にします。 | これで BRE を使用する場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、このオプションを選択します。  |
   |  データ ストア  | ルール データベースをホストするサーバー名を入力します。 このサーバーに BizTalk と SQL の両方がインストールされている場合は、ローカル サーバー名を入力します。 SQL Server が別のコンピューターにある場合は、SQL Server 名を入力します。<br/><br/>既定のデータベース名を保持するか、独自のものを入力します。 |
   |   Windows サービス  |  ルール更新サービスの実行に使用するアカウントを入力します。 SQL Server が別のコンピューターにある場合は、ドメイン アカウントを入力します。  |

### <a name="configure-bam-tools"></a>BAM ツールを構成します。

BAM ツールを使用しない場合は、このセクションをスキップします。

ビジネス アクティビティ監視ツールは次のとおりです。

- BAM 用のアドインの Excel
- BAM マネージャー
- BAM ポータル


- BAM ツールの構成では、特定の SQL Server の管理機能を必要とし、統合サービスがインストールされているマシンから実行する必要があります。
- 複数の BizTalk グループでは、BAM ツールを使用できます。 BAM ツールの構成を解除すると、BizTalk グループへの接続は削除されます。 ただし、SQL Server の BAM インフラストラクチャが十分に他の BizTalk グループを BAM プライマリ インポート テーブルを指す動作します。
- ビジネス アクティビティ監視ツールのページを使用するには、BAM データベースにその場で再構成します。 たとえば、既存の構成を削除することがなく BAM データベースをもう一度構成します。 これらの BAM データベースを再構成するには、既に展開されている OLAP ビューとすべてのアラートが中断されます。 既存のビューとアラートが新しく構成されたデータベースで保持したい場合は、次のいずれかを行います。  
    - 再構成するには、前に警告やビューの展開を解除し、再構成後に再デプロイする. アーカイブされたデータがあるビューに存在します。
    - BAM 警告を使用していない場合、データベースをバックアップを再構成する前にします。 再構成するには後に、、新しく構成された場所にデータベースを復元します。
- 統合する場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース、BAM アーカイブ、および BAM 分析データベースを除外する必要があります。


1. 選択**BAM ツール**します。
2. 次を構成します。

    |プロパティ|目的|
    | --- | --- |
    |ビジネス アクティビティの監視ツールを有効にする | 有効にして、このコンピューターに BAM ツールをインストールします。 |
    | BAM 集計用に Analysis Services を有効にする | BAM 警告の追跡情報を提供します。|
    |データ ストア| BAM データベースをホストするサーバー名を入力します。 このサーバーに BizTalk と SQL の両方がインストールされている場合は、ローカル サーバー名を入力します。 SQL Server が別のコンピューターにある場合は、SQL Server 名を入力します。<br/><br/>既定のデータベース名を保持するか、独自のものを入力します。|
    |この BizTalk グループのビジネス アクティビティの監視ツールを削除します。 | アンインストールし、BizTalk グループから BAM ツールを削除します。 |

   ### <a name="configure-bam-alerts"></a>BAM 警告を構成します。 

BAM 警告では、BAM ツールを有効にする必要があります。

1. 選択**BAM 警告**します。
2. 次を構成します。

    |プロパティ|目的|
    | --- | --- |
    | BAM 警告を有効にします。 | BAM 警告を使用する場合は、このオプションを確認します。 <br/><br/>BAM 警告を使用する SQL データベース メールを既に構成に注意してください。 |
    | Windows サービス | BAM 警告サービスを実行するために使用するアカウントを入力します。 SQL Server が別のコンピューターにある場合は、ドメイン アカウントを入力します。 |
    | BAM 警告 SMTP サーバー| SQL Database Mail を構成した SMTP サーバーの名前を入力します。 |
    | BAM 警告ファイルの場所| BAM 警告を格納するネットワーク共有を入力します。 <br/><br/>**注:** <br/>BAM 警告がファイルを保存する前に、この共有を手動で作成する必要があります。|
    | 警告データベース用 SQL Server | 警告データベースをホストする SQL サーバー名を入力します。<br/><br/>**注:** <br/>警告データベース用、NS SQL サーバーを指定する IPv6 アドレスの使用がサポートされていません。 ただし、コンピューター名を使用することができ、検索、DNS の変換が実行されます。|
    |警告データベース名のプレフィックス| 警告データベース用に使用するプレフィックスを入力します。|  

### <a name="configure-the-bam-portal"></a>BAM ポータルを構成します。

1. 選択**BAM ポータル**します。
2. 次を構成します。

    |プロパティ|目的|
    | --- | --- |
    |BAM ポータルを有効にします。 | 場合は、シック、BAM ポータルにこのオプションを使用します。 | 
    |Web サービス アカウント | IIS サービスを実行するために使用するアカウントを入力します。 SQL Server が別のコンピューターにある場合は、ドメイン アカウントを入力します。|
    |Windows グループ | 既定のグループの名前を保持するか、独自のものを入力します。 SQL Server が別のコンピューターにある場合は、ドメイン アカウントを入力します。|
    |BAM ポータル Web サイト|BAM ポータルをホストする Web サイトを選択します。 一部の環境では、既定の Web サイトは、構成されている唯一の web サイトです。 |

### <a name="configure-biztalk-edias2-runtime"></a>BizTalk edi/as2 ランタイムを構成します。 

* BizTalk edi/as2 ランタイムを構成する前に、エンタープライズ SSO、グループ、および BizTalk ランタイムを構成する必要があります。 
* BAM ツールは edi/as2 ランタイム状態レポート機能を構成する前に有効にする必要があります。
* EDI のみを構成する場合は、BAM は必要ありません。

1. 選択**BizTalk edi/as2 ランタイム**します。
2. 次を構成します。

    |プロパティ|目的|
    | --- | --- |
    |このコンピューターで BizTalk edi/as2 ランタイムを有効にします。| AS2 プロトコルを企業間メッセージングまたは X12、EDIFACT では、使用する、する場合は、このオプションを選択します。 |
    |この BizTalk グループの BizTalk EDI を有効にします。 | X12 または EDIFACT を使用する場合に選択します。 |
    | この BizTalk グループの BizTalk AS2 を有効にします。 | AS2 を使用する場合に選択します。 |
    | BizTalk edi/as2 ランタイム状態がこの BizTalk グループのレポートを有効にします。 | EDI インターチェンジと確認の状態を提供するレポートのユーザー エクスペリエンスを有効にします。 |
    |この BizTalk グループから BizTalk EDI、AS2、および状態レポート機能を削除します。 | アンインストールし、グループからのレポート機能を削除します。 |

### <a name="configure-windows-sharepoint-services-web-service---biztalk-server-2013-and-r2-only"></a>Windows SharePoint Services web サービス、BizTalk Server 2013 および R2 のみを構成します。 

> [!IMPORTANT] 
> このセクションでは、BizTalk Server 2013 R2 および BizTalk Server 2013 にのみ適用されます。 BizTalk Server 2013 R2 または BizTalk Server 2013 を使用していない場合は、このセクションをスキップします。

* この SharePoint Services web サービス (SSOM) は、BizTalk Server 2016 で開始し、BizTalk Server 2013 R2 で非推奨に削除されます。 SharePoint Services アダプター (CSOM) で置き換えられます。 CSOM オプションは、BizTalk 構成では表示されません。 CSOM オプションは、ファイル アダプターと同様に、BizTalk と共に自動的にインストールされている。 または、HTTP アダプターが自動的にインストールされます。

1. 選択**Windows SharePoint Services アダプター**します。
2. 次を構成します。

    |プロパティ|目的|
    | --- | --- |
    | このコンピューターで Windows SharePoint Services アダプターを有効にします。 | SharePoint Services web サービスをインストールする場合に選択します。 IIS web サービスは、BizTalk Server と同じコンピューターまたは別のコンピューター上にあることができます、SharePoint Services コンピューターにインストールされます。 ほとんどの環境で BizTalk Server と SharePoint Services が別々 のコンピューターには。|
    |Windows グループ|既定のグループの名前を保持するか、独自のものを入力します。 |
    |Windows SharePoint Services アダプター Web サイト|Windows SharePoint Service アダプター web サービスをホストする Web サイトを選択します。|


### <a name="apply-your-configuration"></a>構成を適用します。

選択**構成の適用**、および構成を続行します。 

1. **概要**、選択し、選択したコンポーネントを確認して**次**します。
2. 完了すると、選択**完了**します。

ような一時フォルダーに、構成ログ ファイルを生成し終わったら、:`
C:\Users\username\AppData\Local\Temp\ConfigLog(1-12-2017 2h39m30s).log`します。

## <a name="iis-application-pools-and-web-sites"></a>IIS アプリケーション プールおよび web サイト
構成した後[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、次のインターネット インフォメーション サービス (IIS) アプリケーション プールと仮想アプリケーションを作成することがあります。 

### <a name="application-pools"></a>アプリケーション プール  

|アプリケーション プール|既定のアプリケーション プール Id|説明|  
|---|----|---|  
|BAMAppPool|*ユーザー定義*|BAM ポータルのアプリケーション プール。|  
|BTSSharePointAdapterWSAppPool|*ユーザー定義*|Windows SharePoint Service アダプター Web サービスのアプリケーション プール。|  
|STSWebServiceAppPool|*ユーザー定義*|取引先管理ツールのアプリケーション プール。|  
|TpmWSAppPool|*ユーザー定義*|TPM 管理 Web サービスのアプリケーション プール。|  

### <a name="virtual-applications"></a>仮想アプリケーション  

|仮想アプリケーション|既定のアプリケーション プール|説明|  
|---|-----|---|  
|BAM|BAMAppPool|BAM ポータル コンポーネント (ページ、画像、プリコンパイル済みコード、およびその他のリソース) をホストする仮想アプリケーション。 この仮想アプリケーションは、BAM データベースとの通信に BAMManagementService アプリケーションを呼び出しています。 **注:** BAM ポータルをブランド化するには、このアプリケーションの内容を変更できます。|  
|BAMManagementService|BAMAppPool|BAMManagementService web サービスをホストする仮想アプリケーション。 この web サービスは、BAM プライマリ インポート テーブル (PIT) と通信するために、BAM ポータル アプリケーションによって使用されます。 データベースとの通信は、構成中に作成されたレジストリに保存されている、権限を借用した資格情報を使用して行われます。 この web サービスによって公開されるメソッドは、カスタム クライアントによってビューとその詳細、関連のアクティビティを取得するために使用して、ピボット テーブル レイアウトを任意のユーザー。 さらに、データベース内の警告の管理にも使用できます。|  
|BTSharePointAdapterWS|BTSSharePointAdapterWSAppPool|Windows SharePoint Service アダプター Web サービスをホストする仮想アプリケーション。 BizTalk Server 2013 R2 および 2013 のみに適用されます。|  


## <a name="more-configuration-topics"></a>複数の構成に関するトピック  

 [Azure VM での BizTalk Server の構成](http://msdn.microsoft.com/library/azure/jj248689.aspx)  

[BizTalk Server クラスターの構成](../install-and-config-guides/configure-biztalk-server-in-a-cluster.md)

[環境を最適化するための構成後の手順](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md)

 [BizTalk Server の展開をセキュリティで保護します。](../install-and-config-guides/securing-your-biztalk-server-deployment.md)  
