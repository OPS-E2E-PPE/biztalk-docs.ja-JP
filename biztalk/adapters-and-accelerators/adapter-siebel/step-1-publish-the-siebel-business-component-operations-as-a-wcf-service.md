---
title: 手順 1:Siebel ビジネス コンポーネントの操作を WCF サービスとして発行する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: acfa0c36-50f1-45c1-9fc2-e5e5cedaa6a0
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b11d94de7e7b5d6ff9ced397d30c78235ad20bfe
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370682"
---
# <a name="step-1-publish-the-siebel-business-component-operations-as-a-wcf-service"></a>手順 1:Siebel ビジネス コンポーネントの操作を WCF サービスとして発行します。
![手順 4 の 1](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")  
  
 **所要時間:** 10 分  
  
 **目標:** WCF アダプター サービス開発ウィザードを使用して、インターネット インフォメーション サービス (IIS) または Windows プロセス アクティブ化サービス (WAS) などのホスティング環境でホストされる WCF サービスを生成することができます。 このトピックでは、ウィザードを使用して WCF サービスのファイルを生成する方法を示します。  
  
## <a name="prerequisites"></a>前提条件  
 ウィザードを実行する前に、次のようにインストールします。  
  
- [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] いずれかで、**完了**オプションまたは**カスタム**オプション (選択して**ツール**このオプションで)。 これにより、WCF アダプター サービス開発ウィザードには、Visual Studio テンプレートがインストールされます。  
  
- [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]  
  
- 必要な Siebel クライアント。  
  
  これらの前提条件の詳細については、次を参照してください。、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]インストール ガイドです。 通常、インストール ガイドにインストールされて\<インストール ドライブ\>: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents します。  
  
## <a name="publish-the-siebel-business-components-as-a-wcf-service"></a>WCF サービスとしての Siebel ビジネス コンポーネントを発行します。  
  
