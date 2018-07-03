---
title: '手順 1: 作成して WCF サービスを発行する、Oracle E-business アダプターの使用 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7cd76f6f-600f-4eb5-8eee-8f3604d0fef4
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75bbbb57b633475d9973d187d61d6e698f6cadb2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981027"
---
# <a name="step-1-use-the-oracle-e-business-adapter-to-create-and-publish-a-wcf-service"></a>手順 1: Oracle E-business アダプターを使用して作成して WCF サービスを発行するには
![手順 4 の 1](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")  
  
 **所要時間:** 15 分  
  
 **目標:** を使用することができます、[!INCLUDE[afsvcdevwizlong](../../includes/afsvcdevwizlong-md.md)]をインターネット インフォメーション サービス (IIS) または Windows プロセス アクティブ化サービス (WAS) などのホスティング環境でホストできる Oracle E-business Suite の成果物から WCF サービスを生成します。 このトピックでは、ウィザードを使用して WCF サービスのファイルを生成する方法を示します。  
  
## <a name="prerequisites"></a>前提条件  
 ウィザードを実行する前に、次のようにインストールします。  
  
- [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] いずれかで、**完了**オプションまたは**カスタム**オプション (選択して**ツール**このオプションで)。 これにより、インストール、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]用のテンプレート、[!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)]します。  
  
- [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。  
  
  これらの前提条件の詳細については、次を参照してください。、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]インストール ガイドです。 通常、インストール ガイドにインストールされて\<インストール ドライブ\>: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents します。  
  
> [!NOTE]
>  作成する Microsoft Office SharePoint Server のサンプルで提供される create_apps_artifacts.sql スクリプトを実行することも必要があります、 **MS_SAMPLE_EMPLOYEE**インターフェイス テーブルで、**アプリケーション オブジェクト ライブラリ**アプリケーション。 このインターフェイスのテーブルは、このチュートリアルで使用されます。  
  

  
##  <a name="Create_Service"></a> Oracle E-business 成果物の操作を WCF サービスを作成します。  
 このセクションでは、MS_SAMPLE 従業員のインターフェイス テーブルに対する Select 操作の WCF サービスを作成する方法を説明します。  
  
#### <a name="to-create-a-wcf-service-for-the-select-operation-on-the-mssample-employee-interface-table"></a>MS_SAMPLE 従業員のインターフェイス テーブルに対する Select 操作の WCF サービスを作成するには  
  
1. 開始[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、し、プロジェクトを作成します。  
  
2. **新しいプロジェクト** ダイアログ ボックスから、**プロジェクトの種類**ペインで、 **Visual c#** します。 **テンプレート**ペインで、 **WCF アダプタ サービス**します。  
  
    またはから、**プロジェクトの種類**ウィンドウで、展開**Visual c#**、し、 **Web**します。 **テンプレート**ペインで、 **WCF アダプタ サービス**します。  
  
    ![新しいプロジェクト ダイアログ ボックス](../../adapters-and-accelerators/adapter-oracle-ebs/media/01-new-project.gif "01 _ new_project")  
  
   > [!NOTE]
   >  インストールした場合[!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)]、Web 開発コンポーネントと、 **WCF アダプタ サービス**テンプレートが表示されます、**新しい Web サイト**オプション (**ファイル** > **新しい** > **Web サイト**)。  
   > 
   >  ただし、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]のみ、ファイル システム上に作成される Web サイトをサポートします。 そのため、新しい Web サイト ダイアログ ボックス、Web サイトを作成するときに、場所の一覧でファイル システムをクリックしてください。  
  
3. ソリューションでは、場所と名前を指定し、クリックして**OK**します。 WCF[!INCLUDE[afsvcdevwizshort](../../includes/afsvcdevwizshort-md.md)]を開始します。  
  
4. [ようこそ] ページで、次のようにクリックします。**次**します。  
  
