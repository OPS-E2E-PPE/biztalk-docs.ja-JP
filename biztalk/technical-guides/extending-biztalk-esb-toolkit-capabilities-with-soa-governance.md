---
title: SOA ガバナンスと BizTalk ESB Toolkit の機能を拡張 |Microsoft ドキュメント
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
ms.openlocfilehash: f872d24c7c792d01f80463da0e3c27f31d76d8ee
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299794"
---
# <a name="extending-biztalk-esb-toolkit-capabilities-with-soa-governance"></a>SOA ガバナンスと BizTalk ESB Toolkit の機能を拡張します。
[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]に付属して[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ツールと拡張するライブラリのコレクションで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]の疎結合および動的なメッセージング アーキテクチャをサポートする機能。 これは、サービスとコンシューマーとの間の迅速な仲介のためのツールを提供するミドルウェアとして機能します。 実行時に、最大限の柔軟性を有効にすると、[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]サービス エンドポイントの疎結合の構成とサービスとの対話の管理を簡略化します。  
  
 Sentinet の BizTalk Server の拡張機能の能力を増強する[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]Sentinet、SOA ガバナンスと、Microsoft プラットフォーム向けの API 管理ソフトウェア ソリューションと統合します。 Sentinet の最初のリリース[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]拡張機能の提供、 [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] BizTalk Server 2013 と統合する SOA リポジトリ リゾルバー [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]、および Visual Studio 2012。  
  
 方法については、このホワイト ペーパーで Sentinet SOA リゾルバー拡張[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]機能、Sentinet SOA リゾルバー、および最後に、Sentinet の SOA 競合回避モジュールを使用する方法をデモンストレーションするサンプルを構成する方法。  
  
## <a name="esb-toolkit-and-sentinet-soa-resolver"></a>ESB Toolkit と Sentinet SOA 競合回避モジュール  
 特に、ESB Toolkit リゾルバーが次を提供する必要があります。  
  
-   サービス エンドポイントとその構成の実行時の解決  
  
