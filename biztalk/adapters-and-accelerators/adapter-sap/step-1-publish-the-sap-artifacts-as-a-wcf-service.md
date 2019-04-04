---
title: '手順 1: WCF サービスとしての SAP の成果物の発行 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF service, generating a
- WCF Adapter Service Development Wizard , using the
- WCF Adapter Service Development Wizard
- SAP artifacts, publishing as a WCF service
ms.assetid: bd3087b0-e20f-4b75-beef-a913336d767b
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4af261acd7d61ae49aef53a9f7f206fb8a597fbd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989379"
---
# <a name="step-1-publish-the-sap-artifacts-as-a-wcf-service"></a>手順 1: WCF サービスとしての SAP の成果物を発行します。
![手順 4 の 1](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")  
  
 **所要時間:** 10 分  
  
 **目標:** WCF アダプター サービス開発ウィザードを使用して、インターネット インフォメーション サービス (IIS) または Windows プロセス アクティブ化サービス (WAS) などのホスティング環境でホストされる WCF サービスを生成することができます。 このトピックでは、ウィザードを使用して WCF サービスのファイルを生成する方法を示します。  
  
## <a name="prerequisites"></a>前提条件  
 ウィザードを実行する前に、次のようにインストールします。  
  
- [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] いずれかで、**完了**オプションまたは**カスタム**オプション (選択して**ツール**このオプションで)。 これにより、インストール、 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] WCF アダプター サービス開発ウィザード用のテンプレート。  
  
- [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。  
  
- 必要な SAP クライアント ライブラリです。  
  
  これらの前提条件の詳細については、、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]インストール ガイドを参照してください。 通常、インストール ガイドにインストールされて\<インストール ドライブ\>: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents します。  
  
### <a name="to-publish-the-sap-artifacts-as-a-wcf-service"></a>WCF サービスとしての SAP アイテムを発行するには  
  
1. 開始[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、し、プロジェクトを作成します。  
  
2. **新しいプロジェクト** ダイアログ ボックスから、**プロジェクトの種類**ペインで、 **Visual c#** します。 **テンプレート**ペインで、 **WCF アダプタ サービス**します。  
  
    またはから、**プロジェクトの種類**ウィンドウで、展開**Visual c#**、し、 **Web**します。 **テンプレート**ペインで、 **WCF アダプタ サービス**します。  
  
   > [!NOTE]
   >  インストールした場合[!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)]、Web 開発コンポーネントと、 **WCF アダプタ サービス**テンプレートが表示されます、**新しい web サイト**オプション。  
  
3. ソリューションでは、場所と名前を指定し、クリックして**OK**します。 WCF アダプター サービス開発ウィザードを開始します。  
  
4. [ようこそ] ページで、次のようにクリックします。**次**します。  
  
5. 操作の選択 ページで、SAP システムに接続する接続文字列を指定します。 そのためには次を行います。  
  
   1. **バインディングを選択**一覧で、[ **sapBinding**、] をクリックし、**構成**。  
  
   2. **アダプターの構成**ダイアログ ボックスで、をクリックして、**セキュリティ**タブ。  
  
   3. **クライアント資格情報の種類**一覧で、 **Username**、し、有効な SAP ユーザー名と SAP システムに接続するためのパスワードを指定します。  
  
   4. をクリックして、 **URI プロパティ**タブをクリックし、接続パラメーターの値を指定します。 接続 URI の詳細についてはの[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を参照してください[SAP システム接続 URI の作成](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)です。  
  
      > [!NOTE]
      >  接続パラメーターに XML の特殊文字) などの予約文字が含まれている場合、としてを指定する必要がありますのでは、 **URI プロパティ**タブ、つまり、エスケープ文字を使用せずします。 ただし、直接の URI を指定する場合、 **URI の構成**ボックスとの接続パラメーターは、予約文字を含めることが、適切なエスケープ文字を使用して接続パラメーターを指定する必要があります。  
  
   5. をクリックして、**バインド プロパティ**タブをクリックし、対象と操作のために必要な場合、バインドのプロパティの値を指定します。 このチュートリアルでは、特定の顧客の販売注文の一覧を取得する BAPI_SALESORDER_GETLIST RFC が呼び出されます。 販売注文情報は、日付列を含めることも可能性があります。 設定することをお勧め、日付列の値を取得するときに、 **EnableSafeTyping**プロパティをバインド**True**メタデータを生成するときにします。 このプロパティが設定されている場合は、SAP DATS のデータ型が文字列として表示されます。  
  
       SAP のデータ型を同等の .NET 型にマップする方法の詳細については、[SAP データ型の基本的な](../../adapters-and-accelerators/adapter-sap/basic-sap-data-types.md)を参照してください。  
  
       バインド プロパティの詳細については、[mySAP Business Suite のバインドのプロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)を参照してください。  
  
   6. をクリックして**OK**、順にクリックします**Connect**します。 接続が確立されると、接続の状態が表示として**接続**します。  
  
