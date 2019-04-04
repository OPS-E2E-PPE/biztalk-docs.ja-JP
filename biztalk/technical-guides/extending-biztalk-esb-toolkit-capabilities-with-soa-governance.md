---
title: SOA ガバナンスによる BizTalk ESB Toolkit 機能の拡張 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b66a121b-d86f-4f97-a05f-5141ffe719e8
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a770599e082d2f25062588247acfeb6a0449b974
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977507"
---
# <a name="extending-biztalk-esb-toolkit-capabilities-with-soa-governance"></a>SOA ガバナンスによる BizTalk ESB Toolkit 機能の拡張
[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]が付属して[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ツールと拡張ライブラリのコレクションであると[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]の疎結合および動的なメッセージング アーキテクチャをサポートしている機能です。 これは、サービスおよびそのコンシューマー間の迅速な仲介のツールを提供するミドルウェアとして機能します。 実行時に、最大限の柔軟性を有効にすると、[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]サービス エンドポイントの疎結合の構成とサービスの相互作用の管理を簡素化します。  
  
 Sentinet の BizTalk Server の拡張機能の機能を強化する[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]Sentinet、SOA ガバナンスと、Microsoft プラットフォーム向けの API 管理ソフトウェア ソリューションと統合することができます。 Sentinet の最初のリリース[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]拡張機能の提供、[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]と BizTalk Server 2013 では、統合された SOA リポジトリ リゾルバー [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]、および Visual Studio 2012。  
  
 Sentinet SOA の競合回避モジュールを拡張、方法の詳細については、このホワイト ペーパーで[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]機能、Sentinet SOA リゾルバー、および最後に Sentinet SOA 競合回避モジュールを使用する方法を示したサンプルを構成する方法。  
  
## <a name="esb-toolkit-and-sentinet-soa-resolver"></a>ESB Toolkit と Sentinet SOA 競合回避モジュール  
 その他のもの、ESB Toolkit は競合回避モジュールは、次に提供する必要があります。  
  
- サービス エンドポイントとその構成の実行時の解決  
  
- 疎結合メッセージングを使用した BizTalk ESB ソリューション。  
  
  Sentinet の提供、堅牢かつ包括的な[SOA リポジトリ](http://www.nevatech.com/sentinet/soa-repository)SOA ガバナンスとランタイムの高度な統合ソリューションの SOA 管理機能を提供します。 Sentinet SOA リポジトリと組み合わせると、Sentinet SOA の競合回避モジュールは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]高度で使いやすい ESB の構成、動的なメッセージのルーティングおよびメッセージ セキュリティの実装の機能を使用した ESB アーキテクチャ。  
  
  次の高レベルの図 Sentinet SOA 競合回避モジュールを収める方法を示します、[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]アーキテクチャ。  
  
  ![BizTalk ESB Toolkit の Sentinet](../technical-guides/media/sentinetwp-arch.png "SentinetWP_Arch")  
  
  実行時に、**エンドポイントの解決とルーティング**(つまり、ESB Toolkit の競合回避モジュールのフレームワークの一部) 上の図でコンポーネントをインスタンス化する (Visual Studio の旅行プラン デザイナーで作成した)、行程のドキュメントを使用して特定の競合回避モジュールと、サービス エンドポイントとその構成を提供するには、競合回避モジュールを要求します。 旅行プラン自体は、競合回避モジュールでは、この参照を使用して、レジストリまたはリポジトリ内の要求されたエンドポイントを検索することができるように、サービス エンドポイントへの参照を使用して構成するのにがあります。 デザイン時の (スケジュールが作成される) 場合に、サービス エンドポイントの実際の物理アドレスが不明し、も、サービスに必要なセキュリティ ポリシーが。 以降の段階では、ランタイムを使用して、ESB Toolkit は、必要なサービスのセキュリティ設定で実際の物理サービス アドレスにメッセージを送信する動的送信ポートを傾斜を構成するサービス エンドポイントを解決します。 サービスのエンドポイント アドレス、通信プロトコル、またはセキュリティ要件は、レジストリ/リポジトリの構成のみを変更する場合は、更新する必要があります。 ESB または BizTalk Server アイテムのランタイム構成を更新する必要はありません。  
  
## <a name="how-does-the-sentinet-resolver-add-value-to-an-esb-toolkit-application"></a>Sentinet のリゾルバーでは、方法は、ESB Toolkit アプリケーションに、値して追加のでしょうか。  
 Sentinet のリゾルバーを使用して、SOA リポジトリとの 2 つの主な利点は次のとおりです。  
  
- – ほとんどの場合、解決済みの外部サービス エンドポイントへのクライアント id の割り当て解決 ESB エンドポイントは特定のクライアント id (ユーザー名/パスワード、特定の Windows アカウントの資格情報または特定の X.509 などの外部サービスを呼び出す必要があります。証明書)。 これは、その他の ESB リゾルバー/レジストリは適切に処理されず、非常に一般的なセキュリティ要件です。  
  
- 以前の制限を回避するのに – セキュリティ情報へのアクセスを制限するその他の競合回避モジュールは、必要なセキュリティ id を持つ複雑な XML が含まれる Tmodel を手動で構成を使用できます。 ただし、レジストリ/リポジトリの一部として、セキュリティ情報の保存は、適切なアプローチではありません。 これにより、サービス コンシューマーなど、ユーザー名やパスワードなど、サービスにアクセスするセキュリティの詳細情報に簡単にアクセスします。  
  
  Sentinet のリゾルバーと Sentinet SOA リポジトリは、柔軟にする機能を提供し、安全に標準またはカスタムの WCF エンドポイント動作を使用して解決 ESB エンドポイントに任意の特定のクライアント id を割り当てます。 Sentinet では、セキュリティ情報と共に Sentinet のリゾルバー、および Sentinet SOA リポジトリではなくを構成することで、これを実現します。 Sentinet のリゾルバーで構成されているすべてのクライアント資格情報は、暗号化された形式で格納されます。  
  
  これに加えて次に Sentinet のリゾルバーと Sentinet SOA リポジトリを使用するその他の利点のいくつか示します。  
  
- 包括的な SOA リポジトリを提供します。 リポジトリは、サービス メタデータの内容、サービス id、およびポリシーへのアクセス、サービスのバージョンなどのサポートを提供します。  
  
- Sentinet レジストリにサービスの WSDL をアップロードすることで物理サービスを登録するための容易さ。  
  
- 包括的で使いやすい Sentinet 管理コンソール。 コンソールは、すべてのサービス メタデータにアクセスできるように管理とアクセス サービスの操作とそのデータ スキーマ、サービス エンドポイント、セキュリティ ポリシーなどの単純なユーザー インターフェイスに、成果物を関連付けられています。  
  
- 管理および解決済みのエンドポイントのカスタム動作の構成。 Sentinet のリゾルバーは、解決済みのエンドポイントの構成が容易な完全にカスタマイズ可能なエンドポイントの動作を提供します。  
  
- 検索条件のさまざまな Sentinet のリゾルバーを構成するオプション。 スケジュールでは、サービス エンドポイントに割り当てられているいずれかのキーワードを定義したり、リポジトリのサービス階層内のサービスにサービスのパスを使用することができます。  
  
- 高度な競合回避モジュールの機能をテストします。 Sentinet のリゾルバー構成は、Visual Studio の旅程デザイナーから直接テストできます。 他の競合回避モジュールは、エンドポイントの基本的なプロパティに関する情報を提供することができますのみ、Sentinet のリゾルバーは解決済みのエンドポイントに関する拡張情報を提供します。 Sentinet のリゾルバーでは、だけでなく、エンドポイントの基本的なプロパティを識別するプロパティ解決 Sentinet リポジトリ内のサービスとエンドポイントの場所が表示されます。 スケジュール オンランプ デザイナーは、Sentinet のリゾルバーとそのさまざまな検索条件の影響の解像度結果旅行プラン自体は実行時に使用する前にテストできます。  
  
## <a name="installing-the-sentinet-biztalk-server-extensions"></a>Sentinet の BizTalk Server の拡張機能のインストール  
 ダウンロードしてから Sentinet BizTalk の拡張機能をインストール[ここ](http://www.nevatech.com/download)します。 拡張機能をインストールすると、ESB Toolkit、ドキュメント、および拡張機能を使用する方法のサンプルの Sentinet のリゾルバーがインストールされます。  
  
 インストールして、BizTalk Server の Sentinet 拡張機能を構成する方法の詳細を示すドキュメントは、使用可能な製品のダウンロードの一環として。  
  
## <a name="using-the-sentinet-biztalk-server-extensions"></a>Sentinet の BizTalk Server の拡張機能の使用  
 このセクションで Sentinet BizTalk Server の拡張機能を使用して、上記で説明した機能を紹介する方法について説明します。  
  
### <a name="prerequisites"></a>前提条件  
 手順については、このホワイト ペーパーでは、次をインストールして構成したとします。  
  
-   Visual Studio 2012.  
  
-   BizTalk Server 2013。 手順については、[BizTalk Server 2013 のインストール](http://msdn.microsoft.com/library/jj248688\(v=bts.80\).aspx)を参照してください。  
  
-   BizTalk Server ESB Toolkit です。 手順については、[のインストールと構成、Microsoft BizTalk ESB Toolkit](http://msdn.microsoft.com/library/jj684558\(v=bts.80\).aspx)を参照してください。  
  
-   Sentinet の BizTalk Server の拡張機能。 手順については、使用可能なドキュメントを参照します。 使用可能な製品のダウンロードの一環として[ここ](http://www.nevatech.com/download)。  
  
### <a name="register-a-web-service"></a>Web サービスを登録します。  
 Sentinet インフラストラクチャによって管理されている web サービスは、リポジトリに登録する必要があります。 このホワイト ペーパーでは、Sentinet インストール パッケージに同梱されている WCF の顧客の検索サンプルのサービスを使用します。  
  
1. 開始、**顧客検索**Sentinet インストール パッケージによってインストールされるサービスのサンプルです。 管理者として顧客の検索サンプルを起動、ポリシーのバインドを選択します (例: **wsHttpBinding**) 順にクリックします**開始**します。  
  
2. サービスが実行している場合、クリックして、**ビュー Wsdl**サービスのメタデータ URL とサービスの WSDL でブラウザーを開きへのリンク。 ブラウザーのアドレス バーから、メタデータ URL をコピーします。  
  
3. ブラウザーを開き、URL を入力します (`https://[computer-name]/sentinet`) Sentinet 管理コンソールを起動します。 ログインと選択、**リポジトリ**のルート要素、**リポジトリ**ビュー パネル。 右クリックし、**リポジトリ**ルート要素をクリックして、**追加 > サービス > SOAP**メニュー オプション。  
  
4. **サービスの追加** ダイアログ ボックスの**URL から WSDL**オプションで、先ほどコピーしたサービスのメタデータ URL を貼り付けますをクリックして**次へ**します。  
  
    ![サービスの URL を追加](../technical-guides/media/sentinetwp-addserviceurl.png "SentinetWP_AddServiceURL")  
  
5. ウィザードでは、サービス メタデータのダウンロードを開始します。 ダウンロードが完了すると、ウィザードには、Web サービスのツリー構造が表示されます。 サービスの名前を指定し、をクリックして**完了**Sentinet リポジトリにサービス メタデータをアップロードします。  
  
    ![Web サービスの構造](../technical-guides/media/sentinetwp-servicestructure.png "SentinetWP_ServiceStructure")  
  
6. サービスは、バージョン 1 と、リポジトリにインポートされます。 バージョンを選択し、エンドポイントを選択します。 **エンドポイントの詳細**ペインの下部で、クリックして、**添付ファイル**タブをクリックし、をクリックし、**変更**します。  
  
    ![サービス エンドポイントを変更](../technical-guides/media/sentinetwp-serviceendpoint.png "SentinetWP_ServiceEndpoint")  
  
7. エンドポイントの詳細 タブで、をクリックして、(**+**) に対して署名**キーワード**、エンドポイントに関連付けるキーワードを入力します (たとえば、 **TestKeyword**) とクリックして**保存**します。 キーワードは、SOA のリポジトリにエンドポイント タグ (または識別子) として使用されます。  
  
    ![キーワードを指定](../technical-guides/media/sentinetwp-enterkeyword.png "SentinetWP_EnterKeyword")  
  
   新しいバージョンを追加する上記の手順を繰り返して、 **CustomerSearch**サービスが別々 のバインドが、たとえば**basicHttpBinding**します。 このホワイト ペーパーの後半を取り上げます Sentinet のリゾルバーをさまざまなサービス (または同じサービスの異なるバージョン) に解決できる方法だけで、サービス エンドポイントに検索キーワードを関連付けること。  
  
### <a name="configure-sentinet-resolver"></a>Sentinet のリゾルバーを構成します。  
 このセクションでは、単純な BizTalk ESB 行程デザイナー プロジェクトでは、Sentinet のリゾルバーを構成する方法とキーワードを使用してサービス エンドポイントに解決するには一意にする方法を具体的には表示されます。 このセクションでは、ESB のすべてのメッセージを送信することがなく Visual Studio 自体から競合回避モジュールをテストする方法も示します。  
  
1.  Visual Studio を起動し、作成、 **BizTalk ESB 行程デザイナー**プロジェクト。  
  
2.  ソリューション エクスプ ローラーでは、旅行プラン デザイナーで開く旅程をダブルクリックします。  
  
3.  ツールボックスからドラッグ アンド ドロップ、**行程サービス**デザイナー画面に図形。  
  
4.  選択、**スケジュール サービス**図形し、変更、**旅行プラン サービスのエクステンダー**プロパティを**メッセージング エクステンダー**ドロップダウン リストから。  
  
     ![Message Extender のプロパティを設定](../technical-guides/media/sentinetwp-setmessageextender.png "SentinetWP_SetMessageExtender")  
  
5.  右クリックし、**リゾルバー**内の要素、**スケジュール サービス**図形を**新しいリゾルバーを追加**。  
  
     ![新しいリゾルバーを追加](../technical-guides/media/sentinetwp-addnewresolver.png "SentinetWP_AddNewResolver")  
  
6.  新しいリゾルバー要素を選択して、その名前を変更 (例: **MyResolver**)、およびの**リゾルバーの実装**プロパティを選択**Sentinet のリゾルバー拡張機能**。  
  
     ![リゾルバーの実装設定](../technical-guides/media/sentinetwp-addresolverimplementation.png "SentinetWP_AddResolverImplementation")  
  
7.  指定、**アクション**と**キーワード**Sentinet のリゾルバー拡張機能のプロパティ。 Sentinet リポジトリに先ほど追加したサービスを一意に解決するのには、これらのプロパティを使用します。 同様に他のプロパティの Sentinet のリゾルバー拡張機能を指定できますがあります。 これらのプロパティに関する詳細については、Sentinet BizTalk の拡張機能ユーザー ガイドを参照してください。  
  
    |プロパティ|説明|  
    |--------------|-----------------|  
    |操作|呼び出されるサービス操作を一意に識別するメッセージのアクション ヘッダー。 このアクション ヘッダーはサービスの WSDL の一部であり、サービス WSDL、または操作の要求メッセージのプロパティ Sentinet 管理コンソール ユーザー インターフェイスからのいずれか見つかんだことができますです。|  
    |キーワード|キーワードを指定 (例: **TestKeyword**) Sentinet 管理コンソールでサービスに割り当てられています。|  
  
     次のスクリーン ショットは、指定されたアクションとキーワードのプロパティを示しています、 **MyResolver**構成します。  
  
     ![Sentinet のリゾルバー構成](../technical-guides/media/sentinetwp-resolverconfig.png "SentinetWP_ResolverConfig")  
  
8.  構成の変更を保存します。  
  
#### <a name="advanced-resolver-configuration"></a>高度な競合回避モジュールの構成  
 Sentinet BizTalk 拡張機能の構成アプリケーションが変更**Sentinet.BizTalk.config**パッケージのインストール フォルダーのルートにあるファイル (既定の場所は`<installation drive>:\Program Files\Nevatech\Sentinet BizTalk Extensions\Sentinet.BizTalk.config`)。 ファイルの外部で変更することができます**Sentinet BizTalk 拡張機能の構成**アプリケーションに高度な構成オプションを提供します。 たとえば、多くの実際の ESB シナリオで解決されるエンドポイント提供する必要はサービス エンドポイントのアドレスとバインディング、だけでなく、特定のクライアント id (のユーザー名/パスワード、特定の Windows アカウント資格情報、または X.509 クライアントも証明書)。 せず、適切なクライアント id は、ESB 傾斜オフ送信ポートは、外部サービスを呼び出すに失敗します。 Sentinet のリゾルバーでは、旅行プラン開発者が適切なクライアントのエンドポイント id を提供する特定のエンドポイント動作を割り当てることができます。 複数のエンドポイントの動作は、事前構成済みの標準の WCF エンドポイント動作として、 **Sentinet.BizTalk.config**ファイル、および、特定のエンドポイントの動作は Sentinet のリゾルバーから行程で参照できます動作の名前を指定することで、構成、**エンドポイント動作の解決**プロパティ。  
  
### <a name="test-the-resolver-configuration"></a>競合回避モジュールの構成をテストします。  
 関連するプロパティの値を指定して Sentinet のリゾルバーを構成した後は、Visual Studio 自体から競合回避モジュールをテストできます。  
  
1. デザイン画面に追加した Sentinet のリゾルバーを右クリックし、**行程サービス**図形をクリックして**テスト構成の競合回避モジュール**します。  
  
    出力ウィンドウには、抜粋を次に示すようなテスト結果が表示されます。  
  
   ```  
   ***** Resolved Service Endpoint *****  
  
   Service Path and Name          : /CustomerSearch  
   Service Id                     : 2b6d686a-cae1-4b7b-93da-99affef98478  
   Service Version                : 1  
   Endpoint Name                  : WSHttpBinding_ICustomerSearch  
   Endpoint Address               : http://btscloudcar/CustomerSearch/1  
   ```  
  
    競合回避モジュールでのエンドポイントが返されることに注意してください、 **CustomerSearch**サービス**バージョン 1**する検索条件 (**TestKeyword**) がアタッチされています。  
  
2. 削除、 **TestKeyword**に関連付けられている、**バージョン 1**の**CustomerSearch**サービスし、サービスの 2 番目のバージョンのエンドポイントに関連付けます。  
  
   1.  Sentinet の管理コンソールを開き、**バージョン 1**下、 **CustomerSearch**サービス、wsHttpBinding エンドポイントをクリックして、**添付ファイル**タブをクリックし、をクリックし、**変更**します。  
  
        ![CustomerSearch サービスからキーワードを削除](../technical-guides/media/sentinetwp-removekeyword.png "SentinetWP_RemoveKeyword")  
  
   2.  キーワードを削除するには、をクリックする前に入力したキーワードに対してボタンをクリックします。**はい** をクリックし、メッセージ ボックスで**保存**します。  
  
        ![CustomerSearch サービスからキーワードを削除](../technical-guides/media/sentinetwp-removekeyword-2.png "SentinetWP_RemoveKeyword_2")  
  
   3.  これで、同じキーワードを割り当てる (**TestKeyword**) に、 **basicHttpBinding**エンドポイント、**バージョン 2**の同じサービス。  
  
3. Visual Studio に戻るし、もう一度競合回避モジュールの構成をテストします。 Sentinet 管理コンソールで、削除、 **TestKeyword**に関連付けられている、**バージョン 1**のCustomerSearchサービスし、関連付けるバージョン 2サービス。  
  
    出力ウィンドウには、抜粋を次に示すようなテスト結果が表示されます。  
  
   ```  
   ***** Resolved Service Endpoint *****  
  
   Service Path and Name          : /CustomerSearch  
   Service Id                     : 5b9e5878-7016-44ab-9f0e-5282a8c3e508  
   Service Version                : 2  
   Endpoint Name                  : BasicHttpBinding_ICustomerSearch  
   Endpoint Address               : http://btscloudcar/CustomerSearch/2  
   ```  
  
4. もう一度テスト メッセージを送信、**行程クライアントのテスト**今回は、カウンターがインクリメントの basicHttpBinding と共に配置されているサービスのバージョン 2 を表す ダイアログ ボックスに注意してください。  
  
   キーワードを割り当てる (**TestKeyword**) サービスのバージョン 1 に戻す (で、 **WSHttpBinding**エンドポイント)。  
  
## <a name="using-the-sentinet-biztalk-server-extensions"></a>Sentinet の BizTalk Server の拡張機能の使用  
 このセクションでは、ESB リゾルバー、と共に、Sentinet BizTalk 拡張機能を使用してサービスを一意に識別し、サービスまたはメッセージを送信するクライアントへルーティングを最小限に抑えると共に、そのサービスにメッセージ、またはまったく変更する方法に注目します。 2 つのシナリオをテストします。  
  
- (接続されているキーワード) を使用して、Sentinet リポジトリに登録されているサービスにサンプル メッセージを送信します。 Sentinet の管理コンソールを使用して、サービスのポリシーのバインドを変更し、もう 1 つのサンプル メッセージを送信します。 このシナリオでは、サービスのセキュリティ ポリシーを変更するもの影響も、クライアント アプリケーションも ESB 行程を示します。  
  
- (接続されているキーワード) を使用して、Sentinet リポジトリに登録されているサービス エンドポイントには、サンプル メッセージを送信します。 同じキーワードを同じサービスの別のバージョンにアタッチし、もう一度メッセージを送信します。 このシナリオでは、サービスの新しいバージョンにメッセージをルーティング キーワードを異なるサービスのバージョンに自動的にアタッチする方法を示します。  
  
  これらのシナリオをテストするには、次のサンプルを使用します。  
  
- **顧客の検索サービス**Sentinet インストーラーに付属します。 このサービスは、[スタート] メニューから起動できます。  
  
- **Nevatech.Vsb.BizTalk.Samples** Sentinet インストーラーで提供されるソリューションです。 このサンプルは`<installation drive>:\Program Files\Nevatech\Sentinet BizTalk Extensions\Samples`します。  
  
- ESB します。Itinerary.Test サンプルが付属[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]します。 これは、「`<install drive>:\Program Files (x86)\Microsoft BizTalk ESB Toolkit\ESBSource.zip\Source\Samples\Itinerary\Source\ESB.Itinerary.Test`サンプル メッセージをカスタマーの検索サービスをテストするために使用します。  
  
#### <a name="to-test-the-sentinet-resolver-by-changing-the-service-policy-binding"></a>サービス ポリシーのバインドを変更することで、Sentinet のリゾルバーをテストするには  
  
1. 必ず、 **CustomerSearch** wsHttpBinding でデプロイされたサービスが実行されています。  
  
2. **Nevatech.Vsb.BizTalk.Samples**サンプルでは、開いている**CustomerSearch.Search.itinerary**を選択します**サービス エンドポイントを解決するには**下、**メッセージエクステンダー**内で、**メッセージ ルーティング**図形、および、**キーワード**プロパティ、キーワードを指定します。 **TestKeyword**します。  
  
    ![キーワードを割り当てる](../technical-guides/media/sentinetwp-assignkeyword.png "SentinetWP_AssignKeyword")  
  
3. 旅行プランに変更を保存し、モデルをエクスポートします。 スケジュール オンランプのデザイナー画面で任意の場所を右クリックし をクリックして**モデルのエクスポート**します。  
  
4. 右クリックし、BizTalk Server 管理コンソールで、 **Microsoft.Practices.ESB**アプリケーションでは、インポート をクリックし、バインド順にクリックします。 ESB リゾルバーのサンプルの場所に移動します`<installation drive>:\Program Files\Nevatech\Sentinet BizTalk Extensions\Samples\ESB Resolver`を開き、 **BizTalk.Bindings.xml**ファイル。 これを作成、 **Sentinet 送信請求-応答**と**Sentinet の一方向**サンプル スケジュールに必要なポートを送信します。  
  
    また、すべての送信ポートと受信場所のことを確認してください、 **Microsoft.Practices.ESB** BizTalk アプリケーションが参加しているし、開始します。  
  
5. 開く、 **ESB します。Itinerary.Test**アプリケーションがそれをビルドして実行します。 起動するスケジュールのテスト クライアントで、次の手順に従います。  
  
   1.  旅行プランのテスト クライアントで  **Web サービス オプション**チェック ボックスをオフ**WCF サービスを使用して**を選択し、**方法の 2 つのサービス**します。  
  
   2.  **サービスの種類**ドロップダウン リストで選択**メッセージング**します。  
  
   3.  をクリックして**ロード行程**に移動し、 **CustomerSearch.Search.Itinerary.xml**にあるサンプル プロジェクトのファイル**ExportedItineraries** フォルダー`<installation drive>:\Program Files\Nevatech\Sentinet BizTalk Extensions\Samples\ESB Resolver\ExportedItineraries`.  
  
   4.  省略記号ボタンをクリックします (**..**) **ロード メッセージ**グループに移動して**CustomerSearch.Search.Request.xml**プロジェクトに**SampleMessages** フォルダー`<installation drive>:\Program Files\Nevatech\Sentinet BizTalk Extensions\Samples\ESB Resolver\SampleMessages`.  
  
   5.  クリックして**要求を提出**で応答が受信したことを確認します。  
  
6. **CustomerSearch**ダイアログ ボックスで、カウンターが 1 つずつ増加に注目してください。  
  
7. Sentinet の管理コンソールでは、wsHttpBinding ではなく、basicHttpBinding を使用するエンドポイントの詳細を更新します。  
  
   1.  サービス エンドポイントを選択して、、**詳細**タブをクリックし、をクリックし、**変更**します。  
  
   2.  **詳細** タブで、省略記号をクリックします (**.**) で、**ポリシー**セクションで、起動するため、**ポリシーの変更**ウィザード。  
  
        ![ポリシーの変更ウィザードを起動して](../technical-guides/media/sentinetwp-modifypolicy-1.png "SentinetWP_ModifyPolicy_1")  
  
   3.  最初のページでの保持ポリシーの種類として**プライベート**順にクリックします**次**します。  
  
   4.  2 番目のページでの変更、 **wsHttpBinding** XML 要素を**basicHttpBinding** (大文字)、順にクリックします**完了**します。  
  
        ![ポリシーのバインドを更新](../technical-guides/media/sentinetwp-modifypolicy-2.png "SentinetWP_ModifyPolicy_2")  
  
   5.  クリックして**保存**エンドポイントの詳細に変更を保存します。  
  
8. 停止、 **CustomerSearch**からバインドを変更するサービスは、 **wsHttpBinding**に**basicHttpBinding**、サービスをもう一度開始します。  
  
    ![異なるバインディングでサービスを再起動](../technical-guides/media/sentinetwp-restartcustservice.png "SentinetWP_RestartCustService")  
  
9. **行程クライアントのテスト**顧客の検索サービスをもう一度テスト メッセージを送信します。 顧客サービスの検索 ダイアログ ボックスで、カウンターが 1 ずつインクリメントされます再ことに注意してください。  
  
     Sentinet 管理コンソールから、メッセージは正常に受信されると変更の詳細にバックアップ ポリシー **wsHttpBinding**します。 同様に、停止、**顧客検索**サービス、wsHttpBinding にポリシーを変更し、サービスを開始します。  
  
   これは、またはクライアントの旅行プランを変更することがなく Sentinet リポジトリ内のサービスの詳細を更新済みサービスのエンドポイントをターゲットには即座に更新する方法について説明します。  
  
#### <a name="to-test-the-sentinet-resolver-by-changing-keyword-assignments"></a>キーワードの割り当てを変更することで、Sentinet のリゾルバーをテストするには  
  
1.  2 つのインスタンスを必ず**CustomerSearch** basicHttpBinding と wsHttpBinding で展開されたサービスが実行されています。  
  
2.  **Nevatech.Vsb.BizTalk.Samples**サンプルでは、開いている**CustomerSearch.Search.itinerary**を選択します**サービス エンドポイントを解決するには**下、**メッセージエクステンダー**内で、**メッセージ ルーティング**図形、および、**キーワード**プロパティ、キーワードを指定します。 **TestKeyword**します。  
  
     ![キーワードを割り当てる](../technical-guides/media/sentinetwp-assignkeyword.png "SentinetWP_AssignKeyword")  
  
3.  旅行プランに変更を保存し、モデルをエクスポートします。 スケジュール オンランプのデザイナー画面で任意の場所を右クリックし をクリックして**モデルのエクスポート**します。  
  
4.  右クリックし、BizTalk Server 管理コンソールで、 **Microsoft.Practices.ESB**アプリケーションでは、インポート をクリックし、バインド順にクリックします。 ESB リゾルバーのサンプルの場所に移動します`<installation drive>:\Program Files\Nevatech\Sentinet BizTalk Extensions\Samples\ESB Resolver`を開き、 **BizTalk.Bindings.xml**ファイル。 これを作成、 **Sentinet 送信請求-応答**と**Sentinet の一方向**サンプル スケジュールに必要なポートを送信します。  
  
     また、すべての送信ポートと受信場所のことを確認してください、 **Microsoft.Practices.ESB** BizTalk アプリケーションが参加しているし、開始します。  
  
5.  開く、 **ESB します。Itinerary.Test**アプリケーションがそれをビルドして実行します。 起動するスケジュールのテスト クライアントで、次の手順に従います。  
  
    1.  旅行プランのテスト クライアントで  **Web サービス オプション**チェック ボックスをオフ**WCF サービスを使用して**を選択し、**方法の 2 つのサービス**します。  
  
    2.  **サービスの種類**ドロップダウン リストで選択**メッセージング**します。  
  
    3.  をクリックして**ロード行程**に移動し、 **CustomerSearch.Search.Itinerary.xml**にあるサンプル プロジェクトのファイル**ExportedItineraries** フォルダー`<installation drive>:\Program Files\Nevatech\Sentinet BizTalk Extensions\Samples\ESB Resolver\ExportedItineraries`.  
  
    4.  省略記号ボタンをクリックします (**..**) **ロード メッセージ**グループに移動して**CustomerSearch.Search.Request.xml**プロジェクトに**SampleMessages** フォルダー`<installation drive>:\Program Files\Nevatech\Sentinet BizTalk Extensions\Samples\ESB Resolver\SampleMessages`.  
  
    5.  クリックして**要求を提出**で応答が受信したことを確認します。  
  
6.  **CustomerSearch**ダイアログ ボックスで、カウンターが 1 つずつ増加に注目してください。  
  
7.  Sentinet 管理コンソールで、削除、 **TestKeyword**に関連付けられている、**バージョン 1**の**CustomerSearch**サービスし、関連付ける**バージョン 2**サービス。  
  
    1.  Sentinet の管理コンソールを開き、**バージョン 1**下、 **CustomerSearch**サービス、wsHttpBinding エンドポイントをクリックして、**添付ファイル**タブをクリックし、をクリックし、**変更**します。  
  
         ![CustomerSearch サービスからキーワードを削除](../technical-guides/media/sentinetwp-removekeyword.png "SentinetWP_RemoveKeyword")  
  
    2.  キーワードを削除するには、をクリックする前に入力したキーワードに対してボタンをクリックします。**はい** をクリックし、メッセージ ボックスで**保存**します。  
  
         ![CustomerSearch サービスからキーワードを削除](../technical-guides/media/sentinetwp-removekeyword-2.png "SentinetWP_RemoveKeyword_2")  
  
    3.  これで、同じキーワードを割り当てる (**TestKeyword**) に、 **basicHttpBinding**エンドポイント、**バージョン 2**の同じサービス。  
  
8.  もう一度テスト メッセージを送信、**行程クライアントのテスト**今回は、カウンターがインクリメントの basicHttpBinding と共に配置されているサービスのバージョン 2 を表す ダイアログ ボックスに注意してください。