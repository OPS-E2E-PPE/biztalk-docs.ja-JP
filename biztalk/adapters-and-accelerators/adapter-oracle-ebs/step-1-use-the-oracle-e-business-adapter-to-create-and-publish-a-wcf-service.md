---
title: "手順 1: Oracle E-business アダプターを使用して作成して、WCF サービスを発行する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7cd76f6f-600f-4eb5-8eee-8f3604d0fef4
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c03f11ad2849b3d46e9e489a1657aa043fb0e61
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-use-the-oracle-e-business-adapter-to-create-and-publish-a-wcf-service"></a>手順 1: Oracle E-business アダプターを使用して作成して、WCF サービスを発行するには
![4 のステップ 1](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")  
  
 **所要時間:** 15 分  
  
 **目標:**使用することができます、[!INCLUDE[afsvcdevwizlong](../../includes/afsvcdevwizlong-md.md)]をインターネット インフォメーション サービス (IIS) または Windows プロセス アクティブ化サービス (WAS) などのホスト環境でホストできる Oracle E-business Suite 成果物から WCF サービスを生成します。 このトピックでは、ウィザードを使用して WCF サービスのファイルを生成する方法を示します。  
  
## <a name="prerequisites"></a>前提条件  
 ウィザードを実行する前に、次のようにインストールします。  
  
-   [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]いずれかで、**完了**オプションまたは**カスタム**オプション (を選択して**ツール**は、このオプションで)。 これにより、インストール、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]用のテンプレート、[!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)]です。  
  
-   [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)][!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。  
  
 これらの前提条件の詳細については、次を参照してください。、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]インストール ガイドです。 インストール ガイドがインストールされている通常\<インストール ドライブ >: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents です。  
  
> [!NOTE]
>  作成する Microsoft Office SharePoint Server のサンプルに用意されている create_apps_artifacts.sql スクリプトを実行する必要があります、 **MS_SAMPLE_EMPLOYEE**インターフェイス テーブルに、**アプリケーション オブジェクト ライブラリ**アプリケーションです。 このインターフェイスのテーブルは、このチュートリアルで使用されます。  
  

  
##  <a name="Create_Service"></a>Oracle E-business 成果物の演算の WCF サービスを作成します。  
 このセクションでは、MS_SAMPLE 従業員インターフェイス テーブルに対する Select 操作の WCF サービスを作成する方法を説明します。  
  
#### <a name="to-create-a-wcf-service-for-the-select-operation-on-the-mssample-employee-interface-table"></a>MS_SAMPLE 従業員インターフェイス テーブルに対する Select 操作の WCF サービスを作成するには  
  
1.  開始[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、し、プロジェクトを作成します。  
  
2.  **新しいプロジェクト** ダイアログ ボックスから、**プロジェクトの種類**ペインで、 **Visual c#**です。 **テンプレート**ペインで、 **WCF アダプタ サービス**です。  
  
     またはから、**プロジェクトの種類**] ウィンドウで、展開**Visual c#**、し、[ **Web**です。 **テンプレート**ペインで、 **WCF アダプタ サービス**です。  
  
     ![[新しいプロジェクト] ダイアログ ボックス](../../adapters-and-accelerators/adapter-oracle-ebs/media/01-new-project.gif "01 _ new_project")  
  
    > [!NOTE]
    >  インストールした場合[!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)]Web 開発コンポーネントと、 **WCF アダプタ サービス**テンプレートもサポートされてから、**新しい Web サイト**オプション (**ファイル** > **新しい** > **Web サイト**)。  
    >   
    >  ただし、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]のみ、ファイル システム上に作成される Web サイトをサポートします。 そのため、新しい Web サイト ダイアログ ボックスで、Web サイトを作成中に、ファイル システムを場所の一覧でクリックしてください。  
  
3.  名前と、ソリューションの場所を指定し、クリックして**OK**です。 WCF[!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)]を開始します。  
  
4.  [ようこそ] ページで、をクリックして**次**です。  
  
