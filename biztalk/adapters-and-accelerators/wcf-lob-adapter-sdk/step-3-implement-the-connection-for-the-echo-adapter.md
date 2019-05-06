---
title: '手順 3: エコー アダプターの接続の実装 |Microsoft Docs'
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
ms.openlocfilehash: 15749fdca84508654fc915fff0c1abe7008de2f3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988411"
---
# <a name="step-3-implement-the-connection-for-the-echo-adapter"></a>手順 3: エコー アダプターの接続を実装します。
![手順 9 の 3](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-3of9.gif "Step_3of9")  

 **所要時間:** 45 分  

 この手順では、エコー アダプターの接続機能を実装します。 に従って、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]、ターゲット システムに接続するときに、次の抽象クラスとインターフェイスを実装する必要があります。  

- `Microsoft.ServiceModel.Channels.Common.ConnectionUri`  

- `Microsoft.ServiceModel.Channels.Common.IConnection`  

- `Microsoft.ServiceModel.Channels.Common.IConnectionFactory`  

  上記からの派生ではなく抽象クラスとインターフェイスを[!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]3 つの派生クラス、EchoAdapterConnection、EchoAdapterConnectionUri、および EchoAdapterConnectionFactory を自動的に生成されます。 特定の例外をスローします。 既定のメソッドは、クラスを作成するだけでなく`System.NotImplementedException`します。  このステートメントは、開発者は、各クラスを実装するよう通知します。  クラスが実装された場合、この例外のスロー ステートメントを削除する必要があります。  

  次のセクションでは、接続を処理する方法、URI の構造は URI のさまざまな要素をプログラムで取得し、アダプター内での要素を使用する方法の理解を深めるためにこれら 3 つのクラスを更新します。  

## <a name="prerequisites"></a>前提条件  
 この手順を開始する前にする必要がありますが正常に完了して[手順 2: アダプターと接続のプロパティを分類](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-categorize-the-adapter-and-connection-properties.md)します。 明確に理解しておくと、 `Microsoft.ServiceModel.Channels.Common.IConnection`、 `Microsoft.ServiceModel.Channels.Common.IConnectionFactory`、および`Microsoft.ServiceModel.Channels.Common.ConnectionUri`クラス。  

## <a name="connection-related-classes"></a>接続に関連するクラス  
 [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] 3 つの派生クラス、EchoAdapterConnection、EchoAdapterConnectionUri、および EchoAdapterConnectionFactory が生成されます。 関連付けられた各メソッドの簡単な概要を次に示します。  

### <a name="echoadapterconnection"></a>EchoAdapterConnection  
 アダプターの複雑さによっては、次の 5 つのメソッドをすべて実装する必要があります。 エコー アダプターのほとんどはサポートされていません、エコー アダプターのサンプルが他のシステムが含まれないためです。  

|**方法**|**[説明]**|  
|----------------|---------------------|  
|public void 閉じる (TimeSpan タイムアウト)|ターゲット システムへの接続を閉じます。 エコー アダプターでは、このメソッドを使用して、トレース イベントをトレース リスナーにのみ追加します。|  
|public bool IsValid (TimeSpan タイムアウト)|接続がまだ有効かどうかを示す値を返します。<br /><br /> エコー アダプターによってサポートされていません。|  
|public void オープン (TimeSpan タイムアウト)|ターゲット システムへの接続を開きます。<br /><br /> エコー アダプターの該当なし。 しかし、例を示します enableAuthentication と呼ばれる URI の要素を使用して、ユーザーのユーザー名を指定する必要がある方法。|  
|public void ClearContext()|接続のコンテキストをクリアします。 接続が戻り、接続プールに設定されている場合は、このメソッドが呼び出されます。<br /><br /> エコー アダプターによってサポートされていません。|  
|public void Abort()|ターゲット システムへの接続を中止します。<br /><br /> エコー アダプターによってサポートされていません。|  

