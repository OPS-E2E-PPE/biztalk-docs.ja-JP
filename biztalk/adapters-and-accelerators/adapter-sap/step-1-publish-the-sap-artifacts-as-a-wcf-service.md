---
title: "手順 1: WCF サービスとして SAP アイテムを発行する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF service, generating a
- WCF Adapter Service Development Wizard , using the
- WCF Adapter Service Development Wizard
- SAP artifacts, publishing as a WCF service
ms.assetid: bd3087b0-e20f-4b75-beef-a913336d767b
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a83dd69e7c66c8ce8ff1af78662392dd0aa66ff2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="step-1-publish-the-sap-artifacts-as-a-wcf-service"></a>手順 1: WCF サービスとして SAP アイテムを公開します。
![4 のステップ 1](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")  
  
 **所要時間:** 10 分  
  
 **目標:**インターネット インフォメーション サービス (IIS) または Windows プロセス アクティブ化サービス (WAS) などのホスト環境でホストできる WCF サービスを生成する、WCF アダプター サービス開発ウィザードを使用することができます。 このトピックでは、ウィザードを使用して WCF サービスのファイルを生成する方法を示します。  
  
## <a name="prerequisites"></a>前提条件  
 ウィザードを実行する前に、次のようにインストールします。  
  
-   [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]いずれかで、**完了**オプションまたは**カスタム**オプション (を選択して**ツール**は、このオプションで)。 これにより、インストール、 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] WCF アダプター サービス開発ウィザード用のテンプレートです。  
  
-   [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)][!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。  
  
-   必要な SAP クライアント ライブラリです。  
  
 これらの前提条件の詳細については、次を参照してください。、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]インストール ガイドです。 インストール ガイドがインストールされている通常\<インストール ドライブ\>: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents です。  
  
### <a name="to-publish-the-sap-artifacts-as-a-wcf-service"></a>WCF サービスとして SAP アイテムをパブリッシュするには  
  
1.  開始[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、し、プロジェクトを作成します。  
  
2.  **新しいプロジェクト** ダイアログ ボックスから、**プロジェクトの種類**ペインで、 **Visual c#**です。 **テンプレート**ペインで、 **WCF アダプタ サービス**です。  
  
     またはから、**プロジェクトの種類**] ウィンドウで、展開**Visual c#**、し、[ **Web**です。 **テンプレート**ペインで、 **WCF アダプタ サービス**です。  
  
    > [!NOTE]
    >  インストールした場合[!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)]Web 開発コンポーネントと、 **WCF アダプタ サービス**テンプレートもサポートされてから、**新しい web サイト**オプション。  
  
3.  名前と、ソリューションの場所を指定し、クリックして**OK**です。 WCF アダプター サービス開発ウィザードを開始します。  
  
4.  [ようこそ] ページで、をクリックして**次**です。  
  