5.  操作の選択 ページで、Oracle E-business Suite に接続する接続文字列を指定します。 そのためには次を行います。  
  
    1.  **バインディングを選択**一覧で、をクリックして**oracleEBSBinding**、クリックして**構成**です。  
  
    2.  **アダプターの構成**ダイアログ ボックスで、をクリックして、**バインドのプロパティ**タブです。  
  
        1.  下にある、**全般**カテゴリの**ClientCredentialType**選択バインディング プロパティ、 **EBusiness**です。  
  
        2.  下にある、 **OracleEBS**カテゴリで、適切な値を指定、 **OracleUserName**、 **OraclePassword**、および**OracleEBSResponsibilityName**プロパティをバインドします。 この場合、データベースの資格情報を指定する必要があります、 **OracleUserName**と**OraclePassword**プロパティをバインドします。  
  
        3.  下にある、**メタデータ**カテゴリの**EnableSafeTyping**選択バインディング プロパティ、 **True**です。 設定することをお勧め、日付列の値を取得する場合、 **EnableSafeTyping**にプロパティのバインド**True**メタデータを生成するときにします。  
  
    3.  クリックして、 **URI プロパティ**タブをクリックし、接続パラメーターの値を指定します。 詳細については、接続 URI の[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を参照してください[Oracle E-business Suite 接続 URI を作成](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md)です。  
  
    4.  クリックして、**セキュリティ** タブで、し、、**クライアント資格情報の種類**一覧で、 **Username**です。 有効な Oracle E-business Suite のユーザー名と Oracle E-business Suite への接続にパスワードを指定します。  
  
    5.  をクリックして**OK**をアダプターの構成 ダイアログ ボックスを閉じ、をクリックして**接続**です。 Visual Studio が正常に Oracle E-business Suite への接続を確立した後、接続状態が表示**接続**です。 操作の選択 ページに表示されている Oracle E-business Suite のメタデータを表示することもできます。  
  
6.  操作の選択] ページで、[、**選択コントラクト型**一覧で、をクリックして**クライアント (送信操作)**です。  
  
7.  **カテゴリを選択**ボックスに、アプリケーション オブジェクトのライブラリ アプリケーションで MS_SAMPLE_EMPLOYEE インターフェイス テーブルに移動します。 アダプター内の成果物を参照する方法については、次を参照してください。[参照、検索、および取得操作のメタデータの Oracle E-business](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)です。  
  
8.  **利用可能なカテゴリと操作**ボックスで、選択、**選択**操作、およびクリック**追加**です。 選択操作を追加、**カテゴリと操作を追加**ボックス。  
  
     ![Select 操作の追加](../../adapters-and-accelerators/adapter-oracle-ebs/media/02-msb-gui.gif "02 _ msb_gui")  
  
    > [!NOTE]
    >  各成果物を 1 つ以上の操作を追加することができます。 別の Oracle E-business Suite 成果物のための操作を追加することもできます。 たとえば、インターフェイス テーブルの 1 つの操作と同時実行プログラムを追加できます。 さらに、特定の操作に対して検索式のワイルドカード文字を指定して検索できます。 サポートされている特殊文字およびノードのレベルを検索できる操作の詳細については、次を参照してください。 [Oracle E-business Suite 操作の検索](../../adapters-and-accelerators/adapter-oracle-ebs/search-for-oracle-e-business-suite-operations.md)です。  
  
9. 操作の選択 ページで、をクリックして**次**です。  
  
10. [サービスの構成とエンドポイントの動作] ページで、サービスとエンドポイント動作を構成する値を指定します。  
  
    1.  **サービス動作構成**ボックスで、次の値を指定します。  
  
        |プロパティの|値を指定します。|  
        |----------------------|-----------------------|  
        |EnableMetadataExchange|これを設定して**True** metadata exchange エンドポイントを作成します。 値を設定する**True**、サービス メタデータを Ws-metadata Exchange (MEX) や HTTP/GET 要求などの標準化プロトコルを使用して利用できるようにします。 既定値は**False**です。|  
        |IncludeExceptionDetailsinFault|これを設定して**True**デバッグのためのクライアントに返される SOAP エラーの詳細にマネージ例外情報を含めます。 既定値は**False**です。|  
        |名前|サービス動作の構成の名前です。 このチュートリアルでは、次のように入力します。 **customServiceBehavior**です。|  
        |UseServiceCertificate|WCF のメッセージ レベルのセキュリティ モードを使用するかどうかを指定します。 既定値は**True**です。 このチュートリアルでは、設定する必要がこれ**False**です。|  
  
        > [!NOTE]
        >  このチュートリアルではサービス証明書使用しない、ため値を入力する必要はありません、 **FindValue**、 **StoreLocation**、 **StoreName**、および**X509FindType**プロパティです。 証明書および関連付けられたプロパティの詳細についてを参照してください「X509ClientCertificateCredentialsElement プロパティ」 [http://go.microsoft.com/fwlink/?LinkId=103771](http://go.microsoft.com/fwlink/?LinkId=103771)です。  
  
    2.  **エンドポイント動作の構成**ボックスで、次の値を指定します。  
  
        |プロパティの|値を指定します。|  
        |----------------------|-----------------------|  
        |[認証の種類]|WCF サービスを使用する Microsoft Office SharePoint Server のこの設定の値として**HTTPUserNamePassword**です。 これにより、クライアントが HTTP ヘッダーの一部としてユーザー名とパスワードを指定できます。|  
        |名前|エンドポイント動作の構成の名前を指定します。 このチュートリアルでは、次のように入力します。 **customEndpointBehavior**です。|  
        |UsernameHeader|ユーザー名ヘッダーの名前です。 この例では、指定**MyUserHeader**です。 HTTP ヘッダーの詳細についてを参照してください「のサポートをカスタム HTTP ヘッダーと SOAP ヘッダー」 [http://go.microsoft.com/fwlink/?LinkId=106692](http://go.microsoft.com/fwlink/?LinkId=106692)です。 **注:**場合は、このプロパティの値を指定する必要があります、**認証の種類**に設定されている**HTTPUserNamePassword**です。 場合**認証の種類**に設定されている**自動**、このプロパティはオプションです。|  
        |PasswordHeader|パスワード ヘッダーの名前です。 この例では、指定**MyPassHeader**です。 HTTP ヘッダーの詳細についてを参照してください「のサポートをカスタム HTTP ヘッダーと SOAP ヘッダー」 [http://go.microsoft.com/fwlink/?LinkId=106692](http://go.microsoft.com/fwlink/?LinkId=106692)です。 **注:**場合は、このプロパティの値を指定する必要があります、**認証の種類**に設定されている**HTTPUserNamePassword**です。 場合**認証の種類**に設定されている**自動**、このプロパティはオプションです。|  
  
     次の図は、値を指定して、サービスの構成とエンドポイントの動作 ページを示します。  
  
     ![サービスとエンドポイントの動作 ページを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/media/03-service-and-endpoint-behavior.gif "03 _ service_and_endpoint_behavior")  
  
11. サービスの構成およびエンドポイントの動作 ページで、**次**です。  
  
12. [サービス エンドポイントのバインドの構成とアドレス] ページで、**を構成するコントラクトを選択**構成した成果物 (MS_SAMPLE_EMPLOYEE) が表示されます。 **[選択したコントラクトの操作**ボックスが表示されたら、**選択**成果物の管理の選択] ページの選択した操作。  
  
13. **されたコントラクトのバインディングとアドレスを構成する**ボックスで、次の値を指定します。  
  
    |プロパティの|値を指定します。|  
    |----------------------|-----------------------|  
    |バインドの構成|ウィザードは、基本 HTTP バインドのみをサポートします。 バインド構成のフィールドが自動的に設定されます、 *System.ServiceModel.Configuration.BasicHttpBindingElement*です。<br /><br /> 省略記号ボタンをクリックして**([...])** HTTP バインディングのプロパティを変更します。 セキュリティで保護された通信チャネルを使用する必要があります、常に設定、**モード**プロパティを**トランスポート**です。 ウィザードの既定値の設定、**モード**プロパティとして**トランスポート**です。<br /><br /> 公開されるその他のバインディングの詳細についてを参照してください「BasicHttpBindingElement メンバー」 [http://go.microsoft.com/fwlink/?LinkId=103773](http://go.microsoft.com/fwlink/?LinkId=103773)です。|  
    |[エンドポイント名]|コントラクトのエンドポイント名を指定します。|  
  
     このページの他のフィールドは、前のページで指定した値に基づいて自動的に入力します。  
  
     **[適用]**をクリックします。  
  
    > [!NOTE]
    >  このページの任意の値を指定しない場合は、すべてのコントラクトの既定値が受け入れられます。  
  
     次の図は、サービス エンドポイントのバインドの構成と指定した値とアドレス ページを示します。  
  
     ![サービス エンドポイントのバインドとアドレスの構成](../../adapters-and-accelerators/adapter-oracle-ebs/media/04-service-endpoint-binding.gif "04 _ service_endpoint_binding")  
  
14. サービス エンドポイントのバインドの構成とアドレス ページで、をクリックして**次**です。  [概要] ページには、Oracle E-business Suite 成果物と成果物の選択された操作のツリー構造が一覧表示します。  
  
15. 概要を確認し、をクリックして**完了**です。  
  
16. ウィザードは、WCF サービスを作成し、次のファイルを追加、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]プロジェクト。  
  
    1.  .svc ファイルです。 これは、WCF サービスのファイルです。 ウィザードでは、各コントラクトに対して 1 つのファイルを生成します。  
  
    2.  Web.config ファイルです。  
  
    3.  サービス コード (.cs ファイル)  
  
##  <a name="cs"></a>.Cs ファイルを変更します。  
 Oracle E-business Suite 成果物を使用して、外のサービスを作成する場合、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Microsoft Office SharePoint Server でビジネス データ一覧 Web パーツから使用して、WHERE 句から始まる完全なフィルター句を指定することが求め. たとえば、名は"John"した従業員を検索する場合は、ビジネス データ一覧 Web パーツでは、次のフィルター句を指定する必要があります。  
  
```  
where NAME like ‘JOHN’  
```  
  
 ただし、する場合は、入力をユーザーにのみ、名前を入力としてフィルター句に全体のフィルター句を実際に触れることがなく、することがコードを追加、Microsoft Office でビジネス データ一覧 Web パーツから取り込むフィルター句を変更する .cs ファイルに WHERE 句の形式での Oracle E-business を渡すことの SharePoint サーバー。  
  
 たとえばの場合はこのチュートリアルでは、ユーザーが Microsoft Office SharePoint Server でビジネス データ一覧 Web パーツに従業員の名前を入力し、その従業員のレコードを取得する場合できます追加する、次のコード .cs ファイルに。  
  
```  
SelectResponse InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE.Select(SelectRequest request)   
{  
     request.FILTER = "where NAME like '" + request.FILTER + "'"; // The code to avoid the users from specifying the WHERE clause in the filter from Business Data List Web Part.  
     return base.Channel.Select(request);  
}  
```  
  
##  <a name="Publish"></a>WCF サービスを発行します。  
 IIS で SSL が有効であることを確認してください。 IIS の SSL を有効にする方法については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=197170](http://go.microsoft.com/fwlink/?LinkId=197170)です。  
  
 WCF サービスを発行します。  
  
1.  ソリューション エクスプ ローラーでプロジェクトを右クリックし、をクリックして**発行**です。  
  
2.  **Web の発行** ダイアログ ボックスで、WCF サービスの URL を指定します。 例:  
  
    ```  
    https://<COMPUTER_NAME>:<PORT_NUMBER>/MS_SAMPLE_EMPLOYEE/  
    ```  
  
    > [!NOTE]
    >  SSL が有効な場所には、WCF サービスを公開する必要があります。 値、つまり、**ターゲットの場所**ボックスは、"https://"を始める必要があります。 ユーザーの資格情報は、HTTP ヘッダーに渡されるため、ウィザードは自動的に SSL 暗号化を意味するセキュリティ モードとして「トランスポート」を使用するアダプターのバインドの動作を構成します。 もちろん、戻っておよびの値を変更するために web.config ファイルを編集できます、 **\<セキュリティ モード >**パラメーターは、SSL を使用して常に推奨される選択肢機密情報がクリア テキストで転送がある場合、HTTP ヘッダー。  
  
3.  **コピー**ボックスで、クリックして**すべてのプロジェクト ファイル**です。  
  
4.  **[パブリッシュ]**をクリックします。  
  
5.  WCF サービスが正常に公開されていることを確認します。  
  
    1.  IIS の Microsoft 管理コンソールを起動します。 をクリックして**開始**、 をポイント**管理ツール**、順にクリック**インターネット インフォメーション サービス (IIS) マネージャー**です。  
  
    2.  サービスを発行したノードに移動します。 **MS_SAMPLE_EMPLOYEE**サービスに移動**インターネット インフォメーション サービス** > **\<コンピューター名 >**  > **Websites** > **既定の Web サイト** > **MS_SAMPLE_EMPLOYEE**です。  
  
    3.  右側のペインで InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE.svc ファイルを右クリックし、をクリックして**参照**です。  
  
    4.  WSDL を取得するための URL を使用して、Web ページが表示されます。 メタデータの取得を使用してテストすることも、 **svcutil**コマンド。 たとえば、MS_SAMPLE_EMPLOYEE サービスのメタデータを取得するコマンドには。  
  
        ```  
        svcutil.exe https://<COMPUTER_NAME>:<PORT_NUMBER>/MS_SAMPLE_EMPLOYEE/InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE.svc?wsdl  
  
        ```  
  
## <a name="next-step"></a>次の手順  
 Oracle E-business Suite 成果物のアプリケーション定義ファイルを作成するには、ビジネス データ カタログ定義エディターを使用します。 手順については、次を参照してください。[手順 2: Oracle E-business Suite 成果物のため、アプリケーション定義ファイルを作成する](../../adapters-and-accelerators/adapter-oracle-ebs/step-2-create-an-application-definition-file-for-the-oracle-ebs-artifacts.md)です。 アプリケーション定義ファイルは、LOB データが格納されているとは、格納されている形式を識別します。  
  
## <a name="see-also"></a>参照  
 [チュートリアル: SharePoint サイト上の Oracle E-business Suite からデータを表示します。](Tutorial:%20Present%20data%20from%20Oracle%20E-Business%20Suite%20on%20a%20SharePoint%20Site.md)