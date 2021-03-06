---
title: BizTalk Server の展開のセキュリティに関する推奨事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, security
- Windows Server 2003 Security Configuration Wizard (SCW)
- user accounts, security
- permissions
- access control
- security, deploying
- channel level encryption
- security, permissions
ms.assetid: 033fff11-d989-46ba-83ed-5063f7cd7818
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5513670afcdd6568f224d4f2fb79fedb721b02cb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279956"
---
# <a name="security-recommendations-for-a-biztalk-server-deployment"></a>BizTalk Server の展開のセキュリティに関する推奨事項
このセクションには、Microsoft BizTalk Server 環境をセキュリティで保護する高レベルで機能に依存しない推奨事項が含まれています。  
  
## <a name="topology-level-recommendations"></a>トポロジ レベルの推奨事項  
 **チャネル レベルの暗号化を使用します。** 既定では、BizTalk Server 内のさまざまなコンポーネント間のネットワーク データ フローはクリア テキストです。 メッセージを移動する際に、データの改ざんを見つけ出す、または別のコンピューターには問題にならなければ、インターネット プロトコル セキュリティ (IPSec) または Secure Sockets Layer (SSL) などのチャネル レベルの暗号化を使用することをお勧めします。 BizTalk Server は既定ではチャネル レベルの暗号化を構成していない、BizTalk Server は暗号化キーなどの重要なデータを配置しないと、ネットワーク上でのパスワードはクリア テキスト。 SSO データベースは、マスター シークレット サーバーによって提供されるマスター シークレット (暗号化キー) を使用して暗号化された形式で格納することによって、機密情報を管理します。 既定では、SSO データベースは受信、ストア、および暗号化された形式で機密情報を送信します。  
  
 SSL の詳細については、次を参照してください。 [ http://go.microsoft.com/fwlink/p/?LinkId=189708](http://go.microsoft.com/fwlink/p/?LinkId=189708)します。  
  
 **サーバーの物理的なセキュリティが確保されます。** 必要がありますも考慮に入れて、サーバー、デバイス、ネットワーク、ケーブル、電源装置、およびその他のコンポーネントの物理的なセキュリティ。 安全な環境でコンピューターを設置し、データベースなどのビジネスに不可欠な情報が含まれているコンピューターへのアクセスを制限する必要があります。  
  
 **使用するコンポーネントだけをインストールします。** (または HTTP および SOAP アダプターを実行しているコンピューターで、境界ネットワーク内のコンピューター) で、環境でインターネット インフォメーション サービス (IIS) をインストールする必要がある場合は、ファイル転送プロトコル (FTP)、WebDAV、および簡易メールをインストールする必要はありません。IIS のサブコンポーネントをプロトコル (SMTP) を転送します。 同様に、のみインストールして、環境に必要な BizTalk Server 機能の構成を実行することを確認します。 使用する場合は、BizTalk メッセージ キュー アダプタをのみ構成などです。 これは、環境内の潜在的な攻撃対象領域を削減するのに役立ちます。  
  
Internet Explorer を使用する場合は、Internet Explorer のセキュリティ強化を有効にするをお勧めします。  
  
 **サービス パックおよび更新プログラムをインストール**します。 持つすべてのサーバーで常に最新の製品のサービス パックと Microsoft 更新プログラムをインストールすることをお勧めします。[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]などのリソースを[!INCLUDE[btsSQLServerNoVersion_md](../includes/btssqlservernoversion-md.md)]します。  
  
 **スクリプトまたはバインド ファイルにクリア テキストでパスワードを保存しないでください。** 必要がありますで保存するスクリプトの場所で強力な随意アクセス制御リスト (Dacl) ように BizTalk Server 管理者のみがあるアクセス許可を表示、変更、およびこれらのスクリプトを実行します。 スクリプトおよびバインド ファイルには、パスワードが必要がある場合は、構成または展開スクリプトを使用するとすぐにパスワードをマスクするを確認します。 クリア テキストでこれらのファイルのパスワードを確保できません。  
  
 **使用して強力な随意アクセス制御リスト (Dacl) です。** ユーザーと、それを使用するアカウントのリソースにのみアクセス権を付与することを付けると、タスクを実行する最小のアクセス許可を確認します。 構成スクリプトを BizTalk Server 管理者に Dacl の場所に配置し、スクリプトにクリア テキスト パスワードを含めないようにします。 アクセスできるようにするサービス アカウントと BizTalk 管理者を BizTalk Server を使用してすべてのサービス アカウントの一時ディレクトリがある、Dacl を確認します。  
  
 カスタム アダプターがある場合は、BizTalk Server の管理者のみがこれらのコンポーネントへの書き込み権限があるために、強力な Dacl での場所にアダプター拡張コンポーネントを格納することをお勧めします。  
  
 **境界ネットワーク内の BizTalk Server を配置しないでください。** インターネットによる直接的な攻撃を受ける危険があります、境界ネットワーク内の他のサーバーからの攻撃する、会社のサイズに関係なくは、サーバーを公開、境界ネットワーク内の BizTalk Server を配置します。 BizTalk Server は、データ ドメイン内の Microsoft SQL Server データベースに通信するため、悪意のあるユーザーは重要なビジネス プロセスおよび構成データを改ざんする危険にさらされた BizTalk Server を最大限活用でした。  
  
## <a name="biztalk-server-groups-and-accounts"></a>BizTalk Server グループおよびアカウント  
 **最低限の権限およびユーザー権限を持つアカウントを使用します。** BizTalk Server システムのすべてのアカウント、タスクを実行に必要な最小ユーザー権限が必要です。 たとえば、処理サーバーで使用するサービス アカウントには、BizTalk Server、SQL Server、または Windows Server で管理者のユーザーの権限はありません。 アカウントは、BizTalk Server でタスクを実行する必要がある最低限のセキュリティ権限とユーザー権利の詳細については、次を参照してください。[最小セキュリティ ユーザー権限](../core/minimum-security-user-rights.md)します。 グループと BizTalk Server を使用するアカウントの詳細については、次を参照してください。 [Windows グループと BizTalk Server でのユーザー アカウント](../core/windows-groups-and-user-accounts-in-biztalk-server.md)します。  
  
 **さまざまな関数の異なるアカウントを使用します。** BizTalk Server 環境のセキュリティを維持するため、各環境内で実行するホスト インスタンスの別のサービス アカウントを作成することをお勧めします。 これもパスワードの更新中に可用性の向上に割り当てます。 1 つのサービス アカウントは、BizTalk Server の複数の Windows グループのメンバーではないことをお勧めします。  
  
 さらに、各 BizTalk ホストのさまざまな Windows グループを使用することと、1 つのグループのメンバーであるサービス アカウントがある別のホスト Windows グループのメンバーをできないことを勧めします。 これは、各 BizTalk ホストの強力なセキュリティの分離を提供します。  
  
 追跡ホストのだけは、Windows グループを作成することと、追跡のため、このグループのサービス アカウントを使用することをお勧めホストのインスタンス。 他のサービスでは、このサービス アカウントを使用しないでくださいし、追跡、BizTalk 管理者のアカウントを使用しないホストのインスタンス。  
  
 **さまざまな関数のさまざまなホストを使用します。** 追跡専用のホストを作成することをお勧めします。 ホスト「ホストの追跡」するように構成を読んだと、メッセージ ボックス データベース内の追跡テーブルへの書き込みアクセスだけでなく、追跡データベースのテーブルにアクセスします。 そのため、追跡を行うホストのホストで実行されているすべてのオブジェクトには、これらのテーブルを読み書きする権限があります。 パイプラインやオーケストレーションなどのユーザー項目の追跡可能性のある機密データへのアクセスをブロックにお勧めを行わない追跡専用のホストを作成することを処理、送信またはメッセージを受信します。  
  
 さらに、別のホストを使用して、処理、受信、およびメッセージを送信するをお勧めします。 会社のプライベート証明書にアクセスするサービス アカウントを分離できます。 これらのアカウントで実行中のあるコードは少なくを有効にすると脆弱性からアカウントを侵害する可能性を低くプライベート証明書が侵害される危険性が減少します。  
  
 **パスワードを定期的に変更します。** サービス アカウントのパスワードを定期的に変更する必要があります。 検討のホスト インスタンスに複数のサービス アカウントを必要に応じて、これらのサービス アカウントごとにパスワードを変更する必要があります。  
  
> [!CAUTION]
>  BizTalk 管理コンソールでホスト インスタンス サービス アカウントのパスワードを変更する必要があります。 コンピュータの管理コンソールでホスト インスタンス サービス アカウントのパスワードを変更すると、構成の問題が発生することができます。  
  
 **BizTalk 管理者グループのメンバーシップを制限します。** BizTalk Server 管理者は、暗号化またはそれ以外の場合、ほとんどのデータへのアクセスなど、BizTalk Server 環境全体にわたるスパン ユーザー権限を持っています。 そのため、BizTalk 管理者が誤って不適切な構成では、重要なセキュリティ ホールを公開できます。 不適切な動作は、BizTalk 管理者は、機密性、整合性、および顧客データの可用性の完全なセキュリティ侵害を含む、システムに損害を実行できます。  
  
 状況は、開発者直接オーケストレーションをコンピューターに展開、運用環境で、ドメイン管理者必要があります開発者 BizTalk 管理者ユーザー権限を付与します。 既に説明した理由により、これは推奨されません。  
  
 **COM + 管理者グループのメンバーシップを制限します。** により、さまざまなアーキテクチャ上の理由は、COM + 管理者は、いくつかの BizTalk Server コンポーネントで管理者としてユーザー権限を持っています。 すべて実際には、コンピューターで COM + 管理者は、BizTalk 管理者もと、BizTalk 実稼働サーバーには、このグループのメンバーシップを制限する必要がありますと想定する必要があります。  
  
 **アクセスを必要なサービスを実行するコンピューターにのみ、ユーザー アクセス権を付与します。** すべてのアカウントには、すべてのコンピューターへのアクセス許可が必要があります。 BizTalk ホスト インスタンスは、メモリ内の機密情報を保持します。 これらは、パスワードや企業情報などの重要なデータで可能性があります。 非常に厳密なローカル ユーザーのポリシーは、これらのコンピューターを設定する必要があります。 たとえば、デプロイを維持するために必要とするユーザーにのみこれらのコンピューター上のローカル ログオン権限を付与します。 これは、スワップ ファイルおよびクラッシュ ダンプをアクセスによる脅威を軽減します。  
  
 **Power Users グループのアクセス許可を制限または削除します。** このグループのユーザー権利の Power Users グループの提供メンバーの既定のアクセス許可は、グローバル アセンブリ キャッシュ (GAC) に登録されている BizTalk アセンブリを含む、コンピューター全体の設定を変更します。 各コンピューターでは、1 つまたは複数のアプリケーションを共有するアセンブリを格納する GAC があります。 アセンブリ、Power Users グループを変更するアクセス許可を削除することや、運用環境の BizTalk Server から、Power Users グループを削除することをお勧めします。  
  
 
## <a name="see-also"></a>参照  
 [グループおよびサービス アカウントのアクセス制御](../core/access-control-for-groups-and-service-accounts.md)   
 [管理ロールのアクセス制御](../core/access-control-for-administrative-roles.md)   
 [セキュリティ保護のための最小ユーザー権限](../core/minimum-security-user-rights.md)   
 [セキュリティの計画](../core/planning-for-security.md)