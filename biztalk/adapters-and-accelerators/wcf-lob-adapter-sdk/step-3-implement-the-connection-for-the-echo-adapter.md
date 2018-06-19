---
title: '手順 3: 実装エコー アダプターの接続 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dc223901-3ad3-4e71-8672-fea6bb4efe65
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0a735654fd03f5efb39fe73eb845f4db3632d283
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2018
ms.locfileid: "22227266"
---
# <a name="step-3-implement-the-connection-for-the-echo-adapter"></a>手順 3: エコー アダプターの接続を実装します。
![手順 9 3](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-3of9.gif "Step_3of9")  
  
 **所要時間:** 45 分  
  
 このステップでは、エコー アダプターの接続機能を実装します。 よると、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]、ターゲット システムに接続するときに、次の抽象クラスとインターフェイスを実装する必要があります。  
  
-   `Microsoft.ServiceModel.Channels.Common.ConnectionUri`  
  
-   `Microsoft.ServiceModel.Channels.Common.IConnection`  
  
-   `Microsoft.ServiceModel.Channels.Common.IConnectionFactory`  
  
 上記から派生するのではなくクラスとインターフェイス、抽象化、 [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] 3 つの派生クラス、EchoAdapterConnection、EchoAdapterConnectionUri、および EchoAdapterConnectionFactory を自動的に生成されます。 に加えて、クラスを作成するには、それぞれが特定の例外をスローする既定のメソッド`System.NotImplementedException`です。  このステートメントには、各クラスを実装する、開発者が通知されます。  クラスが実装された場合は、この例外スローのステートメントを削除する必要があります。  
  
 次のセクションでは、接続を処理する方法、URI 構造、およびプログラムで URI のさまざまな要素を取得し、アダプター内での要素を使用する方法の理解を深めるためにこれら 3 つのクラスを更新します。  
  
## <a name="prerequisites"></a>前提条件  
 この手順を開始する前にする必要がありますが正常に完了しました[手順 2: アダプターと接続のプロパティを分類](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-categorize-the-adapter-and-connection-properties.md)です。 明確に理解する必要がありますする、 `Microsoft.ServiceModel.Channels.Common.IConnection`、 `Microsoft.ServiceModel.Channels.Common.IConnectionFactory`、および`Microsoft.ServiceModel.Channels.Common.ConnectionUri`クラスです。  
  
## <a name="connection-related-classes"></a>接続に関連するクラス  
 [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] 3 つの派生クラス、EchoAdapterConnection、EchoAdapterConnectionUri、および EchoAdapterConnectionFactory が生成されます。 次に、それぞれに関連付けられているメソッドの概要を示します。  
  
### <a name="echoadapterconnection"></a>EchoAdapterConnection  
 アダプターの複雑さによっては、次の 5 つのメソッドのすべてを実装する必要があります。 エコー アダプターのほとんどはサポートされていません、エコー adapter サンプルは、ターゲット システムを含まないためです。  
  
|**方法**|**Description**|  
|----------------|---------------------|  
|public void 閉じる (TimeSpan タイムアウト)|ターゲット システムへの接続を閉じます。 エコー アダプターでは、このメソッドを使用して、トレース リスナーにのみトレース イベントを追加します。|  
|パブリック bool IsValid (TimeSpan タイムアウト)|接続が有効であるかどうかを示す値を返します。<br /><br /> エコー アダプターによってサポートされていません。|  
|public void Open(TimeSpan timeout)|ターゲット システムへの接続を開きます。<br /><br /> エコー アダプターに対しては不適用です。 しかし、例を示します enableAuthentication と呼ばれる URI 要素を使用して、ユーザー名を指定するユーザーに要求する方法。|  
|public void ClearContext()|接続のコンテキストをクリアします。 このメソッドは、接続のセットは、接続プールに戻すときに呼び出されます。<br /><br /> エコー アダプターによってサポートされていません。|  
|public void Abort()|ターゲット システムへの接続を中止します。<br /><br /> エコー アダプターによってサポートされていません。|  
  