6. 操作の選択] ページで、**選択のコントラクト型**一覧で、[**クライアント (送信操作)** します。  
  
7. **カテゴリを選択**ボックスに、SAP アイテムの種類を展開します。 たとえば、展開、 **RFC**ノードを格納している WCF サービスを生成する RFC 機能グループを参照してください。  
  
8. **利用可能なカテゴリと操作**ボックスをクリックして、WCF サービスを生成する操作を選択します。**追加**します。 選択した操作が記載されて、**カテゴリと操作を追加**ボックス。  
  
   > [!NOTE]
   >  各成果物の 1 つ以上の操作を追加することができます。 異なる SAP アイテムの操作を追加することもできます。 たとえば、RFC の 1 つの操作と別の IDOC を追加できます。 さらに、検索式のワイルドカード文字を指定することによって、特定の操作を検索できます。 サポートされている特殊文字および位置は、操作を検索することができます、ノード レベルの詳細については、次を参照してください[Visual Studio を使用してメタデータの追加アダプター ウィザードでの SAP への接続。](../../adapters-and-accelerators/adapter-sap/connecting-to-sap-in-visual-studio-using-add-adapter-metadata-wizard.md)  
  
    この例で、SD_RFC_CUSTOMER_GET と BAPI_SALESORDER_GETLIST Rfc は追加されます。  
  
   > [!NOTE]
   >  SAP システムの一部のバージョンでは、SD_RFC_CUSTOMER_GET ではなく RFC_CUSTOMER_GET RFC を公開します。  
  
    ![SAP アイテムの選択](../../adapters-and-accelerators/adapter-sap/media/f944f9a0-7387-46cb-8eb6-337344d01d29.gif "f944f9a0-7387-46cb-8eb6-337344d01d29")  
  
9. 操作の選択 ページで、次のようにクリックします。**次**します。  
  
10. サービスの構成およびエンドポイントの動作 ページで、サービスとエンドポイントの動作を構成する値を指定します。  
  
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
       >  証明書と関連付けられているプロパティの詳細についてを参照してください「X509ClientCertificateCredentialsElement プロパティ」 [ http://go.microsoft.com/fwlink/?LinkId=103771](http://go.microsoft.com/fwlink/?LinkId=103771)します。  
  
    2. **エンドポイント動作の構成**ボックスで、次の値を指定します。  
  
       |プロパティの|値を指定します。|  
       |----------------------|-----------------------|  
       |[認証の種類]|-この設定**ClientCredentialUserNamePassword** WCF サービスを使用するときに、ユーザー名とパスワードを指定するクライアントを有効にします。<br /><br /> -この設定**HTTPUserNamePassword** HTTP ヘッダーの一部としてユーザー名とパスワードを指定するクライアントを有効にします。<br /><br /> -この設定**自動**最初から資格情報を指定するクライアントを有効にする、 **ClientCredential**インターフェイス。 これが失敗すると、クライアントは、HTTP ヘッダーの一部として資格情報を渡すことができます。<br /><br /> 既定値は**自動**します。WCF サービスを使用する Microsoft Office SharePoint server、として設定する必要があります**HTTPUserNamePassword**します。|  
       |名前|エンドポイントの動作の構成の名前を指定します。|  
       |UsernameHeader|ユーザー名ヘッダーの名前です。 この例では、指定**MyUserHeader**します。 HTTP ヘッダーの詳細についてを参照してください「のサポートのカスタム HTTP ヘッダーと SOAP ヘッダー」 [ http://go.microsoft.com/fwlink/?LinkId=106692](http://go.microsoft.com/fwlink/?LinkId=106692)します。<br /><br /> **注:** 場合は、このプロパティの値を指定する必要があります、**認証の種類**に設定されている**HTTPUserNamePassword**します。 場合**認証の種類**に設定されている**自動**、このプロパティは省略可能です。|  
       |PasswordHeader|パスワード ヘッダーの名前です。 この例では、指定**MyPassHeader**します。 HTTP ヘッダーの詳細についてを参照してください「のサポートのカスタム HTTP ヘッダーと SOAP ヘッダー」 [ http://go.microsoft.com/fwlink/?LinkId=106692](http://go.microsoft.com/fwlink/?LinkId=106692)します。<br /><br /> **注:** 場合は、このプロパティの値を指定する必要があります、**認証の種類**に設定されている**HTTPUserNamePassword**します。 場合**認証の種類**に設定されている**自動**、このプロパティは省略可能です。|  
  
       次の図は、値を指定して、サービスの構成およびエンドポイントの動作のページを示しています。  
  
       ![サービスとエンドポイントの動作 ページを構成する](../../adapters-and-accelerators/adapter-sap/media/0a286b0c-7f0d-46c5-9b56-29bef3a1deea.gif "0a286b0c-7f0d-46c5-9b56-29bef3a1deea")  
  
11. サービスの構成およびエンドポイントの動作 ページで、**次**します。  
  
12. サービス エンドポイントのバインドを構成し、アドレス ページで、**を構成する契約を選択**ボックスは、操作の選択 ページで、操作を選択した SAP アイテムを一覧表示されます。  
  
     RFC および IDOC、成果物を選択した場合など、**を構成する契約を選択**RFC および IDOC の両方を一覧表示されます。 RFC のみを選択した場合、ボックスは RFC のみを示します。  
  
13. **選択した契約の下での操作**ボックスには、各成果物の管理の選択 ページの選択した操作が表示されます。  
  
14. **アドレスとコントラクトのバインディング構成**ボックスで、次の値を指定します。  
  
    |プロパティの|値を指定します。|  
    |----------------------|-----------------------|  
    |バインドの構成|ウィザードでは、基本的な HTTP バインドのみサポートされます。 バインド構成のフィールドを自動的に作成されて、 *System.ServiceModel.Configuration.BasicHttpBindingElement*します。<br /><br /> 省略記号ボタンをクリックします **([...])。** HTTP バインディングのプロパティを変更します。 セキュリティで保護された通信チャネルを使用する必要があります常に設定する、**モード**プロパティを**トランスポート**します。 ウィザードの既定値の設定、**モード**プロパティとして**トランスポート**します。<br /><br /> 公開されているその他のバインディングの詳細についてを参照してください「BasicHttpBindingElement メンバー」 [ http://go.microsoft.com/fwlink/?LinkId=103773](http://go.microsoft.com/fwlink/?LinkId=103773)します。|  
    |[エンドポイント名]|コントラクトのエンドポイント名を指定します。|  
  
     このページの他のフィールドには、前のページで指定した値に基づいて自動的に設定されます。  
  
     **[適用]** をクリックします。 下に表示されるすべての契約にこの手順を実行、**を構成する契約を選択**ボックス。  
  
    > [!NOTE]
    >  このページで任意の値を指定しない場合は、すべてのコントラクトの既定値が受け入れられます。  
  
     次の図は、サービス エンドポイントのバインドの構成と指定した値のアドレス ページを示します。  
  
     ![サービス エンドポイントのバインドとアドレスの構成](../../adapters-and-accelerators/adapter-sap/media/356e297c-9893-494c-a834-9d0b8b42da2e.gif "356e297c-9893-494c-a834-9d0b8b42da2e")  
  
15. サービス エンドポイントのバインドを構成し、アドレス ページで、**次**します。  [概要] ページには、SAP アイテムとその各成果物用に選択された操作下にあるツリー構造が一覧表示します。  
  
16. 概要を確認し、**完了**します。  
  
17. ウィザードが WCF サービスを作成し、次のファイルを追加します、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]プロジェクト。  
  
    1.  .svc ファイルです。 これは、WCF サービスのファイルです。 ウィザードでは、各コントラクトに対して 1 つのファイルを生成します。  
  
    2.  Web.config ファイルです。  
  
    3.  サービス コード (.cs ファイル)  
  
18. WCF サービスを発行します。  
  
    1.  SSL がインターネット インフォメーション サービス (IIS) を有効にすることを確認します。 IIS の SSL を有効にする方法については、[ http://go.microsoft.com/fwlink/?LinkId=197170](http://go.microsoft.com/fwlink/?LinkId=197170)を参照してください。  
  
    2.  ソリューション エクスプ ローラーでプロジェクトを右クリックし、をクリックし、**発行**します。  
  
    3.  **Web の発行** ダイアログ ボックスで、WCF サービスの URL を指定します。 以下に例を示します。  
  
        ```  
        https://<computer_name>/Customer_Order/  
        ```  
  
    4.  **コピー**ボックスで、**すべてのプロジェクト ファイル**します。  
  
    5.  **[パブリッシュ]** をクリックします。  
  
19. WCF サービスが正常に発行されることを確認します。  
  
    1.  IIS の Microsoft 管理コンソールを起動します。 クリックして**開始**、 をポイント**管理ツール**、順にクリックします**インターネット インフォメーション サービス (IIS) マネージャー**します。  
  
    2.  サービスを発行したノードに移動します。 **Customer_Order**サービスに移動して**インターネット インフォメーション サービス** > **\<コンピューター名\>**  > **Websites** > **Default Web Site** > **Customer_Order**します。  
  
    3.  右側のウィンドウで Rfc.svc ファイルを右クリックし、**参照**します。  
  
    4.  WSDL を取得するための URL を使用して、Web ページが表示されます。 使用してメタデータの取得をテストすることも、 **svcutil**コマンド。 たとえば、Customer_Order サービスのメタデータを取得するコマンドには。  
  
        ```  
        svcutil.exe https://<computer_name>/Customer_Order/Rfc.svc?wsdl  
  
        ```  
  
## <a name="next-step"></a>次の手順  
 SAP アイテム用のアプリケーション定義ファイルを作成するには、ビジネス データ カタログ定義エディターを使用します。 参照してください[手順 2: SAP アイテム用のアプリケーション定義ファイルの作成](../../adapters-and-accelerators/adapter-sap/step-2-create-an-application-definition-file-for-the-sap-artifacts.md)手順についてはします。 LOB データが格納されていると、形式が格納されているアプリケーション定義ファイルを識別します。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 1: SAP システムからのデータを SharePoint サイトに表示する](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md)