### <a name="echoadapterconnectionfactory"></a>EchoAdapterConnectionFactory  
 接続ファクトリは、接続を作成する責任を負います。 既定では、ターゲット システムに接続するときにのみ、このクラスを変更する必要があります。 エコー アダプターは、他のシステムを含まないが方法を示します、接続がユーザー認証が必要な場合に enableAuthentication と呼ばれるカスタム URI 要素を使用します。  

> [!NOTE]
>  EnableAuthentication は、キーワードではありませんが、変数名にすぎません。 そのため、これは任意の名前を選択できます。  

### <a name="echoadapterconnectionuri"></a>EchoAdapterConnectionUri  
 これは、ターゲット システムに接続文字列を表します。  


|               **方法**               |                                                                                                                                       **[説明]**                                                                                                                                        |
|----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|        パブリック オーバーライドの Uri の Uri         |                                                                                                    取得し、Uri を設定します。 Uri 文字列を作成するを取得し、Uri 文字列の解析を設定します。                                                                                                     |
|   パブリック EchoAdapterConnectionUri()    |                                                                                                                    ConnectionUri クラスの新しいインスタンスを初期化します。                                                                                                                    |
| パブリック オーバーライド文字列 SampleUriString | Returns EchoAdapter.SCHEME + "://{hostname}/{application}?enableAuthentication={True&#124;False}".<br /><br /> としてこの戻り値の文字列が表示されます、**例**で、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]ツールを次の図に示すようにします。 |

 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/e4b9d0b8-f07f-4342-815f-9ef1507b0980.gif "e4b9d0b8-f07f-4342-815f-9ef1507b0980")  

## <a name="echo-adapter-connection-uri"></a>エコー アダプターの接続 URI  
 サンプルのエコー アダプターの接続 URI のとおりです: EchoAapter.SCHEME://{hostname}/{application}?enableAuthentication={true&#124;false}  

 EchoAapter.SCHEME echov2 であるため、接続 URI です。  

 echo2://lobhostname/lobapplication?enableAuthentication={true&#124;false}  

 前の接続 URI を読み取ることができる場合 enableAuthentication false を次のように =。  

 Echov2 トランスポートのスキーマを使用して、移動 lobhostname、という名前のコンピューターに接続の任意の認証を必要としない lobapplication をという名前のアプリケーションが待機しています。  

 または、enableAuthentication = true の場合、次のように、接続の読み取り。  

 Echov2 トランスポートのスキーマを使用して、移動 lobhostname、という名前のコンピューターで、lobapplication をという名前のアプリケーションでは、接続が認証を待機しているが必要です。 エコー アダプターの場合は、ユーザー名のみが必要です。  

 定義済みの URI を持つプログラムで使用し、接続および構成の解析できます。 接続には、ユーザー名とパスワードなどの機密データが必要とする場合は、URI では、このような情報は含まれません。 代わりに、このような情報を追加、`System.ServiceModel.Description.ClientCredentials`オブジェクト。 追加するコード例では、操作を行う方法を示します。  

 次のコードでは、エコー アダプターは、アダプターが URI のさまざまな要素を使用して、アダプターの機能を変更する方法を説明する 2 つの方法で URI を構築します。  

 echo2://lobhostname/lobapplication?enableAuthentication=[true&#124;false]  

 echo2://lobhostname/lobapplication?enableAuthentication=[true&#124;false]&echoInUpperCase=true  

### <a name="retrieving-the-uri-element"></a>URI の要素を取得します。  
 エコー アダプター URI echo2 内の各 URI 要素を解析することができます://lobhostname/lobapplication? enableAuthentication = false & echoInUpperCase = false。  URI の要素の値と関連付けられているメソッドは、次の表のとおりです。  

|**URI の要素の値**|**方法**|  
|---------------------------|----------------|  
|lobhostname|`System.Uri.Host%2A` ホスト名を取得するには|  
|Lobapplication|`System.Uri.AbsolutePath%2A` ターゲット アプリケーションの名前を取得するには|  
|enableAuthentation = false|GetQueryStringValue("enableAuthentication")<br /><br /> この URI の要素を使用して、ユーザーの資格情報を検証する**注:** GetQueryStringValue 静的メソッドで定義されているは、 `Microsoft.ServiceModel.Channels.Common.ConnectionUri`|  
|echoInUpperValue=false|GetQueryStringValue("echoInUpperValue")<br /><br /> 受信の文字列を大文字に変換するためには、この URI の要素を使用します。|  

