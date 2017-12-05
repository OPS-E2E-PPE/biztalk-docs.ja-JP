---
title: "WCF LOB Adapter SDK を使用して、IIS でアダプターをホスト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 90b6cd97-01b3-4c98-a190-c6e0ccf24d2b
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 326dc5f3102354c8f2aa6fa785b145b72014f3d3
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="host-an-adapter-in-iis-using-the-wcf-lob-adapter-sdk"></a>WCF LOB Adapter SDK を使用して、IIS でアダプターをホストします。
このセクションの内容には使用して構築されたアダプターのホスティングに関する情報が含まれています、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]インターネット インフォメーション サービス (IIS) にします。 他のホスティング オプションの詳細については、次を参照してください。[ホスティング サービス](https://msdn.microsoft.com/library/ms730158.aspx)です。
  
## <a name="use-iis-and-aspnet"></a>IIS と ASP.NET を使用します。
 IIS を使用して、WCF LOB Adapter SDK で作成されたアダプターを公開する ASP.NET を使用することができます。 によって作成されたアダプターをホストする、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]、WCF サービスを公開するためにインターネット インフォメーション サービス (IIS) を構成します。 次に、ASP.NET、WCF adapterwith を使用する方法を検討してください。
 
 使用可能なホスティング モードには、IIS で WCF サービスをホストする場合:**サイド バイ サイド**と A**互換性モードが SP.NET**です。 既定のホスト モードは、サイド バイ サイドです。 サイド バイ サイドのモードは、ソリューションをホストしている他の WCF で、一貫した動作です。 そのため、IIS でホストされる WCF サービスでは、コンソール アプリケーションでホストされているいずれかと同じでは動作します。 ただし、このことがありますできません望ましい web 開発者期待される動作を ASP.NET に似ています。 たとえば、サイド バイ サイドのモードで WCF 動作に従っていませんで指定された URL ベースの承認ルール、 `<system.web> <authorization>` web.config ファイルの構成要素。  
  
 ASP.NET 互換性モードでは、ASP.NET のすべての機能を使用して、ASPX ページと同様に動作する WCF サービスただし、この機能を有効にするように WCF アダプターを作成するときに、追加の手順を実行する必要があります。 詳細については、以下をご覧ください。 
 
 [WCF サービスと ASP.NET](https://msdn.microsoft.com/library/aa702682.aspx)
 
[インターネット インフォメーション サービスをホストしています。](https://msdn.microsoft.com/library/ms734710.aspx)

[WCF サービスをホストしています。](https://msdn.microsoft.com/library/ms730158.aspx)

## <a name="use-the-wcf-adapter-service-development-wizard"></a>使用して、WCF アダプター サービス開発ウィザード

使用して、[!INCLUDE[afsvcdevwizlong](../../includes/afsvcdevwizlong-md.md)]インターネット インフォメーション サービス (IIS) 内で、アダプターをホストするための Web プロジェクトの作成を自動化します。 ホストされているアダプターは、Windows Communication Framework (WCF) または Web サービスを使用するクライアントで使用できます。  
  
### <a name="publish-an-adapter-as-a-wcf-service-hosted-in-iis"></a>IIS でホストされる WCF サービスとしてアダプターを公開します。  
  
1.  [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)]を開きます。 **ファイル**メニューの **新規**、し、 **Web サイト**です。  
  
2.  **テンプレート** **Visual c#**を選択し、 **WCF アダプタ サービス**です。  
  
3.  クリックして、ソリューションを保存するフォルダーを入力して**OK**です。 **WCF アダプター サービス開発ウィザード**を開始します。  
  
4.  **概要** ページで、をクリックして**次**です。  
  
5.  **選択操作** ページで、このホステッド サービスに使用するには、バインディング、コントラクト、および操作を指定します。  
  
    1.  **バインディングを選択**一覧で、をクリックし、アダプターのバインドを選択**構成**です。 これが表示されます、**アダプターの構成** ダイアログ ボックス。 アダプターを呼び出すと、操作のメタデータを取得するために必要な値を提供します。  
  
    2.  **セキュリティ**] タブで、[、**クライアント資格情報の種類**クライアント資格情報をアダプターに渡すときに使用します。  
  
        |[資格情報の種類]|Description|  
        |---------------------|-----------------|  
        |**なし**|クライアントは、資格情報を提示する必要はありません。|  
        |**Windows**|クライアントでは、Windows 資格情報を使用します。|  
        |**ユーザー名**|ユーザー名とパスワード、クライアントから提供されます。|  
        |**[MSSQLSERVER のプロトコルのプロパティ]**|クライアントは、X.509 証明書を使用して認証されます。 この値が設定されている場合にクリックして**参照**で、**クライアント証明書**領域、および使用する証明書を選択します。|  
  
    3.  **URI プロパティ**タブで、アダプターに必要な URI パラメーターを指定します。 このタブに表示されるエントリで公開されているプロパティによって異なります、`ConnectionUri Properties`アダプターのクラスです。  
  
    4.  **バインド プロパティ** タブで、アダプターに必要なバインドのプロパティの値を指定します。 **全般**セクションには、タイムアウト値などの一般的な設定が含まれています。 追加のプロパティに公開されるカスタム プロパティを基に一覧表示されます、`AdapterBinding`クラスです。  
  
6.  構成値を指定すると、クリックして**接続**です。  
  
    1.  **選択コントラクト型**一覧で、使用するコントラクトを選択します。 これによって、**カテゴリを選択**ツリー コントロールにカテゴリおよびこのアダプターから実行できる操作の一覧です。 アダプターを使用して検索機能を実装する場合、`MetadataRetrievalClient`クラス、検索用語を入力することができます、**カテゴリで検索**フィールドをカテゴリと、検索用語が含まれている操作のみを返します。  
  
        > [!NOTE]
        >  送信操作のみが選択可能な。  
  
    2.  **利用可能なカテゴリと操作**ボックスで、をクリックし、追加の項目を選択**追加**です。 目的のアイテムを追加した後にをクリックして**次**です。  
  
7.  **サービスの構成およびエンドポイント動作** ページで、このアダプターの目的の動作を設定します。  
  
    1.  **サービス動作構成**セクションには、サービスの動作を制御するエントリが含まれています。 ウィザードを実行すると、web.config ファイルを編集して、選択したサービスの動作を変更できます。  
  
        |プロパティ|Description|  
        |--------------|-----------------|  
        |**EnableMetadataExchange**|この値を設定**True**クライアントの要求にメタデータの公開をサービスすることができます。 これは変更することによっても設定できます\< **serviceMetadata httpGetEnabled =""** \> web.config でします。既定値は**False**|  
        |**IncludeExceptionDetailsinFault**|この値を設定**True** SOAP エラー内のクライアントにマネージ例外情報で結果が返されます。 これは変更することによっても設定できます\< **serviceDebug usingincludeExceptionDetailInFaults =""** \> web.config でします。既定値は**False**です。|  
        |**名前**|サービス動作の構成の名前です。|  
        |**UseServiceCertificate**|この値は、サービスがクライアントのプロセスに対する認証に X.509 証明書を使用するかどうかを判断します。 既定値は**True**です。|  
        |**FindValue**|この値は、証明書ストアで特定の X.509 証明書の検索に使用されます。 これは変更することによっても設定できます\< **serviceCredentials findValue =""** \> web.config で**注:**場合にのみ、このプロパティの値を指定**UseServiceCertificate**に設定されている**True**です。|  
        |**StoreLocation**|この値は、指定された証明書を検索するシステム ストアの場所を指定します。 これは変更することによっても設定できます\< **serviceCredentials storeLocation =""** \> web.config でします。**注:**場合にのみ、このプロパティの値を指定**UseServiceCertificate**に設定されている**True**です。|  
        |**StoreName**|この値は、指定された証明書を検索する特定のシステム ストアを指定します。 これは変更することによっても設定できます\< **serviceCredentials storeName =""** \> web.config で**注:**場合にのみ、このプロパティの値を指定**UseServiceCertificate**に設定されている**True**です。|  
        |**X509FindType**|使用する特定の証明書を検索するために、FindValue で使用する検索の種類は前に指定します。 これは変更することによっても設定できます\< **serviceCredentials x509FindType =""** \> web.config で**注:**場合にのみ、このプロパティの値を指定**UseServiceCertificate**に設定されている**True**です。|  
  
    2.  **エンドポイント動作の構成**セクションでは、エンドポイント動作を制御します。  
  
        |プロパティ|Description|  
        |--------------|-----------------|  
        |**名前**|エンドポイントの動作の名前|  
        |**AuthenticationType**|この値は、クライアント資格情報を取得、受信ドキュメントの場所をアダプターに指示します。 クライアント サービスに対する認証にクライアント証明書を指定するため、これを設定**ClientCredentialUsernamePassword**です。 クライアントが HTTP ヘッダーの一部として、ユーザー名とパスワードを指定できるように、これを設定**HTTPUsernamePassword**です。 クライアントが、ClientCredential インターフェイスを通じて資格情報の指定を有効にするには、設定**自動**です。これが失敗した場合、クライアントは HTTP ヘッダーの一部として資格情報を渡すことができます。<br /><br /> この値は、変更することによって設定することもできます\< **endpointBehavior adapterSecurityBridgeType** \> web.config でします。既定値は**自動**です。|  
        |**UsernameHeader**|これには、サービスにユーザー名を渡すために使用するヘッダーの名前を指定します。 HTTP ヘッダーの詳細についてを参照してください「のカスタム HTTP および SOAP ヘッダーのサポート」 [http://go.microsoft.com/fwlink/?LinkId=106692](http://go.microsoft.com/fwlink/?LinkId=106692)<br /><br /> この値は、変更することによって設定することもできます\< **endpointBehavior usernameHttpHeader** \> web.config でします。**注:**場合は、このプロパティの値を指定する必要があります、 **AuthenticationType**に設定されている**HTTPUserNamePassword**です。  場合設定**自動**、このプロパティはオプションです。|  
        |**PasswordHeader**|これには、サービスにユーザーのパスワードを渡すために使用するヘッダーの名前を指定します。 HTTP ヘッダーの詳細についてを参照してください「のサポートをカスタム HTTP ヘッダーと SOAP ヘッダー」 [http://go.microsoft.com/fwlink/?LinkId=106692](http://go.microsoft.com/fwlink/?LinkId=106692)<br /><br /> この値は、変更することによって設定することもできます <**endpointBehavior passwordHttpHeader**< web.config でします。**注:**場合は、このプロパティの値を指定する必要があります、 **AuthenticationType**に設定されている**HTTPUserNamePassword**です。 場合設定**自動**、このプロパティはオプションです。|  
  
    3.  目的の動作を設定した後をクリックして**次**を続行します。  
  
8.  **構成サービスのエンドポイントのバインドとアドレス** ページで、コントラクトのアドレスとバインディングのプロパティを構成することができます。 コントラクトを選択、**を構成するコントラクトを選択**一覧、およびで目的の値を入力し、**されたコントラクトのバインディングとアドレスを構成する** ダイアログ ボックス。  
  
    1.  選択、 **BindingConfiguration**バインドのプロパティの下のエントリ。 ウィザードだけでは、基本的な HTTP バインディング、バインディング構成のフィールドが自動的に設定**System.ServiceModel.Configuration.BasicHttpBindingElement**です。 このバインディングの構成プロパティを変更するには、省略記号をクリック**しています.** ボタンをクリックします。 セキュリティで保護された通信チャネルを使用する必要があります、常に設定、**モード**プロパティを**トランスポート**です。 これが既定値です。  
  
    2.  選択、 **EndpointName**、エンドポイントの必要な名前を入力します。  
  
    3.  をクリックして変更を適用するには、**適用**です。  
  
9. 続行するには、 **[次へ]**をクリックします。 [概要] ページには、選択されたアダプターの操作のツリー構造が一覧表示します。  
  
10. 概要を確認し、をクリックして**完了**です。  
  
11. ウィザードでは、Web プロジェクトを作成し、次のファイルを追加します。  
  
    |ファイル|Description|  
    |----------|-----------------|  
    |.svc|WCF プロキシを参照するサービス ファイル。|  
    |.cs|WCF プロキシを実装します。|  
    |web.config|含む\<**エンドポイント**\, \<**バインド**\>、および\<**動作**\>要素\<**システムです。ServiceModel**\>|  
  
12. WCF サービス プロジェクトを発行します。  
  
    1.  ソリューション エクスプ ローラーでプロジェクトを右クリックし、をクリックして**発行**です。  
  
    2.  **Web サイトの発行** ダイアログ ボックスで、WCF サービスのターゲット URL を指定します。  
  
    3.  選択**このプリコンパイル済みサイトの更新を許可する**です。  
  
    4.  選択**固定名およびシングル ページ アセンブリを使用する**です。  
  
    5.  選択**プリコンパイル済みアセンブリに厳密な名前を有効にする**、しを使用する署名キーを指定します。  
  
13. Web サイトを発行する をクリックして**OK**です。  
  
14. サービスが正常に公開されていることを確認します。  
  
    1.  IIS 管理コンソールを起動します。  をクリックして**開始**、 をポイント**管理ツール**、順にクリック**インターネット インフォメーション サービス**です。  
  
    2.  サービスを発行したノードに移動します。  サービスは、http://localhost/myservice としてパブリッシュした場合に移動**インターネット インフォメーション サービス**> **コンピューター名**> **Websites** >  **Default Web Site**> **myservice**です。  
  
    3.  右側のウィンドウでは、.svc ファイルを右クリックし、をクリックして**参照**です。 Web ページは、サービスに関する情報と共に表示されます。 クライアント アプリケーションから WCF や Web サービスの呼び出しを使用してこのサービスを使用できるようになりました。 

## <a name="security"></a>セキュリティ
アダプターが、サービス内でホストされている場合、クライアント アプリケーションからの呼び出しはアダプター セキュリティ ブリッジを使用して、クライアントの資格情報をアダプターに渡す。  
  
 WCF クライアントで認証を WCF サービスに送信すると、通常、サービスは、認証を使用します。 、の場合は、アダプターという概念が、基になる LOB システムで使用する認証情報をキャプチャします。 これは、エンドポイントの動作として表示される、アダプターのセキュリティ ブリッジを介して実装されます。 アダプター開発者はありません。 この機能を活用するために実装する必要があります。ただし、アダプターを展開するときに、どのクライアントによってサービスに資格情報が提供するを考慮する必要があります。  
  
 メッセージ レベルのセキュリティを使用している場合、アダプターのセキュリティ ブリッジは任意のバインディングでクライアント アプリケーションによって送信される ClientCredentials を取得できます。 基本 HTTP バインディングを使用している場合、カスタム ヘッダーを使用してユーザー名とパスワード情報を渡す代わりに選択できます。 多くの Web サービス クライアント アプリケーションは、カスタム ヘッダーを使用して資格情報を渡す必要がありますが、資格情報を渡す WCF に用意された ClientCredential クラスを使用することをお勧めします。  
  
 アダプターが、クライアント アプリケーションを提供する ClientCredentials で資格情報を検索する場所、構成の例を次に示します。 いずれも見つからない場合、アダプターは、指定された HTTP 要求ヘッダーで検索します。  
  
```  
<endpointBehaviors>  
   <behavior name="customEndpointBehavior">  
      <endpointBehavior usernameHttpHeader="UNHdr" passwordHttpHeader="PWHdr"  
         adapterSecurityBridgeType="Auto" />  
    </behavior>  
</endpointBehaviors>  
```      
  
## <a name="see-also"></a>参照  
 [開発アクティビティ](../../esb-toolkit/development-activities.md)