1. 開始[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、し、プロジェクトを作成します。  
  
2. **新しいプロジェクト** ダイアログ ボックスから、**プロジェクトの種類**ペインで、 **Visual c#** します。 **テンプレート**ペインで、 **WCF アダプタ サービス**します。  
  
    またはから、**プロジェクトの種類**ウィンドウで、展開**Visual c#**、し、 **Web**します。 **テンプレート**ペインで、 **WCF アダプタ サービス**します。  
  
   > [!NOTE]
   >  Web 開発コンポーネントでは、Visual Studio がインストールされている場合、 **WCF アダプタ サービス**テンプレートが表示されます、**新しい web サイト**オプション。  
  
3. ソリューションでは、場所と名前を指定し、クリックして**OK**します。 WCF アダプター サービス開発ウィザードを開始します。  
  
4. [ようこそ] ページで、次のようにクリックします。**次**します。  
  
5. 操作の選択 ページで、Siebel システムに接続する接続文字列を指定します。 そのためには次を行います。  
  
   1. **バインディングを選択**一覧で、[ **siebelBinding**、] をクリックし、**構成**。  
  
   2. **アダプターの構成**ダイアログ ボックスで、をクリックして、**セキュリティ**タブ。  
  
   3. **クライアント資格情報の種類**一覧で、 **Username**、し、ユーザー名と Siebel システムへの接続にパスワードを指定します。  
  
   4. をクリックして、 **URI プロパティ**タブをクリックし、接続パラメーターの値を指定します。 接続 URI の詳細についてはの[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を参照してください[Siebel システムの接続 URI を作成する](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)します。  
  
      > [!NOTE]
      >  接続パラメーターに XML の特殊文字) などの予約文字が含まれている場合、としてを指定する必要がありますのでは、 **URI プロパティ**タブ、つまり、エスケープ文字を使用せずします。 ただし、直接の URI を指定する場合、 **URI の構成**フィールドと接続パラメーターは、予約文字を含めることが、適切なエスケープ文字を使用して接続パラメーターを指定する必要があります。  
  
   5. をクリックして、**バインド プロパティ**タブをクリックし、対象と操作のために必要な場合、バインドのプロパティの値を指定します。  
  
       バインド プロパティの詳細については、次を参照してください。 [for Siebel のバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)します。  
  
   6. をクリックして**OK**、順にクリックします**Connect**します。 接続が確立されると、接続の状態が表示として**接続**します。  
  
6. 操作の選択] ページで、**選択のコントラクト型**一覧で、[**クライアント (送信操作)** します。  
  
7. **カテゴリを選択**ボックスで、展開、Siebel**ビジネス オブジェクト**Siebel リポジトリ内のビジネス オブジェクトの一覧を表示するノード。 この例では、次の操作を行います。  
  
   1.  展開、**アカウント**ビジネス オブジェクト、およびクリック、**アカウント**ビジネス コンポーネント。  
  
   2.  **利用可能なカテゴリと操作**ボックスで、選択、**クエリ**操作、およびクリック**追加**します。 選択した操作が記載されて、**カテゴリと操作を追加**ボックス。  
  
        ![Siebel ビジネス コンポーネント操作の選択](../../adapters-and-accelerators/adapter-siebel/media/ed0cb649-dc4d-49ce-9541-c491c9cc9ac9.gif "ed0cb649-dc4d-49ce-9541-c491c9cc9ac9")  
  
8. 操作の選択 ページで、次のようにクリックします。**次**します。  
  
9. サービスの構成およびエンドポイントの動作 ページで、サービスとエンドポイントの動作を構成する値を指定します。  
  
   1. **サービス動作構成**ボックスで、次の値を指定します。  
  
      |プロパティの|値を指定します。|  
      |----------------------|-----------------------|  
      |EnableMetadataExchange|これを設定**True** metadata exchange エンドポイントを作成します。 値を設定する**True**、サービス メタデータを Ws-metadata Exchange (MEX) や HTTP/GET 要求などの標準化プロトコルを使用して利用できるようにします。<br /><br /> 既定値は**False**します。|  
      |IncludeExceptionDetailsinFault|これを設定**True**デバッグのためのクライアントに返される SOAP エラーの詳細にマネージ例外情報を含めます。 既定値は**False**します。|  
      |名前|サービス動作の構成の名前です。|  
      |UseServiceCertificate|WCF のメッセージ レベルのセキュリティ モードを使用するかどうかを指定します。 既定値は**True**します。<br /><br /> このチュートリアルである必要がありますこれを設定して**False**します。|  
      |FindValue|X.509 証明書ストアで検索する値を指定する文字列。<br /><br /> **注:** 場合にのみ、このプロパティの値を指定**UseServiceCertificate**に設定されている**True**します。|  
      |StoreLocation|サービスは、クライアントの証明書の検証に使用できる証明書ストアの場所を指定する値。<br /><br /> **注:** 場合にのみ、このプロパティの値を指定**UseServiceCertificate**に設定されている**True**します。|  
      |StoreName|開く X.509 証明書ストアの名前です。<br /><br /> **注:** 場合にのみ、このプロパティの値を指定**UseServiceCertificate**に設定されている**True**します。|  
      |X509FindType|実行する X.509 検索の種類。<br /><br /> **注:** 場合にのみ、このプロパティの値を指定**UseServiceCertificate**に設定されている**True**します。|  
  
      > [!NOTE]
      >  証明書と関連付けられているプロパティの詳細については、次を参照してください。 [X509ClientCertificateCredentialsElement プロパティ](https://msdn.microsoft.com/library/system.servicemodel.configuration.x509clientcertificatecredentialselement_properties.aspx)します。
  
   2. **エンドポイント動作の構成**ボックスで、次の値を指定します。  
  
      |プロパティの|値を指定します。|  
      |----------------------|-----------------------|  
      |[認証の種類]|-この設定**ClientCredentialUserNamePassword** WCF サービスを使用しているとき、ユーザー名とパスワードを指定するクライアントを有効にします。<br /><br /> -この設定**HTTPUserNamePassword** HTTP ヘッダーの一部としてユーザー名とパスワードを指定するクライアントを有効にします。<br /><br /> -この設定**自動**最初から資格情報を指定するクライアントを有効にする、 **ClientCredential**インターフェイス。 これが失敗すると、クライアントは、HTTP ヘッダーの一部として資格情報を渡すことができます。<br /><br /> 既定値は**自動**します。WCF サービスを使用する Microsoft Office SharePoint server、として設定する必要があります**HTTPUserNamePassword**します。|  
      |名前|エンドポイントの動作の構成の名前を指定します。|  
      |UsernameHeader|ユーザー名ヘッダーの名前です。 この例では、指定**MyUserHeader**します。 HTTP ヘッダーの詳細についてを参照してください「のサポートのカスタム HTTP ヘッダーと SOAP ヘッダー」 [ http://go.microsoft.com/fwlink/?LinkId=106692](http://go.microsoft.com/fwlink/?LinkId=106692)します。<br /><br /> **注:** 場合、このプロパティの値を指定する必要があります、**認証の種類**に設定されている**HTTPUserNamePassword**します。 場合**認証の種類**に設定されている**自動**、このプロパティは省略可能です。|  
      |PasswordHeader|パスワード ヘッダーの名前です。 この例では、指定**MyPassHeader**します。 HTTP ヘッダーの詳細についてを参照してください「のサポートのカスタム HTTP ヘッダーと SOAP ヘッダー」 [ http://go.microsoft.com/fwlink/?LinkId=106692](http://go.microsoft.com/fwlink/?LinkId=106692)します。<br /><br /> **注:** 場合、このプロパティの値を指定する必要があります、**認証の種類**に設定されている**HTTPUserNamePassword**します。 場合**認証の種類**に設定されている**自動**、このプロパティは省略可能です。|  
  
      次の図は、値を指定して、サービスの構成およびエンドポイントの動作のページを示しています。  
  
      ![サービスとエンドポイントの動作 ページを構成する](../../adapters-and-accelerators/adapter-sap/media/0a286b0c-7f0d-46c5-9b56-29bef3a1deea.gif "0a286b0c-7f0d-46c5-9b56-29bef3a1deea")  
  
10. サービスの構成およびエンドポイントの動作 ページで、**次**します。  
  
11. サービス エンドポイントのバインドを構成し、アドレス ページで、**を構成する契約を選択**ボックスには、Siebel ビジネス コンポーネントを選択した操作の選択 ページで、操作のコントラクトが一覧表示されます。 **選択した契約の下での操作**ボックスには、各成果物の管理の選択 ページの選択した操作が表示されます。  
  
12. **アドレスとコントラクトのバインディング構成**ボックスで、次の値を指定します。  
  
    |プロパティの|値を指定します。|  
    |----------------------|-----------------------|  
    |バインドの構成|ウィザードでは、基本的な HTTP バインドのみサポートされます。 バインド構成のフィールドを自動的に作成されて、 *System.ServiceModel.Configuration.BasicHttpBindingElement*します。<br /><br /> 省略記号ボタンをクリックします **([...])。** HTTP バインディングのプロパティを変更します。 セキュリティで保護された通信チャネルを使用する必要があります常に設定する、**モード**プロパティを**トランスポート**します。 ウィザードの既定値の設定、**モード**プロパティとして**トランスポート**します。<br /><br /> 公開されているその他のバインディングの詳細については、次を参照してください。 [BasicHttpBindingElement クラス](https://msdn.microsoft.com/library/system.servicemodel.configuration.basichttpbindingelement.aspx)します。|  
    |[エンドポイント名]|コントラクトのエンドポイント名を指定します。|  
  
     このページの他のフィールドには、前のページで指定した値に基づいて自動的に設定されます。  
  
     **[適用]** をクリックします。 下に表示されるすべての契約にこの手順を実行、**を構成する契約を選択**ボックス。  
  
    > [!NOTE]
    >  このページで任意の値を指定しない場合は、すべてのコントラクトの既定値が受け入れられます。  
  
     次の図は、サービス エンドポイントのバインドの構成と指定した値のアドレス ページを示します。  
  
     ![サービス エンドポイントのバインドとアドレスの構成](../../adapters-and-accelerators/adapter-siebel/media/467d3e18-027d-4218-9d72-0740c1f559e3.gif "467d3e18-027d-4218-9d72-0740c1f559e3")  
  
13. サービス エンドポイントのバインドを構成し、アドレス ページで、**次**します。 [概要] ページには、選択した Siebel ビジネス コンポーネントをその下にある各ビジネス コンポーネントの選択した操作コントラクトのツリー構造が一覧表示します。  
  
14. 概要を確認し、**完了**します。  
  
15. ウィザードが WCF サービスを作成し、次のファイルを追加します、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]プロジェクト。  
  
    1.  .svc ファイルです。 これは、WCF サービスのファイルです。 ウィザードでは、各コントラクトに対して 1 つのファイルを生成します。  
  
    2.  Web.config ファイルです。  
  
    3.  サービス コード (.cs ファイル)。  
  
16. WCF サービスを発行します。  
  
    1.  SSL がインターネット インフォメーション サービス (IIS) を有効にすることを確認します。 参照してください[SSL を設定する方法](https://docs.microsoft.com/iis/manage/configuring-security/how-to-set-up-ssl-on-iis)します。
  
    2.  ソリューション エクスプ ローラーでプロジェクトを右クリックし、をクリックし、**発行**します。  
  
    3.  **Web の発行** ダイアログ ボックスで、WCF サービスの URL を指定します。 以下に例を示します。  
  
        ```  
        https://<computer_name>/Siebel_Account/  
        ```  
  
    4.  **コピー**ボックスで、**すべてのプロジェクト ファイル**します。  
  
    5.  **[パブリッシュ]** をクリックします。  
  
17. WCF サービスが正常に発行されることを確認します。  
  
    1.  IIS の Microsoft 管理コンソールを起動します。 クリックして**開始**、 をポイント**管理ツール**、順にクリックします**インターネット インフォメーション サービス**します。  
  
    2.  サービスを発行したノードに移動します。 **Siebel_Account**サービスに移動して**インターネット インフォメーション サービス** > **\<コンピューター名\>**  > **Websites** > **Default Web Site** > **Siebel_Account**します。  
  
    3.  右側のウィンドウで BusinessObjects_Account_Account_Operation.svc ファイルを右クリックし、**参照**します。  
  
    4.  WSDL を取得するための URL を使用して、Web ページが表示されます。 Svcutil コマンドを使用してメタデータの取得をテストすることがあります。 たとえば、Siebel_Account サービスのメタデータを取得するコマンドには。  
  
        ```  
        svcutil.exe https://localhost/Siebel_Account/BusinessObjects_Account_Account_Operation.svc?wsdl  
        ```  
  
## <a name="next-steps"></a>次の手順  
 Siebel ビジネス コンポーネントの WCF サービスがあるようになりました。 Siebel ビジネス コンポーネント操作用のアプリケーション定義ファイルを作成するのにには、ビジネス データ カタログ定義エディターを使用します。 参照してください[手順 2。Siebel ビジネス コンポーネント操作用のアプリケーション定義ファイルの作成](../../adapters-and-accelerators/adapter-siebel/step-2-create-an-application-definition-file-for-siebel-business-component.md)手順についてはします。 LOB データが格納されていると、形式が格納されているアプリケーション定義ファイルを識別します。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 1:Siebel システムからのデータを SharePoint サイトに表示する](../../adapters-and-accelerators/adapter-siebel/tutorial-1-presenting-data-from-a-siebel-system-on-a-sharepoint-site.md)