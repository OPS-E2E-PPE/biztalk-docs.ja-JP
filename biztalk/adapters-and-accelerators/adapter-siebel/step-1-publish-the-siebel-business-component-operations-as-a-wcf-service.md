---
title: "手順 1: WCF サービスとしての Siebel ビジネス コンポーネント操作の公開 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: acfa0c36-50f1-45c1-9fc2-e5e5cedaa6a0
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1dc83a0531460f513d146e2d03d0ef7e0a7c529f
ms.sourcegitcommit: 6b6d905bbef7796c850178e99ac293578bb58317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2017
---
# <a name="step-1-publish-the-siebel-business-component-operations-as-a-wcf-service"></a>手順 1: WCF サービスとしての Siebel ビジネス コンポーネント操作を公開します。
![4 のステップ 1](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")  
  
 **所要時間:** 10 分  
  
 **目標:**インターネット インフォメーション サービス (IIS) または Windows プロセス アクティブ化サービス (WAS) などのホスト環境でホストできる WCF サービスを生成する、WCF アダプター サービス開発ウィザードを使用することができます。 このトピックでは、ウィザードを使用して WCF サービスのファイルを生成する方法を示します。  
  
## <a name="prerequisites"></a>前提条件  
 ウィザードを実行する前に、次のようにインストールします。  
  
-   [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]いずれかで、**完了**オプションまたは**カスタム**オプション (を選択して**ツール**は、このオプションで)。 これには、WCF アダプター サービス開発ウィザードの Visual Studio テンプレートがインストールされます。  
  
-   [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]  
  
-   必要な Siebel クライアント。  
  
 これらの前提条件の詳細については、次を参照してください。、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]インストール ガイドです。 インストール ガイドがインストールされている通常\<インストール ドライブ >: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents です。  
  
## <a name="publish-the-siebel-business-components-as-a-wcf-service"></a>WCF サービスとしての Siebel ビジネス コンポーネントを公開します。  
  
1.  開始[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、し、プロジェクトを作成します。  
  
2.  **新しいプロジェクト** ダイアログ ボックスから、**プロジェクトの種類**ペインで、 **Visual c#**です。 **テンプレート**ペインで、 **WCF アダプタ サービス**です。  
  
     またはから、**プロジェクトの種類**] ウィンドウで、展開**Visual c#**、し、[ **Web**です。 **テンプレート**ペインで、 **WCF アダプタ サービス**です。  
  
    > [!NOTE]
    >  Web 開発コンポーネントでは、Visual Studio がインストールされている場合、 **WCF アダプタ サービス**テンプレートもサポートされてから、**新しい web サイト**オプション。  
  
3.  名前と、ソリューションの場所を指定し、クリックして**OK**です。 WCF アダプター サービス開発ウィザードを開始します。  
  
4.  [ようこそ] ページで、をクリックして**次**です。  
  