5. 操作の選択 ページで、Oracle E-business Suite に接続する接続文字列を指定します。 そのためには次を行います。  
  
   1. **バインディングを選択**一覧で、[ **oracleEBSBinding**、] をクリックし、**構成**。  
  
   2. **アダプターの構成**ダイアログ ボックスで、をクリックして、**バインドのプロパティ**タブ。  
  
      1.  下、**全般**カテゴリの**ClientCredentialType**プロパティ、バインドを選択**EBusiness**します。  
  
      2.  下、 **OracleEBS**カテゴリで、適切な値を指定、 **OracleUserName**、 **OraclePassword**、および**OracleEBSResponsibilityName**プロパティをバインドします。 この場合、データベース資格情報を提供する必要があります、 **OracleUserName**と**OraclePassword**プロパティをバインドします。  
  
      3.  下、**メタデータ**カテゴリの**EnableSafeTyping**選択プロパティ、バインド**True**。 設定することをお勧め、日付列の値を取得する場合、 **EnableSafeTyping**プロパティをバインド**True**メタデータを生成するときにします。  
  
   3. をクリックして、 **URI プロパティ**タブをクリックし、接続パラメーターの値を指定します。 接続 URI の詳細についてはの[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を参照してください[Oracle E-business Suite 接続 URI の作成](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md)です。  
  
   4. をクリックして、**セキュリティ**] タブで、および、**クライアント資格情報の種類**一覧で、[**ユーザー名**します。 有効な Oracle E-business Suite ユーザー名と Oracle E-business Suite に接続するためのパスワードを指定します。  
  
   5. をクリックして**OK**アダプターの構成 ダイアログ ボックスを閉じ、クリックして**Connect**。 Visual Studio は、Oracle E-business Suite との接続を正常に確立する接続の状態が表示として**接続**します。 操作の選択 ページに表示されている Oracle E-business Suite のメタデータを表示することもできます。  
  
6. 操作の選択] ページで、**選択のコントラクト型**一覧で、[**クライアント (送信操作)** します。  
  
7. **カテゴリを選択**ボックスに、アプリケーション オブジェクト ライブラリのアプリケーションで MS_SAMPLE_EMPLOYEE インターフェイス テーブルに移動します。 アダプターで成果物への参照については、次を参照してください。[参照、検索、および取得操作のメタデータの Oracle E-business](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)します。  
  
8. **利用可能なカテゴリと操作**ボックスで、**選択**操作、およびクリック**追加**します。 選択操作に追加されます、**カテゴリと操作を追加**ボックス。  
  
    ![選択操作を追加する](../../adapters-and-accelerators/adapter-oracle-ebs/media/02-msb-gui.gif "02 _ msb_gui")  
  
   > [!NOTE]
   >  各成果物の 1 つ以上の操作を追加することができます。 Oracle E-business Suite の各アイテムの操作を追加することもできます。 たとえば、インターフェイス テーブルの 1 つの操作と同時実行プログラムを追加できます。 さらに、検索式のワイルドカード文字を指定することによって、特定の操作を検索できます。 サポートされている特殊文字および位置は、操作を検索することができます、ノード レベルの詳細については、次を参照してください。 [Oracle E-business Suite 操作の検索](../../adapters-and-accelerators/adapter-oracle-ebs/search-for-oracle-e-business-suite-operations.md)します。  
  
9. 操作の選択 ページで、次のようにクリックします。**次**します。  
  
10. サービスの構成およびエンドポイントの動作 ページで、サービスとエンドポイントの動作を構成する値を指定します。  
  
    1. **サービス動作構成**ボックスで、次の値を指定します。  
  
       |プロパティの|値を指定します。|  
       |----------------------|-----------------------|  
       |EnableMetadataExchange|これを設定**True** metadata exchange エンドポイントを作成します。 値を設定する**True**、サービス メタデータを Ws-metadata Exchange (MEX) や HTTP/GET 要求などの標準化プロトコルを使用して利用できるようにします。 既定値は**False**します。|  
       |IncludeExceptionDetailsinFault|これを設定**True**デバッグのためのクライアントに返される SOAP エラーの詳細にマネージ例外情報を含めます。 既定値は**False**します。|  
       |名前|サービス動作の構成の名前です。 このチュートリアルでは、入力**customServiceBehavior**します。|  
       |UseServiceCertificate|WCF のメッセージ レベルのセキュリティ モードを使用するかどうかを指定します。 既定値は**True**します。 このチュートリアルである必要がありますこれを設定して**False**します。|  
  
       > [!NOTE]
       >  このチュートリアルではサービス証明書が使用していない、ために、値を指定する必要はありません、 **FindValue**、 **StoreLocation**、 **StoreName**、および**X509FindType**プロパティ。 証明書と関連付けられているプロパティの詳細についてを参照してください「X509ClientCertificateCredentialsElement プロパティ」 [ http://go.microsoft.com/fwlink/?LinkId=103771](http://go.microsoft.com/fwlink/?LinkId=103771)します。  
  
    2. **エンドポイント動作の構成**ボックスで、次の値を指定します。  
  
       |プロパティの|値を指定します。|  
       |----------------------|-----------------------|  
       |[認証の種類]|WCF サービスを使用する Microsoft Office SharePoint server、として設定する必要があります**HTTPUserNamePassword**します。 これにより、クライアントが HTTP ヘッダーの一部としてユーザー名とパスワードを指定できます。|  
       |名前|エンドポイントの動作の構成の名前を指定します。 このチュートリアルでは、入力**customEndpointBehavior**します。|  
       |UsernameHeader|ユーザー名ヘッダーの名前です。 この例では、指定**MyUserHeader**します。 HTTP ヘッダーの詳細についてを参照してください「のサポートのカスタム HTTP ヘッダーと SOAP ヘッダー」 [ http://go.microsoft.com/fwlink/?LinkId=106692](http://go.microsoft.com/fwlink/?LinkId=106692)します。 **注:** 場合は、このプロパティの値を指定する必要があります、**認証の種類**に設定されている**HTTPUserNamePassword**します。 場合**認証の種類**に設定されている**自動**、このプロパティは省略可能です。|  
       |PasswordHeader|パスワード ヘッダーの名前です。 この例では、指定**MyPassHeader**します。 HTTP ヘッダーの詳細についてを参照してください「のサポートのカスタム HTTP ヘッダーと SOAP ヘッダー」 [ http://go.microsoft.com/fwlink/?LinkId=106692](http://go.microsoft.com/fwlink/?LinkId=106692)します。 **注:** 場合は、このプロパティの値を指定する必要があります、**認証の種類**に設定されている**HTTPUserNamePassword**します。 場合**認証の種類**に設定されている**自動**、このプロパティは省略可能です。|  
  
       次の図は、値を指定して、サービスの構成およびエンドポイントの動作のページを示しています。  
  
       ![サービスとエンドポイントの動作 ページを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/media/03-service-and-endpoint-behavior.gif "03 _ service_and_endpoint_behavior")  
  
11. サービスの構成およびエンドポイントの動作 ページで、**次**します。  
  
12. サービス エンドポイントのバインドを構成し、アドレス ページで、**を構成する契約を選択**構成した成果物 (MS_SAMPLE_EMPLOYEE) が表示されます。 **選択した契約の下での操作**ボックスが表示されます、**選択**操作の選択 ページで成果物用に選択した操作。  
  
13. **アドレスとコントラクトのバインディング構成**ボックスで、次の値を指定します。  
  
    |プロパティの|値を指定します。|  
    |----------------------|-----------------------|  
    |バインドの構成|ウィザードでは、基本的な HTTP バインドのみサポートされます。 バインド構成のフィールドを自動的に作成されて、 *System.ServiceModel.Configuration.BasicHttpBindingElement*します。<br /><br /> 省略記号ボタンをクリックします **([...])。** HTTP バインディングのプロパティを変更します。 セキュリティで保護された通信チャネルを使用する必要があります常に設定する、**モード**プロパティを**トランスポート**します。 ウィザードの既定値の設定、**モード**プロパティとして**トランスポート**します。<br /><br /> 公開されているその他のバインディングの詳細についてを参照してください「BasicHttpBindingElement メンバー」 [ http://go.microsoft.com/fwlink/?LinkId=103773](http://go.microsoft.com/fwlink/?LinkId=103773)します。|  
    |[エンドポイント名]|コントラクトのエンドポイント名を指定します。|  
  
     このページの他のフィールドには、前のページで指定した値に基づいて自動的に設定されます。  
  
     **[適用]** をクリックします。  
  
    > [!NOTE]
    >  このページで任意の値を指定しない場合は、すべてのコントラクトの既定値が受け入れられます。  
  
     次の図は、サービス エンドポイントのバインドの構成と指定した値のアドレス ページを示します。  
  
     ![サービス エンドポイントのバインドとアドレスの構成](../../adapters-and-accelerators/adapter-oracle-ebs/media/04-service-endpoint-binding.gif "04 _ service_endpoint_binding")  
  
14. サービス エンドポイントのバインドを構成し、アドレス ページで、**次**します。  [概要] ページには、Oracle E-business Suite の成果物と成果物の選択された操作のツリー構造が一覧表示します。  
  
15. 概要を確認し、**完了**します。  
  
16. ウィザードが WCF サービスを作成し、次のファイルを追加します、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]プロジェクト。  
  
    1.  .svc ファイルです。 これは、WCF サービスのファイルです。 ウィザードでは、各コントラクトに対して 1 つのファイルを生成します。  
  
    2.  Web.config ファイルです。  
  
    3.  サービス コード (.cs ファイル)  
  
##  <a name="cs"></a> .Cs ファイルを変更します。  
 Oracle E-business Suite 成果物を使用して、外のサービスを作成する場合、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Microsoft Office SharePoint server、ビジネス データ一覧 Web パーツからそれを使用して、WHERE 句で始まる完全なフィルター句を指定することが求め. たとえば、従業員は、名前が"John"を検索する場合は、ビジネス データ一覧 Web パーツでは、次のフィルター句を指定する必要があります。  
  
```  
where NAME like ‘JOHN’  
```  
  
 ただし、のみを提供する名前を入力としてフィルター句に全体のフィルター句を実際に触れることがなく、ユーザーにする場合は、追加できますコードを .cs ファイルで、Microsoft Office でビジネス データ一覧 Web パーツからフィルター句を変更します。 SharePoint サーバーを使用して、Oracle E-business に WHERE 句の形式で渡します。  
  
 などの場合はこのチュートリアルでは、ユーザーが Microsoft Office SharePoint Server では、ビジネス データ一覧 Web パーツに従業員の名前を入力し、その従業員のレコードを取得する場合追加できます、次のコード、.cs ファイル。  
  
```  
SelectResponse InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE.Select(SelectRequest request)   
{  
     request.FILTER = "where NAME like '" + request.FILTER + "'"; // The code to avoid the users from specifying the WHERE clause in the filter from Business Data List Web Part.  
     return base.Channel.Select(request);  
}  
```  
  
##  <a name="Publish"></a> WCF サービスを発行します。  
 IIS で SSL が有効であることを確認します。 IIS の SSL を有効にする方法については、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=197170](http://go.microsoft.com/fwlink/?LinkId=197170)します。  
  
 WCF サービスを発行するには。  
  
1.  ソリューション エクスプ ローラーでプロジェクトを右クリックし、をクリックし、**発行**します。  
  
2.  **Web の発行** ダイアログ ボックスで、WCF サービスの URL を指定します。 以下に例を示します。  
  
    ```  
    https://<COMPUTER_NAME>:<PORT_NUMBER>/MS_SAMPLE_EMPLOYEE/  
    ```  
  
    > [!NOTE]
    >  SSL が有効な場所には、WCF サービスを発行する必要があります。 値、つまり、**ターゲットの場所**ボックスは、"https://"で開始する必要があります。 HTTP ヘッダーでは、ユーザーの資格情報が渡される、ため、ウィザードは自動的に SSL 暗号化のことを意味するセキュリティ モードとして「トランスポート」を使用するアダプターのバインドの動作を構成します。 もちろんに移動しの値を変更する web.config ファイルを編集できます、 **\<セキュリティ モード\>** 常に機密情報がクリア テキストで転送がある場合、パラメーターが SSL を使用してはより適切なオプションHTTP ヘッダー内のテキスト。  
  
3.  **コピー**ボックスで、**すべてのプロジェクト ファイル**します。  
  
4.  **[パブリッシュ]** をクリックします。  
  
5.  WCF サービスが正常に発行されることを確認します。  
  
    1.  IIS の Microsoft 管理コンソールを起動します。 クリックして**開始**、 をポイント**管理ツール**、順にクリックします**インターネット インフォメーション サービス (IIS) マネージャー**します。  
  
    2.  サービスを発行したノードに移動します。 **MS_SAMPLE_EMPLOYEE**サービスに移動して**インターネット インフォメーション サービス** > **\<コンピューター名\>**  > **Websites** > **Default Web Site** > **MS_SAMPLE_EMPLOYEE**します。  
  
    3.  右側のウィンドウで InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE.svc ファイルを右クリックし、**参照**します。  
  
    4.  WSDL を取得するための URL を使用して、Web ページが表示されます。 使用してメタデータの取得をテストすることも、 **svcutil**コマンド。 たとえば、MS_SAMPLE_EMPLOYEE サービスのメタデータを取得するコマンドには。  
  
        ```  
        svcutil.exe https://<COMPUTER_NAME>:<PORT_NUMBER>/MS_SAMPLE_EMPLOYEE/InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE.svc?wsdl  
  
        ```  
  
## <a name="next-step"></a>次の手順  
 Oracle E-business Suite の成果物のアプリケーション定義ファイルを作成するには、ビジネス データ カタログ定義エディターを使用します。 手順については、次を参照してください。[手順 2: Oracle E-business Suite の成果物のアプリケーション定義ファイルを作成](../../adapters-and-accelerators/adapter-oracle-ebs/step-2-create-an-application-definition-file-for-the-oracle-ebs-artifacts.md)です。 LOB データが格納されていると、形式が格納されているアプリケーション定義ファイルを識別します。  
  
## <a name="see-also"></a>参照  
 [チュートリアル: SharePoint サイト上の Oracle E-business Suite からデータを表示します。](Tutorial:%20Present%20data%20from%20Oracle%20E-Business%20Suite%20on%20a%20SharePoint%20Site.md)