### <a name="enableauthentication-uri-element"></a>EnableAuthentication URI 要素  
 多くの場合、ターゲット システムでは、ターゲット システムへの接続を確立するためにクライアントの資格情報を指定する必要があります。 前述のように、エコー アダプターは、他のシステムを関与しません。 サンプルとして、enableAuthentication と呼ばれるカスタム URI 要素を使用して、資格情報を提供する方法を示します。  

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

 EnableAuthentication が true の場合と、ユーザー名が提供されていない場合、コードを確認しますユーザー名が指定されていない場合でキャッチされた例外がスローされます、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]ツールを次に示すよう。  

 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/901095c7-c70d-491a-a1ae-8f37f22a61a7.gif "901095c7-c70d-491a-a1ae-8f37f22a61a7")  

 ユーザー名を指定する入力できますが、アダプターの構成 ダイアログ ボックスで、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]ツールを次の図に示すようにします。  

 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/e4069a7d-1403-4195-b0b5-21ad97dbc3ce.gif "e4069a7d-1403-4195-b0b5-21ad97dbc3ce")  

### <a name="echoinuppercase-uri-element"></a>EchoInUpperCase URI 要素  
 EchoInUpperCase URI 要素は、ブール型のフラグのように参照できます。 フラグが true の場合、アダプター EchoStrings 操作の入力文字列を大文字に変換します。  

 EchoInUpperCase URI 要素の既定値を変更するには、アダプターでの構成の URI のプロパティ タブを使用、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]以下に示すようにします。  

 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/f22511b2-3fca-4875-ac65-8e61f4367e94.gif "f22511b2-3fca-4875-ac65-8e61f4367e94")  

## <a name="updating-echoadapterconnection"></a>EchoAdapterConnection を更新しています  
 EchoAdapterConnection クラスの IsValid、Open、Close メソッドを実装するとします。  

#### <a name="to-update-the-echoadapterconnection-class"></a>EchoAdapterConnection クラスを更新するには  

1.  **ソリューション エクスプ ローラー**、ダブルクリックして、 **EchoAdapterConnection.cs**ファイル。  

2.  Visual Studio エディターで、任意の場所を右クリック コンテキスト メニューで、エディター内をポイント**アウトライン**、 をクリックし、**アウトラインの中止**します。  

3.  Visual Studio エディターで検索、 **IsValid**メソッド。 内で、 **IsValid**メソッドでは、既存の実装を次に置き換えます。  

    ```csharp  
    return true;  
    ```  

4.  Visual Studio エディターで検索、**オープン**メソッド。 内で、**オープン**メソッドでは、既存の実装を次の実装に置き換えます。 これは、URI enableAuthentication 要素を使用して、ユーザー名が提供されていることを確認する方法を示します。  

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

5.  Visual Studio エディターで検索、**閉じる**メソッド。 内で、**閉じる**メソッドでは、次の 1 つのステートメントを追加します。  

    ```csharp  
    EchoAdapterUtilities.Trace.Trace(System.Diagnostics.TraceEventType.Information, "EchoAdapterConnection::Close", "Connection successfully closed!");  
    ```  

## <a name="updating-the-echoadapterconnectionfactory"></a>EchoAdapterConnectionFactory を更新しています  
 EchoAdapterConnectionFactory コンストラクターを実装し、ClientCredentials、ConnectionUri という 2 つのプロパティを追加します。  

#### <a name="to-update-the-echoadapterconnectionfactory-class"></a>EchoAdapterConnectionFactory クラスを更新するには  

1.  **ソリューション エクスプ ローラー**、ダブルクリックして、 **EchoAdapterConnectionFactory.cs**ファイル。  

2.  Visual Studio エディターで、任意の場所を右クリック コンテキスト メニューで、エディター内をポイント**アウトライン**、 をクリックし、**アウトラインの中止**します。  