### <a name="echoadapterconnectionfactory"></a>EchoAdapterConnectionFactory  
 接続ファクトリは、接続を作成します。 既定では、ターゲット システムに接続するときにのみ、このクラスを変更する必要があります。 エコー アダプターが、ターゲット システムを含まないが方法を示します、接続は、ユーザー認証を必要とする場合は、enableAuthentication と呼ばれるカスタム URI 要素を使用します。  
  
> [!NOTE]
>  EnableAuthentication はキーワード、変数の名前だけです。 そのため、任意の名前を選択できます。  
  
### <a name="echoadapterconnectionuri"></a>EchoAdapterConnectionUri  
 これは、ターゲット システムに接続文字列を表します。  
  
|**方法**|**Description**|  
|----------------|---------------------|  
|パブリック オーバーライド Uri の Uri|取得し、Uri を設定します。 Uri 文字列を作成するを取得し、Uri 文字列の解析を設定します。|  
|public EchoAdapterConnectionUri()|ConnectionUri クラスの新しいインスタンスを初期化します。|  
|パブリック オーバーライド文字列 SampleUriString|Returns EchoAdapter.SCHEME + "://{hostname}/{application}?enableAuthentication={True&#124;False}".<br /><br /> この戻り値の文字列でとして表示されます、**例**で、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]ツールを次の図に示すようにします。|  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/e4b9d0b8-f07f-4342-815f-9ef1507b0980.gif "e4b9d0b8-f07f-4342-815f-9ef1507b0980")  
  
## <a name="echo-adapter-connection-uri"></a>アダプターの接続 URI をエコーします。  
 URI として説明されているサンプル エコー アダプターの接続: EchoAapter.SCHEME://{hostname}/{application}?enableAuthentication={true&#124;false}  
  
 なので、EchoAapter.SCHEME echov2、接続 URI です。  
  
 echo2://lobhostname/lobapplication?enableAuthentication={true&#124;false}  
  
 以前の接続 URI を読み取ることができる場合に enableAuthentication false を次のように。  
  
 を使用して echov2 トランスポート スキーマ移動 lobhostname、という名前のコンピューターに接続して任意の認証を必要としない lobapplication をという名前のアプリケーションが待機しています。  
  
 または、enableAuthentication = true の場合、次のように、接続の読み取り。  
  
 Echov2 トランスポートのスキーマを使用して、移動 lobhostname、という名前のコンピューターで、lobapplication をという名前のアプリケーションでは、接続が認証を待機しているが必要です。 エコー アダプターは、ユーザー名のみが必要です。  
  
 定義済みの URI を持つプログラムで使用し、接続と構成を解析できます。 接続は、ユーザー名とパスワードなどの機密データを必要とする場合は、URI では、このような情報は含まれません。 代わりに、このような情報を追加、`System.ServiceModel.Description.ClientCredentials`オブジェクト。 追加するコード例では、これを行う方法を示します。  
  
 次のコードでは、エコー アダプターは、アダプターが URI のさまざまな要素を使用して、アダプターの機能を変更する方法を表示する 2 つの方法で URI を構築します。  
  
 echo2://lobhostname/lobapplication?enableAuthentication=[true&#124;false]  
  
 echo2://lobhostname/lobapplication?enableAuthentication=[true&#124;false]&echoInUpperCase=true  
  
### <a name="retrieving-the-uri-element"></a>URI の要素を取得します。  
 エコー アダプター URI echo2 内の各 URI 要素を解析することができます://lobhostname/lobapplication? enableAuthentication = false & echoInUpperCase = false。  URI の要素の値と関連するメソッドは、次の表のとおりです。  
  
|**URI の要素の値**|**方法**|  
|---------------------------|----------------|  
|lobhostname|`System.Uri.Host%2A` ホスト名を取得するには|  
|Lobapplication|`System.Uri.AbsolutePath%2A` 対象アプリケーション名を取得するには|  
|enableAuthentation=false|GetQueryStringValue("enableAuthentication")<br /><br /> この URI 要素を使用して、ユーザーの資格情報を検証する**注:** GetQueryStringValue 静的メソッドで定義されているは、 `Microsoft.ServiceModel.Channels.Common.ConnectionUri`|  
|echoInUpperValue=false|GetQueryStringValue("echoInUpperValue")<br /><br /> 着信の文字列を大文字に変換するためには、この URI 要素を使用します。|  
  