-   BizTalk ESB 疎結合メッセージング ソリューションです。  
  
 Sentinet の提供、堅牢で包括的な[SOA リポジトリ](http://www.nevatech.com/sentinet/soa-repository)SOA 統合ソリューションおよび SOA ガバナンスとランタイムの高度な管理機能を提供します。 Sentinet SOA 競合回避モジュールの提供の Sentinet SOA リポジトリと組み合わせると、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ESB アーキテクチャ高度な使いやすい ESB の構成、動的なメッセージのルーティングおよびメッセージ セキュリティの実装の機能を使用します。  
  
 概要レベル ダイアグラムの下 Sentinet SOA 競合回避モジュールの動作を示しています、[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]アーキテクチャ。  
  
 ![BizTalk ESB Toolkit の Sentinet](../technical-guides/media/sentinetwp-arch.png "SentinetWP_Arch")  
  
 実行時に、**エンドポイント解決およびルーティング**(つまり、ESB Toolkit の競合回避モジュールのフレームワークの一部) 上の図のコンポーネントがインスタンス化する (Visual Studio 行程デザイナーで作成した) 行程ドキュメントを使用特定の競合回避モジュールおよびサービス エンドポイントとその構成を提供する競合回避モジュールを要求します。 行程自体が、サービス エンドポイントへの参照を使用して構成する競合回避モジュールは、レジストリやリポジトリで要求されたエンドポイントを検索するこの参照を使用できるようにします。 デザイン時 (行程が作成される) 場合、既知のサービス エンドポイントの実際の物理アドレスでないと、サービスに必要なセキュリティ ポリシーは、どちらもします。 以降の段階では、ランタイムを使用して、ESB Toolkit は、必要なサービスのセキュリティ設定を含む実際の物理サービス アドレスにメッセージを送信する、出口動的送信ポートを構成するサービス エンドポイントを解決します。 サービス エンドポイント アドレス、通信プロトコル、またはセキュリティ要件は、レジストリまたはリポジトリが構成のみを変更する場合は、更新しています。 ESB または BizTalk Server アイテムのランタイム構成を更新する必要はありません。  
  
## <a name="how-does-the-sentinet-resolver-add-value-to-an-esb-toolkit-application"></a>Sentinet のリゾルバーでは、方法は ESB Toolkit のアプリケーションに、値して追加のですか。  
 SOA リポジトリと共に Sentinet のリゾルバーを使用しての 2 つの主な利点は次のとおりです。  
  
-   解決済みの外部サービス エンドポイント – ほとんどの場合、クライアントの id を割り当てる解決 ESB エンドポイントは (ユーザー名/パスワード、特定の Windows アカウントの資格情報や特定の X.509 などの外部サービスを呼び出すための特定のクライアント id が必要です。証明書)。 これは、その他の ESB の競合回避モジュール/レジストリで適切に処理されないが非常に一般的なセキュリティ要件です。  
  
-   以前の制限を回避するのに-セキュリティ情報へのアクセスを制限するその他の競合回避モジュールは、必要なセキュリティ id を持つ複雑な XML を Tmodel を手動で構成を使用できます。 ただし、レジストリ/リポジトリの一部として、セキュリティ情報の保存は、適切なアプローチではありません。 これにより、サービス コンシューマーなど、ユーザー名やパスワードなど、サービスにアクセスするセキュリティの詳細に簡単にアクセスします。  
  
 Sentinet のリゾルバー Sentinet SOA リポジトリ機能を柔軟にし、指定安全に標準またはカスタムの WCF エンドポイント動作を使用して解決 ESB エンドポイントに、特定のクライアント id を割り当てます。 Sentinet では、セキュリティ情報を含む Sentinet のリゾルバー、および Sentinet SOA リポジトリではなくを構成することによって、これを実現します。 Sentinet のリゾルバーで構成されているすべてのクライアントの資格情報は暗号化された形式で格納されます。  
  
 これに加えて、Sentinet のリゾルバーと Sentinet SOA リポジトリを使用するその他の利点の一部を次に示します。  
  
-   包括的な SOA リポジトリを提供します。 リポジトリは、サービス メタデータの内容、およびアクセスするサービス id ポリシー、サービスのバージョンなどのサポートを提供します。  
  
-   サービスの WSDL をアップロードすることによって、Sentinet レジストリに物理サービスを登録するの容易。  
  
-   では包括的で使いやすい Sentinet 管理コンソールです。 コンソールでは、すべてのサービス メタデータへの管理アクセスを提供し、の成果物をサービス操作のアクセスと、データのスキーマ、サービス エンドポイント、セキュリティ ポリシーなどの単純なユーザー インターフェイスに関連付けられています。  
  
-   管理および解決済みのエンドポイントのカスタム動作の構成。 Sentinet のリゾルバーでは、解決済みのエンドポイントを完全にカスタマイズでき、簡単に構成可能なエンドポイントの動作を提供します。  
  
-   さまざまな検索条件の Sentinet のリゾルバーを構成するオプションです。 行程では、サービス エンドポイントに割り当てられているすべてのキーワードを定義したり、リポジトリのサービス階層でサービスを指すサービス パスを使用することができます。  
  
-   高度な競合回避モジュールの機能をテストします。 Visual Studio 行程デザイナーから直接 Sentinet のリゾルバー構成をテストすることができます。 その他の競合回避モジュールは、エンドポイントの基本的なプロパティに関する情報を提供することができますのみ、Sentinet のリゾルバーは解決済みのエンドポイントに関する拡張情報を提供します。 エンドポイントの基本的なプロパティだけでなく Sentinet のリゾルバーを識別するプロパティ解決 Sentinet リポジトリ内のサービスとエンドポイントの場所が表示されます。 Itinerary デザイナーは、Sentinet のリゾルバーとそのさまざまな検索条件結果に与える解決行程自体は実行時に使用する前にテストできます。  
  
## <a name="installing-the-sentinet-biztalk-server-extensions"></a>Sentinet BizTalk サーバーの拡張機能をインストールします。  
 ダウンロードして Sentinet BizTalk の拡張機能をインストールすることができます[ここ](http://www.nevatech.com/download)です。 拡張機能をインストールすると、ESB Toolkit、ドキュメント、および拡張機能を使用する方法のサンプルの Sentinet のリゾルバーがインストールされます。  
  
 インストールして Sentinet BizTalk サーバーの拡張機能を構成する方法の詳細を示す、ドキュメントが利用可能な製品のダウンロードの一部として。  
  
## <a name="using-the-sentinet-biztalk-server-extensions"></a>Sentinet の BizTalk Server の拡張機能の使用  
 このセクションの Sentinet BizTalk サーバーの拡張機能を使用し、上記で説明した機能を紹介する方法について説明します。  
  
### <a name="prerequisites"></a>前提条件  
 ホワイト ペーパーではこの手順では、次のインストールし、構成があることが想定しています。  
  
-   Visual Studio 2012。  
  
-   BizTalk Server 2013。 手順については、次を参照してください。 [BizTalk Server 2013 のインストール](http://msdn.microsoft.com/library/jj248688\(v=bts.80\).aspx)です。  
  
-   BizTalk Server ESB Toolkit です。 手順については、次を参照してください。[のインストールと構成、Microsoft BizTalk ESB Toolkit](http://msdn.microsoft.com/library/jj684558\(v=bts.80\).aspx)です。  
  
-   Sentinet の BizTalk Server の拡張機能です。 手順については、ドキュメントを参照して、使用可能な製品のダウンロードの一部として[ここ](http://www.nevatech.com/download)です。  
  
### <a name="register-a-web-service"></a>Web サービスを登録します。  
 Sentinet インフラストラクチャによって管理されている web サービスは、リポジトリに登録する必要があります。 このホワイト ペーパーでは、Sentinet インストール パッケージに同梱されている WCF 顧客の検索サンプル サービスを使用します。  
  
1.  開始、**顧客検索**サンプル サービス Sentinet インストール パッケージでインストールします。 管理者として顧客の検索サンプルを起動して、ポリシーのバインドを選択 (例: **wsHttpBinding**) をクリックし、**開始**です。  
  
2.  サービスが実行されていると、クリックして、**ビュー Wsdl**ブラウザーを開き、サービス メタデータの URL と、サービス WSDL にリンクします。 ブラウザーのアドレス バーからのメタデータ URL をコピーします。  
  
3.  ブラウザーを開き、URL を入力します (`https://[computer-name]/sentinet`) Sentinet 管理コンソールを起動します。 ログインを選択、**リポジトリ**のルート要素、**リポジトリ**ビュー パネルです。 右クリックし、**リポジトリ**ルート要素とをクリックして、**追加 > サービス > SOAP**メニュー オプション。  
  
4.  **サービスの追加** ダイアログ ボックスの**URL から WSDL**オプションを以前にコピーするサービス メタデータの URL を貼り付けるを順にクリックして**次へ**です。  
  
     ![サービスの URL を追加](../technical-guides/media/sentinetwp-addserviceurl.png "SentinetWP_AddServiceURL")  
  
5.  ウィザードでは、サービス メタデータのダウンロードを開始します。 ダウンロードが完了したら、Web サービスのツリー構造が表示されます。 サービスの名前を指定し、をクリックして**完了**Sentinet リポジトリにサービス メタデータをアップロードします。  
  
     ![Web サービスの構造](../technical-guides/media/sentinetwp-servicestructure.png "SentinetWP_ServiceStructure")  
  
6.  サービスは、バージョン 1 としてリポジトリにインポートされます。 バージョンを選択し、エンドポイントを選択します。 **エンドポイントの詳細**ペインの下部で、クリックして、**添付ファイル** タブをクリックして**変更**です。  
  
     ![サービス エンドポイントを変更](../technical-guides/media/sentinetwp-serviceendpoint.png "SentinetWP_ServiceEndpoint")  
  
7.  エンドポイントの詳細 タブで、をクリックして、(**+**) に対して署名**キーワード**、エンドポイントに関連付けるにキーワードを入力して (たとえば、 **TestKeyword**)、およびをクリックして**保存**です。 キーワードは、SOA リポジトリ内のエンドポイント タグに (または識別子) として使用されます。  
  
     ![キーワードを指定する](../technical-guides/media/sentinetwp-enterkeyword.png "SentinetWP_EnterKeyword")  
  
 新しいバージョンを追加する上記の手順を繰り返して、 **CustomerSearch**サービスは、ですが、異なるバインド、たとえば**basicHttpBinding**です。 このホワイト ペーパーの後半を示します Sentinet のリゾルバーをさまざまなサービス (または同じサービスのさまざまなバージョン) に解決できる方法、サービス エンドポイントを検索キーワードを関連付けることによってのみです。  
  
### <a name="configure-sentinet-resolver"></a>Sentinet のリゾルバーを構成します。  
 このセクションでは、単純な BizTalk ESB 行程デザイナー プロジェクトで、Sentinet のリゾルバーを構成する方法とキーワードを使用して、サービス エンドポイントに解決するには一意にする方法を具体的には示しています。 このセクションでは、ESB のすべてのメッセージを送信せずに Visual Studio 自体から競合回避モジュールをテストする方法も示します。  
  
1.  Visual Studio を起動し、作成、 **BizTalk ESB 行程デザイナー**プロジェクト。  
  
2.  ソリューション エクスプ ローラーでは、行程デザイナーで開く旅程をダブルクリックします。  
  
3.  ツールボックスからドラッグ アンド ドロップ、**行程サービス**デザイナー画面上の図形です。  
  
4.  選択、**行程サービス**図形し、変更、**行程サービス エクステンダー**プロパティを**エクステンダーのメッセージング**ドロップダウン リストからです。  
  
     ![Message Extender のプロパティを設定](../technical-guides/media/sentinetwp-setmessageextender.png "SentinetWP_SetMessageExtender")  
  
5.  右クリックし、**リゾルバー**内の要素、**行程サービス**図形をクリックして**新しいリゾルバーを追加**です。  
  
     ![新しいリゾルバーを追加](../technical-guides/media/sentinetwp-addnewresolver.png "SentinetWP_AddNewResolver")  
  
6.  新しいリゾルバー要素を選択し、その名前を変更 (例: **MyResolver**)、およびの**リゾルバーの実装**プロパティを選択**Sentinet のリゾルバー拡張機能**します。  
  
     ![リゾルバーの実装を設定](../technical-guides/media/sentinetwp-addresolverimplementation.png "SentinetWP_AddResolverImplementation")  
  
7.  指定して、**アクション**と**キーワード**Sentinet のリゾルバー拡張機能のプロパティです。 Sentinet リポジトリに追加しましたサービスを一意に解決するのには、これらのプロパティを使用します。 同様に他のプロパティの Sentinet のリゾルバー拡張機能を指定できますがあります。 これらのプロパティに関する詳細については、Sentinet BizTalk の拡張機能のユーザー ガイドを参照してください。  
  
    |プロパティ|Description|  
    |--------------|-----------------|  
    |操作|呼び出されるサービス操作を一意に識別するメッセージのアクション ヘッダー。 この action ヘッダーはサービスの WSDL の一部であり、Sentinet 管理コンソール ユーザー インターフェイスから、操作の要求メッセージのプロパティ または、サービス WSDL で検出されたことができますです。|  
    |キーワード|キーワードを指定 (例: **TestKeyword**) Sentinet 管理コンソールでサービスに割り当てられています。|  
  
     次のスクリーン ショットは、指定されたアクションとキーワードのプロパティを表示、 **MyResolver**構成します。  
  
     ![Sentinet のリゾルバー構成](../technical-guides/media/sentinetwp-resolverconfig.png "SentinetWP_ResolverConfig")  
  
8.  構成に変更を保存します。  
  
#### <a name="advanced-resolver-configuration"></a>高度な競合回避モジュールの構成  
 Sentinet BizTalk 拡張機能の構成アプリケーション変更**Sentinet.BizTalk.config**パッケージのインストール フォルダーのルートにあるファイル (既定の場所は`<installation drive>:\Program Files\Nevatech\Sentinet BizTalk Extensions\Sentinet.BizTalk.config`)。 ファイルの外部で変更することができます**Sentinet BizTalk 拡張機能の構成**をアプリケーションに高度な構成オプションを提供します。 たとえば、多くの実用的な ESB シナリオで解決エンドポイント提供する必要はサービス エンドポイント アドレスとバインディング、だけでなく、特定のクライアント id (のユーザー名/パスワード、特定の Windows アカウント資格情報、または X.509 クライアントでも証明書)。 適切なクライアント id がない場合は、ESB 出口送信ポートは、外部サービスを呼び出すため失敗します。 Sentinet のリゾルバーでは、行程開発者が適切なクライアントのエンドポイント id を提供する特定のエンドポイント動作を割り当てることができます。 複数のエンドポイントの動作は、事前構成済みの標準の WCF エンドポイントの動作として、 **Sentinet.BizTalk.config** Sentinet のリゾルバーから行程で参照できるファイル、および、特定のエンドポイント動作動作の名前を指定することによって、構成、**エンドポイント動作の解決**プロパティです。  
  
### <a name="test-the-resolver-configuration"></a>構成をテストする競合回避モジュール  
 関連するプロパティ値を指定して Sentinet のリゾルバーを構成した後は、Visual Studio 自体から競合回避モジュールをテストできます。  
  
1.  デザイン サーフェイスに追加した Sentinet のリゾルバーを右クリックし、**行程サービス**図形をクリックして**テスト構成の競合回避モジュール**です。  
  
     出力ウィンドウには、これの抜粋は、次に示すに似ています、テストの結果が表示されます。  
  
    ```  
    ***** Resolved Service Endpoint *****  
  
    Service Path and Name          : /CustomerSearch  
    Service Id                     : 2b6d686a-cae1-4b7b-93da-99affef98478  
    Service Version                : 1  
    Endpoint Name                  : WSHttpBinding_ICustomerSearch  
    Endpoint Address               : http://btscloudcar/CustomerSearch/1  
    ```  
  
     競合回避モジュールでのエンドポイントが返されることに注意してください、 **CustomerSearch**サービス**バージョン 1**する検索条件 (**TestKeyword**) が接続されています。  
  
2.  削除、 **TestKeyword**に関連付けられている、**バージョン 1**の**CustomerSearch**サービスし、サービスの 2 番目のバージョンのエンドポイントに関連付けます。  
  
    1.  Sentinet の管理コンソールを開き、**バージョン 1**下にある、 **CustomerSearch**サービスを wsHttpBinding エンドポイントをクリックし、をクリックして、**添付ファイル**タブをクリックして**変更**です。  
  
         ![CustomerSearch サービスからキーワードを削除](../technical-guides/media/sentinetwp-removekeyword.png "SentinetWP_RemoveKeyword")  
  
    2.  キーワードを削除 をクリックする前に入力したキーワードに対してボタンをクリックして**はい**をクリックしてメッセージ ボックスで、**保存**です。  
  
         ![CustomerSearch サービスからキーワードを削除](../technical-guides/media/sentinetwp-removekeyword-2.png "SentinetWP_RemoveKeyword_2")  
  
    3.  これで、同じキーワードを割り当てる (**TestKeyword**) に、 **basicHttpBinding**エンドポイント、**バージョン 2**同じサービスのです。  
  
3.  Visual Studio に戻るし、競合回避モジュールの構成をもう一度テストします。 追加した Sentinet のリゾルバーを右クリックし、**行程サービス**図形をクリックして**テスト構成の競合回避モジュール**です。  
  
     出力ウィンドウには、これの抜粋は、次に示すに似ています、テストの結果が表示されます。  
  
    ```  
    ***** Resolved Service Endpoint *****  
  
    Service Path and Name          : /CustomerSearch  
    Service Id                     : 5b9e5878-7016-44ab-9f0e-5282a8c3e508  
    Service Version                : 2  
    Endpoint Name                  : BasicHttpBinding_ICustomerSearch  
    Endpoint Address               : http://btscloudcar/CustomerSearch/2  
    ```  
  
4.  競合回避モジュールが現在の詳細を返す方法に注意してください、**バージョン 2**サービスの場合でも変更していない ESB 行程アプリケーションの任意のものです。  
  
 キーワードを割り当てる (**TestKeyword**) サービスのバージョン 1 に戻す (で、 **WSHttpBinding**エンドポイント)。  
  
## <a name="using-the-sentinet-biztalk-server-extensions"></a>Sentinet の BizTalk Server の拡張機能の使用  
 このセクションでを見てみましょう ESB リゾルバー、と共に、Sentinet BizTalk 拡張機能を使用してサービスを一意に識別して、サービスまたはメッセージを送信するクライアントを最小限に抑えると共に、そのサービスにメッセージ、またはまったく変更をルーティングする方法です。 2 つのシナリオをテストします。  
  
-   (接続されているキーワード) を使用して、Sentinet リポジトリに登録されているサービスにサンプル メッセージを送信します。 Sentinet の管理コンソールを使用して、サービスのポリシーのバインドを変更し、別のサンプル メッセージを送信します。 このシナリオでは、サービスのセキュリティ ポリシーの変更もへの影響も、クライアント アプリケーションも ESB 行程を示します。  
  
-   (キーワードを使ってアタッチ Sentinet リポジトリに登録されているサービス エンドポイントにサンプル メッセージを送信します。 同じキーワードを同じサービスの別のバージョンにアタッチし、メッセージを再送信します。 このシナリオでは、サービスの新しいバージョンにメッセージをルーティング キーワードを異なるサービスのバージョンに自動的にアタッチする方法を示します。  
  
 これらのシナリオをテストするには、次のサンプルを使用します。  
  
-   **顧客の Search サービス**Sentinet インストーラーに用意されています。 このサービスは、[スタート] メニューから起動できます。  
  
-   **Nevatech.Vsb.BizTalk.Samples** Sentinet インストーラーに用意されているソリューションです。 このサンプルは、「`<installation drive>:\Program Files\Nevatech\Sentinet BizTalk Extensions\Samples`です。  
  
-   ESB です。Itinerary.Test サンプルが付属[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]です。 これは、「`<install drive>:\Program Files (x86)\Microsoft BizTalk ESB Toolkit\ESBSource.zip\Source\Samples\Itinerary\Source\ESB.Itinerary.Test`サンプル メッセージ顧客の Search サービスをテストするために使用されます。  
  
#### <a name="to-test-the-sentinet-resolver-by-changing-the-service-policy-binding"></a>サービスのポリシーのバインドを変更することによって、Sentinet のリゾルバーをテストするには  
  
1.  確認、 **CustomerSearch** wsHttpBinding と共に配置されるサービスが実行されています。  
  
2.  **Nevatech.Vsb.BizTalk.Samples**サンプルについては、開いている**CustomerSearch.Search.itinerary****サービス エンドポイントを解決するには**下にある、**メッセージExtender**内で、**メッセージをルーティング**図形、および、**キーワード**プロパティなど、キーワードを指定**TestKeyword**です。  
  
     ![キーワードを割り当てる](../technical-guides/media/sentinetwp-assignkeyword.png "SentinetWP_AssignKeyword")  
  
3.  、旅行計画に変更を保存し、モデルをエクスポートします。 Itinerary デザイナー画面で、任意の場所を右クリックし、クリックして**モデルのエクスポート**です。  
  
4.  BizTalk Server 管理コンソールを右クリックし、 **Microsoft.Practices.ESB**アプリケーションでは、[インポート] を [バインド] をクリックします。 ESB 競合回避モジュールのサンプルの場所に移動`<installation drive>:\Program Files\Nevatech\Sentinet BizTalk Extensions\Samples\ESB Resolver`を開き、 **BizTalk.Bindings.xml**ファイル。 これを作成、 **Sentinet 送信請求-応答**と**一方向の Sentinet**サンプル旅程に必要なポートを送信します。  
  
     また、確認の送信ポートと受信場所のすべての**Microsoft.Practices.ESB** BizTalk アプリケーションの登録し、開始します。  
  
5.  開く、 **ESB です。Itinerary.Test**アプリケーションが、それをビルドして実行します。 行程テスト クライアントで起動する、次の手順に従います。  
  
    1.  行程テスト クライアントで、 **Web サービス オプション**チェック ボックスをオフ**を使用して WCF サービス**を選択し、**方法の 2 つのサービス**です。  
  
    2.  **サービスの種類**ドロップダウン リストで、**メッセージング**です。  
  
    3.  をクリックして**ロード行程**に移動し、 **CustomerSearch.Search.Itinerary.xml**サンプルのプロジェクトにあるファイル**ExportedItineraries** フォルダー`<installation drive>:\Program Files\Nevatech\Sentinet BizTalk Extensions\Samples\ESB Resolver\ExportedItineraries`.  
  
    4.  省略記号ボタン (**..**) **メッセージの読み込み**グループに移動して**CustomerSearch.Search.Request.xml**プロジェクトの配置**SampleMessages** フォルダー`<installation drive>:\Program Files\Nevatech\Sentinet BizTalk Extensions\Samples\ESB Resolver\SampleMessages`.  
  
    5.  をクリックして**要求を提出**で応答が受信したことを確認してください。  
  
6.  **CustomerSearch**  ダイアログ ボックスで、1 つずつ、カウンタが増加します。  
  
7.  Sentinet の管理コンソールでは、wsHttpBinding ではなく、basicHttpBinding を使用するエンドポイントの詳細を更新します。  
  
    1.  サービス エンドポイントを選択し、をクリックして、**詳細** タブをクリックして**変更**です。  
  
    2.  **詳細** タブで、省略記号ボタン (**.**) で、**ポリシー**  セクションを起動する、**ポリシーの変更**ウィザード。  
  
         ![ポリシーの変更ウィザードを起動して](../technical-guides/media/sentinetwp-modifypolicy-1.png "SentinetWP_ModifyPolicy_1")  
  
    3.  最初のページに保持ポリシーの種類として**プライベート** をクリックし、**次**です。  
  
    4.  2 番目のページで変更、 **wsHttpBinding** XML 要素を**basicHttpBinding** (大文字小文字を区別)、をクリックして**完了**です。  
  
         ![ポリシーのバインドを更新](../technical-guides/media/sentinetwp-modifypolicy-2.png "SentinetWP_ModifyPolicy_2")  
  
    5.  をクリックして**保存**エンドポイントの詳細に変更を保存します。  
  
8.  停止、 **CustomerSearch**サービス, からバインドを変更する**wsHttpBinding**に**basicHttpBinding**、サービスをもう一度開始します。  
  
     ![異なるバインディングでサービスを再起動](../technical-guides/media/sentinetwp-restartcustservice.png "SentinetWP_RestartCustService")  
  
9. **行程クライアントのテスト**顧客の検索サービスをもう一度テスト メッセージを送信します。 顧客サービスの検索 ダイアログ ボックスで、カウンターがもう一度 1 だけインクリメントしたに注意してください。  
  
     Sentinet 管理コンソールから、メッセージは正常に受信すると変更の詳細にバックアップ ポリシー **wsHttpBinding**です。 同様に、停止、**顧客検索**サービス、wsHttpBinding にポリシーを変更し、サービスを開始します。  
  
 これは、itinerary またはクライアントを変更することがなく Sentinet リポジトリ内のサービスの詳細をターゲット更新済みサービスのエンドポイントをその場で更新する方法について説明します。  
  
#### <a name="to-test-the-sentinet-resolver-by-changing-keyword-assignments"></a>キーワードの割り当てを変更することによって、Sentinet のリゾルバーをテストするには  
  
1.  2 つのインスタンスを確認してください**CustomerSearch** basicHttpBinding、wsHttpBinding を展開するサービスを実行しています。  
  
2.  **Nevatech.Vsb.BizTalk.Samples**サンプルについては、開いている**CustomerSearch.Search.itinerary****サービス エンドポイントを解決するには**下にある、**メッセージExtender**内で、**メッセージをルーティング**図形、および、**キーワード**プロパティなど、キーワードを指定**TestKeyword**です。  
  
     ![キーワードを割り当てる](../technical-guides/media/sentinetwp-assignkeyword.png "SentinetWP_AssignKeyword")  
  
3.  、旅行計画に変更を保存し、モデルをエクスポートします。 Itinerary デザイナー画面で、任意の場所を右クリックし、クリックして**モデルのエクスポート**です。  
  
4.  BizTalk Server 管理コンソールを右クリックし、 **Microsoft.Practices.ESB**アプリケーションでは、[インポート] を [バインド] をクリックします。 ESB 競合回避モジュールのサンプルの場所に移動`<installation drive>:\Program Files\Nevatech\Sentinet BizTalk Extensions\Samples\ESB Resolver`を開き、 **BizTalk.Bindings.xml**ファイル。 これを作成、 **Sentinet 送信請求-応答**と**一方向の Sentinet**サンプル旅程に必要なポートを送信します。  
  
     また、確認の送信ポートと受信場所のすべての**Microsoft.Practices.ESB** BizTalk アプリケーションの登録し、開始します。  
  
5.  開く、 **ESB です。Itinerary.Test**アプリケーションが、それをビルドして実行します。 行程テスト クライアントで起動する、次の手順に従います。  
  
    1.  行程テスト クライアントで、 **Web サービス オプション**チェック ボックスをオフ**を使用して WCF サービス**を選択し、**方法の 2 つのサービス**です。  
  
    2.  **サービスの種類**ドロップダウン リストで、**メッセージング**です。  
  
    3.  をクリックして**ロード行程**に移動し、 **CustomerSearch.Search.Itinerary.xml**サンプルのプロジェクトにあるファイル**ExportedItineraries** フォルダー`<installation drive>:\Program Files\Nevatech\Sentinet BizTalk Extensions\Samples\ESB Resolver\ExportedItineraries`.  
  
    4.  省略記号ボタン (**..**) **メッセージの読み込み**グループに移動して**CustomerSearch.Search.Request.xml**プロジェクトの配置**SampleMessages** フォルダー`<installation drive>:\Program Files\Nevatech\Sentinet BizTalk Extensions\Samples\ESB Resolver\SampleMessages`.  
  
    5.  をクリックして**要求を提出**で応答が受信したことを確認してください。  
  
6.  **CustomerSearch**  ダイアログ ボックスで、1 つずつ、カウンタが増加します。  
  
7.  Sentinet 管理コンソールで、削除、 **TestKeyword**に関連付けられている、**バージョン 1**の**CustomerSearch**サービスし、に関連付ける**バージョン 2**サービス。  
  
    1.  Sentinet の管理コンソールを開き、**バージョン 1**下にある、 **CustomerSearch**サービスを wsHttpBinding エンドポイントをクリックし、をクリックして、**添付ファイル**タブをクリックして**変更**です。  
  
         ![CustomerSearch サービスからキーワードを削除](../technical-guides/media/sentinetwp-removekeyword.png "SentinetWP_RemoveKeyword")  
  
    2.  キーワードを削除 をクリックする前に入力したキーワードに対してボタンをクリックして**はい**をクリックしてメッセージ ボックスで、**保存**です。  
  
         ![CustomerSearch サービスからキーワードを削除](../technical-guides/media/sentinetwp-removekeyword-2.png "SentinetWP_RemoveKeyword_2")  
  
    3.  これで、同じキーワードを割り当てる (**TestKeyword**) に、 **basicHttpBinding**エンドポイント、**バージョン 2**同じサービスのです。  
  
8.  もう一度テスト メッセージを送信、**行程クライアントのテスト**し、今回は、カウンターはインクリメントされます ダイアログ ボックスの basicHttpBinding と共に配置されている、サービスのバージョン 2 を表すことを確認します。