3.  Visual Studio エディターで検索、**プライベート フィールド**リージョン。 次の 1 つのステートメントを追加します。  

    ```csharp  
    private EchoAdapterConnectionUri connectionUri;  
    ```  

     プライベート フィールドの一覧は、次と一致する必要があります。  

    ```csharp  
    // Stores the client credentials  
    private ClientCredentials clientCredentials;  
    // Stores the adapter class  
    private EchoAdapter adapter;  
    private EchoAdapterConnectionUri connectionUri;  
    ```  

4.  Visual Studio エディターで検索、 **EchoAdapterConnectionFactory**メソッド。 内で、 **EchoAdapterConnectionFactory**コンストラクターのメソッドの前に"}"、最後のステートメントとして次の 1 つのステートメントを追加します。  

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

5.  Visual Studio エディターで検索、**パブリック プロパティ**リージョン。 次のコードを追加します。  

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

## <a name="updating-the-echoadapterconnectionuri"></a>EchoAdapterConnectionUri を更新しています  
 EchoAdapterConnectionUri 既定のコンストラクターを実装して、EchoAdapterConnectionUri(Uri uri) コンストラクターをオーバー ロードされたパブリック Uri Uri プロパティをオーバーライドします。  

#### <a name="to-update-the-echoadapterconnectionuri-class"></a>EchoAdapterConnectionUri クラスを更新するには  

1.  **ソリューション エクスプ ローラー**、ダブルクリックして、 **EchoAdapterConnectionUri.cs**ファイル。  

2.  Visual Studio エディターで、任意の場所を右クリック コンテキスト メニューで、エディター内をポイント**アウトライン**、 をクリックし、**アウトラインの中止**します。  

3.  Visual Studio エディターで検索、**コンストラクター**リージョン。 内で、 **EchoAdapterConnectionUri()** 既定コンストラクターを次のステートメントを追加します。  

    ```csharp  
    Uri = new Uri("echov2://lobhostname/lobapplication?enableauthentication=False");  
    ```  

4.  Visual Studio エディターでの内部、 **EchoAdapterConnectionUri (Uri の uri)** コンストラクターをオーバー ロードされ、次のステートメントを追加します。  

    ```csharp  
    Uri = uri;  
    ```  

     EchoAdapterConnectionUri(Uri uri) メソッドの実装は、次と一致する必要があります。  

    ```csharp  
    public EchoAdapterConnectionUri(Uri uri)  
        : base()  
    {  
        Uri = uri;  
    }  
    ```  

5.  Visual Studio エディターで内で、**パブリック Uri の Uri をオーバーライドする**メソッドを次のロジックで置き換えます。 Get は、echoInUpperCase 有無にかかわらず、Uri を構築します。 セットは、ホスト名、データベース名、およびクエリの値を取得する URI を解析します。  

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

6.  Visual Studio での**ファイル** メニューのをクリックして**すべて保存**します。  

7.  **[ビルド]** メニューの **[ソリューションのビルド]** をクリックします。 プロジェクトを正常にコンパイルする必要があります。 そうでない場合は、上記のすべての手順に従っていることを確認します。  

> [!NOTE]
>  これで作業が保存されました。 安全にこの時点で Visual Studio を閉じて、次の手順に進むまたは[手順 4: エコー アダプターのメタデータ参照ハンドラーを実装する](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-implement-the-metadata-browse-handler-for-the-echo-adapter.md)します。  

## <a name="what-did-i-just-do"></a>でしただけ何か。  
 エコー アダプターの接続を実装しました。 接続のコンポーネントについて説明しました、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]、接続 URI の基本的な構造、URI の要素をプログラムで解析する方法および URI 要素を使用して、アダプターの機能を変更する方法。  

## <a name="next-steps"></a>次の手順  
 メタデータの参照、検索、および機能、および送信のメッセージ交換の解決を実装します。 最後に、ビルドし、アダプターを展開します。  

## <a name="see-also"></a>参照  
 [手順 4: エコー アダプターのメタデータ参照ハンドラーを実装する.](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-implement-the-metadata-browse-handler-for-the-echo-adapter.md)   
 [チュートリアル 1: エコー アダプターを開発する](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)