### <a name="enableauthentication-uri-element"></a>EnableAuthentication URI 要素  
 多くの場合、ターゲット システムでは、ターゲット システムへの接続を確立するためにクライアントの資格情報を指定する必要があります。 前述のように、エコー アダプターは、ターゲット システムを行いません。 サンプルは、としても、enableAuthentication と呼ばれるカスタム URI 要素を使用して、資格情報を提供する方法を示します。  
  
```  
 public class EchoAdapterConnection : IConnection   
{  
….  
   public void Open(TimeSpan timeout)  
  {  
    // only validate the credentials if EnableAuthentication  
    // connection property value is true  
    if (this.ConnectionFactory.ConnectionUri.EnableAuthentication)  
    {  
        // this adapter expects a value in username  
        if (this.connectionFactory.ClientCredentials != null &&  
            string.IsNullOrEmpty(this.connectionFactory.ClientCredentials.UserName.UserName))  
        {  
            throw new CredentialsException("Username is expected.");  
        }  
  }  
}  
```  
  
 コードをチェックして enableAuthentication が true の場合、およびユーザー名が指定されていません。によってキャッチされましたが、例外がスロー ユーザー名が指定されていない場合、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]ツールを次のようにします。  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/901095c7-c70d-491a-a1ae-8f37f22a61a7.gif "901095c7-c70d-491a-a1ae-8f37f22a61a7")  
  
 ユーザー名を指定することができますを入力することでアダプターの構成 ダイアログ ボックスで、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]ツールを次の図に示すようにします。  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/e4069a7d-1403-4195-b0b5-21ad97dbc3ce.gif "e4069a7d-1403-4195-b0b5-21ad97dbc3ce")  
  
### <a name="echoinuppercase-uri-element"></a>EchoInUpperCase URI 要素  
 EchoInUpperCase URI 要素は、ブール型のフラグと同様に参照できます。 フラグが true の場合、アダプターに変換 EchoStrings 操作の入力文字列を大文字にします。  
  
 EchoInUpperCase URI 要素の既定値を変更するには URI のプロパティ タブでアダプターの構成を使用して、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、次のようにします。  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/f22511b2-3fca-4875-ac65-8e61f4367e94.gif "f22511b2-3fca-4875-ac65-8e61f4367e94")  
  
## <a name="updating-echoadapterconnection"></a>EchoAdapterConnection の更新  
 EchoAdapterConnection クラスの IsValid、Open、および Close メソッドを実装するとします。  
  
#### <a name="to-update-the-echoadapterconnection-class"></a>EchoAdapterConnection クラスの更新  
  
1.  **ソリューション エクスプ ローラー**をダブルクリックして、 **EchoAdapterConnection.cs**ファイル。  
  
2.  Visual Studio エディターで、任意の場所を右クリック コンテキスト メニューで、エディター内のをポイント**アウトライン**、クリックして**アウトラインの中止**です。  
  
3.  Visual Studio エディターで、検索、 **IsValid**メソッドです。 内部、 **IsValid**メソッド、既存の実装を次に置き換えます。  
  
    ```csharp  
    return true;  
    ```  
  
4.  Visual Studio エディターで、検索、**開く**メソッドです。 内部、**開く**メソッド、既存の実装を次の実装に置き換えます。 これは、URI enableAuthentication 要素を使用して、ユーザー名が提供されることを確認する方法を示します。  
  
    ```csharp  
    // only validate the credentials if EnableAuthentication  
    // connection property value is true  
    if (this.ConnectionFactory.ConnectionUri.EnableAuthentication)  
    {  
        // this adapter expects a value in username  
        // it just logs the credentials in the trace file  
        if (this.connectionFactory.ClientCredentials != null &&  
            string.IsNullOrEmpty(this.connectionFactory.ClientCredentials.UserName.UserName))  
        {  
            throw new CredentialsException("Username is expected.");  
        }  
        // got the username, log it in trace file  
        EchoAdapterUtilities.Trace.Trace(System.Diagnostics.TraceEventType.Information, "EchoAdapterConnection::Open", "Username is " + this.connectionFactory.ClientCredentials.UserName.UserName);  
    }  
    EchoAdapterUtilities.Trace.Trace(System.Diagnostics.TraceEventType.Information, "EchoAdapterConnection::Open", "Connection successfully established!");  
    ```  
  