5.  操作の選択 ページで、SAP システムに接続する接続文字列を指定します。 そのためには次を行います。  
  
    1.  **バインディングを選択**一覧で、をクリックして**sapBinding**、クリックして**構成**です。  
  
    2.  **アダプターの構成**ダイアログ ボックスで、をクリックして、**セキュリティ**タブです。  
  
    3.  **クライアント資格情報の種類**一覧で、 **Username**、有効な SAP ユーザー名と、SAP システムへの接続にパスワードを指定します。  
  
    4.  クリックして、 **URI プロパティ**タブをクリックし、接続パラメーターの値を指定します。 詳細については、接続 URI の[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を参照してください[SAP システム接続 URI を作成する](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)です。  
  
        > [!NOTE]
        >  接続パラメーター (XML の特殊文字) などの予約文字を含める場合は、そのままを指定する必要がありますのでは、 **URI プロパティ** タブでは、エスケープ文字を使用せずします。 ただし、URI で直接指定する場合、 **URI の構成**ボックスと接続パラメーターは、予約文字を含める、適切なエスケープ文字を使用して接続パラメーターを指定する必要があります。  
  
    5.  クリックして、**バインド プロパティ**タブをクリックし、対象となる操作に、必要な場合、バインド プロパティの値を指定します。 このチュートリアルでは、特定の顧客の販売注文の一覧を取得する BAPI_SALESORDER_GETLIST RFC が呼び出されます。 販売注文情報は、日付列を含めるも可能性があります。 設定することをお勧め、日付列の値を取得するときに、 **EnableSafeTyping**にプロパティのバインド**True**メタデータを生成するときにします。 このプロパティが設定されている場合、SAP DATS データ型は文字列として表示します。  
  
         SAP のデータ型を同等の .NET 型にマップする方法の詳細については、次を参照してください。 [SAP の基本データ型](../../adapters-and-accelerators/adapter-sap/basic-sap-data-types.md)です。  
  
         バインドのプロパティの詳細については、次を参照してください。 [mySAP Business Suite のバインドのプロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)です。  
  
    6.  をクリックして**OK**、順にクリック**接続**です。 接続が確立されると、接続状態は表示**接続**です。  
  
6.  操作の選択] ページで、[、**選択コントラクト型**一覧で、をクリックして**クライアント (送信操作)**です。  
  
7.  **カテゴリを選択**ボックスで、SAP アイテムの種類を展開します。 たとえば、展開、 **RFC**ノードを含む WCF サービスを生成する RFC 機能グループを表示します。  
  
8.  **利用可能なカテゴリと操作**ボックスで、WCF サービスを生成し、をクリックする操作を選択**追加**です。 選択した操作が記載されて、**カテゴリと操作を追加**ボックス。  
  
    > [!NOTE]
    >  各成果物を 1 つ以上の操作を追加することができます。 異なる SAP アイテムの操作を追加することもできます。 たとえば、1 つの操作の RFC および IDOC 用に別を追加することができます。 さらに、特定の操作に対して検索式のワイルドカード文字を指定して検索できます。 サポートされている特殊文字およびノードのレベルを検索できる操作の詳細については、次を参照してください[Visual Studio を使用して追加ウィザードで、アダプター メタデータの SAP への接続。](../../adapters-and-accelerators/adapter-sap/connecting-to-sap-in-visual-studio-using-add-adapter-metadata-wizard.md)  
  
     この例では、SD_RFC_CUSTOMER_GET と BAPI_SALESORDER_GETLIST Rfc が追加されます。  
  
    > [!NOTE]
    >  SAP システムのバージョンによっては、SD_RFC_CUSTOMER_GET ではなく RFC_CUSTOMER_GET RFC を公開します。  
  
     ![SAP アイテムの選択](../../adapters-and-accelerators/adapter-sap/media/f944f9a0-7387-46cb-8eb6-337344d01d29.gif "f944f9a0-7387-46cb-8eb6-337344d01d29")  
  
9. 操作の選択 ページで、をクリックして**次**です。  
  
10. [サービスの構成とエンドポイントの動作] ページで、サービスとエンドポイント動作を構成する値を指定します。  
  
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
        >  証明書および関連付けられたプロパティの詳細についてを参照してください「X509ClientCertificateCredentialsElement プロパティ」 [http://go.microsoft.com/fwlink/?LinkId=103771](http://go.microsoft.com/fwlink/?LinkId=103771)です。  
  
    2.  **エンドポイント動作の構成**ボックスで、次の値を指定します。  
  
        |プロパティの|値を指定します。|  
        |----------------------|-----------------------|  
        |[認証の種類]|-この設定**ClientCredentialUserNamePassword**を WCF サービスを使用するときに、ユーザー名とパスワードを指定するようにクライアントを有効にします。<br /><br /> -この設定**HTTPUserNamePassword** HTTP ヘッダーの一部としてユーザー名とパスワードを指定するクライアントを有効にします。<br /><br /> -この設定**自動**を通じて資格情報を指定するクライアントを最初に有効にする、 **ClientCredential**インターフェイスです。 これが失敗した場合、クライアントは HTTP ヘッダーの一部として資格情報を渡すことができます。<br /><br /> 既定値は**自動**です。WCF サービスを使用する Microsoft Office SharePoint Server のこの設定の値として**HTTPUserNamePassword**です。|  
        |名前|エンドポイント動作の構成の名前を指定します。|  
        |UsernameHeader|ユーザー名ヘッダーの名前です。 この例では、指定**MyUserHeader**です。 HTTP ヘッダーの詳細についてを参照してください「のサポートをカスタム HTTP ヘッダーと SOAP ヘッダー」 [http://go.microsoft.com/fwlink/?LinkId=106692](http://go.microsoft.com/fwlink/?LinkId=106692)です。<br /><br /> **注:**場合は、このプロパティの値を指定する必要があります、**認証の種類**に設定されている**HTTPUserNamePassword**です。 場合**認証の種類**に設定されている**自動**、このプロパティはオプションです。|  
        |PasswordHeader|パスワード ヘッダーの名前です。 この例では、指定**MyPassHeader**です。 HTTP ヘッダーの詳細についてを参照してください「のサポートをカスタム HTTP ヘッダーと SOAP ヘッダー」 [http://go.microsoft.com/fwlink/?LinkId=106692](http://go.microsoft.com/fwlink/?LinkId=106692)です。<br /><br /> **注:**場合は、このプロパティの値を指定する必要があります、**認証の種類**に設定されている**HTTPUserNamePassword**です。 場合**認証の種類**に設定されている**自動**、このプロパティはオプションです。|  
  
     次の図は、値を指定して、サービスの構成とエンドポイントの動作 ページを示します。  
  
     ![サービスとエンドポイントの動作 ページを構成する](../../adapters-and-accelerators/adapter-sap/media/0a286b0c-7f0d-46c5-9b56-29bef3a1deea.gif "0a286b0c-7f0d-46c5-9b56-29bef3a1deea")  
  
11. サービスの構成およびエンドポイントの動作 ページで、**次**です。  
  
12. サービス エンドポイントのバインドの構成とアドレス ページで、**を構成するコントラクトを選択**ボックスには、操作の選択 ページでは、操作を選択した SAP アイテムが一覧表示されます。  
  
     たとえば、RFC および IDOC、成果物を選択した場合、**を構成するコントラクトを選択**RFC および IDOC の両方を一覧表示します。 RFC のみを選択した場合、ボックスは RFC のみを示します。  
  
13. **[選択したコントラクトの操作**ボックスには、各成果物の管理の選択] ページを選択した操作が表示されます。  
  
14. **されたコントラクトのバインディングとアドレスを構成する**ボックスで、次の値を指定します。  
  
    |プロパティの|値を指定します。|  
    |----------------------|-----------------------|  
    |バインドの構成|ウィザードは、基本 HTTP バインドのみをサポートします。 バインド構成のフィールドが自動的に設定されます、 *System.ServiceModel.Configuration.BasicHttpBindingElement*です。<br /><br /> 省略記号ボタンをクリックして**([...])** HTTP バインディングのプロパティを変更します。 セキュリティで保護された通信チャネルを使用する必要があります、常に設定、**モード**プロパティを**トランスポート**です。 ウィザードの既定値の設定、**モード**プロパティとして**トランスポート**です。<br /><br /> 公開されるその他のバインディングの詳細についてを参照してください「BasicHttpBindingElement メンバー」 [http://go.microsoft.com/fwlink/?LinkId=103773](http://go.microsoft.com/fwlink/?LinkId=103773)です。|  
    |[エンドポイント名]|コントラクトのエンドポイント名を指定します。|  
  
     このページの他のフィールドは、前のページで指定した値に基づいて自動的に入力します。  
  
     **[適用]**をクリックします。 この手順はすべて、コントラクトの下に表示されます、**を構成するコントラクトを選択**ボックス。  
  
    > [!NOTE]
    >  このページの任意の値を指定しない場合は、すべてのコントラクトの既定値が受け入れられます。  
  
     次の図は、サービス エンドポイントのバインドの構成と指定した値とアドレス ページを示します。  
  
     ![サービス エンドポイントのバインドとアドレスの構成](../../adapters-and-accelerators/adapter-sap/media/356e297c-9893-494c-a834-9d0b8b42da2e.gif "356e297c-9893-494c-a834-9d0b8b42da2e")  
  
15. サービス エンドポイントのバインドの構成とアドレス ページで、をクリックして**次**です。  [概要] ページには、SAP アイテムと、その操作を各成果物を選択して、下にあるツリー構造が一覧表示します。  
  
16. 概要を確認し、をクリックして**完了**です。  
  
17. ウィザードは、WCF サービスを作成し、次のファイルを追加、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]プロジェクト。  
  
    1.  .svc ファイルです。 これは、WCF サービスのファイルです。 ウィザードでは、各コントラクトに対して 1 つのファイルを生成します。  
  
    2.  Web.config ファイルです。  
  
    3.  サービス コード (.cs ファイル)  
  
18. WCF サービスを発行します。  
  
    1.  SSL には、インターネット インフォメーション サービス (IIS) を有効にすることを確認します。 IIS の SSL を有効にする方法については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=197170](http://go.microsoft.com/fwlink/?LinkId=197170)です。  
  
    2.  ソリューション エクスプ ローラーでプロジェクトを右クリックし、をクリックして**発行**です。  
  
    3.  **Web の発行** ダイアログ ボックスで、WCF サービスの URL を指定します。 例:  
  
        ```  
        https://<computer_name>/Customer_Order/  
        ```  
  
    4.  **コピー**ボックスで、クリックして**すべてのプロジェクト ファイル**です。  
  
    5.  **[パブリッシュ]**をクリックします。  
  
19. WCF サービスが正常に公開されていることを確認します。  
  
    1.  IIS の Microsoft 管理コンソールを起動します。 をクリックして**開始**、 をポイント**管理ツール**、順にクリック**インターネット インフォメーション サービス (IIS) マネージャー**です。  
  
    2.  サービスを発行したノードに移動します。 **Customer_Order**サービスに移動**インターネット インフォメーション サービス** > **\<コンピューター名\>**  > **Websites** > **既定の Web サイト** > **Customer_Order**です。  
  
    3.  右側のペインで Rfc.svc ファイルを右クリックし、をクリックして**参照**です。  
  
    4.  WSDL を取得するための URL を使用して、Web ページが表示されます。 メタデータの取得を使用してテストすることも、 **svcutil**コマンド。 たとえば、Customer_Order サービスのメタデータを取得するコマンドには。  
  
        ```  
        svcutil.exe https://<computer_name>/Customer_Order/Rfc.svc?wsdl  
  
        ```  
  
## <a name="next-step"></a>次の手順  
 SAP アイテム用のアプリケーション定義ファイルを作成するには、ビジネス データ カタログ定義エディターを使用します。 参照してください[手順 2: SAP 成果物のため、アプリケーション定義ファイルを作成する](../../adapters-and-accelerators/adapter-sap/step-2-create-an-application-definition-file-for-the-sap-artifacts.md)手順についてはします。 アプリケーション定義ファイルは、LOB データが格納されているとは、格納されている形式を識別します。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 1: SAP システムからのデータを SharePoint サイトに表示する](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md)