5.  操作の選択 ページで、Siebel システムへの接続への接続文字列を指定します。 そのためには次を行います。  
  
    1.  **バインディングを選択**一覧で、をクリックして**siebelBinding**、クリックして**構成**です。  
  
    2.  **アダプターの構成**ダイアログ ボックスで、をクリックして、**セキュリティ**タブです。  
  
    3.  **クライアント資格情報の種類**一覧で、 **Username**、し、ユーザー名と Siebel システムへの接続にパスワードを指定します。  
  
    4.  クリックして、 **URI プロパティ**タブをクリックし、接続パラメーターの値を指定します。 詳細については、接続 URI の[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を参照してください[Creat Siebel システム接続 URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)です。  
  
        > [!NOTE]
        >  接続パラメーター (XML の特殊文字) などの予約文字を含める場合は、そのままを指定する必要がありますのでは、 **URI プロパティ** タブでは、エスケープ文字を使用せずします。 ただし、URI で直接指定する場合、 **URI の構成**フィールドと接続パラメーターは、予約文字を含める、適切なエスケープ文字を使用して接続パラメーターを指定する必要があります。  
  
    5.  クリックして、**バインド プロパティ**タブをクリックし、対象となる操作に、必要な場合、バインド プロパティの値を指定します。  
  
         バインドのプロパティの詳細については、次を参照してください。 [BizTalk Adapter for Siebel のバインド プロパティ読む](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)です。  
  
    6.  をクリックして**OK**、順にクリック**接続**です。 接続が確立されると、接続状態は表示**接続**です。  
  
6.  操作の選択] ページで、[、**選択コントラクト型**一覧で、をクリックして**クライアント (送信操作)**です。  
  
7.  **カテゴリを選択**ボックスで、展開、Siebel**ビジネス オブジェクト**Siebel リポジトリ内のビジネス オブジェクトの一覧を表示するノードです。 この例では、次の操作を行います。  
  
    1.  展開して、**アカウント**クリックして、ビジネス オブジェクト、**アカウント**ビジネス コンポーネントです。  
  
    2.  **利用可能なカテゴリと操作**ボックスで、選択、**クエリ**操作、およびクリック**追加**です。 選択した操作が記載されて、**カテゴリと操作を追加**ボックス。  
  
         ![Siebel ビジネス コンポーネント操作の選択](../../adapters-and-accelerators/adapter-siebel/media/ed0cb649-dc4d-49ce-9541-c491c9cc9ac9.gif "ed0cb649-dc4d-49ce-9541-c491c9cc9ac9")  
  
8.  操作の選択 ページで、をクリックして**次**です。  
  
9. [サービスの構成とエンドポイントの動作] ページで、サービスとエンドポイント動作を構成する値を指定します。  
  
    1.  **サービス動作構成**ボックスで、次の値を指定します。  
  
        |プロパティの|値を指定します。|  
        |----------------------|-----------------------|  
        |EnableMetadataExchange|これを設定して**True** metadata exchange エンドポイントを作成します。 値を設定する**True**、サービス メタデータを Ws-metadata Exchange (MEX) や HTTP/GET 要求などの標準化プロトコルを使用して利用できるようにします。<br /><br /> 既定値は**False**です。|  
        |IncludeExceptionDetailsinFault|これを設定して**True**デバッグのためのクライアントに返される SOAP エラーの詳細にマネージ例外情報を含めます。 既定値は**False**です。|  
        |名前|サービス動作の構成の名前です。|  
        |UseServiceCertificate|WCF のメッセージ レベルのセキュリティ モードを使用するかどうかを指定します。 既定値は**True**です。<br /><br /> このチュートリアルでは、設定する必要がこれ**False**です。|  
        |FindValue|X.509 証明書ストアで検索する値を指定する文字列。<br /><br /> **注:**場合にのみ、このプロパティの値を指定**UseServiceCertificate**に設定されている**True**です。|  
        |StoreLocation|サービスがクライアントの証明書の検証に使用できる証明書ストアの場所を指定する値。<br /><br /> **注:**場合にのみ、このプロパティの値を指定**UseServiceCertificate**に設定されている**True**です。|  
        |StoreName|開く X.509 証明書ストアの名前です。<br /><br /> **注:**場合にのみ、このプロパティの値を指定**UseServiceCertificate**に設定されている**True**です。|  
        |X509FindType|実行する X.509 検索の種類。<br /><br /> **注:**場合にのみ、このプロパティの値を指定**UseServiceCertificate**に設定されている**True**です。|  
  
        > [!NOTE]
        >  証明書および関連付けられたプロパティの詳細については、次を参照してください。 [X509ClientCertificateCredentialsElement プロパティ](https://msdn.microsoft.com/library/system.servicemodel.configuration.x509clientcertificatecredentialselement_properties.aspx)です。
  
    2.  **エンドポイント動作の構成**ボックスで、次の値を指定します。  
  
        |プロパティの|値を指定します。|  
        |----------------------|-----------------------|  
        |[認証の種類]|-この設定**ClientCredentialUserNamePassword**を WCF サービスを使用しているとき、ユーザー名とパスワードを指定するようにクライアントを有効にします。<br /><br /> -この設定**HTTPUserNamePassword** HTTP ヘッダーの一部としてユーザー名とパスワードを指定するクライアントを有効にします。<br /><br /> -この設定**自動**を通じて資格情報を指定するクライアントを最初に有効にする、 **ClientCredential**インターフェイスです。 これが失敗した場合、クライアントは HTTP ヘッダーの一部として資格情報を渡すことができます。<br /><br /> 既定値は**自動**です。WCF サービスを使用する Microsoft Office SharePoint Server のこの設定の値として**HTTPUserNamePassword**です。|  
        |名前|エンドポイント動作の構成の名前を指定します。|  
        |UsernameHeader|ユーザー名ヘッダーの名前です。 この例では、指定**MyUserHeader**です。 HTTP ヘッダーの詳細についてを参照してください「のサポートをカスタム HTTP ヘッダーと SOAP ヘッダー」 [http://go.microsoft.com/fwlink/?LinkId=106692](http://go.microsoft.com/fwlink/?LinkId=106692)です。<br /><br /> **注:**場合は、このプロパティの値を指定する必要があります、**認証の種類**に設定されている**HTTPUserNamePassword**です。 場合**認証の種類**に設定されている**自動**、このプロパティはオプションです。|  
        |PasswordHeader|パスワード ヘッダーの名前です。 この例では、指定**MyPassHeader**です。 HTTP ヘッダーの詳細についてを参照してください「のサポートをカスタム HTTP ヘッダーと SOAP ヘッダー」 [http://go.microsoft.com/fwlink/?LinkId=106692](http://go.microsoft.com/fwlink/?LinkId=106692)です。<br /><br /> **注:**場合は、このプロパティの値を指定する必要があります、**認証の種類**に設定されている**HTTPUserNamePassword**です。 場合**認証の種類**に設定されている**自動**、このプロパティはオプションです。|  
  
     次の図は、値を指定して、サービスの構成とエンドポイントの動作 ページを示します。  
  
     ![サービスとエンドポイントの動作 ページを構成する](../../adapters-and-accelerators/adapter-sap/media/0a286b0c-7f0d-46c5-9b56-29bef3a1deea.gif "0a286b0c-7f0d-46c5-9b56-29bef3a1deea")  
  
10. サービスの構成およびエンドポイントの動作 ページで、**次**です。  
  
11. サービス エンドポイントのバインドの構成とアドレス ページで、**を構成するコントラクトを選択**ボックスには、操作の選択 ページでは、操作を選択した Siebel ビジネス コンポーネントのコントラクトが一覧表示されます。 **[選択したコントラクトの操作**ボックスには、各成果物の管理の選択] ページを選択した操作が表示されます。  
  
12. **されたコントラクトのバインディングとアドレスを構成する**ボックスで、次の値を指定します。  
  
    |プロパティの|値を指定します。|  
    |----------------------|-----------------------|  
    |バインドの構成|ウィザードは、基本 HTTP バインドのみをサポートします。 バインド構成のフィールドが自動的に設定されます、 *System.ServiceModel.Configuration.BasicHttpBindingElement*です。<br /><br /> 省略記号ボタンをクリックして**([...])** HTTP バインディングのプロパティを変更します。 セキュリティで保護された通信チャネルを使用する必要があります、常に設定、**モード**プロパティを**トランスポート**です。 ウィザードの既定値の設定、**モード**プロパティとして**トランスポート**です。<br /><br /> 公開されるその他のバインディングの詳細については、次を参照してください。 [BasicHttpBindingElement クラス](https://msdn.microsoft.com/library/system.servicemodel.configuration.basichttpbindingelement.aspx)です。|  
    |[エンドポイント名]|コントラクトのエンドポイント名を指定します。|  
  
     このページの他のフィールドは、前のページで指定した値に基づいて自動的に入力します。  
  
     **[適用]**をクリックします。 この手順はすべて、コントラクトの下に表示されます、**を構成するコントラクトを選択**ボックス。  
  
    > [!NOTE]
    >  このページの任意の値を指定しない場合は、すべてのコントラクトの既定値が受け入れられます。  
  
     次の図は、サービス エンドポイントのバインドの構成と指定した値とアドレス ページを示します。  
  
     ![サービス エンドポイントのバインドとアドレスの構成](../../adapters-and-accelerators/adapter-siebel/media/467d3e18-027d-4218-9d72-0740c1f559e3.gif "467d3e18-027d-4218-9d72-0740c1f559e3")  
  
13. サービス エンドポイントのバインドの構成とアドレス ページで、をクリックして**次**です。 [概要] ページには、選択された Siebel ビジネス コンポーネントと、その、下にある操作を各ビジネス コンポーネントを選択して、コントラクトのツリー構造が一覧表示します。  
  
14. 概要を確認し、をクリックして**完了**です。  
  
15. ウィザードは、WCF サービスを作成し、次のファイルを追加、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]プロジェクト。  
  
    1.  .svc ファイルです。 これは、WCF サービスのファイルです。 ウィザードでは、各コントラクトに対して 1 つのファイルを生成します。  
  
    2.  Web.config ファイルです。  
  
    3.  サービス コード (.cs ファイル)。  
  
16. WCF サービスを発行します。  
  
    1.  SSL には、インターネット インフォメーション サービス (IIS) を有効にすることを確認します。 参照してください[SSL を設定する方法](https://docs.microsoft.com/iis/manage/configuring-security/how-to-set-up-ssl-on-iis)です。
  
    2.  ソリューション エクスプ ローラーでプロジェクトを右クリックし、をクリックして**発行**です。  
  
    3.  **Web の発行** ダイアログ ボックスで、WCF サービスの URL を指定します。 例:  
  
        ```  
        https://<computer_name>/Siebel_Account/  
        ```  
  
    4.  **コピー**ボックスで、クリックして**すべてのプロジェクト ファイル**です。  
  
    5.  **[パブリッシュ]**をクリックします。  
  
17. WCF サービスが正常に公開されていることを確認します。  
  
    1.  IIS の Microsoft 管理コンソールを起動します。 をクリックして**開始**、をポイント**管理ツール**、順にクリック**インターネット インフォメーション サービス**です。  
  
    2.  サービスを発行したノードに移動します。 **Siebel_Account**サービスに移動**インターネット インフォメーション サービス** > **\<コンピューター名 >**  >  **Web サイト** > **既定の Web サイト** > **Siebel_Account**です。  
  
    3.  右側のペインで BusinessObjects_Account_Account_Operation.svc ファイルを右クリックし、をクリックして**参照**です。  
  
    4.  WSDL を取得するための URL を使用して、Web ページが表示されます。 Svcutil コマンドを使用してメタデータの取得をテストすることがあります。 たとえば、Siebel_Account サービスのメタデータを取得するコマンドには。  
  
        ```  
        svcutil.exe https://localhost/Siebel_Account/BusinessObjects_Account_Account_Operation.svc?wsdl  
        ```  
  
## <a name="next-steps"></a>次の手順  
 Siebel ビジネス コンポーネントの WCF サービスがあるようになりました。 ビジネス データ カタログ定義エディターを使用すると、Siebel ビジネス コンポーネント操作用のアプリケーション定義ファイルを作成できます。 参照してください[手順 2: Siebel ビジネス コンポーネント操作のアプリケーション定義ファイルを作成](../../adapters-and-accelerators/adapter-siebel/step-2-create-an-application-definition-file-for-siebel-business-component.md)手順についてはします。 アプリケーション定義ファイルは、LOB データが格納されているとは、格納されている形式を識別します。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 1: SharePoint サイト上の Siebel システムからのデータの表示](../../adapters-and-accelerators/adapter-siebel/tutorial-1-presenting-data-from-a-siebel-system-on-a-sharepoint-site.md)