5.  Visual Studio エディターで、検索、**閉じる**メソッドです。 内部、**閉じる**メソッド、次の 1 つのステートメントを追加します。  
  
    ```csharp  
    EchoAdapterUtilities.Trace.Trace(System.Diagnostics.TraceEventType.Information, "EchoAdapterConnection::Close", "Connection successfully closed!");  
    ```  
  
## <a name="updating-the-echoadapterconnectionfactory"></a>EchoAdapterConnectionFactory の更新  
 EchoAdapterConnectionFactory コンス トラクターを実装して ClientCredentials、ConnectionUri という 2 つのプロパティを追加します。  
  
#### <a name="to-update-the-echoadapterconnectionfactory-class"></a>EchoAdapterConnectionFactory クラスの更新  
  
1.  **ソリューション エクスプ ローラー**をダブルクリックして、 **EchoAdapterConnectionFactory.cs**ファイル。  
  
2.  Visual Studio エディターで、任意の場所を右クリック コンテキスト メニューで、エディター内のをポイント**アウトライン**、クリックして**アウトラインの中止**です。  
  
3.  Visual Studio エディターで、検索、**プライベート フィールド**領域。 次の 1 つのステートメントを追加します。  
  
    ```csharp  
    private EchoAdapterConnectionUri connectionUri;  
    ```  
  
     プライベート フィールドの一覧を次に一致する必要があります。  
  
    ```csharp  
    // Stores the client credentials  
    private ClientCredentials clientCredentials;  
    // Stores the adapter class  
    private EchoAdapter adapter;  
    private EchoAdapterConnectionUri connectionUri;  
    ```  
  
4.  Visual Studio エディターで、検索、 **EchoAdapterConnectionFactory**メソッドです。 内部、 **EchoAdapterConnectionFactory**コンス トラクター メソッドの前に"}"、最後のステートメントとして次の 1 つのステートメントを追加します。  
  
    ```csharp  
    this.connectionUri = connectionUri as EchoAdapterConnectionUri;  
    ```  
  
     実装、 **EchoAdapterConnectionFactory**メソッドは、次と一致する必要があります。  
  
    ```csharp  
    /// <summary>  
    /// Initializes a new instance of the EchoAdapterConnectionFactory class  
    /// </summary>  
    public EchoAdapterConnectionFactory(ConnectionUri connectionUri  
        , ClientCredentials clientCredentials  
        , EchoAdapter adapter)  
    {  
        this.clientCredentials = clientCredentials;  
        this.adapter = adapter;  
        //added  
        this.connectionUri = connectionUri as EchoAdapterConnectionUri;  
    }  
    ```  
  
5.  Visual Studio エディターで、検索、**パブリック プロパティ**領域。 次のコードを追加します。  
  
    ```csharp  
    /// <summary>  
    /// Returns the client credentials  
    /// </summary>  
    public ClientCredentials ClientCredentials  
    {  
        get  
        {  
            return this.clientCredentials;  
        }  
    }  
  
    /// <summary>  
    /// Returns the Connection Uri for this adapter  
    /// </summary>  
    public EchoAdapterConnectionUri ConnectionUri  
    {  
        get  
        {  
            return this.connectionUri;  
        }  
    }  
    ```  
  
## <a name="updating-the-echoadapterconnectionuri"></a>EchoAdapterConnectionUri の更新  
 EchoAdapterConnectionUri 既定のコンス トラクターを実装する、EchoAdapterConnectionUri(Uri uri) コンス トラクターはオーバー ロードおよびパブリック Uri Uri プロパティをオーバーライドします。  
  
#### <a name="to-update-the-echoadapterconnectionuri-class"></a>EchoAdapterConnectionUri クラスの更新  
  
1.  **ソリューション エクスプ ローラー**をダブルクリックして、 **EchoAdapterConnectionUri.cs**ファイル。  
  
2.  Visual Studio エディターで、任意の場所を右クリック コンテキスト メニューで、エディター内のをポイント**アウトライン**、クリックして**アウトラインの中止**です。  
  
3.  Visual Studio エディターで、検索、**コンス トラクター**領域。 内部、 **EchoAdapterConnectionUri()** 既定コンス トラクターで、次のステートメントを追加します。  
  
    ```csharp  
    Uri = new Uri("echov2://lobhostname/lobapplication?enableauthentication=False");  
    ```  
  
4.  Visual Studio エディターでの内部、 **EchoAdapterConnectionUri (Uri uri)** コンス トラクターをオーバー ロードされ、次のステートメントを追加します。  
  
    ```csharp  
    Uri = uri;  
    ```  
  
     EchoAdapterConnectionUri(Uri uri) メソッドの実装を次に一致する必要があります。  
  
    ```csharp  
    public EchoAdapterConnectionUri(Uri uri)  
        : base()  
    {  
        Uri = uri;  
    }  
    ```  
  
5.  Visual Studio エディターでの内部、**パブリック オーバーライドの Uri の Uri**メソッドを次のロジックで置き換えます。 Get は、echoInUpperCase 有無にかかわらず、Uri を構築します。 セットでは、ホスト名、データベース名、およびクエリの値を取得する URI を解析します。  
  
    ```csharp  
    get  
    {  
        // Build the uri  
        if (String.IsNullOrEmpty(this.hostname)) throw new InvalidUriException("Invalid target system host name.");  
        if (String.IsNullOrEmpty(this.application)) throw new InvalidUriException("Invalid target system data source name.");  
        if (EchoInUpperCase)  
        {  
            // build the uri with echoInUpperCase= query string  
            return new Uri(EchoAdapter.SCHEME + "://" + Hostname + "/" + Application + "?" + "enableAuthentication=" + EnableAuthentication + "&" + "echoInUpperCase=" + echoInUpperCase);  
        }  
        else  
        {  
            // build the uri without echoInUpperCase= query string  
            return new Uri(EchoAdapter.SCHEME + "://" + Hostname + "/" + Application + "?" + "enableAuthentication=" + EnableAuthentication);  
        }  
    }  
    set  
    {  
        // Parse the uri  
        String[] enableAuthValue = GetQueryStringValue(value, "enableAuthentication");  
        if (enableAuthValue.Length > 0) this.enableAuthentication = Boolean.Parse(enableAuthValue[0]);  
        String[] echoInUpperValue = GetQueryStringValue(value, "echoInUpperCase");  
        if (echoInUpperValue.Length > 0) this.echoInUpperCase = Boolean.Parse(echoInUpperValue[0]);  
  
        this.hostname = value.Host;  
        String[] applicationValue = value.AbsolutePath.Split('/');  
        if (applicationValue.Length > 1) this.Application = applicationValue[1];  
    }  
    ```  
  
6.  Visual Studio での**ファイル** メニューのをクリックして**すべて保存**です。  
  
7.  **[ビルド]** メニューの **[ソリューションのビルド]** をクリックします。 プロジェクトを正常にコンパイルする必要があります。 以外の場合は、上記のすべてのステップに従っていることを確認します。  
  
> [!NOTE]
>  これで作業が保存されました。 安全にこの時点で Visual Studio を終了したり、次の手順に進みます[手順 4: エコー アダプターのメタデータ参照ハンドラーの実装](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-implement-the-metadata-browse-handler-for-the-echo-adapter.md)です。  
  
## <a name="what-did-i-just-do"></a>でしただけは何ですか。  
 エコー アダプターの接続が実装されます。 接続のコンポーネントの学習、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]、接続 URI の基本的な構造、プログラムによって、URI 要素を解析する方法および URI 要素を使用して、アダプターの機能を変更する方法です。  
  
## <a name="next-steps"></a>次の手順  
 メタデータの参照、検索、および機能、および送信メッセージ交換の解決を実装するとします。 最後に、ビルドおよび展開するアダプター。  
  
## <a name="see-also"></a>参照  
 [手順 4: エコー アダプターのメタデータ参照のハンドラーを実装します。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-implement-the-metadata-browse-handler-for-the-echo-adapter.md)   
 [チュートリアル 1: エコー アダプターを開発する](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)